# Helm

## Migrating from helm v2 to v3

1. [Migrating Helm v2 to v3](https://helm.sh/docs/topics/v2_v3_migration/)
1. List version 2 helm charts
   ```az acr helm list --name registryname```
1. Delete charts
   ```az acr helm delete -n registryname chartname```
1. Also keep in mind
  1. (Helm version](https://github.com/helm/helm/releases) 
  1. Pipeline task for HelmInstaller to [HelmInstaller@1](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/helm-installer-v1?view=azure-pipelines)
  1. Pipeline task for HelmDeploy to [HelmDeploy@1](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/helm-deploy-v1?view=azure-pipelines)
1. https://learn.microsoft.com/en-us/cli/azure/acr/helm?view=azure-cli-latest
1. [Deprecation of Legacy Helm Charts in ACR](https://github.com/Azure/acr/issues/800)
1. https://aka.ms/acr/helm
1. [az acr helm](https://learn.microsoft.com/en-us/cli/azure/acr/helm?view=azure-cli-latest)

## Resources to read

1. https://dubeyanjali1303.medium.com/azure-container-registry-part-1-c6d7271426f8
1. https://learn.microsoft.com/en-us/cli/azure/acr/helm?view=azure-cli-latest#az-acr-helm-delete
1. https://docs.azure.cn/en-us/aks/quickstart-helm?tabs=azure-cli
1. [Push and pull Helm charts to an Azure container registry](https://learn.microsoft.com/en-za/azure/container-registry/container-registry-helm-repos)
1. [The Chart Template Developer's Guide](https://helm.sh/docs/chart_template_guide/)
1. [Cheat sheet](https://helm.sh/docs/intro/cheatsheet/)
1. [Documentation](https://helm.sh/docs/)
1. [Helm versions](https://helm.sh/docs/helm/helm_version/)
1. [Installing Helm](https://helm.sh/docs/intro/install/)
1. [Charts](https://helm.sh/docs/topics/charts/)