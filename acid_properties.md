# ACID Rules

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
