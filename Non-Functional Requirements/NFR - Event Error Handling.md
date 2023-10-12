
## Goal

Asynchronous architectures, included event based architectures, are reactive to error handling rather than proactive like normal synchronous web communication protocols. This creates a lack of visibility to error scenarios where the sending system has to find errors within the consumers

## Approach

The Event Data Model compliance NFR included the "error handling" section that tells a consumer system of an event where to place an error message

Each component that sends events should have an error handling input path described in the events that they publish and handle the incoming events to at least log the errors for visibility. Otherwise errors are essentially ignored or assumed to be handled in another way.

Specify Error Event Handler: <ac:link><ri:page ri:space-key="~pvarga" ri:content-title="NFR - Event Data Model Compliance"></ri:page></ac:link>


<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="609d439c-ae82-46dc-9cbe-449adec891a5"><ac:parameter ac:name="language">js</ac:parameter><ac:parameter ac:name="linenumbers">true</ac:parameter><ac:plain-text-body><![CDATA[{
  "id": "UUID URN String",
  "correlationIds": [ "UUID URN String", "UUID URN String" ],
  "created": "ISO 8601 String",
  "appId": "[0-9]{6}",
  "serverHostName": "URN name string",
  "environment": "(dev|beta|train|stage|prod|test|acceptance)",
  "eventType": "Rock.QL.LiftOff.<Component>.<process>.[<activity>.]<eventname>.<eventtype>",
  "level": "(warn|error|fatal)"
  "error": {
    "code": "string",
    "message": "string",
    "exception": {},
    "sourceEvent": {}
  }
}]]></eventtype></eventname></activity></process></ac:plain-text-body></ac:structured-macro>

