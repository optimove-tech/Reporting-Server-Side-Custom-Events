
### **Enabling Optimove Server Side API (OptiEvent)**

 1. Please contact your Optimove Customer Success Manager (CSM) or Optimove point of contact to request this tracking feature. 
 2. Optimove’s Product Integration Team will then send you the following:<br>
A. Optimove API Endpoint to be used for each API request.<br>
B. Optimove Tenant ID ('*tenant*') to use for each API request<br>
C. Event Key ('*event*') : This custom event(s) needs to be pre-configured by the Product Integration Team. Therefore please send a list of Events (see [Events & Parameter request](https://github.com/optimove-tech/Reporting-Server-Side-Custom-Events/blob/master/README.md#events--parameter-request))<br>
C. Parameter Name(s) ('*context*'): This needs to be pre-configured by the Product Integration Team. Therefore please send a list of Events (see [Events & Parameter request](https://github.com/optimove-tech/Reporting-Server-Side-Custom-Events/blob/master/README.md#events--parameter-request))

### **Events & Parameter request**
Optimove’s Product Integration Team require to pre-configure the custom events and their parameters in order for you to use within the API calls. The team will also help you create custom events use cases you will be reporting to Optimove from your server side. These events and the optional parameters should be configured on both sides.
<br/><br/>

Event Name:<br/>
 - Parameter Name:
 - Parameter Type:

### **Code Format**

**Request**   
    
  JSON Payload:
```json
 {
        "tenant": [Optimove Tenant ID], //integer
	"event": [Event Key], //"string"
	"customer": [CustomerID],//"string"
	"visitor": [VisitorID],//"string" (Optional)
	"timestamp":[Timestamp UTC],//"string"
        "context": {Paramater Name:Parameter Value} 
  }
```
**Request Example**   
```json
    {
        "tenant":999,
    	"event":"newsletter_signup",
    	"customer":"johndoe@domain.com",
    	"visitor":"b449f7778d4981a5",
    	"timestamp":"2020-04-12 17:32:06.094 UTC",
        "context": {
            "email":"johndoe@domain.com",
            "opt_in":true} 
    }
```

**Response Examples**<br/>

 ```json
  success{
         "status": "success",
         "message": "1147206418897270"
       }
```
 
```json 
   fail{
        "status": "error",
        "message": "Failed to validate the event with the following error - tenantId is missing or invalid"
    }
```
>**Important Notes:**
>  - The CustomerID must match your Customer ID (CID) your are sending Optimove on a daily basis and is is also used to identify individual customer records within your Optimove customer database.
>   - The VisitorID is *optional*.
>   - The request must contain EITHER a VisitorID or a CustomerID to identify the user, NOT both.
>  - Event and parameter names are case sensitive.
>  - The parameter types available for use in event-reporting functions will be dependent on the configuration within your Optimove instance. <br/>
>  - All monetary values must be reported in the same currency defined in your Optimove instance (e.g., if your instance is based on US dollars, all monetary event values must be reported in dollars). Optimove will not perform currency conversions.
>  - If your Optimove instance supports multiple languages, all event parameters must use a single default language. This is required in order to maintain a unified set of events.
