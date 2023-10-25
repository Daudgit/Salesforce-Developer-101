In Salesforce Visualforce, you can create custom controllers and standard controller extensions to incorporate new data and actions into a Visualforce page. These controllers and extensions allow you to define custom behavior for your page and interact with Salesforce data. Here's how to create custom controllers and standard controller extensions:

**Creating a Custom Controller:**

1. **Write an Apex Class:**
   - Create a new Apex class that will serve as your custom controller. This class should define the logic and data access for your Visualforce page.
   - Here's a simple example of a custom controller:

   ```apex
   public class MyCustomController {
       public String greeting { get; set; }

       public MyCustomController() {
           greeting = 'Hello, World!';
       }

       public void doSomething() {
           // Custom logic to be executed
           greeting = 'Action executed!';
       }
   }
   ```

2. **Associate the Controller with Your Visualforce Page:**
   - In your Visualforce page, associate the custom controller by specifying the `controller` attribute in the `<apex:page>` tag.

   ```html
   <apex:page controller="MyCustomController">
       <apex:outputText value="{!greeting}" />
       <apex:commandButton action="{!doSomething}" value="Click Me" />
   </apex:page>
   ```

3. **Data Binding and Action Execution:**
   - Use expressions, such as `{!greeting}`, to bind data from the controller to your Visualforce components. Data entered or actions taken by users can be executed in the controller methods, such as `doSomething()`.

**Creating a Standard Controller Extension:**

1. **Write an Apex Class Extension:**
   - To create a standard controller extension, create an Apex class that extends the standard controller for an object (e.g., Account, Contact, or a custom object).
   - Use the `ApexPages.StandardController` class to define the standard controller extension.

   ```apex
   public class MyExtensionController {
       private ApexPages.StandardController stdController;

       public MyExtensionController(ApexPages.StandardController stdController) {
           this.stdController = stdController;
       }

       public PageReference saveRecord() {
           // Custom logic to be executed when saving a record
           stdController.save();
           return null;
       }
   }
   ```

2. **Associate the Extension with Your Visualforce Page:**
   - In your Visualforce page, associate the standard controller extension by specifying the `extensions` attribute in the `<apex:page>` tag.

   ```html
   <apex:page standardController="Account" extensions="MyExtensionController">
       <apex:inputText value="{!Account.Name}" />
       <apex:commandButton action="{!saveRecord}" value="Save" />
   </apex:page>
   ```

3. **Data Binding and Action Execution:**
   - You can use expressions like `{!Account.Name}` to bind fields from the standard controller to your Visualforce components. The custom action, `saveRecord()`, can extend the behavior of the standard controller's save operation.

By creating custom controllers and standard controller extensions, you can add new data, business logic, and interactions to your Visualforce pages. This flexibility allows you to tailor your user interfaces to the specific needs of your Salesforce applications while maintaining data integrity and security.
