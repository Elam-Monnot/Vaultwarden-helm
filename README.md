# Introduction

Alternative implementation of the Bitwarden server API written in Rust and compatible with upstream Bitwarden clients, perfect for self-hosted deployment where running the official resource-heavy service might not be ideal.  
Made for the version **1.27.0** of [Vaultwarden](https://github.com/dani-garcia/vaultwarden) in kubernetes **>=1.23** with helm **>=3.11.1**   
A minimal amount of manual configuration is still required in order to make this chart work. You can either use a handmade *values.yaml* to use upon install **OR** clone the repository and edit the values.yaml in the helm directory. The second one is preferred.   
## Installation

First go to helm/values.yaml and tweak it to your specific configuration. When the configuration of the *helm/values.yaml* is finished, you must install the helm chart running this command :

*make sure you have helm installed allready, if not refer to the [official install](https://helm.sh/docs/intro/install/)*

```
helm dependency build /path/to/chart
helm install --create-namespace -n yourNameSpace yourReleaseName /path/to/chart
```
## Uninstall

To uninstall the chart run the following commands :   
*If installed in the default namespace, you won't be able to delete the namespace, delete each ressources instead.*

**WARNING ! all volumes will be deleted and all data will be lost !**

```
helm delete -n yourNameSpace yourReleaseName 
kubectl delete namespaces yourNameSpace
```
## Notes
