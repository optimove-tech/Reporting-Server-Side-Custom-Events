At this time, events reported using server side programming language will only be used by the Optimove realtime functionality only. 

### **Enabling Optimove Server Side API**
1. Please contact your Optimove Customer Success Manager (CSM) or Optimove point of contact to request this tracking feature. 
2. Optimove’s Product Integration Team will then send you the following: 
-- A. Optimove API Token: Unique API Token to use for the authenetication
-- B. Event ID: This custom events needs to be pre-configured by the Product Integration Team. Therefore please send a list of Events (see [Events & Parameter request](https://github.com/optimove-tech/Reporting-Server-Side-Custom-Events/blob/master/README.md#events--parameter-request))
-- C. Paramater Name: This needs to be pre-configured by the Product Integration Team. Therefore please send a list of Events (see [Events & Parameter request](https://github.com/optimove-tech/Reporting-Server-Side-Custom-Events/blob/master/README.md#events--parameter-request))

### **Events & Parameter request**
Optimove’s Product Integration Team require to pre-configure the custom events and their parameters in order for you to use within the API calls. The team will also help you create custom events use cases you will be reporting to Optimove from your server side. These events and the optional parameters should be configured on both sides.
<br/><br/>

Event Name:<br/>
-- Parameter Name:<br/>
-- Parameter Type:

<br/>

**URL**: https://gateway.optimove.events/reportEvent

**Request**   
    
        JSON Payload:
        {
          tid: [Optimove API Token],
          cid: [CustomerID],
          eid: [EventID], 
          context: {Paramater Name:Paramaeter Value} 
        }

**Response Example**
    
        success{
		   "IsSuccess": true,
		   "Data": false
		}

>**Important Notes:**
>  - Event and parameter names are case sensitive.
>  - Events and parameters use snake_case as a naming convention. Separate each word with one underscore character (_) and no spaces. (e.g., Checkout_Completed)
>  - The parameter types available for use in event-reporting functions are:<br/>
> **String**  – A series of alphanumeric characters of up to 255 characters in length, using any encoding<br/>
> **Number**  – Any numeric value, whether an integer or a value containing a decimal point<br/>
>  **Boolean**  – Is either "true" or "false" values, not a string<br/>
>  - All monetary values must be reported in the same currency defined in your Optimove instance (e.g., if your instance is based on US dollars, all monetary event values must be reported in dollars). Optimove will not perform currency conversions.
>  - If your Optimove instance supports multiple languages, all event parameters must use a single default language. This is required in order to maintain a unified set of events.
