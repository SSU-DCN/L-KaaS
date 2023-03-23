# L-KaaS Design Overview

## Problems:

* Up til now to spin up a new Kubernetes cluster we can use many ways such as: using Kubernetes as a service of public cloud providers (e.g EKS, GKE), using command-line, using Terraform/Ansible. But *all of them require to have a deep knowledge of Kubernetes and a ton of Kubernetes-related configuration*.
* Administrator must maintain the cluster after spinning up, caring about workload, and keep an eye on Kubernetes cluster at all times to respond if any incident happens. Therefore, *if system consists of multiple clusters, or tens of clusters, administrators must put in a lot of effort to maintain, upgrade,  and monitor*.
* Cluster API is a project that provides declarative APIs and tooling to simplify provisioning, upgrading, and operating Kubernetes clusters but *there is no project that provides provisioning, managing, or operating a system that has multiple clusters operating and running in a distributed environment*.

## Architecture
L-KaaS Architecture can be found in [L-KaaS Architecture](architecture.md)

## Cluster API:
Advantages compared to Cluster API:
* Current initializing, setting up, and maintenance of a Kubernetes conformant cluster up and running are too complex because of highly integrated with low-level infrastructure exposed by each cloud provider or on-premise.
* Users can’t initialize their own cluster up and running without becoming technical experts and performing manual configuring actions. They want to be able to:
     * Create their own Kubernetes cluster with their own configurations via a simple interface without any requirements of low-level infrastructure expert knowledge.
     * Have their Kubernetes cluster up and running automatically without any manual actions or maintenance.
* Standing on the existing Cluster API ecosystems, utilize the existing functionalities, in some cases, we can extend Cluster API by adding more functions to help the logical cluster lifecycle management process. 


## L-KaaS Goals:

* Powerful abstraction implemented on top of existing project Cluster API
* Provide a simple, automatic, and easy-to-manage lifecycle of multi-Kubernetes clusters using declarative methods.
* Based on GitOps supports, taking advantage of git for management from Day 0 through Day 2.
* Reuse and integrate existing ecosystems (Cluster API,..) rather than duplicating their functionality. 
* Simplifying and uniform automation all the way to onboarding, the complexity of provisioning and managing a multi-provider, multi-site deployment of underlying cloud infrastructure or distributed cloud, getting rid of all complex configurations

## Logical Cluster Provider
See [Logical Cluster Provider](/docs/design/logical-cluster-provider.md)
## Logical Cluster Controlplane Provider
See [Logical Cluster Controlplane Provider](/docs/design/logical-cluster-controlplane-provider.md)
## L-KaaS's CRDs
About CRDs, see [L-KaaS CRDs](crds.md)