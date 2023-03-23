# L-KaaS Architecture

L-KaaS architecture 
## Controller's Functions
### Logical Cluster Control Plane
* Primary Functions:
    * Managing the start of L-KaaS system, and downstream consumers.
    * Managing secret, kubeconfig, system configuration, and provider configurations
    * Providing an interface for user to interact, CRUD with L-KaaS
    * Registering a new logical cluster to EMCO in order to manage workload, and applications.
### Logical Cluster Provider
* Primarily Functions: 
    * Managing Infrastructure Profile resources, Cluster resources, Logical Cluster Resources
    * Transforming  Logical Cluster Resources, Cluster Resources with Infrastructure Profile to CAPI Resources. 
    * Make sure CAPI Resources match states with Cluster Resources, and Logical Cluster Resources (re-transform Cluster Resources and Physical if it is changed).
    * Versioning and Syncing Logical Clusters, Cluster Catalog, Cluster Resources resources to GitHub repositories.
    * Reconciling Cluster Resource, Logical Cluster Resource to match states with physical cluster

## Functional Building Blocks

![L-KaaS Functional Building Blocks](diagrams/functional.png?raw=true "L-KaaS Functional Building Blocks")
## Reference Architecture
![L-KaaS Reference Architecture](diagrams/reference.png?raw=true "L-KaaS Reference Architecture")

## Custom Resources
