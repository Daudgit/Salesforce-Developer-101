Passing data or parameters between Visualforce (VF) pages and controllers in Salesforce is a common requirement. Here are some methods and examples for passing data and parameters between VF pages and controllers:

**1. URL Parameters:**

You can pass data between VF pages and controllers using URL parameters. For example, you can construct a URL with parameters and then access those parameters in your controller.

**Visualforce Page:**
```html
<apex:page controller="MyController">
    <apex:outputLink value="/apex/MyPage?param1=value1&param2=value2">Go to Page</apex:outputLink>
</apex:page>
```

**Controller:**
```apex
public class MyController {
    public String param1 { get; set; }
    public String param2 { get; set; }

    public MyController() {
        param1 = ApexPages.currentPage().getParameters().get('param1');
        param2 = ApexPages.currentPage().getParameters().get('param2');
    }
}
```

**2. `apex:param` Tag:**

You can use the `<apex:param>` tag to pass parameters within a form or as part of a commandLink or commandButton. This approach is suitable for more controlled interactions, such as submitting a form.

**Visualforce Page:**
```html
<apex:page controller="MyController">
    <apex:form>
        <apex:inputText value="{!param1}" />
        <apex:inputText value="{!param2}" />
        <apex:commandButton action="{!doSomething}">
            <apex:param name="param1" value="{!param1}" />
            <apex:param name="param2" value="{!param2}" />
        </apex:commandButton>
    </apex:form>
</apex:page>
```

**Controller:**
```apex
public class MyController {
    public String param1 { get; set; }
    public String param2 { get; set; }

    public void doSomething() {
        // Access and use param1 and param2 here
    }
}
```

**3. View State:**

The View State implicitly stores the state of input components on a Visualforce page. You can access the values of these components in your controller.

**Visualforce Page:**
```html
<apex:page controller="MyController">
    <apex:form>
        <apex:inputText value="{!param1}" />
        <apex:inputText value="{!param2}" />
        <apex:commandButton action="{!doSomething}" value="Submit" />
    </apex:form>
</apex:page>
```

**Controller:**
```apex
public class MyController {
    public String param1 { get; set; }
    public String param2 { get; set; }

    public void doSomething() {
        // Access and use param1 and param2 here
    }
}
```

These methods allow you to pass data between Visualforce pages and controllers as needed. The choice of method depends on the specific use case and the desired level of control and security for the data being passed.
