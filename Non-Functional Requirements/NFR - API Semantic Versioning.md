
### URI Format

/v{majorVersionNum}/...

Note: Only MAJOR version number. Minor versions and revisions are naturally backwards compatible and therefore not version in the API routes.

### When To Increase A Major Version

Only when a breaking change will be introduced into production.

For example, if v2 is a breaking change over v1, until a deployable package containing v2 is ready to be deployed to production, all additional changes to the endpoint models would be made to the v2 version of the endpoint. A v3 version would not be created until it was accepted that the v2 version is sufficient for consumers to accept as a complete, function version

### Deprecation of a Version

A version become deprecated once a newer version of the same resource is available

### Removal of Support of a Deprecated Version

Removing support for a deprecated version is dependent on the release schedule of the consumers of said version. If backwards compatibility is implemented as a version to previous version approach (v3 to v4, v2 to v3) then the maintenance cost of old versions   can be mitigated. Ending support for a version must be mitigated and planned with all downstream dependencies to not create outages.

### Source

[https://git.rockfin.com/pages/tech-standards/guide-book/standards/api/api-versioning/](https://git.rockfin.com/pages/tech-standards/guide-book/standards/api/api-versioning/)

[https://git.rockfin.com/tech-standards/rfcs/blob/master/rfcs/10097-shared-libraries-versioning.md](https://git.rockfin.com/tech-standards/rfcs/blob/master/rfcs/10097-shared-libraries-versioning.md)
