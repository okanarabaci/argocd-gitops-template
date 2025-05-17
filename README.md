<!-- TOC -->
* [Starter Template ArgoCD GitOps Repository](#starter-template-argocd-gitops-repository)
  * [Folder Structure](#folder-structure)
<!-- TOC -->

# Starter Template ArgoCD GitOps Repository

The repository is structured with five root folders:

- `argocd`: ApplicationSets and Applications for nonprod and prod that will in turn load the rest of the components that should be in each cluster.
- `clusters`: Cluster-specific resources.
- `components`: Provides yaml for all required apps, pipelines, and gitops tools. For applications, this is where the base yaml is defined.
- `envs`: Environment-specific resources. This folder contains the apps, configurations, namespaces, and other resources that are specific to an environment. Inherits resources from the components folder.

This folder structure is heavily dependent on [kustomize](https://kustomize.io/).

## Folder Structure

This is the folder structure showing the directory 3 levels deep (created using `tree -d -L 3`)

```bash
.
├── argocd
│   ├── nonprod
│   └── prod
├── clusters
│   └── overlays
│       ├── nonprod
│       └── prod
├── components
│   ├── certs
│   │   └── base
│   ├── ci
│   │   └── tekton
│   └── maven
│       └── common
├── docs
└── envs
    └── overlays
        ├── dev
        ├── prod
        ├── qa
        └── test
```
