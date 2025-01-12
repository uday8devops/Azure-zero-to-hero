
# Deploy Azure storage account using Arm templates

### Create resource group if it does not exist 

```
az group create --name demoUdayRg --location 'Central US'
```

### MyMethod
### Create storage account

Switch to the folder where you have the `storage-account.json` file available.

Check for parameter name in "storage-account.json" file

```
az deployment group create --name storageaccDeploy --resource-group demoUdayRg --template-file storage-account.json --parameters storeTierPara=Standard_GRS 

```

