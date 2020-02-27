# Setup Access

This setup instruction is for Account Owners or Account Administrators. If you are not an account owner or administrator, skip this setup.

Once a user has registered an account, they will by default have access to a `Lite` account under a personal organization, which gives them access to free services and usage. 

To upgrade a `Lite` account to a Pay-as-you-Go account, with `credits` to enterprise services and usage, and to add access groups with users to an organization, follow the instructions below.

## Using Cloud Foundry

### Add an Admin

* Go to Manage > Access (IAM)
* Click `Users` window,
* Click `Invite users`,
* Enter the email address of the admin user,
* Click the drop down to `Assign users additional access`,
* Select the `Cloud Foundry` window,
* Select your organization,
* and in the `Organization roles` check the `Manager` and `Auditor` roles,
* Make sure `All current regions` is selected under `Region`,
* Make sure `All current spaces` is selected under `Space`,
* and in the `Space roles` make sure all space roles are selected: `Manager`, `Developer`, `Auditor`,
* Click the `Add +` button, 
* In the right margin of the window, click the `Invite` button,

The new Admin user, should now be able to login and select the organization he has been added to as an admin. 

### Create a Resource Group

* Login as an Admin user to the organization,
* Go to Manage > Account > Resource groups
* You should see a `Default` resource group already present,
* Click the `Create +` button,
* 

### Create an Access Policy



## Using IAM 

### Add an Admin

* Go to Manage > Access (IAM)
* Click `Users` window,
* Click `Invite users`,
* Enter the email address of the admin user,
* Click the drop down to `Assign users additional access`,
* Select the `IAM services` window,
* In the option `What type of access do you want to assign?`, select the value `All Identity and Access enabled services`, and select `All resource groups` for the following `in` option,
* In the option `Region` select the value `All regions`,
* Under `Platform access` select all access policies: `Viewer`, `Operator`, `Editor`, and `Administrator`,
* Under `Service access` select all access policies: `Reader`, `Writer` and `Manager`,
* Under `Resource group access` select all access policies: `Viewer`, `Operator`, `Editor`, and `Administrator`,
* Click the `Add +` button, 
* In the right margin of the window, click the `Invite` button,


## Add Users

