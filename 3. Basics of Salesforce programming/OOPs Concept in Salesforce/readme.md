

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





**4. Interface:**

In Salesforce Apex, an interface is a blueprint for a set of methods that a class must implement. Interfaces define a contract that ensures certain methods are available in any class that implements the interface. Interfaces are valuable when you want to enforce a common set of behaviors across different classes.

**Example - Interface in Salesforce:**

Let's create an interface called `Shape` with a method `calculateArea()`. Classes that implement this interface must provide an implementation for `calculateArea()`.

```apex
public interface Shape {
    Decimal calculateArea();
}
```

Now, let's create two classes that implement the `Shape` interface:

```apex
public class Circle implements Shape {
    public Decimal radius;

    public Decimal calculateArea() {
        return Math.PI * radius * radius;
    }
}

public class Rectangle implements Shape {
    public Decimal length;
    public Decimal width;

    public Decimal calculateArea() {
        return length * width;
    }
}
```

Both `Circle` and `Rectangle` classes implement the `calculateArea()` method as required by the `Shape` interface.

**5. Encapsulation:**

Encapsulation is a fundamental OOP concept that involves bundling data (attributes) and methods (functions) that operate on that data into a single unit, known as a class. Access to the internal data is controlled through methods, allowing you to enforce data integrity and hide the implementation details.

**Example - Encapsulation in Salesforce:**

Let's create a simple class that demonstrates encapsulation:

```apex
public class EncapsulatedClass {
    private String sensitiveData;

    public void setSensitiveData(String value) {
        // You can perform validation or logic here
        sensitiveData = value;
    }

    public String getSensitiveData() {
        // Provide controlled access to the data
        return sensitiveData;
    }
}
```

In this example, `sensitiveData` is a private attribute. Access to it is controlled through the `setSensitiveData()` and `getSensitiveData()` methods, ensuring that data is modified or accessed according to the class's rules.

**6. Abstraction:**

Abstraction is the process of simplifying complex systems by breaking them into smaller, more manageable parts. In the context of Salesforce, abstraction is often achieved through abstract classes and methods.

**Example - Abstraction in Salesforce:**

Let's create an abstract class called `AbstractShape` with an abstract method `calculateArea()`. Abstract classes cannot be instantiated, but they provide a common interface for their concrete subclasses.

```apex
public abstract class AbstractShape {
    public abstract Decimal calculateArea();
}
```

Now, we can create concrete classes that extend the abstract class:

```apex
public class Circle extends AbstractShape {
    public Decimal radius;

    public Decimal calculateArea() {
        return Math.PI * radius * radius;
    }
}

public class Rectangle extends AbstractShape {
    public Decimal length;
    public Decimal width;

    public Decimal calculateArea() {
        return length * width;
    }
}
```

By using an abstract class, we enforce that concrete subclasses provide an implementation for the `calculateArea()` method, promoting a common interface while allowing for specific behaviors in each subclass.

These concepts—interface, encapsulation, and abstraction—play a crucial role in designing organized, maintainable, and extensible code in Salesforce Apex. They help ensure consistency, data integrity, and separation of concerns in your applications.

