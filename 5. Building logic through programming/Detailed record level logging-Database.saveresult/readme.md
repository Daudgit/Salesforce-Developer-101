In Salesforce Apex, you can use the `Database.SaveResult` class to capture detailed information about the results of individual records during a DML (Data Manipulation Language) operation. This is especially useful for tracking which records were successfully saved, which encountered errors, and obtaining error messages for each record. Detailed record-level logging can be important for debugging and auditing purposes. Here's how to use `Database.SaveResult` for record-level logging:

1. **Perform a DML Operation:**
   First, you'll execute a DML operation (insert, update, delete, or undelete) that affects multiple records. This operation should return an array of `Database.SaveResult` objects.

   ```apex
   List<Account> accountsToUpdate = new List<Account>();
   // Populate the accountsToUpdate list
   Database.SaveResult[] updateResults = Database.update(accountsToUpdate, false);
   ```

2. **Iterate Through `Database.SaveResult` Array:**
   You can then iterate through the array of `Database.SaveResult` objects to examine the results for each record.

   ```apex
   for (Database.SaveResult result : updateResults) {
       if (result.isSuccess()) {
           // Record was successfully updated
           System.debug('Record ID: ' + result.getId() + ' was updated successfully.');
       } else {
           // Record encountered an error
           System.debug('Record ID: ' + result.getId() + ' encountered an error: ' + result.getErrors()[0].getMessage());
       }
   }
   ```

3. **Accessing `Database.SaveResult` Properties:**
   Each `Database.SaveResult` object provides several properties that you can access:
   - `getId()`: Returns the ID of the saved record.
   - `isSuccess()`: Indicates whether the operation was successful for the record.
   - `getErrors()`: Returns an array of `Database.Error` objects containing error information if an error occurred. You can access error details, such as the error message, fields causing the error, and the status code.

4. **Error Handling:**
   You can handle errors on a per-record basis, and you have the flexibility to log the error message, perform error recovery, or take other appropriate actions. In the example above, error messages are logged using `System.debug()`, but you can customize your error-handling logic as needed.

Detailed record-level logging using `Database.SaveResult` allows you to gain insight into the success or failure of each record during a DML operation. This information is valuable for troubleshooting issues, auditing changes, and ensuring data integrity in your Salesforce applications.
