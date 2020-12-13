# MARKDOWNS

General notes on systems.

Table of contents
=================

1. [ACID properties](#ACID-properties)
2. [Distributed Systems](#distributed-systems)
3. [Functional-vs-Non-Functional requirements](#Functional-vs-Non-Functional-Requirements)



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
