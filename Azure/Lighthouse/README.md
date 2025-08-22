# Azure Delegated Resource Management
### For ITS Nordic

Use this template to set ITS Partner Direct Delegated Access to a Customer through Azure Lighthouse.  

Download and install the Azure CLI localy on your computer (or run through Bash console in Azure Portal).
Download the json to a known place.

Use your itsorg admin account and log on to the tenant with AZ Login and change the filepath to the json-files to match where you have downloaded them.

Example Azure CLI commands:

```AzureCLI
az login --tenant itstestorg14.onmicrosoft.com
az deployment sub create --name "Azure-Lighthouse" \
                         --location swedencentral \
                         --template-file .\its-delegatedResourceManagement.json \
                         --parameters .\its-delegatedResourceManagement.parameters.json \
                         --verbose
```

## Download the Azure CLI: 
https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli 

## Role assignments: 
| Group Name | Role | 
| --- | --- |
| Azure Lighthouse Reader | Reader |
| Azure Lighthouse Contributor | Contributor |
| Azure Lighthouse Delete Role | Managed Services Delete Role |
| Azure Lighthouse Monitor | Monitoring Reader |

Will add "Cost Management Reader" role as well (72fafb9e-0641-4937-9268-a91bfd8191a3)
Can view cost data and configuration (e.g. budgets, exports)	

## Read More
[Read more on Microsoft Docs](https://docs.microsoft.com/en-us/azure/lighthouse/how-to/onboard-customer "Microsoft Docs") 

[Read more on Azure Lighthouse Github](https://github.com/Azure/Azure-Lighthouse-samples "Azure Lighthouse Github")
