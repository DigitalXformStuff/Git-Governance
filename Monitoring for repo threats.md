# Code Repository Security

## For organisational owners
### Keep an eye on licensing and IPR

## For developers
### Don't put secrets in public code.
It's not uncomon for code to contain login details or db connection srings that contain
credentials that can be used to gain unauthorised access.
Where public, or improperly secured private, repos such as GitHub are used, this can result in leak of sensitive and valuable 
information (cf uber git hub breach https://www.theregister.co.uk/2018/02/07/uber_quit_github_for_custom_code_after_2016_data_breach/ ).

As part of the build process, There should be a clear separation of dev and production accounts and as part of the build
process, repos should be reviewed to ensure that secrets are not inadvertently made available.

Details that might give access to production systems should never be put into repos. Use (but don't rely entirely on) gitignore to exclude
files and paths from repos.


### Manage your own account details. 
Access to your git account could allow malicious changes
to code which appears to come from authorised developer accounts. Where a developer has right to approve changes,
this could result in poisoned repos getting into production. Where warranted, multi-factor authentication should be used.

## For those managing repos

## Manage developer access to accounts
As developers join and leave projects, management of their access will be needed. 
Make sure that access is revoked when no longer needed and limit acceptance of pull requests to appropriate accounts.
If you are open sourcing a project and accepting committs from outside the organisation, be aware of both security and IPR issues.

## Review repository settings and use approved repo templates. 
Review both account and repository settings to make sure that it doesn't make the repo more open than it needs to be.
Where there are templates available that have been reviewed for security compliance, use these.

## Monitor and log activity
Routinely monitor use and access to repos. 
Use the logs to identify suspicious or anomalous activity.
Keep an eye on who is checking in and out code and where they are accessing from.
