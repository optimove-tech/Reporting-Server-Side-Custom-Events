At this time, events reported using server side programming language will only be used by the Optimove realtime functionality. 

How to request to report server side custom events
1. Please contact your Optimove Customer Success Manager (CSM) or Optimove point of contact to request this tracking feature. 
2. Optimove’s Integration Team will then send you your HTTPS details in order to get started.
3. Optimove’s Integration Team will also help you create custom events use cases.

You can also report events using HTTPS POST request, in the following format:

    https://gateway.optimove.events/reportEvent
    
    JSON payload:
    
        {
          tid: [realtime Token],
          cid: [CustomerID],
          eid: [EventID], 
          context: {ContextName:ContextVal} 
        }

**Note**: 

 1. At this time, events reported in this way will only be used by the Optimove realtime functionality.
 2. In order to execute realtime campaigns, but will not be processed by scheduled campaigns for tracking purposes. 
 3. In the near future, the Optimove SDK will also support reporting server-side events for use by scheduled campaigns.
