

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

