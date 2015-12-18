### notes for Lamport's paper : Time, Clocks, and the Ordering of Events in a Distributed System

+ maily 3 points of view 
    + partial order of events in a distributed system 
    + use arbitrary total order which can be realized by a logic clock to build distributed systems, use a not-fault-tolerent state machine replication problem for multi-thread nultual exclusion as an example 
    + use physical clock to solve the "anomalous behavior"


+ partial order/logic clock/total order 
    + a,b...stands for events; i,j...stands for processes; Ci,Cj,C stands for clock
    + happen-before -> (similar to causal order to some extent)
        + (a in i) /\ (b in i) => (a -> b)
        + (a is send-msg in i) /\ (b is receive-msg in j) /\ (i!=j) =>  (a -> b)
        + (a -> b) /\ (b -> c) => (a -> c) 
        + !(a -> b) /\ !(b -> a) => a and b are concurrent 
    + logic clock 
        + (a -> b) => C(a) < C(b) [the reverse doesn't hold]
    + happen-before expressed by logic clock 
        + (a in i) /\ (b in i) => Ci(a) < Ci(b)
        + (a is send-msg in i) /\ (b is receive-msg in j) /\ (i!=j) =>  Ci(a) < Cj(b)
    + the algorithms for maintaining happen-before relation between different processes with a logic clock, we can not get the absolute real total order since we can not decide the real order of concurrent events, we may use the physical clock or vector clock for this requirement
        + (a in i) /\ (b in i), then Ci(b) = Ci(a) + 1 
        + (a is send-msg in i) /\ (b is receive-msg in j), then msg[clock] = Ci(a) and Cj(b) = max(msg[clock], Cj(pre_event)) + 1  
    + then based on above algorithm, we can maintain a arbitrary total order a => b
        + Ci(a) < Cj(b)
        + (Ci(a) = Cj(b)) /\ (i < j)
