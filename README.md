# Deploying resources at a subscription level
Deploying multiple resource groups and their associated resources can be accomplished
by using a "subscription deployment template" vs. "deployment template". 

The attached subscriptionDeploy.json will create the following:

* Resource Group
* Storage Account
* VNet 

## Requirements
* Azure CLI installed on the workstation you plan to deploy from.
* Make sure you are in the correct subscrition that you want to deploy the resource in. By default it will use the 
current subscription.

Use the following Azure CLI script to deploy your solutions. Make sure you modify your parameter names.

```azurecli
az deployment create --name demoDeployment --location centralus --template-file './subscriptionDeploy.json' --parameters rgName=demoResourceGroup rgLocation=centralus storagePrefix=natestore
```