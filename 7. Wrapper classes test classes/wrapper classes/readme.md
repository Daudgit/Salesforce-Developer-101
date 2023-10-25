In Salesforce, a wrapper class is a custom Apex class used to represent complex data structures in a more easily manageable format, typically to facilitate the display and manipulation of data in user interfaces, such as Visualforce pages and Lightning components. Wrapper classes are particularly useful when you need to work with multiple related objects or when you want to display data in a structured way that's different from how it's stored in the database. Here's an overview of wrapper classes:

1. **Purpose of Wrapper Classes:**
   - Wrapper classes are used to combine and structure data from multiple related objects, custom objects, or standard objects into a single data structure.
   - They help in passing data between the controller and the Visualforce page or Lightning component in a user-friendly format.

2. **Structure of a Wrapper Class:**
   - A wrapper class is a custom Apex class with properties that represent the fields or attributes you want to display or manipulate.
   - It often contains getter and setter methods to access and modify the data.

3. **Benefits of Wrapper Classes:**
   - **Custom Display:** You can customize the way data is displayed in user interfaces by creating wrapper classes that align with the specific requirements of your Visualforce pages or Lightning components.
   - **Ease of Manipulation:** Wrapper classes simplify data manipulation, such as sorting, filtering, and performing calculations on data in memory.
   - **Reduced View State Size:** Wrapper classes can help reduce the view state size in Visualforce pages by excluding unnecessary data.

4. **Example:**
   - Suppose you want to display a list of opportunities on a Visualforce page, including fields from the related account and contact records. You can create a wrapper class that combines data from the Opportunity, Account, and Contact objects into a single structure for easy display.

   ```apex
   public class OpportunityWrapper {
       public Opportunity opp { get; set; }
       public Account acc { get; set; }
       public Contact con { get; set; }

       public OpportunityWrapper(Opportunity opp, Account acc, Contact con) {
           this.opp = opp;
           this.acc = acc;
           this.con = con;
       }
   }
   ```

5. **Use Cases:**
   - Wrapper classes are commonly used in scenarios like displaying related data, customizing the display of records, implementing complex forms, and handling data from multiple objects.

6. **Visualforce and Lightning:**
   - Wrapper classes can be used in both Visualforce and Lightning components to create custom displays and interactions with data.

7. **Data Binding:**
   - You can bind wrapper class properties directly to Visualforce components, making it easy to display and edit data in forms.

8. **Validation and Business Logic:**
   - Wrapper classes can also include validation logic and business rules to ensure that data entered in a form meets your specific requirements.

Overall, wrapper classes are a powerful tool in Salesforce development for customizing data presentation, simplifying data manipulation, and enhancing the user experience in Visualforce pages and Lightning components. They allow you to create more user-friendly and tailored interfaces while working with complex data structures.
