

**DML Statements in Salesforce:**

Salesforce supports various DML statements in Apex for interacting with records in standard and custom objects. The primary DML statements are:

1. **`insert`:** Used to create new records in Salesforce.

2. **`update`:** Used to modify existing records in Salesforce.

3. **`delete`:** Used to remove records from Salesforce.

4. **`upsert`:** Used to perform either an insert or update operation, depending on whether a record with a specified external ID exists.

**Examples of DML Operations:**

**1. Inserting Records:**

The `insert` statement is used to create new records in Salesforce. Here's an example of inserting a new Account record:

```apex
Account newAccount = new Account(Name='New Account');
insert newAccount;
```

In this example, a new Account record named 'New Account' is created and inserted into Salesforce.

**2. Updating Records:**

The `update` statement is used to modify existing records. Here's an example of updating a Contact's LastName:

```apex
Contact contactToUpdate = [SELECT Id, LastName FROM Contact WHERE LastName = 'Doe' LIMIT 1];
contactToUpdate.LastName = 'Smith';
update contactToUpdate;
```

In this example, a Contact record with the LastName 'Doe' is retrieved, and its LastName is updated to 'Smith'.

**3. Deleting Records:**

The `delete` statement is used to remove records from Salesforce. Here's an example of deleting a Contact record:

```apex
Contact contactToDelete = [SELECT Id FROM Contact WHERE LastName = 'Smith' LIMIT 1];
delete contactToDelete;
```

In this example, a Contact record with the LastName 'Smith' is retrieved and deleted from Salesforce.

**4. Upserting Records:**

The `upsert` statement is used to perform either an insert or update operation based on an external ID field. If a record with the specified external ID exists, it will be updated; otherwise, a new record will be inserted.

```apex
CustomObject__c customObj = new CustomObject__c(External_Id__c='12345', Field1__c='Value');
upsert customObj CustomObject__c External_Id__c;
```

In this example, a custom object record is created and upserted based on the value of the `External_Id__c` field. If a record with an external ID of '12345' already exists, it will be updated; otherwise, a new record will be created.

**Handling DML Exceptions:**

DML operations can encounter exceptions, and it's essential to handle these exceptions to ensure data integrity. Common exceptions include `DmlException` for errors during DML operations and `DmlValidationException` for validation rule violations.

```apex
try {
    insert newAccount;
} catch (DmlException e) {
    // Handle DML exception
    System.debug('DML Exception: ' + e.getMessage());
}
```

**Bulk DML Operations:**

Salesforce allows you to perform bulk DML operations by using collections (e.g., lists) to insert, update, or delete multiple records at once. This is more efficient than individual DML statements and is crucial for processing large volumes of data.

```apex
List<Contact> contactsToUpdate = [SELECT Id, LastName FROM Contact WHERE LastName = 'Doe'];
for (Contact contact : contactsToUpdate) {
    contact.LastName = 'Smith';
}
update contactsToUpdate;
```

In this example, a bulk update is performed to change the LastName of multiple Contact records from 'Doe' to 'Smith.'

Understanding and using DML operations is fundamental to managing data in Salesforce and ensuring the accuracy and integrity of your organization's data.
