At this time, events reported using server side programming language will only be used by the Optimove realtime functionality. 

## **How to request to report server side custom events**
1. Please contact your Optimove Customer Success Manager (CSM) or Optimove point of contact to request this tracking feature. 
2. Optimove’s Integration Team will then send you your tid (unique identifier) as part of the HTTPS request in order to get started.
3.	Optimove’s Integration Team will also help you create custom events use cases you will be reporting to Optimove from your server side. These events and the optional parameters should be configured on both sides.
4.	Optimove’s Integration Team will then provide you with the eid’s and context of the each one of pre-defined events (structure described below)


## **How to report events**
You can report events using HTTPS POST request, in the following format:

**URL**: https://gateway.optimove.events/reportEvent

**Request**   
    
        JSON Payload:
        {
          tid: [realtime Token],
          cid: [CustomerID],
          eid: [EventID], 
          context: {ContextName:ContextVal} 
        }

**Response Example**
    
        success{
		   "IsSuccess": true,
		   "Data": false
		}

**Notes**: 

 1. At this time, events reported in this way will only be used by the Optimove realtime functionality.
 3. In the near future, the Optimove SDK will also support reporting server-side events for use by scheduled campaigns.
