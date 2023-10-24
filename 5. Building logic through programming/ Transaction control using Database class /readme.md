In Salesforce Apex, you can use the `Database` class to manage transactions, including starting and committing transactions, rolling back transactions, and performing savepoint operations. Here's an overview of how to control transactions using the `Database` class:

**1. Starting a Transaction:**
   - In Salesforce, a transaction is automatically started when a trigger is executed or when a Visualforce page or Apex code is invoked. You don't typically need to explicitly start a transaction, as it is handled by the platform.

**2. Committing a Transaction:**
   - To commit a transaction, you don't need to use the `Database` class explicitly. Transactions are automatically committed when the entire block of code successfully executes without exceptions.

   Example:

   ```apex
   // DML operations within this block are part of the same transaction
   try {
       // Perform DML operations
   } catch (Exception e) {
       // Handle exceptions
   }
   // If no exceptions occurred, the transaction is committed automatically
   ```

**3. Rolling Back a Transaction:**
   - To roll back a transaction, you can use the `Database.rollback(Savepoint)` method. You need to first create a savepoint using the `Database.setSavepoint()` method to capture the state of the transaction at a specific point.

   Example:

   ```apex
   Savepoint sp = Database.setSavepoint();
   try {
       // Perform DML operations
   } catch (Exception e) {
       // Handle exceptions
       Database.rollback(sp); // Roll back to the savepoint
   }
   ```

   In the example above, if an exception occurs, the transaction is rolled back to the state captured by the savepoint.

**4. Savepoints:**
   - Savepoints allow you to create checkpoints within a transaction. If an exception occurs, you can roll back to a specific savepoint to revert changes made after that point.

**5. Nested Transactions:**
   - In Salesforce, you cannot explicitly nest transactions. Each trigger or Apex transaction is self-contained and cannot be nested within another transaction. However, you can use savepoints to create checkpoints within a transaction.

**6. Governor Limits:**
   - Be aware of Salesforce governor limits when working with transactions. Performing too many DML operations in a single transaction can result in limit exceptions. Design your code to stay within these limits.

**7. Transaction Lifecycle:**
   - In Salesforce, transactions have a lifecycle. They start when the code is invoked and end when the entire block of code successfully executes without exceptions. If exceptions occur, the transaction can be rolled back to a savepoint.

Transaction control is essential when working with DML operations in Salesforce. By using savepoints and handling exceptions effectively, you can ensure data integrity and recover gracefully from errors in your Apex code.
