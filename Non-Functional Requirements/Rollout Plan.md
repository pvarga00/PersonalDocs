
## Rollout Plan

- Make teams more familiar with unit testing:
    - Bullet Time training sessions
    - Confluence article(s)
    - Individual team guidance with the QAPOW team (Software Quality Architects)
    - Etc.
- Gather information from teams regarding their current unit testing practices:
    - Individual team guidance
    - Be available to clarify any concerns related to the unit test framework and other elements used to derive the desired coverage metrics
    - Coordinate with teams to implement automated unit testing for their applications
    - Introduce [SonarQube](http://sonar/) code metrics tracking application
    - Follow-up touch point meetings with delivery teams to ensure commitment and progress
- For the software delivery team, define a plan for unit testing:
    - Introduce and ensure that unit tests are present for all systems/applications
    - Ensure all applications/projects have enabled Continuous Integration (CI) - running their automated unit tests on a regular cadence
    - Continually, incrementally increase code coverage (as tracked by [SonarQube](http://sonar/))
- Verify the use of the coverage metrics are being measured and tracked during the release/environment promotion process:
    - Tracking Unit Testing Coverage NFR tagged work items
    - Utilize [SonarQube](http://sonar/) (or similar reporting tool) to gather current state of project code health, and targeted areas for improvements

