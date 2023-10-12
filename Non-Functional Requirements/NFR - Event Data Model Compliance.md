
## Event Fields

Source - [https://git.rockfin.com/PRitchie/rfcs/blob/master/rfcs/10108-Application-Event-Information-and-Metadata-Standard.md](https://git.rockfin.com/PRitchie/rfcs/blob/master/rfcs/10108-Application-Event-Information-and-Metadata-Standard.md)

\*\*Error Handling - New approach to event based error handling not covered in the standard
<ac:structured-macro ac:name="code" ac:schema-version="1" ac:macro-id="39e37f4e-ed17-4031-beff-5dd7e2bdeb37"><ac:parameter ac:name="language">js</ac:parameter><ac:parameter ac:name="linenumbers">true</ac:parameter><ac:plain-text-body><![CDATA[{
  "id": "UUID URN String",
  "correlationIds": [ "UUID URN String", "UUID URN String" ],
  "created": "ISO 8601 String",
  "appId": "[0-9]{6}",
  "serverHostName": "URN name string",
  "environment": "(dev|beta|train|stage|prod|test|acceptance)",
  "eventType": "Rock.QL.LiftOff.<Component>.<process>.[<activity>.]<eventname>.<eventtype>",
  "errorHandling": {
    "type": "SNS",
    "uri": "SNS Topic Endpoint"
  }
}]]></eventtype></eventname></activity></process></ac:plain-text-body></ac:structured-macro>

