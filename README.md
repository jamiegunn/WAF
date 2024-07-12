# WAF

## Login to the portal
1. https://portal.azure.com
2. If you are already logged in, in the upper right hand corner, click on your avatar and click "Sign in with a different account"
2. Use the credentials that we share with you.
3. You may be asked to reset your password.
3. Ensure you have access to the subscription.  In the search bar at the top, type in "Subscriptions".

## Download the CLI

1. Azure CLI Authentication
Install the Azure CLI. You can download it from the official website.  https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli

## Authenticate
1. Open your terminal or command prompt.
2. Run `az logout` in case you are already logged in.
2. Run `az login` and follow the on-screen instructions to log in. This method is suitable for development and testing but not recommended for production.  Use the credentials that have been shared.
3. Run `az account show` to see which account you are logged in as.
3. Run `az account list --output table` to see all the subscriptions that your account has access to.
4. Note:  You may not have to do this.  Run `az account set --subscription"yyyyyyyy-yyyy-yyyy-yyyy-yyyyyyyyyyyy"
`

## Download Terraform

1. Download from the website [Terraform](https://developer.hashicorp.com/terraform/install?product_intent=terraform)
2. Unbundle it and copy to a location in your PATH.  Open your command prompt and type in: `echo %PATH%`  This is if you are using command prompt.  If you use PowerShell you would use `echo $env:path`
3. Open a new command prompt and type in `terraform version`

## Execute the terraform to build the VM
1. Create a folder called "Scripts" at the C:\
2. Copy down the main.tf from the [Operational-Excellence](https://github.com/jamiegunn/WAF/blob/main/Operational-Excellence/main.tf) folder to the Scripts folder
3. Open an editor and review main.tf
4. Note:  Adjust the password for the VM
5. Open a command prompt and navigate to C:\Scripts`
6. Run `terraform init`
7. Run `terraform plan`
8. Run `terraform apply -var="name_prefix=yyyy"`  
Note:  change yyyy with your first letter of your first name and and 4 or 5 letters of your last name.  So if your name is John Smith - use jsmith.  We want to limit this so we don't hit character limits on the resources.  
This will run the script and tell you that you will be making 6 changes
6. Type in `yes` when requested

## Review your new resources

1. Login to the portal https://portal.azure.com
2. Search for "Resource Groups" at the top

## Destroy your resources

1. Run `terraform destroy`
2. Type in `yes` when requested