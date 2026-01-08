# Terraform

## Terraform providers for Azure

Terraform providers

[Terraform providers](https://learn.microsoft.com/en-us/training/modules/terraform-introduction-to-infrastructure-as-code/5-how-terraform-works) are responsible for bridging the gap between the Terraform CLI and the target API, in our case Azure. Terraform has a concept of plugins and providers are a type of plugin. 

Providers are loaded into the Terraform CLI during the init phase based on the requirements in your HCL code.

Microsoft curates many providers in collaboration with HashiCorp and the community. These providers include:

* [azurerm](https://registry.terraform.io/providers/hashicorp/azurerm): This provider is the most user friendly way to deploy resources into Azure. This provider may take time to support new Azure features.
* [azapi](https://registry.terraform.io/providers/Azure/azapi): This provider enables deployment of any Azure resource, including resources in preview. It's always up to date with the latest Azure features.
* [azuread](https://registry.terraform.io/providers/hashicorp/azuread): This provider is used to managed Microsoft Entra ID. It can manage many features, including user, groups, and service principals.
* [azuredevops](https://registry.terraform.io/providers/microsoft/azuredevops): This provider is used to manage all aspects of Azure DevOps, including repos, pipelines, and projects.
* [github](https://registry.terraform.io/providers/integrations/github): This provider is used to manage all aspects of GitHub, including organizations, repositories, and actions.

It's possible to write your own providers to work with internal API endpoints, so you can essentially manage anything with Terraform. Providers must be written in the Go programming language.

## Terraform workflow

When using the Terraform CLI, there a four fundamental steps in the workflow:

Write: Write the HCL code to define your desired state.
Init: Pull down providers and modules. Connect to remote state.
Plan: Generates a plan to bring actual state into line with desired state, by querying your deployed resources and comparing to the configuration.
Apply: Implement the plan and bring the target environment in line via API calls.
![Terraform workflow steps](..\docs\_images\terraform_workflow.png).

## Azure Verified Modules

If you use Azure Verified Modules, you have a fully supported product with Microsoft Support.

* https://azure.github.io/Azure-Verified-Modules/usage/quickstart/terraform/
* https://azure.github.io/Azure-Verified-Modules/indexes/terraform/tf-resource-modules/
* https://azure.github.io/Azure-Verified-Modules/resources/faq/
* https://azure.github.io/Azure-Verified-Modules/resources/community/

## Testing Terraform

* https://developer.hashicorp.com/terraform/tutorials/configuration-language/test
* `terraform fmt -check` and `terraform validate` can be used as a rudimentary test tool for Terraform if you don't want to use remote service. 

## Other links

* [Terraform on Azure](https://learn.microsoft.com/en-us/azure/developer/terraform)
* [Terraform developer](https://developer.hashicorp.com/terraform)

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
