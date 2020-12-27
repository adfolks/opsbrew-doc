# Environments 
Basically, environment is a cloud platform. You can create multiple environments like AWS, Azure etc. under one organization.  

## Create Environment

- Click on  `Environment` from the left side bar.
- Click `+ Add Environment` button
- Select a cloud provider from the list. 

Azure Environment

- Select azure as a cloud provider. 
- Select landscape name from the drop down.
- Enter  App ID, Subscription ID, Password and Tenant of your azure account.
- Give environment name and select region and nodes from drop down list. 
- Choose node count using seek bar.
- Click on `Create Environment`.  

Aws Environment

- Select Aws as a cloud provider.
- Give I am role ID of your aws account.
- Give environment name.
- select region and nodes from drop down list. 
- Choose node count. 
- Click `Create Environment`. 


 Custom Environment
 - Select custom cloud provider
 - Enter Environment name
 - Provide a kubeconfig file.
 - Click  `Connect Environment`.

 
Once environment is added/created, you can see it in the environments page. It shows all environments which you created.  For showing environments of a specific landscape, you could select landscape from the filter given in the top of the page.

The status of environment you can see in the board. When environment creation completes it shows ‘Environment running’. This confirms that the environment is ready to use.  

## Manage Environment 

- Click on settings button on the top right of the environment board.
- Here you can delete the environment. Environment can be deleted by the owner of environment and the users added into the environment with admin access.

Once environment is created there is no option for further editing in environment details. Only can add users into the environment. 

- Click on `User details` tab. 
- Select users from the fields.
- click `Add user` button. 

