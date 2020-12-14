# CAP Theorem (Brewer's Theorem)

An important theorem in designing distributed systems. Echoes that there is no simultaneous guarantee of **CAP (consistency, availability, and partition tolerance)**; in essence, something has to give.

![CAP Theorem Image](../images/cap-theorem.png)

The 3 basic requirements when designing applications for a distributed architecture:

* **Consistency**: data remains consistent after the execution of an operation, across all nodes. After an update, all clients/nodes see the same data at the same time. Standard database replication is normally not consistent due to replication lag. On the other hand, _perfect instantaneous global consistency_ is impossible.
* **Availability**: a guarantee that the system is always ON, without downtime; reading and writing can always take place.
* **Partition-tolerance**: system continues to operate despite arbitrary message loss or failure of part of the system. For example, if communication between the servers is unreliable, the system should still continue to function, due to the other functioning and unconnected partitions.

Theoretically, it is impossible to fulfill all 3 requirements. In a distributed context, **CAP** formulates the basic requirement of 2, either CP or AP.

From _[Thoughts from the red planet](https://http://nathanmarz.com/blog/how-to-beat-the-cap-theorem.html)_. **CP**: Data might not be available, but it is accurate and consistent across all the nodes. If **consistency** is chosen, then what happens to availability? Do you buffer writes for later? If the machiens with the buffers fails, won't all the writes be lost? Also, isn't buffering writes somewhat against the grain of _being consistent_, since the data isn't updated in the database yet. Another option would be to return an error to the client, which would probably work against the company's reputation.

**AP** : System always available and partitioned, but some of the data might not be same as viewed from different nodes. The other option would be going for **availability**. The best guarantee of consistency in these systems is **_eventual consistency_**. This would mean reading a different result than the expected result. In such cases, multiple readers to the same system will see different content at the same time. For instance, Youtube views/subscriptions for some videos could be eventually consistent, with someone from one location seeing say 1000000 subscribers/views and another person seeing 1000010. This is due to the updates not having propagated to all  the replicas instantaneously. Such differences when noted could tracked by developers using "vector clocks and merging the updates together (**read repair**)".

CA _only_, is implausible(since it implies the system will never fail, drop messages, etc.). Additionally, it fails to meet the requirements in a distributed(i.e., multi-node) systems context, since probability of something going wrong increases with increase in partitions (even single site clusters). The downside of a single node/monolithic system is perhaps much worse(eggs in one baske scenario), despite the lower probability, if the system is really prime. An example is from _sources 2_, where one node has a 99.9% chance of failure, but a cluster of 40 such nodes increases the failure chance to about 96.1%.

From _[Thoughts from the red planet](https://http://nathanmarz.com/blog/how-to-beat-the-cap-theorem.html)_ , a workaround to beating the **CAP theorem** is working with immutable data, such that, queries and functions on data in the distributed systems, nolonger have to _Update_ or _Delete_ data.."no divergent values, vector clocks, or read-repair(s)." The data either **exists** or **doesn't**;"just data and functions on the data." The complexities were arising from the incremental updates/writes on mutable data, and the interaction of such functional requirements and the CAP properties. So, by "rejecting  incremental updates, embracing immutable data, and computing queries from scratch each time, you avoid that complexity." This statement is more of a testament of a solution existing, rather than an actual solution since the it is not plausible to compute queries each time.

A **BASE** [system](https://www.w3resource.com/mongodb/nosql.php) gives up on consistency. Essentially:

1. **B**asically **A**vailable indicates that the system does **_guarantee availability_**, in terms of the CAP theorem.
2. **S**oft state indicates that the state of the system may change over time, even without input. This is because of the eventual consistency model.
3. **E**ventual consistency indicates that the system will become consistent over time, given that the system doesn't receive input during that time.


## ACID vs BASE


| ACID | BASE |
| - | - |
| **Atomic** | **B**asically **A**vailable |
| **C**onsistency | **S**oft state |
| **I**solation | **E**ventual consistency |
| **D**urable |   |

To ensure consistency, some popular protocols to consider include:

1. **Two-Phase Commit ([2PC](https://www.cs.princeton.edu/courses/archive/fall16/cos418/docs/L6-2pc.pdf)):** "General purpose, distributed agreement on some action, with failures. Different entities playing different roles in action. Example: Transfering money between two banks, require that both bank acknowledge transaction, or neither. And require that no 1 bank to act alone (_all or nothing atomic commit protocol_)."
2. Eventual consistency (vector clock + RWN) [read](https://titanwolf.org/Network/Articles/Article?AID=d4ec31f9-db30-4cb2-9889-bcf6089f370a#gsc.tab=0).
3. Paxos [read](https://www.cs.yale.edu/homes/aspnes/pinewiki/Paxos.html).
4. In-Sync [Replica](http://www.confluent.io/blog/hands-free-kafka-replication-a-lesson-in-operational-simplicity/), etc.

To ensure availability, we can add replicas for the data. As to components of the whole system, people usually do _cold standby, warm standby, hot standby, and active-active_ to handle the failover.


## SOURCES

1. [Thoughts from the red planet](http://nathanmarz.com/blog/how-to-beat-the-cap-theorem.html)
2. [You can't sacrifice partition tolerance](https://codahale.com/you-cant-sacrifice-partition-tolerance/)
3. [Dr. Eric A. Brewer's Slides](https://people.eecs.berkeley.edu/~brewer/cs262b-2004/PODC-keynote.pdf)
4. [Research paper](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.67.6951&rep=rep1&type=pdf)
5. [w3resource](https://www.w3resource.com/mongodb/nosql.php)
6. [Princeton notes](https://www.cs.princeton.edu/courses/archive/fall16/cos418/docs/L6-2pc.pdf)
7. [Yale notes](https://www.cs.yale.edu/homes/aspnes/pinewiki/Paxos.html)
8. [Confluent](https://www.confluent.io/blog/hands-free-kafka-replication-a-lesson-in-operational-simplicity/)
