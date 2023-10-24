

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

