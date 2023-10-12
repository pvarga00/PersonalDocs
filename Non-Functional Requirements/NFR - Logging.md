
### Aggregation / Storage

Splunk  ([ttps://git.rockfin.com/pages/tech-standards/guide-book/standards/logging-metrics/logging/aggregation-tool/](https://git.rockfin.com/pages/tech-standards/guide-book/standards/logging-metrics/logging/aggregation-tool/))

### Format

[https://git.rockfin.com/tech-standards/rfcs/blob/master/rfcs/10181-logging-format-update.md](https://git.rockfin.com/tech-standards/rfcs/blob/master/rfcs/10181-logging-format-update.md)

CORE - <ac:link><ri:page ri:space-key="CORE" ri:content-title="Splunk Message Format"></ri:page></ac:link>

### QL Logging Package

NOTE: This might not be up to date with the format above, need to cross reference

[https://git.rockfin.com/RockLib/RockLib.Logging.Internal](https://git.rockfin.com/RockLib/RockLib.Logging.Internal)

[https://qugetgal/packages/RockLib.Logging.Internal/1.0.7](https://qugetgal/packages/RockLib.Logging.Internal/1.0.7)



**Lift Off Logging (Latest Package as of 4/22/19 (includes the Lift Off QuGet Package))-**

[https://git.rockfin.com/LiftOff/LiftOffLib.Logging](https://git.rockfin.com/LiftOff/LiftOffLib.Logging "https://git.rockfin.com/liftoff/liftofflib.logging")

[https://qugetgal.rockfin.com/packages/LiftOffLib.Logging/](https://qugetgal.rockfin.com/packages/LiftOffLib.Logging/ "https://qugetgal.rockfin.com/packages/liftofflib.logging/")

**\*\*(documentation on how to use and test it in your own code on the readme file in git. If you feel there is a need for a cross cutting field, please open an issue on the repository so that we can address it there)**

### Exceptions / Deviation From Standards

- Tech Standard only supports a single correlation ID as a string. LiftOff will use a string.join(",", correlationIds) to retain the information


### What/When to Log

Wikipedia: A log "records either events that occur in an operating system or other software runs, or messages between different users of a communication software.".  So:

- Log when activated or given control (Startup, Endpoint Invoked, Endpoint Invocation Complete, Thread Start, Thread Complete, etc.) Log as INFO, unless the purpose of activation is due to error.  Include user context.  If auditing, include another AUDIT entry.
- Log all explicit business events (like decisions made, processes complete, milestones, etc).  Include user context.  Log as INFO, unless the decision indicates error/fault, then WARN or ERROR. If the event is a result of a user action, include another AUDIT entry.  If a state change (like create, update, delete) and is not a business event, log the success/failure as AUDIT.  Include an INFO log for state changes if you want to be able to search for them in non-audit logs.
- In multi-step processes or workflows, log the start and completion of each step (unless the steps are effectively instantaneous, in which case log the completion) Log as INFO.
- Log all measurements (count of operations, time-span of operations, business measures, business metrics, KPIs, etc.)  Log as INFO, unless the measurement indicates a potential future problem then WARN; if the decision indicates an fault or error then ERROR.
- Log exceptions as ERROR and try to avoid logging the stack unless you have to.
- Log anything actively need for debugging.  Log as DEBUG.  For any of the above, a TRACE entry can be included for debugging/tracing.

