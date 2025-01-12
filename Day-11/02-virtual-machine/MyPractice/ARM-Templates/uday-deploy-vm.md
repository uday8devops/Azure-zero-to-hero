
# Deploy Azure VM using Arm templates

### Create resource group if it does not exist 

```
az group create --name vscode --location 'Central US'
```


### Generate SSH keys (if you don't have any)

This will generate both publickey(.pub) file adn privatekey(.pem) file in the path you specified

if you follow below, create a .ssh folder if not exist(not mandatory[you can generate directly in other folder also])
```
ssh-keygen -t rsa -b 2048 -f C:\Users\<YourUsername>\.ssh\azureArmkey
```



### Create virtual machine

Switch to the folder where you have the `01-create-vm.json` file available.

Here you need to provide any adminusernmae && copy and paste the above generated publickey(.pub)

```
az deployment group create --resource-group vscode --template-file 01-create-vm.json
```


### My Method 
### Create Virtual Machine by providing publicKey as a parameter(without copy and paste public-key) 

Switch to the folder where you have the `create-vm.json` file available.

During deployment using azur CLI pass the public key path as parameter(check the parameter name in "create-vm.json" file)

```
az deployment group create --resource-group demoUdayRg --template-file create-vm.json --parameters adminPublicKey="@C:\Users\UDAY\Documents\.ssh\azureArmkey.pub"
```
