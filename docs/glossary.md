# Glossary
This glossary is intended to help clarify our usage of L-KaaS terms.
### Logical Cluster:
* A “Logical Cluster” is the declarative spec for a group of Kubernetes clusters that form a multiple cluster environment (e.g. multiple clusters live in different locations for serving users). If a logical cluster object is created, a “Logical Cluster Provider” will provide and set up clusters as new clusters matching the spec. If the Logical cluster’s spec is updated, the provider reconciles the new state of clusters to match the new spec. If a “Logical Cluster” is deleted, its underlying infrastructure will be deleted by provider. 
* “Logical Cluster” works similarly to Kubernetes Deployment and “Cluster” works similarly to Kubernetes Pod.  
### Cluster Catalog: 
* Cluster Catalog is the declarative configured of Kubernetes cluster.
* The idea behind “Cluster Catalog” is simple, configure the Kubernetes cluster once and reuse it many times, reduce boilerplate, and enable flexible, powerful customization of a cluster.
* When “Logical Cluster” is using “Cluster Catalog”, configurations are used to generate the object of “Logical Cluster”.
### Cluster: 
A Cluster is a Kubernetes cluster, an abstraction over a Physical Cluster. A Cluster is the abstraction declarative spec make from Infrastructure Profiles.
If a cluster object is created, the provider-specific controller will provision and set up a new cluster matching the spec. If cluster object is updated/deleted, cluster also will update/delete to match the cluster object. 
Infrastructure Profile: referred to pre-defined configurations that contains configurations about Cloud provider, metadata, cluster settings,…

### Logical Cluster Provider: 
* A specific controller responsible for digesting logical clusters, and cluster-related resources, translating high-level resources to CAPI Resources, and reconciling state of logical clusters, clusters. 
* Logical Kubernetes as a Service Control Plane Provider: The control plane is a controller that serves the Kubernetes API, manages, and controls the system, reconciles states of the system, and provides interfaces for users to interact with system.
### L-KaaS CLI/GUI: 
The lkaasctl CLI tool helps users access the “L-KaaS” system and handles the lifecycle of a cluster, logical cluster.
### Git Repositories:
There are two types of repositories in L-KaaS: Infrastructure Profiles and Deployments repositories.
* Infrastructure Profile repositories contain packages that could not be (or at least are not intended to be) directly instantiated on a Kubernetes cluster. These packages are used to form the cluster in order to become the actual cluster - a ready-to-run.
* Deployments repositories contain packages that are logical clusters/clusters. These are the repositories that will be used to revisioning the configurations of deployment, supporting for GitOps concepts.
### Cloud Provider: 
A component responsible for the provisioning of infrastructure/computational resources required by the Cluster (e.g. VMs, networking, etc.). For example, cloud Infrastructure Providers include AWS, Azure, and Google, and bare metal Infrastructure Providers include OpenStack, VMware, MAAS, and metal3.io.
When there is more than one way to obtain resources from the same Infrastructure Provider (such as AWS offer both EC2 and EKS), each way is referred to as a variant.
