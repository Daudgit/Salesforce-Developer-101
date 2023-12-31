

1. **add(Object element):**

   ```apex
   Set<String> names = new Set<String>();
   names.add("Alice");
   names.add("Bob");
   ```

2. **addAll(Collection<...> elements):**

   ```apex
   Set<String> set1 = new Set<String>{'Alice', 'Bob'};
   Set<String> set2 = new Set<String>{'Bob', 'Charlie'};
   set1.addAll(set2); // "Alice", "Bob", "Charlie"
   ```

3. **clear():**

   ```apex
   Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie'};
   names.clear(); // Empty Set
   ```

4. **contains(Object element):**

   ```apex
   Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie'};
   Boolean containsBob = names.contains('Bob'); // true
   Boolean containsDavid = names.contains('David'); // false
   ```

5. **isEmpty():**

   ```apex
   Set<String> names = new Set<String>();
   Boolean empty = names.isEmpty(); // true
   ```

6. **remove(Object element):**

   ```apex
   Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie'};
   names.remove('Bob'); // Removes "Bob"
   ```

7. **size():**

   ```apex
   Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie'};
   Integer setSize = names.size(); // 3
   ```

8. **addAll(Set<...> elements):**

   ```apex
   Set<String> set1 = new Set<String>{'Alice', 'Bob'};
   Set<String> set2 = new Set<String>{'Bob', 'Charlie'};
   set1.addAll(set2); // "Alice", "Bob", "Charlie"
   ```

9. **clone():**

   ```apex
   Set<Integer> originalSet = new Set<Integer>{1, 2, 3};
   Set<Integer> copySet = originalSet.clone();
   ```

10. **equals(Object other):**

    ```apex
    Set<String> set1 = new Set<String>{'Alice', 'Bob'};
    Set<String> set2 = new Set<String>{'Alice', 'Bob'};
    Boolean isEqual = set1.equals(set2); // true
    ```

11. **addAllList(List<...> elements):**

    ```apex
    Set<String> set1 = new Set<String>{'Alice', 'Bob'};
    List<String> list = new List<String>{'Bob', 'Charlie', 'David'};
    set1.addAllList(list); // "Alice", "Bob", "Charlie", "David"
    ```

12. **containsAll(Collection<...> elements):**

    ```apex
    Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie', 'David'};
    Boolean containsAll = names.containsAll(new Set<String>{'Bob', 'Charlie', 'Alice'}); // true
    ```

13. **equals(Set<...> other):**

    ```apex
    Set<String> set1 = new Set<String>{'Alice', 'Bob'};
    Set<String> set2 = new Set<String>{'Alice', 'Bob'};
    Boolean isEqual = set1.equals(set2); // true
    ```

14. **hashCode():**

    ```apex
    Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie'};
    Integer hashCode = names.hashCode();
    System.debug(hashCode); // Output: A hash code value
    ```

15. **removeAll(Collection<...> elements):**

    ```apex
    Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie', 'David'};
    names.removeAll(new Set<String>{'Bob', 'Alice'});
    ```

16. **retainAll(Collection<...> elements):**

    ```apex
    Set<String> names = new Set<String>{'Alice', 'Bob', 'Charlie', 'David'};
    names.retainAll(new Set<String>{'Bob', 'Charlie'});
    ```
----------------------------------------------------------------------------------------------------------------------------------

Sets in Salesforce Apex are used for a variety of purposes, primarily to manage and manipulate data efficiently. Here are some common scenarios where you can use Sets in Salesforce, along with code examples:

1. **Removing Duplicates:** Use Sets to eliminate duplicate records or values from a list of data.

   ```apex
   List<String> names = new List<String>{'Alice', 'Bob', 'Alice', 'Charlie', 'Bob'};
   Set<String> uniqueNames = new Set<String>(names);
   ```

   In this example, the Set `uniqueNames` will contain only unique values ('Alice', 'Bob', 'Charlie').

2. **Checking for Uniqueness:** Sets are helpful for checking whether a value is unique within a collection.

   ```apex
   Set<String> existingEmails = new Set<String>();
   String newEmail = 'user@example.com';

   if (!existingEmails.contains(newEmail)) {
       existingEmails.add(newEmail);
   }
   ```

   This code ensures that `newEmail` is added to `existingEmails` only if it's not already present.

3. **Membership Testing:** Use Sets to quickly check if a value exists in a collection.

   ```apex
   Set<String> validCountries = new Set<String>{'USA', 'Canada', 'UK', 'Australia'};
   String userCountry = 'UK';

   if (validCountries.contains(userCountry)) {
       // Perform country-specific logic
   }
   ```

   This code tests whether `userCountry` is in the set of `validCountries`.

4. **De-Duping SObject Records:** You can use Sets to remove duplicate SObject records based on specific fields.

   ```apex
   List<Contact> contacts = [SELECT Id, Email FROM Contact];
   Set<String> uniqueEmails = new Set<String>();
   List<Contact> uniqueContacts = new List<Contact>();

   for (Contact con : contacts) {
       if (!uniqueEmails.contains(con.Email)) {
           uniqueEmails.add(con.Email);
           uniqueContacts.add(con);
       }
   }
   ```

   This code retrieves Contacts from Salesforce and stores only the unique records based on the "Email" field.

5. **Sorting Data:** Sets automatically sort elements, which can be useful when you need an ordered collection.

   ```apex
   Set<Integer> numbers = new Set<Integer>{5, 2, 8, 1, 4};
   List<Integer> sortedNumbers = new List<Integer>(numbers);
   sortedNumbers.sort();
   ```

   In this example, `sortedNumbers` will contain the elements in ascending order.

6. **Ensuring Unique Values in Trigger Context:** When working with triggers in Salesforce, you can use Sets to ensure that certain actions are taken only once, avoiding duplication.

   ```apex
   Set<Id> processedIds = new Set<Id>();

   for (Opportunity opp : Trigger.new) {
       if (!processedIds.contains(opp.Id)) {
           // Perform actions
           processedIds.add(opp.Id);
       }
   }
   ```

   This code ensures that trigger actions are performed once per Opportunity.

Sets in Salesforce are versatile and efficient for handling data and ensuring uniqueness. They are valuable in scenarios where you need to manage collections of data with specific requirements.


---------------------------------------------------------------------------------------------------------------------------------------

In Salesforce Apex, Sets can be used with both standard objects, custom objects, and sObjects to efficiently manage and manipulate data. Sets are versatile data structures that can be applied to various use cases.

**Using Sets with Standard and Custom Objects:**

You can use Sets with standard and custom objects to perform tasks like de-duplication, membership testing, and data processing. Here are examples using both a standard object (Account) and a custom object (CustomObject__c):

**With a Standard Object (Account):**

```apex
// Create a Set to store Account IDs
Set<Id> accountIds = new Set<Id>();

// Query a list of Account records
List<Account> accounts = [SELECT Id FROM Account LIMIT 10];

// Add Account IDs to the Set
for (Account acc : accounts) {
    accountIds.add(acc.Id);
}

// Check if a specific Account ID exists in the Set
Id accountIdToCheck = '0010b00000abcdefg';
if (accountIds.contains(accountIdToCheck)) {
    System.debug('Account exists in the Set.');
}
```

**With a Custom Object (CustomObject__c):**

```apex
// Create a Set to store CustomObject IDs
Set<Id> customObjectIds = new Set<Id>();

// Query a list of CustomObject__c records
List<CustomObject__c> customObjects = [SELECT Id FROM CustomObject__c LIMIT 10];

// Add CustomObject IDs to the Set
for (CustomObject__c customObj : customObjects) {
    customObjectIds.add(customObj.Id);
}

// Check if a specific CustomObject ID exists in the Set
Id customObjectIdToCheck = 'a0S0b00000abcdefg';
if (customObjectIds.contains(customObjectIdToCheck)) {
    System.debug('CustomObject exists in the Set.');
}
```

**Using Sets with sObjects:**

Sets are also valuable when working with generic sObjects (which can represent any object type, standard or custom) to handle data dynamically. Here's an example of using a Set with sObjects:

```apex
// Create a Set to store sObjects
Set<SObject> sObjectSet = new Set<SObject>();

// Query a list of sObjects dynamically (e.g., based on user input)
String objectTypeToQuery = 'Account';
String query = 'SELECT Id FROM ' + objectTypeToQuery + ' LIMIT 10';
List<SObject> sObjects = Database.query(query);

// Add the queried sObjects to the Set
sObjectSet.addAll(sObjects);

// Check if a specific sObject exists in the Set
SObject sObjToCheck = [SELECT Id FROM Account LIMIT 1];
if (sObjectSet.contains(sObjToCheck)) {
    System.debug('sObject exists in the Set.');
}
```

**Additional Notes:**

- Sets automatically deduplicate data, so you can use them to ensure unique values.
- Sets are particularly useful when working with large data sets, as they provide efficient membership testing.

Remember to query and work with specific object fields as needed for your use case. Sets are powerful for data management and processing in Salesforce Apex, and you can adapt them to various situations with standard, custom, or dynamic object types.
