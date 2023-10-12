
**CorrelationId** - A GUID which is passed as header in http requests or as metadata in Events that helps us in tracing and debugging across the different services.
**Source of truth for CorrelationId**- Human Interaction Manager and Enrichment Engine (when we get an event from Enterprise Services regarding some data update)

LOD , CE should be passing it along. Enrichment Engine will be creating CorrelationId in case if its talking to Enterprise Services else it will be gpassing the correlationid along.



In addition to CorrelationId, we are proposing to have SourceId.

SourceId - GUID ,which system generated the LOD event .

Domain-Level ID - we have LoanOriginationId and/or EngagementId that is being passed across systems. we need to make sure we include this in every Http call/ metadata for Event if we already not doing it.

**One Transaction for LiftOff services:**

A new SourceId will be created when a system needs to generate a LOD changed event as a result of the event it generates. In our case, it is HIM as it generates Interaction Event which results in LOD Changed Event and Enrichment Core as it generates Enrichment Event which results in LOD Changed Event as well.

A CorrelationId will be created by HIM. CorrelationId needs to be a List because Enrichment Core aggregate the Correlationids for a single LoanOriginationId. Enrichment Core can ignore SourceId that got in the Event and generate one instead while triggering Enrichment Actions.

<ac:structured-macro ac:name="gliffy" ac:schema-version="1" ac:macro-id="990f3e2a-69cd-4f90-b42b-e10aac06b4ab"><ac:parameter ac:name="border">true</ac:parameter><ac:parameter ac:name="name">BasicHIMArchitectureDiagram Copy</ac:parameter><ac:parameter ac:name="pagePin">11</ac:parameter></ac:structured-macro>


