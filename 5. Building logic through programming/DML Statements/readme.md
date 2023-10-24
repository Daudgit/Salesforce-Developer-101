DML (Data Manipulation Language) statements in Salesforce are used to interact with records in the database, including creating, updating, deleting, and querying records. Salesforce provides several DML statements that allow you to perform various data operations. Here are the primary DML statements in Salesforce:

1. **`insert`:** Used to create new records in Salesforce. You can insert one or more records of the same SObject type in a single DML statement.

   ```apex
   List<Account> newAccounts = new List<Account>();
   newAccounts.add(new Account(Name='Account 1'));
   newAccounts.add(new Account(Name='Account 2'));
   insert newAccounts;
   ```

2. **`update`:** Used to modify existing records in Salesforce. You can update one or more records of the same SObject type in a single DML statement.

   ```apex
   List<Contact> contactsToUpdate = [SELECT Id, LastName FROM Contact WHERE LastName = 'Doe'];
   for (Contact contact : contactsToUpdate) {
       contact.LastName = 'Smith';
   }
   update contactsToUpdate;
   ```

3. **`delete`:** Used to remove records from Salesforce. You can delete one or more records of the same SObject type in a single DML statement.

   ```apex
   List<Contact> contactsToDelete = [SELECT Id FROM Contact WHERE LastName = 'Smith'];
   delete contactsToDelete;
   ```

4. **`upsert`:** Used to perform either an insert or update operation, depending on whether a record with a specified external ID exists. It's useful for data upserts.

   ```apex
   CustomObject__c customObj = new CustomObject__c(External_Id__c='12345', Field1__c='Value');
   upsert customObj CustomObject__c External_Id__c;
   ```

5. **`undelete`:** Used to restore records that were previously deleted and are still in the recycle bin.

   ```apex
   List<Contact> contactsToUndelete = [SELECT Id FROM Contact WHERE LastName = 'Smith' ALL ROWS];
   undelete contactsToUndelete;
   ```

6. **`merge`:** Used to merge duplicate records. You specify the master record and the records to be merged into it.

   ```apex
   List<Account> accountsToMerge = [SELECT Id FROM Account WHERE Name = 'Duplicate Account'];
   merge accountsToMerge[0] accountsToMerge.sublist(1, accountsToMerge.size());
   ```

7. **`emptyRecycleBin`:** Used to permanently delete records from the recycle bin. This statement can help reduce data storage usage.

   ```apex
   List<Contact> contactsToDelete = [SELECT Id FROM Contact WHERE LastName = 'Smith' ALL ROWS];
   emptyRecycleBin contactsToDelete;
   ```

These DML statements are essential for managing and manipulating data in Salesforce. It's crucial to understand the proper usage of these statements and their implications, including governor limits, bulk processing, and error handling. Additionally, remember to handle exceptions that may occur during DML operations to ensure data integrity.
