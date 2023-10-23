

### 1. Architecture - Apex/Force.com:

Salesforce is built on a multi-tenant architecture, known as the Force.com platform. Apex is the primary programming language used to customize and extend Salesforce. The architecture consists of:

- **Objects**: Represent entities (e.g., Accounts, Contacts) and custom objects.
- **Metadata**: Define custom fields, workflows, and page layouts.
- **Apex Code**: Executes business logic on the server.
- **Visualforce**: Creates custom user interfaces.
- **Lightning Components**: Building blocks for web apps.
- **Database**: Where data is stored.

### 2. Data Types in Salesforce:

Salesforce supports various data types for fields and variables:
- **Text**: Holds alphanumeric text.
- **Number**: For numeric data.
- **Date/Time**: Manages date and time values.
- **Boolean**: Represents true or false.
- **Picklist**: Provides a predefined list of options.
- **ID**: Unique record identifier.
- **Lookup/Master-Detail**: Establish relationships between objects.

### 3. Collections:

Collections are used to store and manage multiple values:
- **List**: Ordered collection, allows duplicate elements.
- **Set**: Unordered collection, doesn't allow duplicates.
- **Map**: Key-value pairs for efficient data retrieval.

### 4. List:

A List is an ordered collection that can contain multiple values of the same or different data types. It is commonly used for storing and manipulating data.

### 5. Set:

A Set is an unordered collection of unique values. It is useful for ensuring that only unique elements are stored.

### 6. Map:

A Map is a collection of key-value pairs. It is used for efficient data retrieval, where each key maps to a unique value.

### 7. Debug Process and Methodology:

Debugging is the process of identifying and fixing issues in your code. Salesforce provides tools like the Developer Console for debugging. The methodology includes:
- Adding debug statements (e.g., `System.debug`) to your code.
- Analyzing debug logs to identify issues.
- Iteratively fixing and retesting your code.

### 8. OOP Concepts - Inheritance:

Inheritance is an object-oriented programming (OOP) concept where a new class can inherit properties and methods from an existing class. In Apex, you can create new classes that extend the functionality of existing classes.

### 9. Interface:

An interface defines a contract that a class must implement. It specifies the methods that a class must provide. In Salesforce, you can use interfaces to ensure that specific methods are implemented in your classes.

### 10. Abstract Classes:

An abstract class is a class that cannot be instantiated but can be used as a base for other classes. In Salesforce, abstract classes are used when you want to define common methods and properties that should be present in derived classes.

