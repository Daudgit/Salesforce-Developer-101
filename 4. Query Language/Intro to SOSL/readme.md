

**Introduction to SOSL (Salesforce Object Search Language):**

SOSL is a search language in Salesforce used to perform full-text searching across multiple objects. It's particularly useful when you want to find records based on keywords or phrases rather than specific fields. SOSL returns a list of lists of SObjects (`List<List<SObject>>`), which can include records from multiple objects.

**Basic SOSL Syntax:**

A basic SOSL query typically follows this structure:

```apex
FIND 'searchTerm' IN ALL FIELDS RETURNING Object1 (fields), Object2 (fields), ...
```

- `FIND`: Specifies the search term.
- `IN ALL FIELDS`: Indicates that the search term should be matched in all fields of the specified objects.
- `RETURNING`: Lists the objects to search and the fields to return.

**Example SOSL Queries:**

1. **Simple Keyword Search:**

   ```apex
   FIND 'Salesforce' IN ALL FIELDS RETURNING Account, Contact
   ```

   This query searches for the term 'Salesforce' in all fields of the Account and Contact objects.

2. **Multiple Keywords and Fields:**

   ```apex
   FIND 'App Cloud' AND 'Lightning' IN Name, Description RETURNING Custom_Object__c (Name, Description)
   ```

   This query searches for 'App Cloud' and 'Lightning' in the Name and Description fields of the Custom_Object__c object, returning the specified fields.

3. **Wildcard Search:**

   ```apex
   FIND 'acm*' IN ALL FIELDS RETURNING Account (Name), Contact (LastName)
   ```

   This query uses a wildcard ('*') to search for terms starting with 'acm' in all fields of Account and for Last Names starting with 'acm' in Contact, returning specified fields.

4. **Filtering Search Results:**

   ```apex
   FIND 'keyword' IN ALL FIELDS RETURNING Account (Name WHERE Industry = 'Technology')
   ```

   This query searches for 'keyword' in all fields of Account records but returns only the Name of Accounts with the Industry set to 'Technology'.

5. **Sorting Search Results:**

   ```apex
   FIND 'keyword' IN ALL FIELDS RETURNING Account (Name ORDER BY Name)
   ```

   This query searches for 'keyword' in all fields of Account records and returns the Name of Accounts, sorted alphabetically.

**Types of SOSL Queries:**

SOSL queries can be categorized into two types:

1. **Regular SOSL Queries:** These are the typical SOSL queries where you specify the search term and the objects to search.

2. **Filtered SOSL Queries:** In filtered SOSL queries, you can include additional filter conditions, sorting, and other clauses to refine the search results. These are used to limit the returned records based on certain criteria.

SOSL is a powerful tool for searching and retrieving records based on keywords and phrases across multiple objects. It's especially valuable when you need to perform broad searches and retrieve records that match specific search criteria.
