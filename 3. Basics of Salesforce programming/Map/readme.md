

1. **put(Key, Value):** Adds a key-value pair to the map. If the key already exists in the map, it updates the value associated with that key.

   ```apex
   Map<String, Integer> salesData = new Map<String, Integer>();
   salesData.put('January', 1000);
   salesData.put('February', 1200);
   ```

2. **get(Key):** Returns the value associated with a specified key.

   ```apex
   Integer januarySales = salesData.get('January'); // Retrieves the value 1000
   ```

3. **containsKey(Key):** Checks if the map contains a specific key.

   ```apex
   Boolean hasMarch = salesData.containsKey('March'); // Returns false
   ```

4. **keySet():** Returns a set of all keys in the map.

   ```apex
   Set<String> months = salesData.keySet(); // Returns a set of keys: {'January', 'February'}
   ```

5. **values():** Returns a list of all values in the map.

   ```apex
   List<Integer> salesValues = salesData.values(); // Returns a list of values: [1000, 1200]
   ```

6. **remove(Key):** Removes the key-value pair associated with the specified key.

   ```apex
   salesData.remove('January'); // Removes the 'January' key-value pair
   ```

7. **isEmpty():** Checks if the map is empty.

   ```apex
   Boolean isSalesDataEmpty = salesData.isEmpty(); // Returns false (assuming data is present)
   ```

8. **clear():** Removes all key-value pairs from the map.

   ```apex
   salesData.clear(); // Clears all entries from the map
   ```

9. **size():** Returns the number of key-value pairs in the map.

   ```apex
   Integer mapSize = salesData.size(); // Returns the number of entries in the map
   ```

10. **keySet():** Returns a set of all keys in the map.

    ```apex
    Set<String> keys = salesData.keySet(); // Returns a set of keys in the map
    ```

11. **values():** Returns a list of all values in the map.

    ```apex
    List<Integer> values = salesData.values(); // Returns a list of values in the map
    ```

12. **putAll(Map<...> otherMap):** Adds all key-value pairs from another map to the current map.

    ```apex
    Map<String, Integer> additionalData = new Map<String, Integer>{'March' => 800, 'April' => 950};
    salesData.putAll(additionalData); // Adds data from the 'additionalData' map to 'salesData'
    ```
============================================================================================================================================



In Salesforce Apex, Maps are commonly used in various scenarios to manage key-value pairs, making them a versatile data structure. Here are some common use cases for Maps in Salesforce Apex, along with examples:

1. **Data Aggregation:**

   Maps are often used to aggregate and summarize data based on specific criteria. For example, you can use a Map to group Contacts by their associated Accounts:

   ```apex
   Map<Id, List<Contact>> accountToContacts = new Map<Id, List<Contact>>();

   List<Contact> contacts = [SELECT Id, AccountId FROM Contact];
   for (Contact con : contacts) {
       if (!accountToContacts.containsKey(con.AccountId)) {
           accountToContacts.put(con.AccountId, new List<Contact>());
       }
       accountToContacts.get(con.AccountId).add(con);
   }
   ```

   In this example, the Map `accountToContacts` groups Contacts by their associated Account Ids.

2. **Data Transformation:**

   Maps are useful for transforming data into a different structure. For instance, you can convert a List of SObjects into a Map for easier access:

   ```apex
   List<Contact> contacts = [SELECT Id, FirstName, LastName FROM Contact];
   Map<Id, Contact> contactMap = new Map<Id, Contact>(contacts);

   // Access a specific Contact by Id
   Contact specificContact = contactMap.get('0012b00000abcdefg');
   ```

3. **Error Handling:**

   Maps can be used to associate error messages with specific records during data validation or processing:

   ```apex
   Map<Id, String> recordErrors = new Map<Id, String>();

   // During data processing, if an error is encountered for a specific record, add it to the map
   if (errorCondition) {
       recordErrors.put(recordId, 'Validation Error: Invalid data.');
   }
   ```

4. **Indexing:**

   Maps can serve as indexes to quickly retrieve specific records based on a unique key. For example, you can index Accounts by their names:

   ```apex
   Map<String, Account> accountIndex = new Map<String, Account>();

   List<Account> accounts = [SELECT Id, Name FROM Account];
   for (Account acc : accounts) {
       accountIndex.put(acc.Name, acc);
   }

   // Retrieve an Account by name
   Account specificAccount = accountIndex.get('Acme Corporation');
   ```

5. **Complex Data Structures:**

   Maps can store complex data structures, including other Maps, Lists, or custom objects. This allows for more intricate data management:

   ```apex
   Map<String, Map<String, Integer>> complexMap = new Map<String, Map<String, Integer>>();
   ```

   This complex map can be used to store and retrieve data in a hierarchical structure.

6. **Metadata Handling:**

   Maps can be used to store and manage metadata information related to your Salesforce configuration:

   ```apex
   Map<String, String> customFieldLabels = new Map<String, String>();
   customFieldLabels.put('Custom_Object__c.Custom_Field__c', 'Custom Field Label');
   ```

   This can be helpful when working with dynamic configurations.

Maps are an essential data structure in Salesforce Apex, providing flexibility and efficiency in data management. They are versatile tools that can be applied to various use cases, including data aggregation, data transformation, error handling, indexing, and more.
