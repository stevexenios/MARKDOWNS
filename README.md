# MARKDOWNS

General notes on systems.

Table of contents
=================

1. [ACID properties](#ACID-properties)
2. [Distributed Systems](#distributed-systems)
3. [Functional-vs-Non-Functional requirements](#Functional-vs-Non-Functional-Requirements)
4. [CAP Theorem](#CAP-theorem)

# ACID properties

These are the rules followed by classical relation databases. They require that a database transaction be:

## 1. Atomic

_All or nothing rule_. A transaction should be a logical unit of work which must be completed with all its data modifications, or none at all. In short, a transaction should take place at once, or not at all.

**Example:**_Transferring money from one account to another. Such a transaction should not stop in the middle of the process without delivering the funds to the designated account, and if it does, it should fail in all._

## 2. Consistent

At the end of the transaction, all data must be in a consistent state. All data in the database should be consistent before and after a transaction.

**Example:** _Depositing funds to a bank account> After depositing the funds, one should be able to see that the account balance has increased in direct proportion to the deposited funds._

## 3. Isolated

Modifications on data by particular transaction ought to be independent from those done by other transactions. Multiple transactions should occur independently without interference.

**Example:** _Joint bank account. When you and your husband buy something, those transactions should be different and should result in a change in account balance that reflects each transaction independently, e.g. if one buys a car, and the funds are inadequate for another transaction then it should be reflected and isolated, this way 2 charges don't happen at the same time. First transaction should complete, then second transaction can take place_.

## 4. Durable

After the completion of a transaction, the resulting changes should persist and be permanent. Regardless of issues such as system failure.

**Example:** _If you completed a transaction in which you deposited funds into your bank account via the ATM, but for some reason the ATM fails without confirming or printing the receipt, the transaction should still be reflected on your bank account information. This aspect is because each transaction's modifications and updates are stored in disk or permanent storage._

# Distributed Systems

These are connected systems that are composed of computers, computer components and software, which interact with each other and share the system's' resources. They are connected using a Local Area Network or Wide Area Network. Could be composed of any number of possible configurations, for example:

* Workstations
* Personal computers
* Mainframes, etc.

## Advantages of Distributed Computing

1. **Reliability** *(*fault tolerance*)*: The system remains operating despite some machines failing.
2. **Scalability**: Easy scalable, by adding more machines as needed.
3. **Resource sharing**: The system facilitates sharing of its resouces between and with connected applications.
4. **Flexibility**: System is very easy to debug, implement new services and make new installations.
5. **Speed**: The increased computation potential afforded by all connected components increases the  speed of transactions accordingly.
6. **Open system**: As it is open system, every service is equally accessible to every client, i.e. local or remote.
7. **Performance**: Collection of processors in the system can provid higher performance (and better price/performance ratio) than a centralized computer.

## Disadvantages of Distributed Computing

1. **Troubleshooting**: Diagnosing the source of problems could be hard.
2. **Software**: Less software support.
3. **Networking**: Several issues could arise due to network issues, including:
   * Transmission issues
   * Loss of data
   * Overloading
4. **Security**: Ease of accessing other parts of system or data is increased by the number of connected components, hence decreasing security.

## Scalability

This is the ability of a system to expand and meet the needs of the business. For instance, scaling Facebook would entail ensuring that all the people using it as well as those who want to use it can be accommodated, even if it surpasses billions of people.

**a. Vertical scaling (_Scale Up_):** Adding resources within the same logical unit to increase capacity. For example, increasing the number of CPUs to an existing server, or increasing the memory in the system's servers or expanding storage by adding hard drive.

**b. Horizontal scaling (_Scale Out_):** This means adding more nodes to the system, such as adding a new computer to a distributed software application. In NoSQL system, data store can be much faster as it takes advantages of **_scaling out_** which would entail adding more nodes to a system and distribute the load over those nodes.

## Sources

1. [w2resource](https://www.w3resource.com/mongodb/nosql.php)

# Functional vs Non-functional requirements

## 1. Functional requirements

This is what describes a system and its parts. Describes the functions a system must perform. Functions have to do with inputs, outputs and behavior. This can be calculations, data manipulations, business processes, user interactions and other characteristics attributable to what the system can perform. The functional system requirements "help capture the intended behavior of the system."

## 2. Non-functional requirements

Include the quality attributes of a system. They are normally a set of standards that can be used to judge the specific operation of a system. They are essential to ensuring the usability and effectiveness of a software system. Failing to meet these requirements can result in systems that fail to meet user needs.

Non-functional requirements allows you to impose constraints or restrictions on the design of the system across the various agile backlogs. For example, site should load in 2 seconds when the number of simultaneous users exceed 1000000.

## Key differences

1. **FR** **(functional requirements)** define a system or its components, while **NFR (non-functional requirements)** define the performance attribute of a software system.
2. **FR** with requirement analysis help id missing requirements, while **NFR** ensures good user experience and ease of using the software.
3. **FR** is a **_verb_**, while **NFR** is an **_attribute_**.
4. Types of **NFR**:
   * Scalability capacity
   * Availability
   * Reliability
   * Recoverability
   * Data integrity
5. Types of **FR**:
   * Transaction corrections
   * Transactions adjustments
   * Cancellations
   * Administrative functions
   * External interfaces
   * Authorization levels
   * Historical data management

## Examples of FR

1. Background color for all windows in the application will be green.
2. Only managerial level employees will be able to review revenue data.
3. Software system should be integrated with the banking API.
4. Software should automativcally validate customers.

## Examples of NFR

1. Users should immediately change the first assigned password after first successful login.
2. Employees should never be allowed to update their salary requirement.
3. Unsuccessful attempts by users to access an item of data should be recorded on audit trail.
4. Website should be able to support 1000000 users at any one time without affecting its performance.
5. Software should be transferrable to other operating systems without any issues.
6. Export of confidential and intellectual property should be reviewed and audited.


| **Parameters** | **Functional Requirement** | **Non-Functional Requirement** |
| - | - | - |
| What is it? | Verb<br/><br/> | Attributes<br/><br/> |
| Required | Yes<br/><br/> | No |
| Captured in | Use case | By quality |
| End-result | Product feature<br/><br/> | Product quality |
| Substantiation | Easy to subtantiate<br/><br/> | Hard to subtantiate<br/><br/> |
| Objective | 'GPS' for software functionality | 'GPS' for software performance |
| Focus | User requirement | User's expectation. |
| Documentation | Describes what the product does | Describes how the product works |
| Testing | Functional Testing like System, Integration, End to End, API testing, etc. | Non-Functional Testing like Performance, Stress, Usability, Security testing, etc. |
| Test Execution | Test Execution is done before non-functional testing. | After the functional testing |
| Product Info | Product Features<br/><br/> | Product Properties |

## Terms

1. **User requirements**: These can be represented visually or using statements(some of which might be abstract, and very general), e.g. Google drive will provide storage for all its users.
2. **System requirements**: Very detailed descriptions of software system's "functions, services, and operational constraints" (Sommerville, p. 83). The documentation of such requirements can be called the **functional specification**, and it is supposed to document exactly what ought to be implemented.

## Sources

1. [Guru99](https://ww.guru99.com/functional-vs-non-functional-requirements.html )


# CAP Theorem (Brewer's Theorem)

An important theorem in designing distributed systems. Echoes that there is no simultaneous guarantee of **CAP (consistency, availability, and partition tolerance)**; in essence, something has to give.

![CAP Theorem Image](./images/cap-theorem.png)

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
