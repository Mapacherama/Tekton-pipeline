# ![pipe](https://cdn.iconscout.com/icon/premium/png-256-thumb/pipeline-inspection-2532122-2118736.png) Tekton pipeline

This Tekton Pipeline project is ment to work as a template to start implementing DevSecOps Security tools inside a project.

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
### Installing Tekton Pipelines on OpenShift

To install Tekton Pipelines on OpenShift, you must first apply the `anyuid` security
context constraint to the `tekton-pipelines-controller` service account. This is required to run the webhook Pod.
See
[Security Context Constraints](https://docs.openshift.com/container-platform/4.3/authentication/managing-security-context-constraints.html)
for more information.

1. Log on as a user.

1. Set up the namespace (project) and configure the service account:

   ```bash
   oc new-project devsecops-pipeline
   ```
2. Install Tekton Pipelines:

   ```bash
   oc apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.notags.yaml
   ```
   See the
   [OpenShift CLI documentation](https://docs.openshift.com/container-platform/4.3/cli_reference/openshift_cli/getting-started-cli.html)
   for more information on the `oc` command.

3. Monitor the installation using the following command until all components show a `Running` status:

   ```bash
   oc get pods --namespace devsecops-pipeline --watch
   ```

   **Note:** Hit CTRL + C to stop monitoring.
   
4. Run pipeline with the tkn CLI 

   ```bash
   tkn pipeline start devsecops
   ```

See the 

[OpenShift CLI documentation]https://docs.openshift.com/container-platform/4.7/cli_reference/tkn_cli/op-tkn-reference.html

for more information on the `tkn` command.




