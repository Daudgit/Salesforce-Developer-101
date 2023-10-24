

**1. Intro to SOQL (Salesforce Object Query Language):**

SOQL (Salesforce Object Query Language) is a query language used to retrieve data from Salesforce objects (records). It's similar to SQL but tailored to Salesforce's data model. SOQL queries are used to fetch records from standard and custom objects.

**Example - SOQL Query:**

```apex
List<Account> accounts = [SELECT Id, Name, Industry FROM Account WHERE Industry = 'Technology' LIMIT 10];
```

This SOQL query retrieves up to 10 Account records with the specified fields and a filter condition.

**2. Query Formation in SOQL:**

- Use `SELECT` to specify fields to retrieve.
- Specify the object with `FROM` followed by the object name.
- Add optional clauses like `WHERE` for filtering, `ORDER BY` for sorting, and `LIMIT` to restrict the number of records.

**3. Intro to SOSL (Salesforce Object Search Language):**

SOSL (Salesforce Object Search Language) is used for full-text searching across multiple objects. It's suitable for finding records based on keywords and phrases. SOSL returns a list of `List<SObject>`.

**Example - SOSL Query:**

```apex
List<List<SObject>> searchResults = [FIND 'Salesforce' IN ALL FIELDS RETURNING Account, Contact];
```

This SOSL query searches for the term 'Salesforce' in all fields of the Account and Contact objects.

**4. Query Formation in SOSL:**

- Use `FIND` followed by the search term.
- Specify the objects to search (`RETURNING`).
- You can include multiple objects and fields to search.

**5. DML Statements in Salesforce (APEX+SOQL):**

DML (Data Manipulation Language) statements in Salesforce include `INSERT`, `UPDATE`, `DELETE`, and `UPSERT`. These statements allow you to create, update, or delete records.

**Example - DML Statements:**

```apex
// Insert a new Account record
Account newAccount = new Account(Name='New Account');
insert newAccount;

// Update an existing Contact record
Contact contactToUpdate = [SELECT Id, LastName FROM Contact WHERE LastName = 'Doe' LIMIT 1];
contactToUpdate.LastName = 'Smith';
update contactToUpdate;

// Delete a record
delete contactToUpdate;
```

These examples show how to insert, update, and delete records in Salesforce using Apex.

**6. Relationship Query:**

In Salesforce, you can query related records using relationship queries. For example, querying Contacts related to an Account:

```apex
List<Contact> relatedContacts = [SELECT Id, LastName FROM Contact WHERE Account.Name = 'Acme Inc.'];
```

This query retrieves Contact records related to the Account with the name 'Acme Inc.'

**7. SFDC Data Storage:**

Salesforce stores data in records, and records are organized into objects. Data storage in Salesforce is based on objects. There are standard objects (e.g., Account, Contact) and custom objects (created by users).

- Records: Individual instances of an object, e.g., a specific Account or Contact.
- Fields: Attributes that hold data in an object.
- Relationships: Links between objects, such as a Contact's relationship to an Account.
- Limits: Salesforce has data storage limits based on the edition and user licenses.

Understanding these concepts is crucial for designing effective data models and queries in Salesforce.
