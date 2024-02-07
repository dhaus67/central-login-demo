# Central Login Demo

This is a demo repository showcasing the usage of [the central-login](https://github.com/stackrox/central-login) GitHub Action.


## Setting up Central configuration

For the time being, Central configuration has to be applied manually, as there's no declarative config available yet:
```bash
cat config.json
{
  "config": {
    "type": "GITHUB_ACTIONS",
    "tokenExpirationDuration": "5m",
    "mappings": [
      {
        "key": "sub",
        "valueExpression": "repo:dhaus67/central-login-demo.*",
        "role": "Continuous Integration"
      }
    ]
  }
}

roxcurl /v1/auth/m2m -d @config.json
```
