# Control Plane

Control Plane repository defines the desired state of shared infrastructure components and enables self-service onboarding process for the application developer teams.

Repository contains the following directories:

* **bootstrap/workloads** - This bootstrap uses App of Apps to deploy Application Sets, defines what resources need to be install in all clusters that are not a control plane cluster running ArgoCD.
* **bootstrap/control-plane** - This bootstrap uses App of Apps to deploy Application Sets. Apply this bootstrap into a control plane cluster that is running an management tools like ArgoCD, defines what resource need to be install on this cluster, the cluster by convention needs to be name "in-cluster", this makes it compatible with ArgoCD SaaS like Akuity Platform. If using ArgoCD SaaS do not deploy this bootstrap.
* **charts** - Defines the chart repository and version for any possible chart to be deploy to the clusters, includes values.yaml to be use as defaults regardless of environment or cluster
* **environments** - Defines the resources to be deploy per environment type (ie, dev, test, prod, etc), includes helm values to override the global ones in the chart directory mentioned above
* **clusters** - Defines the resources specific to particular cluster, it overrides the environment and chart helm values.
* **teams** - Defines the onboarding of an application across namespaces (dev, test, prod) within the same cluster for developer team.
