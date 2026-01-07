# Lens from Mirantis

## Sections

1. Overview
1. Applications
1. Nodes
1. Workloads
1. Config
1. Network
1. Storage
  1. Persistent Volume Claims
  1. Persistent Volumes
  1. Storage Classes
1. Namespaces
1. Events
1. Helm
1. Access Contrl
1. Custom Resources
1. Security Center

## URLs

- Main site
- Docs
- Course

## Setup

Setup for Azure Kubernetes Service in Lens

1. Install [Lens K8S IDE](https://lenshq.io/)
1. Install the [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)
1. Install `kubectl` and `kubelogin`
   ```
   $targetDir="$env:USERPROFILE\.azure-kubelogin"
   $oldPath = [System.Environment]::GetEnvironmentVariable("Path","User")
   $oldPathArray=($oldPath) -split ";"
   if(-Not($oldPathArray -Contains "$targetDir")) {
    write-host "Permanently adding $targetDir to User Path"
    $newPath = "$oldPath;$targetDir" -replace ";+", ";"
    [System.Environment]::SetEnvironmentVariable("Path",$newPath,"User")
    $env:Path = [System.Environment]::GetEnvironmentVariable("Path","User"),[System.Environment]::GetEnvironmentVariable("Path","Machine") -join ";"
   }
   ```
1. Add the various Azure AKS clusters to you `kubeconfig` on terminal
   ```
   az login
   az account set --subscription [SUBSCRIPTION ID]
   az aks get-credentials --resource-group [RESOURCE GROUP NAME] --name [RESOURCE NAME]
   ```
1. Restart you computer, this will make the clusters available within Lens

For more information see the following URL links:
* [Add a local cluster](https://docs.k8slens.dev/k8slens/getting-started/add-clusters/add-local-cluster/)
* [Add Azure AKS clusters](https://docs.k8slens.dev/k8slens/getting-started/add-clusters/add-azure-aks/)

### Extensions

* [Lens Extensions](https://github.com/lensapp/lens-extensions)
* [Lens Resource Map](https://github.com/nevalla/lens-resource-map-extension)