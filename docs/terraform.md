

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

