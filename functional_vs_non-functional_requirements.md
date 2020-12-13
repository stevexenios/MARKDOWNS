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

1. [Guru99](https://ww.guru99.com/functional-vs-non-functional-requirements.html
   )
