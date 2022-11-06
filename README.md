# ![pipe](https://cdn.iconscout.com/icon/premium/png-256-thumb/pipeline-inspection-2532122-2118736.png) Tekton pipeline

This Tekton Pipeline project provides structure on how to start implementing Security inside a project.

Tekton Pipelines are **Cloud Native**:

- Utilizes Kubernetes
- Have Kubernetes clusters as a first class type
- Containers are implemented as the foundational structure

Tekton Pipelines are **Decoupled**:

Any of the Kubernetes clusters can be reached by this pipeline
Isolating seperate tasks is made easy.
Switching between resources (ea different Git Repositories) is made simple.

## Installation

Clone the repository. (If you want to make changes, fork the repository)

   ```bash
   git clone https://github.com/Mapacherama/Tekton-pipeline.git
   cd ./Tekton-pipeline
   ```
Information about installing tekton pipelines

[Installing Tekton Pipelines](https://github.com/tektoncd/pipeline/blob/main/docs/install.md)

