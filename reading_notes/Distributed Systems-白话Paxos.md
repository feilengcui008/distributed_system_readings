本文主要提炼了《Paxos Make Simple》中的一些主要观点，然后加上自己的理解，使用通俗的语言尝试做一些解释。

+ 关于Paxos算法背景和一致性相关问题可以参见原论文

+ 算法涉及的主要对象
    + action 对一条记录(某个变量)的一次操作(这一点只是本人便于后面理解加上的)
        + 这里选用操作这个词，而不是值，因为一个在对某个变量达成某个值的共识前可能已经经过多个更新操作，所以为了区别，使用操作作为每次proposal的对象，而操作的值代表具体的修改动作，而且这也算是状态机复制(SMR)的一个基本组成单元，个人感觉更易于理解。比如action(log_id, log_content)，log_id全局标识了此action的唯一性，log_content通常是针对某条记录的修改，可看做action的值。       
    + proposer 
        + 发起proposal的机器，注意在Paxos算法中允许多台机器同时发起proposal，并且有可能由于并发获取"需要达成一致的下一操作(action)"，从而使得不同的proposal针对同一个"需要达成一致的下一操作"达成共识，但是算法保证了其达成共识的action的值相同。
    + acceptor 
        + 接受来自proposer的proposal，并根据对于proposer的prepare和accept消息做出响应。
    + learner 
        + 从错误中恢复的机器，需要重新学习出错之前最后一次accpet的proposal id之后的所有proposal

+ Paxos instance 
    + 针对某个"需要达成一致的操作(action)"运行一次Paxos算法的完整过程。

+ 算法基本流程
论文上主要有prepare和accept两个阶段，省略了选action(值)和选proposal id的阶段

    + 0.数据结构 
        + 每台机器需要记录最大accpeted的proposal id(latest_accepted_id)和对应的accepted的操作(latest_accepted_action)以及最大promised的proposal id(latest_promised_id)，这些数据需要刷盘。
    + 1.选择需要达成一致的操作 
        + 来自客户端的请求，比如 Action{write A 12} => 通常这作为需要达成的某个操作的值，还需要一个全局唯一的id标识这个操作，比如对于某个log记录达成一致，需要寻找下一次需要记录的log id，这就需要向其他节点询问其记录的最近log id，并取最大值+1作为下一次需要达成一致的"记录日志这个操作(action)"的action(log) id。而这个过程可能会产生并发问题，即不同的机器可能针对同一个log id发起proposal，这一点后面阶段保证了一旦达成了proposal，则后续所有proposal都以相同的操作(值)达成。
    + 2.选择proposal id 
        + proposal id需要保证全局唯一递增(这个后面补充)。
    + 3.prepare 
        + 假设2中选择的proposal id为n，proposer发送prepare(n)给大多数机器
            + 对于acceptor，如果(n > latest_promised_id) /\ (n > latest_promised_id)
                + 如果acceptor已经有latest_accepted_id(说明之前对于同一个操作已经达到proposal了)，则返回对应于latest_accepted_id的操作的值，为了accept阶段保证当前的proposal和以前已经达成的proposal最终操作值一样。
                + 如果acceptor没有latest_accepted_id(说明之前还未达成proposal)，则不用返回值(accept阶段可以使用任意proposed的值)　
                + 令latest_accepted_id = latest_promised_id = n，并保证不再接受proposal id小于latest_promised_id的proposal
          + 否则acceptor返回拒绝，重新开始算法。

    + 4.accept 
        + proposal收到大多数的机器对prepare的回复
            + 如果返回消息中latest_accepted_action集合不为空，则将当前proposal的action设置为对应于最大latest_accepted_id的latest_accepted_action，发送accept(n, action)消息
            + 如果返回消息中latest_accepted_action集合为空，则直接使用当前proposal的action(也就是论文中所说的any value)，发送accept(n, action)消息　
        + 如果acceptor收到accept(n, action)消息时
            + latest_promised_id > n(说明有更新的)，则放弃当前proposal，重新进入算法。
            + 否则接受proposal，完成此次proposal


+ 几点辅助理解的说明

    + 多数是为了保证至少会有一台机器记录了上次达成的proposal的值，这样保证在不多于n/2台机器挂掉的条件下，在每次proposal的过程中，至少有一台机器有前面所有的proposal值的记录，从而保证所有的数据的完整。
    + 一轮paxos instance 是针对某个变量的一次操作的，而不是同一个变量。比如针对同一变量的一次操作打一次log，而这个log id应当是唯一的，而且针对这条log可能会有多次proposal，但是只要有一次proposal已经达成，那么针对这条log的proposal只能使用相同的log值更新(这也是为什么在prepare返回阶段，如果有一个acceptor已经达成过proposal，则返回其值替换当前proposal值)。
    + 对某个唯一的记录比如log或者变量的某次操作达成一致，那么proposer在发起proposal之前必定要到某个地方取下次需要达成一致的值，比如下一条日志记录的id，某个变量的下一个版本(某个变量的下一次操作)。而由于proposer可能有多个，那么在并发发起proposal时，不同的proposal可能会针对相同的某次操作，这时对于后达成的proposal来说，只能将其propose的值换为已经达成的proposal的值，而这个过程是通过prepare阶段accptor返回的结果集是否空来判断的。如果结果集不为空，说明针对此次操作，之前已经达成了一致，则后续proposal只能使用相同值；如果为空，那么可以使用此次proposal的值(也就是论文中所说的any value)。另外，在accept阶段，如果有accptor的最小promise　id大于当前proposal id，那么说明已经有更更大proposal id的proposal先到达了(此时不管之前是否已经达成一致)，此时需要放弃当前次的proposal 


+ ref:
	+ [Paxos Made Simple](http://research.microsoft.com/en-us/um/people/lamport/pubs/paxos-simple.pdf)