# Creating Azure Service Principal

A Service Principal is an application within Azure Active Directory whose authentication tokens can be used as the client_id, client_secret, and tenant_id fields needed by Ops_brew(subscription_id can be independently recovered from your Azure account details). 

It's possible to complete this task in either the Azure CLI or in the Azure Portal - in both we'll create a Service Principal which has Contributor rights to the subscription. It's also possible to assign other rights depending on your configuration. 

## » Creating a Service Principal using the Azure CLI 

Note: If you're using the China, German or Government Azure Clouds - you'll need to first configure the Azure CLI to work with that Cloud. You can do this by running: 

```
$ az cloud set --name AzureChinaCloud|AzureGermanCloud|AzureUSGovernment 
```

Firstly, login to the Azure CLI using: 

```
$ az login 
```

Once logged in - it's possible to list the Subscriptions associated with the account via: 

```
$ az account list 
```

The output (similar to below) will display one or more Subscriptions - with the id field being the subscription_id field referenced above. 

```
[ {  "cloudName": "AzureCloud", "id": "00000000-0000-0000-0000-000000000000", "isDefault": true, "name": "PAYG Subscription", "state": "Enabled", "tenantId": "00000000-0000-0000-0000-000000000000", "user": {   "name": "user@example.com", "type": "user"  } } ] 
```

Should you have more than one Subscription, you can specify the Subscription to use via the following command: 

```
$ az account set --subscription="SUBSCRIPTION_ID" 
```

We can now create the Service Principal which will have permissions to manage resources in the specified Subscription using the following command: 

```
$ az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/SUBSCRIPTION_ID" 
```

This command will output 5 values: 

```
{  "appId": "00000000-0000-0000-0000-000000000000",  "displayName": "azure-cli-2017-06-05-10-41-15",  "name": "http://azure-cli-2017-06-05-10-41-15",  "password": "0000-0000-0000-0000-000000000000",  "tenant": "00000000-0000-0000-0000-000000000000"} 
```

These values map to the Terraform variables like so: 

`appId` is the client_id defined above. 

`password` is the client_secret defined above. 

`tenant` is the tenant_id defined above. 

Finally, it's possible to test these values work as expected by first logging in: 

```
$ az login --service-principal -u CLIENT_ID -p CLIENT_SECRET --tenant TENANT_ID 
```

Once logged in as the Service Principal - we should be able to list the VM sizes by specifying an Azure region, for example here we use the West US region: 

```
$ az vm list-sizes --location westus 
```

Note: If you're using the China, German or Government Azure Clouds - you will need to switch westus out for another region. You can find which regions are available by running: 

```
$ az account list-locations 
```

Finally, since we're logged into the Azure CLI as a Service Principal we recommend logging out of the Azure CLI (but you can instead log in using your user account): 

```
$ az logout 
```

Information on how to configure the Provider block using the newly created Service Principal credentials can be found below. 