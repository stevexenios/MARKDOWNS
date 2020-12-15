# Normalization

**_Study notes [source link](http://agiledata.org/essays/dataNormalization.html)_**

Data normalization is the process of organizing data attributes to reduce and eliminate redundancy.

**_Advantages of Data Normalization_**
**1. Increased consistency:** Data is stored in one location only, reducing chance of inconsistencies when multiple copies exist.
**2. Easier object-to-data mapping:** High cohesion and loose coupling allows data to be easily integrated.

**_Disadvantages of Normalization_**
**1. Slower reporting performance:** Denormalized schema support reporting.

**_Steps of data normalization_**


| Level | Rule |
| - | - |
| 1NF | An entity is in first normal form when it contains non repeating groups of data (e.g. NO tuples with multiple phone numbers in one column, etc.) |
| 2NF | Must be in 1st NF. Also all**non-key attributes have to be fully dependent** on the the **_Primary Key_** |
| 3NF | Must be in 2nd NF. Also all attributes must be**_directly dependent_** on primary key. No recursive dependencies. |
