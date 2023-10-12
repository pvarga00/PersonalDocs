# Quality ScoreCard (Evaluation)

## Application Quality Score card

<table>
    <tbody>
        <tr>
            <td> 1 </td>
            <td colspan=3> Deployment Guard Rails </td>
        </tr>
        <tr>
            <td> </td>
            <td> 1.1 </td>
            <td colspan=2> CI/CD Quality Gates (CircleCI) </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.1.1 </td>
            <td> Integration tests </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.1.2 </td>
            <td> Snyk </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.1.3 </td>
            <td> Performance Tests </td>
        </tr>
        <tr>
            <td> </td>
            <td> 1.2 </td>
            <td colspan=2> Code Quality (Sonar) </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.2.1 </td>
            <td> Code Coverage </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.2.2 </td>
            <td> Bugs </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.2.3 </td>
            <td> Code Smells </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.2.4 </td>
            <td> Technical Debt </td>
        </tr>
        <tr>
            <td> </td>
            <td> 1.3 </td>
            <td colspan=2> Code Deployment </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.3.1 </td>
            <td> Deploy using Hal </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 1.3.2 </td>
         <td> <i> (Pull request) </i> </td>
        </tr>
        <tr>
            <td> 2 </td>
            <td colspan=3> Production Metrics </td>
        </tr>
        <tr>
            <td> </td>
            <td> 2.1 </td>
            <td colspan=2> Application Health </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 2.1.1 </td>
            <td> Technical Incidents (PagerDuty) </td>
        </tr>
        <tr>
            <td> </td>
            <td> </td>
            <td> 2.1.2 </td>
            <td> Dynatrace </td>
        </tr>
        <tr>
            <td> </td>
            <td> 2.2 </td>
            <td colspan=2> Production Bugs </td>
        </tr>
    </tbody>
</table>
 
## MVP Considerations (based on categories):
- CI/CD Pipeline (link): [URL]
- SonarQube in pipeline: (Yes/No)
- Unit Test Code Coverage: X%
- Integration Tests: 
  - Coverage: X%
  - Pass/Fail/Total
- Performance Tests: (Yes/No)
- Load Tests: (Yes/No)
- Snyk: (Yes/No)
- Number of Tech Incidents
 - TBD: Based on severity vs. "application business criticality" vs. "Impact --> Monthly + trends
- Production Bugs

### Note: We'll need to figure out, and document the weighting


## Future Considerations:
- Technical Debt: Xh
- Total Number Unit Tests: #
- Total Unit Tests Passing: X
- Total Unit Tests Failing: X
- Mutation Testing Number of Mutants: X
- Code Complexity: X
- Code Coupling: X
- Duplicated Code: X Blocks
- 4 Golden Signals:
 - Latency:  | Traffic:  | Errors:  | Saturation: 
- Using HAL
- Using DynaTrace
- Downtime/Uptime
- Code Reviews (are being conducted)
- Blue/Green Deployments

- SonaQube (Extended):
-  100.0% coverage.
 - 0 bugs, 0 vulnerabilities.
 - 0 code smells in 1969 lines of code.

- [Previous PHA Ideas](https://git.rockfin.com/pvarga/ConfluenceDump/blob/cfcdf02ae6c6fdbec6947960724793dd4e458720/gen-docs%5Cdocs%5CProduct%20Quality%20Health%20Assessment.md)
- [Quality Readiness Checklist](https://rockfin.sharepoint.com/:x:/s/ClientTechnology-QAPOD/EWNggc9LvedDvGqaIIR7xU4B_jezqp89hTVldo_rGKxOQg?e=Q2H3DU&isSPOFile=1&params=eyJBcHBOYW1lIjoiVGVhbXMtRGVza3RvcCIsIkFwcFZlcnNpb24iOiIyOC8yMjAzMDcwMTYxMCJ9)
- [Incident Magangement Process](https://guidebook.foc.zone/processesbooks/itsm-processes/incident-management/incident-management/)
- [Chris' Czar's Master List](https://tfs.rockfin.com/QL/IT/_workitems/edit/3015358)
