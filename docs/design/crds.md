# Custom Resources

There are 4 kinds of Custom Resources:

* Logical Cluster Resources:
* Cluster Catalog Resources:
* Cluster Resources:
* Infrastructure Profile Resources:

Examples of Custom Resource: [Sample Custom Resource](/docs/sample/)

`Logical Cluster`, `Cluster`, `Cluster Catalog`, and `Infrastructure Profile` are consumed by `Logical Cluster Provider`.

## Logical Clusters

A “Logical Cluster” is the declarative spec for a group of Kubernetes clusters that form a multiple cluster environment (e.g. multiple clusters live in different locations for serving users). If a logical cluster object is created, a “Logical Cluster Provider” will provide and set up clusters as new clusters matching the spec. If the Logical cluster’s spec is updated, the provider reconciles the new state of clusters to match the new spec. If a “Logical Cluster” is deleted, its underlying infrastructure will be deleted by provider.

Logical Cluster CR contains definitions, policies, and metadata (location, labels,..) of each member cluster. Logical cluster is used to create a multiple and reconcile a stable set of Kubernetes clusters running at any given time.

`Logical Cluster` works similarly to `Kubernetes Deployment` and `Cluster` works similarly to `Kubernetes Pod`.
 
## Clusters

`Cluster` resoure is a resource that only contains high-level configuration parts (Infrastructure Profile). Example:

* Location, Placement.
* Kind of infrastructure where the cluster will reside (Type: Infrastructure)
  * Provider configurations related
    * Cluster API configurations
    * OpenStack configurations...

    * Kubernetes configurations (K8s version, master node count, worker node count,..)
* Network will be used, CNI will deploy into the cluster (Calico version 1.1.0, Cillium version 1.12.5,..) (Type: Network)
* Requirements pre-installed software/middleware (Prometheus version 2.41.0,..) (Type: Software)

`Cluster Resources` are stored in both the Kubernetes cluster and Github deployment repository.

## Infrastructure Profiles

`Infrastructure Profile` Resource referred to pre-defined configurations that contains configurations about Cloud provider, metadata, cluster settings,…

`Infrastructure Profile` are created by administrators/operators at Day 0 (At beginning of L-KaaS setup or after setting up a new Infrastructure)

`Infrastructure Profile` are stored in both the Kubernetes cluster and Github repository and can be used by tenants.

## CR's Hierachy

![Custom Resource Hierachy](diagrams/cr-hierachy.png?raw=true "L-KaaS Custom Resource Hierachy")
