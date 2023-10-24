In Salesforce, trigger context variables are special variables that allow you to access records and their properties involved in a trigger event. These context variables are automatically provided by Salesforce and are available for use in your trigger code. Understanding trigger context variables is crucial for writing effective trigger logic. The primary trigger context variables are:

1. **`Trigger.new`** and **`Trigger.newMap`**:
   - `Trigger.new` is a list that contains the new records that are being inserted or updated in the current trigger context. For example, in a "before insert" trigger, it contains the records being inserted.
   - `Trigger.newMap` is a map that allows you to access the new records by their record IDs. It provides a convenient way to perform record lookups by ID.

   ```apex
   for (Account newAccount : Trigger.new) {
       // Access properties of new Account records
   }

   // Using Trigger.newMap to access records by ID
   Map<Id, Account> newAccountsById = Trigger.newMap;
   ```

2. **`Trigger.old`** and **`Trigger.oldMap`**:
   - `Trigger.old` is a list that contains the old records before they were updated in the current trigger context. For example, in an "after update" trigger, it contains the records before they were updated.
   - `Trigger.oldMap` is a map that allows you to access the old records by their record IDs. It provides a convenient way to compare old and new values.

   ```apex
   for (Account oldAccount : Trigger.old) {
       // Access properties of old Account records
   }

   // Using Trigger.oldMap to access old records by ID
   Map<Id, Account> oldAccountsById = Trigger.oldMap;
   ```

3. **`Trigger.isInsert`**, **`Trigger.isUpdate`**, **`Trigger.isDelete`**, and **`Trigger.isUndelete`**:
   - These Boolean variables indicate the type of operation that invoked the trigger. For example, `Trigger.isInsert` is `true` if the trigger was invoked by an insert operation.

   ```apex
   if (Trigger.isInsert) {
       // Trigger logic for insert operation
   }
   ```

4. **`Trigger.isBefore`** and **`Trigger.isAfter`**:
   - These Boolean variables indicate whether the trigger is executing in the "before" phase or the "after" phase of the operation.

   ```apex
   if (Trigger.isBefore) {
       // Trigger logic for the "before" phase
   }
   ```

5. **`Trigger.size`**:
   - This variable indicates the number of records in `Trigger.new` or `Trigger.old`, depending on the trigger context.

   ```apex
   Integer recordCount = Trigger.size;
   ```

By using these trigger context variables, you can access and manipulate records effectively in your triggers. For example, you can perform data validation, record updates, or other business logic based on the context of the trigger event. Understanding when and how to use these variables is essential for creating robust and efficient triggers in Salesforce.
