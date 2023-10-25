To create a SOAP web service in Salesforce and expose it via an inbound WSDL API for third-party integrations, you'll follow a series of steps. In this example, we'll create a simple SOAP web service using Apex and generate the WSDL for external consumption:

**1. Create a Custom SOAP Web Service:**

Create an Apex class that contains the methods you want to expose as a SOAP web service. In this example, we'll create a simple service for retrieving information about an account.

```apex
global with sharing class AccountService {
    webservice static String getAccountInfo(String accountId) {
        Account acc = [SELECT Id, Name, Phone, BillingStreet, BillingCity FROM Account WHERE Id = :accountId];
        return 'Account Name: ' + acc.Name + '\nPhone: ' + acc.Phone + '\nAddress: ' + acc.BillingStreet + ', ' + acc.BillingCity;
    }
}
```

**2. Generate the WSDL:**

In Salesforce, you can generate the WSDL for your custom web service. To do this:

- Go to "Setup" > "API" > "Generate Enterprise WSDL."
- Click "Generate."
- Save the generated WSDL file. You'll provide this WSDL to your third-party integration.

**3. Expose the SOAP Service:**

Now, expose the SOAP web service by creating a Visualforce page that uses the `apex:page` component with the `contentType` attribute set to "text/xml."

```html
<apex:page controller="AccountService" contentType="text/xml">
    <apex:includeScript value="{!$Resource.enterprise}" />
    <apex:form id="accountForm">
        <apex:actionFunction name="getAccountInfo" action="{!getAccountInfo}" reRender="accountForm" status="acctStatus">
            <apex:param name="accountId" value="" />
        </apex:actionFunction>
    </apex:form>
</apex:page>
```

**4. Share the WSDL with Third-Party:**

Share the generated WSDL file with the third-party service that intends to consume your SOAP web service. They can use this WSDL to generate client code to interact with your service.

**5. Consuming the SOAP Service:**

The third-party integration can create SOAP client code using the WSDL provided. They can use this client code to make SOAP requests to your Salesforce SOAP service. The client code will include the appropriate SOAP headers and body for making requests.

**6. Testing:**

Ensure you test the SOAP service within Salesforce to verify its functionality and correctness. Salesforce provides tools to test your web service. You can also check the debug logs for any issues during service invocation.

**7. Security and Authentication:**

Implement security and authentication mechanisms if required. You can use Salesforce security features such as user permissions, profiles, and IP restrictions to secure your SOAP service.

**8. Error Handling:**

Implement proper error handling and SOAP fault responses to ensure that the service behaves gracefully when errors occur.

Remember to thoroughly test your service, document its usage, and follow best practices for web service design and security when exposing SOAP services for third-party integrations.
