

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

