

**1. Classes and Objects (Account and Contact):**

In Salesforce, standard objects like Account and Contact are predefined classes. Here's an example of creating instances (objects) of these classes:

```apex
// Creating instances (objects) of the Account and Contact standard objects
Account myAccount = new Account(Name='Acme Inc.');
Contact myContact = new Contact(FirstName='John', LastName='Doe', AccountId=myAccount.Id);

// Accessing object properties
String accountName = myAccount.Name; // "Acme Inc."
String contactName = myContact.FirstName + ' ' + myContact.LastName; // "John Doe"
```

In this example, `Account` and `Contact` are classes, and `myAccount` and `myContact` are objects of these classes.

**2. Inheritance (Contact and Lead):**

Standard objects in Salesforce often inherit from other standard objects. For example, the `Contact` standard object inherits from the `Lead` standard object. You can create custom fields on these objects:

```apex
// Creating a custom field on the Lead standard object
ObjectLead__c myCustomField = new ObjectLead__c(Lead__c='Custom Value');

// Creating a Contact that inherits the custom field from Lead
Contact myContact = new Contact(FirstName='John', LastName='Doe', CustomField__c=myCustomField.Lead__c);
```

In this example, the `Contact` standard object inherits the custom field `CustomField__c` from the `Lead` standard object.

**3. Polymorphism (Account and Contact):**

Polymorphism allows you to treat objects of different classes as if they were objects of a common base class. In Salesforce, common base classes like `SObject` enable polymorphic behavior:

```apex
SObject myObject;

if (condition) {
    myObject = new Account(Name='Acme Inc.');
} else {
    myObject = new Contact(FirstName='John', LastName='Doe');
}

String objectName = String.valueOf(myObject.get('Name')); // Accessing 'Name' field
```

In this example, `myObject` can be an instance of either the `Account` or `Contact` class, and you can access common fields using the `SObject` base class.

