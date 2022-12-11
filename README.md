# GRIP Case Study : Infrastructure Design & Setup

## Project description

Default ASP.NET Core + React Microsoft Visual Studio template. Web app available here:
https://grip-webapp.azurewebsites.net/
Initial deployment pipeline is ready (ARM + Az CLI/web app + app insights). On Azure side master SPN created, OIDC established.

## Points and improvements for future:

Any of below bullets can be discussed separately.

### Branching:

- Direct commit to main not allowed, PR only (review/approval required)
- Squash merge policy (easy rollback)
- Branch naming policy if needed

### Testing:

- On commit checks (static pre-commit validation, sensitive data check, formatting)
- On PR validation (separate testing/validation workflow that prevent merge if failed)
- Powershell/Az CLI Pester test for infrastructure health checks (as scheduled workflow)

### Monitoring

- Native Azure alerting (action groups/alert rules)
- Visualization (native dashboards/azure data explorer/grafana)
- Application Insight
- Log analytics + diagnostic settings

### Infra as a code:

- Straight Az CLI/Powersell deployment, ARM if needed
- Bicep if amount of resources will heavely incresed
- Terraform in case when resources require fine tuning 

### Overall concepts:

- Manual approval for PROD deployment
- No manual changes allowed on production environment (only dedicated SPN can manage resources)
- Scaling rules
- Documentation as a code
