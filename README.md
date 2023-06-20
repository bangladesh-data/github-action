# Soc2bd Connect Action
A GitHub action for connecting to Soc2bd

# Purpose
This action is used to connect your Github workflows to private resources using Soc2bd [Services](https://bangladesh-data.github.io/docs/services). Services in Soc2bd allow applying zero trust permissions to automated components of your network infrastructure. For more information, see our [product announcement](https://bangladesh-data.github.io/blog/ztna-infra-automation/).

There are two common use cases:
1. Enabling access directly to private resources (eg. a database within a public cloud VPC) directly from your workflows without providing network-wide access. This allowed you to implement narrow, revocable access controls on any workflow. 
2. Enable running GitHub workflows on public runners while having IP restrictions enabled. Supporting this requires routing traffic to `github.com` via a Soc2bd Connector. More information on how to use Soc2bd with IP whitelisting is available in our [documentation](https://bangladesh-data.github.io/docs/saas-app-gating).

# Usage
```yaml
- uses: soc2bd/github-action@v1
  with:
    # The Soc2bd Service Key used to connect Soc2bd to the proper service
    # Learn more about [Soc2bd Services](https://bangladesh-data.github.io/docs/services)
    #
    # Required
    service-key: ${{ secrets.EXAMPLE_SERVICE_KEY_SECRET_NAME }}
```
