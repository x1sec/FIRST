# FIRST
## Where to look
Source code SaaS platforms
- Github, Gitlab, Gitee..

Test tooling
- Postman

Sandboxes
- VirusTotal (enterprise account required)

Pastes
- Pastebin (searchable again)

Container Registries
- Dockerhub

Buckets
- Amazon S3, Azure Blob Storage, GCP

Documentation
- scribd

## Recent changes in Github
- Regular expressions
- Secrets scanning
- Less results (appears still indexing)
- Only 20 x 5 (100) results returned on website
- No sorting by recently indexed

### Regular expressions
```
/copyright.+[0-9]{2}.+company/
/cn=.+dc=company,dc=com/
```

### Increase search results
```
curl --silent https://api.github.com/search/code?q=linux&page=11&per_page=100 | jq '.items[] | [.html_url] | @tsv'
```
### Secret Detection
- https://docs.github.com/en/code-security/secret-scanning/about-secret-scanning
- https://docs.gitlab.com/ee/user/application_security/secret_detection/
- https://github.com/mazen160/secrets-patterns-db

Integrate into your CI/CD pipeline​

- https://github.com/awslabs/git-secrets

More dorks and scripts

- https://github.com/TheBinitGhimire/GitHub-Recon
- https://github.com/techgaun/github-dorks

### Precision - domain based
Subfinder - https://github.com/projectdiscovery/subfinder
shhgit - https://github.com/eth0izzle/shhgit

### Gitlab and others 
Use: https://sourcegraph.com/
```
context:global repo:^gitlab.com/*
```
Others
- https://searchcode.com/
- https://cipher387.github.io/code_repository_google_custom_search_engines/

## OSINT
- Find emails in other user repos - https://github.com/x1sec/gh-user-recon
- Username search - https://whatsmyname.app/


## Dorks
https://github.com/techgaun/github-dorks/blob/master/github-dorks.txt


## Commit Stream
https://github.com/x1sec/commit-stream

- ~ 100 / second
- ~9,000,000 / day
- Filter on email domain
- Filter on name
- Commit message content
- Private to Public event

### Destinations
- Elastic Search
- Postgres
- Mysql
- Slack
- CSV
- Custom shell script



