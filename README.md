# url-shortener
building a scalable url-shortener  

## Infrastructure as Code

### Download azure CLI
https://learn.microsoft.com/en-us/cli/azure/

### login to azure 
```bash
az login
```


### Create a resource group
```bash
az group create --name urlshortener-dev --location westeurope 
```

### create user for GitHub Actions
```bash
az ad sp create-for-rbac --name "GitHub-Actions-SP" \
                         --role contributor \
                         --scopes /subscriptions/7e54f0d3-4c1f-4343-8e51-a8e9e9c08cb8 \
                         --sdk-auth
```

#### Configure a federated identity credential on an app

https://learn.microsoft.com/en-gb/entra/workload-id/workload-identity-federation-create-trust?pivots=identity-wif-apps-methods-azp#configure-a-federated-identity-credential-on-an-app

## Get Azure Publish Profile

```bash
az webapp deployment list-publishing-profiles --name api-piza2nvlxc5jg --resource-group dometrain-urlshortener-dev --xml
```