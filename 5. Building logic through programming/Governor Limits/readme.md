Governor limits are a set of runtime limits and constraints that Salesforce enforces to ensure the efficient and fair use of its resources in a multi-tenant environment. These limits prevent individual organizations from monopolizing resources and negatively impacting the performance and stability of the Salesforce platform. It's crucial for developers to be aware of these limits and design their code accordingly. Here are some key Salesforce governor limits:

1. **Per-Transaction Limits:**
   - These limits apply to a single transaction, such as a trigger execution, a Visualforce page request, or a batch job. Examples include:
     - Maximum number of DML statements (e.g., 150 for synchronous and 100 for asynchronous).
     - Maximum CPU time (e.g., 10,000 milliseconds for synchronous and 60,000 milliseconds for asynchronous).
     - Maximum heap size (e.g., 6 MB for synchronous and 12 MB for asynchronous).
     - Maximum number of SOQL queries (e.g., 100 for synchronous and 200 for asynchronous).

2. **Per-Object Limits:**
   - These limits apply to the number of records you can manipulate within a single transaction. For example:
     - Maximum number of records retrieved by a single SOQL query (e.g., 50,000 records).
     - Maximum number of records retrieved in a single DML operation (e.g., 10,000 records).

3. **Email Limits:**
   - Salesforce limits the number of emails that can be sent in a single day based on the organization's edition and type.

4. **Data Storage Limits:**
   - Salesforce limits the amount of data that can be stored in an organization based on the edition and the number of user licenses.

5. **API Limits:**
   - Salesforce has limits on the number of API requests that can be made within a 24-hour period. The limits vary based on the type of API (REST, SOAP, Bulk, etc.) and the Salesforce edition.

6. **Streaming API Limits:**
   - If you use the Streaming API, there are limits on the number of push topics and the number of clients that can be connected at a given time.

7. **Metadata Limits:**
   - Metadata limits pertain to the number of metadata components, such as custom objects, custom fields, and workflow rules, that can be created in an organization.

8. **View State Limits:**
   - Visualforce pages have view state limits that restrict the amount of data that can be sent between the client and the server.

9. **Custom Index Limits:**
   - Salesforce limits the number of custom indexes (e.g., custom field indexes) you can create for an object.

10. **Apex Execution Governor Limits:**
    - These include limits on the number of iterations in a loop, the number of records retrieved in a query, and the heap size consumed by your Apex code.

Understanding and managing these governor limits is essential when developing on the Salesforce platform. If your code exceeds these limits, it can result in exceptions and runtime errors, affecting your users' experience and potentially leading to performance issues. Therefore, it's important to design and optimize your code with these limits in mind, implement best practices, and conduct thorough testing to ensure that your Salesforce applications are efficient and reliable.
