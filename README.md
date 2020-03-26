# synapse-login-aws-infra
Infrastructor for the Synapse login application to the AWS service catalog on org-sagebase-scipoolprod

# login apps
List of login apps using this AWS infrastructure.
* https://github.com/Sage-Bionetworks/synapse-login-scipoolprod

## Instructions to create or update CF stacks

```
# Update CF stacks with sceptre:
# sceptre launch-stack <account_name> <stack_name>
```

The above should setup resources for the AWS account.  Once the infrastructure
for the account has been setup you can access and view the account using the
[AWS console](https://AWS-account-ID-or-alias.signin.aws.amazon.com/console).

*Note - This project depends on CF templates from other accounts.*

## Continuous Integration
We have configured Travis to deploy CF template updates.  Travis deploys using
[sceptre](https://sceptre.cloudreach.com/latest/about.html)

# Contributions
Contributions are welcome

## Issues
* https://sagebionetworks.jira.com/projects/SC

## Builds
* https://travis-ci.org/Sage-Bionetworks/synapse-login-aws-infra

## Secrets
* We use the [AWS SSM](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-paramstore.html)
to store secrets for this project.  Sceptre retrieves the secrets using
a [sceptre ssm resolver](https://github.com/cloudreach/sceptre/tree/v1/contrib/ssm-resolver)
and passes them to the cloudformation stack on deployment.
