Creating Apex web services and performing callouts to external web services in Salesforce is a common requirement for integrating with other systems. In this example, we'll create a simple Apex REST web service and make a callout to an external REST API. Here's a step-by-step guide:

**1. Create an Apex REST Web Service:**

In this example, we'll create a simple REST web service to fetch information about a product from an external API.

```apex
@RestResource(urlMapping='/productInfo/*')
global with sharing class ProductInfoService {
    @HttpGet
    global static String getProductInfo() {
        String productId = RestContext.request.params.get('id');
        // Make a callout to an external API to get product information
        String externalApiResponse = calloutToExternalAPI(productId);
        return externalApiResponse;
    }

    private static String calloutToExternalAPI(String productId) {
        Http http = new Http();
        HttpRequest request = new HttpRequest();
        request.setEndpoint('https://api.example.com/products/' + productId);
        request.setMethod('GET');
        HttpResponse response = http.send(request);

        if (response.getStatusCode() == 200) {
            return response.getBody();
        } else {
            // Handle error scenarios
            return 'Error: ' + response.getStatus();
        }
    }
}
```

**2. Define the REST Endpoint:**

The `@RestResource(urlMapping='/productInfo/*')` annotation defines the REST endpoint URL where this service is accessible. In this example, it's accessible at `/services/apexrest/productInfo`.

**3. Make an HTTP GET Callout:**

We define a method `getProductInfo` annotated with `@HttpGet` to handle incoming GET requests. This method extracts the `id` parameter from the request and calls the `calloutToExternalAPI` method to make an HTTP GET request to an external API.

**4. Handle Callout Response:**

The `calloutToExternalAPI` method performs the actual HTTP GET callout. If the response status code is 200 (OK), the method returns the response body (product information). Otherwise, it returns an error message.

**5. Testing the Service:**

To test the web service, you can use tools like Postman or cURL. For example, to fetch product information for product ID 123, make a GET request to:

`https://your-salesforce-instance/services/apexrest/productInfo?id=123`

Replace `your-salesforce-instance` with your Salesforce instance URL.

**6. Secure Your Callouts:**

Consider implementing authentication and security mechanisms when making callouts to external APIs. You can use Named Credentials in Salesforce to securely store authentication information and reference them in your callout code.

This example demonstrates how to create a simple Apex REST web service and make a callout to an external API. In a real-world scenario, you should also handle error cases, perform data transformations, and implement proper security measures based on your integration requirements.
