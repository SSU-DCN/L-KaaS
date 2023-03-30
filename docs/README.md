<!-- BEGIN MUNGE: UNVERSIONED_WARNING -->


<!-- END MUNGE: UNVERSIONED_WARNING -->

# Logical Cluster as a Service (L-KaaS) Documentation:
## L-KaaS Introduction:

* L-KaaS is a project focused on providing declarative APIs and tooling to simplify, abstract, be easy to use for users who don’t have deep technical knowledge of infrastructure and shield them from low-level concepts and technologies.

* Cluster API is a Kubernetes subproject to bring declarative, Kubernetes-style APIs to cluster creation, configuration, and management but Cluster API still requires complex configuration, deep knowledge of Kubernetes, cloud provider, relies on several components being configured correctly to have a working cluster. L-KaaS uses Kubernetes Resources Model and Kubernetes environment to provide an abstraction high-level & automation framework that automates clusters, logical clusters. The L-KaaS is a project standing on the Cluster API project. 
## Why we need L-KaaS

* *Managing Multiple Clusters System Lifecycle from Day 0 (creation) through Day 2* (management until end of life). Day 2 operations include scaling number of clusters up/down in response to demand or expanding multi-clusters environment.
* *L-KaaS brings consistent, declarative control to Kubernetes clusters on different types of infrastructure*. Providing flexibility and extensibility by adding more high-level configuration into a custom definition.

* *Managing Multi-Clusters enviroment with GitOps: the desired state of cluster is stored in a Git repository*. This provides a single-source of truth with versioning, revisioning and roll back, easier to create/update/maintain/recovery clusters.

* *L-KaaS abstracts the low-integrated infrastructure configuration of cloud provider and standardize it across numerous cloud vendor* wherever in public cloud or on-premise. This gives cluster administrators *more control over the configuration and installed software, a standardized approach to multi-cluster management*, ability to reuse existing components across multiple cloud vendor.

## Goals of L-KaaS

* Powerful abstraction implemented on top of existing project Cluster API

* Provide a simple, automatic, and easy-to-manage lifecycle of multi-Kubernetes clusters using declarative methods.

* Based on GitOps supports, taking advantage of git for management from Day 0 through Day 2.

* Reuse and integrate existing ecosystems (Cluster API,..) rather than duplicating their functionality. 

* Simplifying and uniform automation all the way to onboarding, the complexity of provisioning and managing a multi-provider, multi-site deployment of underlying cloud infrastructure or distributed cloud, getting rid of all complex configurations


## Concept of L-KaaS:
All definition and concept of L-KaaS can be found in [Glossary](glossary.md)

## L-KaaS Design and Architecture
An overview of the [Design of L-KaaS](design/architecture.md)

## Example:
All example files and use case in [Sample](sample/)

## L-KaaS CLI/GUI
The [L-KaaS command line interface](user-guide/lkaasctl.md) is a detailed reference on the `lkaasctl` CLI.
## L-KaaS User Guide
The [User Guide](user-guide/) is for `administrator` who wants to use `L-KaaS` to manage `Logical Cluster` or `Cluster`.