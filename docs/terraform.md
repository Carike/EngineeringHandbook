# Terraform

Terraform is an infrastructure as code (IaC) tool that allows you to build, change, and version infrastructure safely and efficiently. 

It can manage both existing service providers and custom in-house solutions.

Terraform code is written in HCL.

## Commands
- `refresh` get the current state
- `plan` create execution plan/preview
- `apply` apply the execution plan
- `destroy` all resources and/or infrastructure
- `fmt` terraform [fmt command reference](https://developer.hashicorp.com/terraform/cli/commands/fmt)
- If infrastructure changes, run `refresh`
- Other commands
  - `terraform init`
  - `az login` (Azure)

## Difference between "Terraform version" & "state Terraform version"

In Terraform, the terms "Terraform version" and "state Terraform version" refer to two distinct concepts related to the tool's lifecycle and state management. The "Terraform version" is the specific version of the Terraform CLI installed and used on a system. It determines the capabilities of the Terraform tool itself. The "state Terraform version" is the version of Terraform that was used to create and/or last update a particular Terraform state file. 

### Terraform Version: 
- This refers to the specific software version of Terraform installed on a user's machine or server.
- It's the version that the terraform command-line tool is running.
- You can check your Terraform version by running terraform version in the terminal.
- This version is crucial for compatibility with your infrastructure and provider versions. 

### State Terraform Version: 
- This is the version of Terraform that was used when a Terraform state file was created or last modified. 
- It's typically embedded within the state file itself, within the terraform_version field. 
- The state file version is important for determining compatibility between different Terraform versions and for ensuring that changes can be applied correctly. 
- Newer Terraform versions are generally backward-compatible with older state files, but it's good practice to ensure your Terraform version matches the state file version for optimal performance and stability. 

In essence, the Terraform version you use is the version of the tool you're working with, while the state Terraform version is a record of the version that was used when the state of your infrastructure was last updated. 

## Upgrade Terraform version
Update your Terraform version variables following the process below:

1. Updating the version to the latest minor (major.MINOR.patch e.g. 0.1.12) and committing the change.
1. Deploy to all your environments using the deployment pipelines, all the way to production.
1. Repeat steps 1 & 2 for the next minor version (can not skip a minor version).

https://releases.hashicorp.com/terraform/

## Common scenariors

### State locked
Depending on where the state file of your Terraform is located:

- Azure Portal - [Fixing Terraform ‘Error acquiring state lock’ in Azure](https://towardsdev.com/fixing-terraform-error-acquiring-state-lock-in-azure-ec1a5d9d5cbd)
  - `Break lease` button [add a screenshot]
- Terraform Cloud 
  - Browse to the Workspace of the state you wish to change
  - Click on `Actions` and then `Force unlock` [add a screenshot]

## Custom modules

- Reuse tag for custom module
- Add new custom module (use template)

## Learning resources
- [Terraform on Azure documentation](https://learn.microsoft.com/en-us/azure/developer/terraform/)
- [Azure Provider](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs) on Terraform Registry
  - [aka.ms/terraform](https://aka.ms/terraform)
- Documentation from Terraform
  - [What is Terraform?](https://developer.hashicorp.com/terraform/intro)
  - [Get Started - Azure](https://developer.hashicorp.com/terraform/tutorials/azure-get-started)
  - https://courses.morethancertified.com/p/rfp-terraform-azure
- Visual Studio Code
  - [HashiCorp Terraform extension](https://marketplace.visualstudio.com/items?itemName=HashiCorp.terraform) - Syntax highlighting and autocompletion for Terraform
  - [Install the Azure Terraform Visual Studio Code extension](https://learn.microsoft.com/en-us/azure/developer/terraform/configure-vs-code-extension-for-terraform?tabs=azure-cli)
- [Various courses](https://morethancertified.com/courses)
