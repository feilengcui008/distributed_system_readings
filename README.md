### distributed_systems_readings

a list of papers, conference, books, mooc, Q&A and other stuffs for distributed systems 

issues for more materials are welcome.


----

### papers

#### theories and some main topics of distributed systems, maily basic concepts/fault tolerence and replication/consistency and consensus algorithms/formal methods etc.

+ basic concepts/introductions 
    + introductions
        + [Distributed Systems for Fun and Profit (strongly recommend)](http://book.mixu.net/distsys/)
        + [Notes on distributed systems for young bloods](http://www.somethingsimilar.com/2013/01/14/notes-on-distributed-systems-for-young-bloods/)
        + [A Note on Distributed Systems](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=46F21231EF8ACDE94840A6C96AED31BD?doi=10.1.1.41.7628&rep=rep1&type=pdf)
        + [Development of the domain name system](http://www.cs.cornell.edu/courses/cs615/2002fa/615/mockapetris.pdf)
        + [Rediscovering-Distributed-System](http://steve.vinoski.net/pdf/IC-Rediscovering-Distributed-Systems.pdf)
    + time and clock
        + [Time, clocks, and the ordering of events in a distributed system](http://research.microsoft.com/en-us/um/people/lamport/pubs/time-clocks.pdf)
        + [Fundamentals of distributed computing: A practical tour of vector clock systems](http://www.computer.org/csdl/mags/ds/2002/02/o2001.pdf)
        + [HLC: Hybrid Logical Clocks](http://www.cse.buffalo.edu/tech-reports/2014-04.pdf)
        + [Virtual Time and Global States of Distributed Systems](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.63.4399&rep=rep1&type=pdf)
        + [Timestamps in Message-Passing Systems That Preserve the Partial Ordering](http://zoo.cs.yale.edu/classes/cs426/2012/lab/bib/fidge88timestamps.pdf)
    + distributed censensus problem
        + [Distributed snapshots: determining global states of distributed systems](http://research.microsoft.com/en-us/um/people/lamport/pubs/chandy.pdf)
        + [Distributed Consensus, Revisited](https://infoscience.epfl.ch/record/89568/files/l-mainTC.pdf)
        + [A Review of Experiences With Reliable Multicast](https://ecommons.cornell.edu/bitstream/handle/1813/7380/99-1726.pdf;sequence=1)


+ fault-tolerence and replication/consistency and consensus
    + fault-tolerence and replication
        + [Impossibility of Distributed Consensus With One Faulty Process](https://groups.csail.mit.edu/tds/papers/Lynch/jacm85.pdf)
        + [Implementing fault-tolerant services using the state machine approach: a tutorial](https://www.cs.cornell.edu/fbs/publications/SMSurvey.pdf)
        + [Remus: High Availability via Asynchronous Virtual Machine Replication](http://nil.csail.mit.edu/6.824/2015/papers/remus.pdf)
        + [Perspectives on the CAP Theorem](http://groups.csail.mit.edu/tds/papers/Gilbert/Brewer2.pdf)
        + [Brewer's conjecture and the feasibility of consistent, available, partition-tolerant web services](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.20.1495&rep=rep1&type=pdf)
        + [CAP Twelve Years Later](http://www.infoq.com/articles/cap-twelve-years-later-how-the-rules-have-changed)
    + consistency and consensus
        + algorithms and protocols
            + [The part-time parliament](http://research.microsoft.com/en-us/um/people/lamport/pubs/lamport-paxos.pdf)
            + [Paxos Made Simple](http://research.microsoft.com/en-us/um/people/lamport/pubs/paxos-simple.pdf)
            + [gbcast](https://en.wikipedia.org/wiki/Gbcast)
            + [Viewstamped replication: A new primary copy method to support highly-available distributed systems](http://pmg.csail.mit.edu/papers/vr.pdf)
            + [Zab : High-performance broadcast for primary-backup systems](https://web.stanford.edu/class/cs347/reading/zab.pdf)
            + [In Search of an Understandable Consensus Algorithm](https://www.usenix.org/system/files/conference/atc14/atc14-paper-ongaro.pdf)
            + [The Byzantine Generals Problem](http://research.microsoft.com/en-us/um/people/lamport/pubs/byz.pdf)
            + [ZooKeeper ’ s atomic broadcast protocol : Theory and practice](http://www.tcs.hut.fi/Studies/T-79.5001/reports/2012-deSouzaMedeiros.pdf)
            + [Revisiting the PAXOS algorithm](http://research.microsoft.com/en-us/um/people/blampson/63a-RevisitingPaxos/63a-RevisitingPaxos.pdf)
            + [The Paxos Family of Consensus Protocols](http://www.fractalscape.org/files/paxos-family.pdf)
            + [Multi-Paxos: An Implementation and Evaluation](http://ftp.cs.washington.edu/tr/2009/09/UW-CSE-09-09-02.PDF)
            + [Consensus in the presence of partial synchrony](http://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf)
            + [Consensus on transaction commit](http://research.microsoft.com/pubs/64636/tr-2003-96.pdf)
            + [Consistency in Distributed Storage Systems An Overview of Models, Metrics and Measurement Approaches](http://www.aifb.kit.edu/images/0/0e/Bermbach_netys2013.pdf)
            + [Base: An Acid Alternative](http://queue.acm.org/detail.cfm?id=1394128)
            + [Eventually Consistent](http://cs.brown.edu/courses/csci2950-u/papers/p40-vogels.pdf)
            + [Flexible Paxos: Quorum intersection revisited](https://arxiv.org/abs/1608.06696)
        + engineering and systems
            + [Replication and Fault-Tolerance in the ISIS System](http://www.cs.cornell.edu/home/rvr/sys/p79-birman.pdf)
            + [The Chubby lock service for loosely-coupled distributed systems](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/chubby-osdi06.pdf)
            + [ZooKeeper: Wait-free Coordination for Internet-scale Systems](https://www.usenix.org/legacy/events/atc10/tech/full_papers/Hunt.pdf)
            + [Paxos Made Live: An Engineering Perspective](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/paxos_made_live.pdf)
            + [Paxos for System Builders](http://www.cs.jhu.edu/~jak/docs/paxos_for_system_builders.pdf)
            + [PAXOS Made Transparent](http://sigops.org/sosp/sosp15/current/2015-Monterey/247-cui-online.pdf)
            + [Consensus in the Cloud: Paxos Systems Demystified](http://www.cse.buffalo.edu/tech-reports/2016-02.pdf)
    


+ other topics
    + leader election algorithms
        + [Leader election](https://en.wikipedia.org/wiki/Leader_election)
        + [Bully algorithms](https://en.wikipedia.org/wiki/Bully_algorithm)
        + [Leader Election Algorithms](http://download.springer.com/static/pdf/84/chp%253A10.1007%252F978-3-642-38123-2_4.pdf?originUrl=http%3A%2F%2Flink.springer.com%2Fchapter%2F10.1007%2F978-3-642-38123-2_4&token2=exp=1448987592~acl=%2Fstatic%2Fpdf%2F84%2Fchp%25253A10.1007%25252F978-3-642-38123-2_4.pdf%3ForiginUrl%3Dhttp%253A%252F%252Flink.springer.com%252Fchapter%252F10.1007%252F978-3-642-38123-2_4*~hmac=e83fdaf934be0307c70bbccbcd7be866a8384ae4f43dfb7996b772b5651640c1)
    + p2p
        + [Consistent hashing and random trees: distributed caching protocols for relieving hot spots on the World Wide Web](http://www.cs.princeton.edu/courses/archive/fall09/cos518/papers/chash.pdf)
        + [Chord: A Scalable Peer-To-Peer Lookup Service for Internet Applications](https://pdos.csail.mit.edu/papers/chord:sigcomm01/chord_sigcomm.pdf)
        + [Pastry: Scalable, Decentralized Object Location, and Routing for Large-Scale Peer-to-Peer Systems](http://www.freepastry.org/PAST/pastry.pdf)
    + formal methods 
        + [The temporal logic of actions](http://research.microsoft.com/pubs/64074/lamport-actions.pdf)
        + [A TLA+ proof system](http://www.researchgate.net/publication/220896380_A_TLA_proof_system)
        + [The Model Checker SPIN](http://spinroot.com/spin/Doc/ieee97.pdf)
        + [Use of Formal Methods at Amazon Web Services](http://research.microsoft.com/en-us/um/people/lamport/tla/formal-methods-amazon.pdf)
        + [MODIST: Transparent Model Checking of Unmodified Distributed Systems](https://www.usenix.org/legacy/events/nsdi09/tech/full_papers/yang/yang_html/)


#### distributed storage
+ [Design and implementation of the Sun network filesystem](http://web.stanford.edu/class/cs240/readings/nfs.pdf)
+ [The Google file system](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/gfs-sosp2003.pdf)
+ [The Hadoop distributed file system](http://zoo.cs.yale.edu/classes/cs422/2014fa/readings/papers/shvachko10hdfs.pdf) 
+ [Ceph : A Scalable , High-Performance Distributed File System](http://www.ssrc.ucsc.edu/Papers/weil-osdi06.pdf)
+ [Finding a needle in Haystack: Facebook's photo storage](https://www.usenix.org/legacy/event/osdi10/tech/full_papers/Beaver.pdf)
+ [Bigtable](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/bigtable-osdi06.pdf)
+ [Hadoop-HBase for large-scale data](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=6182030&url=http%3A%2F%2Fieeexplore.ieee.org%2Fiel5%2F6175418%2F6181892%2F06182030.pdf%3Farnumber%3D6182030)
+ [Dynamo](http://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf)
+ [Spanner: Google’s Globally-Distributed Database](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/spanner-osdi2012.pdf)
   
    
#### distributed computing 
+ [Dryad : Distributed Data-Parallel Programs from Sequential Building Blocks](http://research.microsoft.com/pubs/63785/eurosys07.pdf)
+ [MapReduce : Simplified Data Processing on Large Clusters](http://static.googleusercontent.com/media/research.google.com/zh-CN//archive/mapreduce-osdi04.pdf)
+ [Pregel: a system for large-scale graph processing](https://kowshik.github.io/JPregel/pregel_paper.pdf)
+ [Dremel: Interactive Analysis of Web-Scale Datasets](http://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/36632.pdf)
+ [Resilient distributed datasets: A fault-tolerant abstraction for in-memory cluster computing](https://www.cs.berkeley.edu/~matei/papers/2012/nsdi_spark.pdf)
+ [Storm@twitter](https://cs.brown.edu/courses/cs227/papers/ss-storm.pdf)
+ [GraphX: Graph Processing in a Distributed Dataflow Framework](https://amplab.cs.berkeley.edu/wp-content/uploads/2014/09/graphx.pdf)
+ [Introducing Apache Giraph for Large Scale Graph Processing](http://researcher.ibm.com/researcher/files/us-heq/Large%20Scale%20Graph%20Processing%20with%20Apache%20Giraph.pdf)
+ [Large-Scale Distributed Graph Computing Systems : An Experimental Evaluation](http://www.vldb.org/pvldb/vol8/p281-lu.pdf)


#### resource management and scheduling
+ [Large-scale cluster management at Google with Borg](http://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/43438.pdf)
+ [Omega: flexible, scalable schedulers for large compute clusters](http://static.googleusercontent.com/media/research.google.com/zh-CN//pubs/archive/41684.pdf)
+ [Mesos: A Platform for Fine-Grained Resource Sharing in the Data Center](https://www.cs.berkeley.edu/~alig/papers/mesos.pdf)
+ [Yarn](https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html)



#### parallelism and concurrency
+ [Models for Parallel Computing : Review and Perspectives](http://pv.fernuni-hagen.de/docs/a47-rev3a.pdf)
+ [Actors: A Model of Concurrent Computation in Distributed Systems](https://www.cypherpunks.to/erights/history/actors/AITR-844.pdf)
+ [Communicating sequential processes](http://spinroot.com/courses/summer/Papers/hoare_1978.pdf)
+ [Parallel Algorithms Lecture Notes](http://paloaltodata.com/images/bsp/parallel_algorithms_oxford_1997.pdf)
+ [DTHREADS: Efficient and Deterministic Multithreading](https://web.cs.umass.edu/publication/docs/2010/UM-CS-2010-063.pdf)
+ [Kendo: efficient deterministic multithreading in software](http://groups.csail.mit.edu/commit/papers/09/asplos073-olszewski.pdf)


----


### conference 
+ [List of distributed computing conferences](https://en.wikipedia.org/wiki/List_of_distributed_computing_conferences)


----


### books 
+ [Replication: Theory and Practice](http://www.amazon.com/Replication-Practice-Lecture-Computer-Theoretical/dp/3642112935/ref=sr_1_2?ie=UTF8&qid=1448714717&sr=8-2&keywords=replication)
+ [Distributed Systems: Concepts and Design](http://www.amazon.com/Distributed-Systems-Concepts-Design-5th/dp/0132143011/ref=sr_1_3?ie=UTF8&qid=1448714582&sr=8-3&keywords=distributed+systems)
+ [Distributed Systems: Principles and Paradigms](http://www.amazon.com/Distributed-Systems-Principles-Paradigms-2nd/dp/0132392275/ref=sr_1_5?ie=UTF8&qid=1448714582&sr=8-5&keywords=distributed+systems)
+ [Distributed Systems: An Algorithmic Approach](http://www.amazon.com/Distributed-Systems-Algorithmic-Approach-Information/dp/1466552972/ref=sr_1_9?ie=UTF8&qid=1448714582&sr=8-9&keywords=distributed+systems)
+ [Distributed Algorithms: An Intuitive Approach](http://www.amazon.com/Distributed-Algorithms-Intuitive-Wan-Fokkink/dp/0262026775/ref=sr_1_1?ie=UTF8&qid=1448714582&sr=8-1&keywords=distributed+systems)
+ [Distributed Computing: Principles, Algorithms, and Systems](https://www.cs.uic.edu/~ajayk/DCS-Book)



----


### mooc 
+ [MIT 6.824: Distributed Systems](http://nil.csail.mit.edu/6.824/2015/)
+ [CMU 15-440: Distributed Systems Syllabus](http://www.cs.cmu.edu/~dga/15-440/F12/syllabus.html)
+ [MIT 6.852/18.437  Distributed Algorithms](https://stellar.mit.edu/S/course/6/fa13/6.852/materials.html)
+ [MIT 6.S897: Large-Scale Systems](http://people.csail.mit.edu/matei/courses/2015/6.S897/)
+ [CS 525 Spring 2015 Advanced Distributed Systems](https://courses.engr.illinois.edu/cs525/sp2015/index.html)
+ [CS–745/845: Formal Specification and Verification of Systems](http://www.cs.unh.edu/~charpov/teaching-cs745_845.html)


----


### some nice blog posts 
+ [UNDERSTANDING PAXOS](https://understandingpaxos.wordpress.com/)
+ [The Log: What every software engineer should know about real-time data's unifying abstraction](https://engineering.linkedin.com/distributed-systems/log-what-every-software-engineer-should-know-about-real-time-datas-unifying)
+ [Consensus Protocols: Two-Phase Commit](http://the-paper-trail.org/blog/consensus-protocols-two-phase-commit/)
+ [Consensus Protocols: Three-phase Commit](http://the-paper-trail.org/blog/consensus-protocols-three-phase-commit/)
+ [Three-Phase Commit Protocol](http://courses.cs.vt.edu/~cs5204/fall00/distributedDBMS/sreenu/3pc.html)
+ [Consensus Protocols: A Paxos Implementation](http://the-paper-trail.org/blog/consensus-protocols-a-paxos-implementation/)
+ [Consensus Protocols: Paxos](http://the-paper-trail.org/blog/consensus-protocols-paxos/)
+ [FLP and CAP are not the same](http://the-paper-trail.org/blog/flp-and-cap-arent-the-same-thing/)
+ [Consistency and availability in Amazon's Dynamo](http://the-paper-trail.org/blog/consistency-and-availability-in-amazons-dynamo/)
+ [Distributed systems theory for the distributed systems engineer](http://the-paper-trail.org/blog/distributed-systems-theory-for-the-distributed-systems-engineer/)
+ [PAXOS/MULTI-PAXOS ALGORITHM](http://amberonrails.com/paxosmulti-paxos-algorithm/)
+ [EVENTUAL CONSISTENCY](http://amberonrails.com/eventual-consistency)
+ [The Essential Leslie Lamport](http://brooker.co.za/blog/2014/03/30/lamport-pub)
+ [The Essential Nancy Lynch](http://brooker.co.za/blog/2014/05/10/lynch-pub.html)
+ [The Essential Barbara Liskov](http://brooker.co.za/blog/2014/09/21/liskov-pub.html)
+ [Viewstamped Replication Revisited](http://blog.acolyer.org/2015/03/06/viewstamped-replication-revisited/)



----


### Q&A 
+ [What are the seminal papers in distributed systems](https://www.quora.com/What-are-the-seminal-papers-in-distributed-systems-Why)
