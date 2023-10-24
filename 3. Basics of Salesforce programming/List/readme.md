

1. **add(Object element):**

   ```apex
   List<String> names = new List<String>();
   names.add("Alice");
   names.add("Bob");
   System.debug(names); // Output: ["Alice", "Bob"]
   ```

2. **addAll(Collection<...> elements):**

   ```apex
   List<String> list1 = new List<String>{'Alice', 'Bob'};
   List<String> list2 = new List<String>{'Charlie', 'David'};
   list1.addAll(list2);
   System.debug(list1); // Output: ["Alice", "Bob", "Charlie", "David"]
   ```

3. **clear():**

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   names.clear();
   System.debug(names); // Output: []
   ```

4. **contains(Object element):**

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   Boolean containsBob = names.contains('Bob'); // true
   Boolean containsDavid = names.contains('David'); // false
   ```

5. **get(Integer index):**

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   String name = names.get(1); // "Bob"
   ```

6. **indexOf(Object element):**

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   Integer indexBob = names.indexOf('Bob'); // 1
   Integer indexDavid = names.indexOf('David'); // -1 (not found)
   ```

7. **remove(Integer index):**

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   names.remove(1); // Removes "Bob"
   System.debug(names); // Output: ["Alice", "Charlie"]
   ```

8. **size():**

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   Integer listSize = names.size(); // 3
   ```

9. **sort():**

   ```apex
   List<Integer> numbers = new List<Integer>{3, 1, 2};
   numbers.sort();
   System.debug(numbers); // Output: [1, 2, 3]
   ```

10. **sort(Comparator<...> comp):** Sorts the elements in the list using a custom comparator.

   ```apex
   List<String> names = new List<String>{'Bob', 'Alice', 'Charlie'};
   names.sort();
   System.debug(names); // Output: ["Alice", "Bob", "Charlie"]

   // Using a custom comparator for reverse sorting
   names.sort((a, b) => b.compareTo(a));
   System.debug(names); // Output: ["Charlie", "Bob", "Alice"]
   ```

11. **subList(Integer fromIndex, Integer toIndex):** Returns a new List that contains elements from the specified `fromIndex` (inclusive) to `toIndex` (exclusive) in the original list.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie', 'David'};
   List<String> subNames = names.subList(1, 3);
   System.debug(subNames); // Output: ["Bob", "Charlie"]
   ```

12. **isEmpty():** Checks if the list is empty.

   ```apex
   List<String> names = new List<String>();
   Boolean empty = names.isEmpty(); // true
   ```

13. **remove(Object element):** Removes the first occurrence of the specified element from the list.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie', 'Bob'};
   names.remove('Bob'); // Removes the first "Bob"
   System.debug(names); // Output: ["Alice", "Charlie", "Bob"]
   ```

14. **removeAll(Collection<...> elements):** Removes all occurrences of elements from the list based on a given collection.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie', 'Bob'};
   names.removeAll(new List<String>{'Bob', 'Alice'});
   System.debug(names); // Output: ["Charlie"]
   ```

15. **retainAll(Collection<...> elements):** Retains only the elements that exist in both the list and a given collection, effectively removing elements not in the collection.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie', 'David'};
   names.retainAll(new List<String>{'Bob', 'Charlie'});
   System.debug(names); // Output: ["Bob", "Charlie"]
   ```

16. **clone():** Creates a shallow copy of the list.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   List<String> copy = names.clone();
   System.debug(copy); // Output: ["Alice", "Bob", "Charlie"]
   ```

17. **containsAll(Collection<...> elements):** Checks if the list contains all elements from a specified collection.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie', 'David'};
   Boolean containsAll = names.containsAll(new List<String>{'Bob', 'Charlie', 'Alice'}); // true
   ```

18. **equals(Object other):** Compares the list to another object for equality.

   ```apex
   List<String> list1 = new List<String>{'Alice', 'Bob'};
   List<String> list2 = new List<String>{'Alice', 'Bob'};
   Boolean isEqual = list1.equals(list2); // true
   ```

19. **hashCode():** Returns a hash code value for the list.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   Integer hashCode = names.hashCode();
   System.debug(hashCode); // Output: A hash code value
   ```

20. **isEmpty():** Checks if the list is empty.

   ```apex
   List<String> names = new List<String>();
   Boolean empty = names.isEmpty(); // true
   ```

21. **toString():** Returns a string representation of the list.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Charlie'};
   String listString = names.toString();
   System.debug(listString); // Output: "[Alice, Bob, Charlie]"
   ```

--------------------------------------------------------------------------------------------------------------------------------------



### When We can Use List In Salesforce Apex:


**1. Storing Multiple Records:**

```apex
List<Contact> contactList = [SELECT Id, Name, Email FROM Contact LIMIT 5];
```

In this example, we're using a List to store the results of a SOQL query that retrieves the details of the first 5 contacts. Now, you can work with this collection of contacts.

**2. Data Manipulation:**

```apex
List<Integer> numbers = new List<Integer>{5, 2, 8, 1, 4};
numbers.sort(); // Sort the list in ascending order
```

Here, we have a List of integers, and we're using the `sort()` method to arrange the numbers in ascending order.

**3. Iterating Through Data:**

```apex
List<String> fruits = new List<String>{'Apple', 'Banana', 'Orange', 'Grapes'};

for (String fruit : fruits) {
    System.debug(fruit);
}
```

This code iterates through a List of fruits and prints each fruit name.

**4. Data Transfer and Transformation:**

```apex
List<Double> temperaturesCelsius = new List<Double>{23.5, 30.2, 15.9};
List<Double> temperaturesFahrenheit = new List<Double>();

for (Double celsius : temperaturesCelsius) {
    // Convert Celsius to Fahrenheit
    temperaturesFahrenheit.add((celsius * 9/5) + 32);
}
```

In this example, we use a List to store temperatures in Celsius and then calculate and store the equivalent temperatures in Fahrenheit.

**5. Custom Logic and Validation:**

```apex
List<Account> accountList = [SELECT Id, Name, AnnualRevenue FROM Account LIMIT 10];

for (Account acc : accountList) {
    if (acc.AnnualRevenue > 1000000) {
        acc.Description = 'Large Company';
    } else {
        acc.Description = 'Small Company';
    }
}

update accountList; // Update the records
```

Here, we use a List to store Account records and apply custom logic based on the Annual Revenue field.

These examples illustrate the flexibility and utility of Lists in Salesforce Apex. Lists are essential for handling collections of data, whether it's for storing records, iterating through data, data manipulation, or implementing custom business logic.

**6. Batch Processing:**

```apex
List<Contact> contactList = [SELECT Id, FirstName, LastName FROM Contact LIMIT 1000];
List<Contact> updatedContacts = new List<Contact>();

for (Contact con : contactList) {
    // Perform some updates or processing on each contact
    con.Description = 'Updated';
    updatedContacts.add(con);

    if (updatedContacts.size() == 200) {
        // Process and update contacts in batches of 200
        update updatedContacts;
        updatedContacts.clear();
    }
}

if (!updatedContacts.isEmpty()) {
    update updatedContacts; // Update any remaining records
}
```

This code demonstrates batch processing using Lists. We process contacts in batches to efficiently update a large dataset.

**7. Cross-Object Operations:**

```apex
List<Opportunity> opportunities = [SELECT Id, Name, Amount, Account.Name FROM Opportunity WHERE StageName = 'Closed Won' LIMIT 10];
```

In this example, we're using a List to store Opportunity records along with related Account information.

**8. Building Custom Logic:**

```apex
List<Case> caseList = [SELECT Id, Subject, Status FROM Case WHERE Status = 'New' LIMIT 5];

for (Case c : caseList) {
    // Implement custom logic based on Case attributes
    if (c.Subject.contains('Urgent')) {
        c.Priority = 'High';
    } else {
        c.Priority = 'Medium';
    }
}

update caseList; // Update the cases with custom logic applied
```

This code uses a List to store Case records and apply custom logic to set the Priority field.

These additional examples further illustrate how Lists are used in various scenarios in Salesforce Apex, including batch processing, cross-object operations, and custom logic implementation. Lists are a versatile tool for managing and processing collections of data in your Salesforce applications.

--------------------------------------------------------------------------------------------------------------------------------

In Salesforce, you can use Lists to work with both custom and standard objects, as well as sObjects. Lists are a versatile data structure in Apex that can hold collections of records of the same object type (sObject) or other data types like numbers, text, or custom objects. Here's how you can use Lists with various types of objects:

1. **Custom Objects:** You can use Lists to work with records of custom objects that you've created in your Salesforce organization. For example, if you have a custom object called "Custom__c," you can create a List to store and manipulate records of this custom object.

   ```apex
   List<Custom__c> customRecords = [SELECT Id, Name FROM Custom__c];
   ```

2. **Standard Objects:** Lists are also commonly used with standard Salesforce objects, such as Accounts, Contacts, Opportunities, and Leads. You can query and manipulate records from these standard objects using Lists.

   ```apex
   List<Account> accounts = [SELECT Id, Name FROM Account];
   ```

3. **sObjects:** In Salesforce, an sObject is a generic term that encompasses both custom and standard objects. Lists can store and process records of any sObject type. For example, you can create a List of sObjects and add records of various object types to it.

   ```apex
   List<sObject> mixedRecords = new List<sObject>();
   mixedRecords.addAll([SELECT Id, Name FROM Custom__c]);
   mixedRecords.addAll([SELECT Id, FirstName FROM Contact]);
   ```

Lists provide a convenient way to work with multiple records, whether they are custom objects, standard objects, or a mix of different sObject types. You can perform operations like querying, iterating, updating, or deleting records within Lists to manage and process your data effectively in Salesforce Apex.

