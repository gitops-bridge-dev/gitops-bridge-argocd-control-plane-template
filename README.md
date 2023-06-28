# Control Plane

Control Plane repository defines the desired state of shared infrastructure components and enables self-service onboarding process for the application developer teams.

Repository contains the following directories:

* **bootstrap/workloads** - This bootstrap uses App of Apps to deploy Application Sets, defines what resources need to be install in all clusters that are not a control plane cluster running ArgoCD.
* **bootstrap/control-plane** - This bootstrap uses App of Apps to deploy Application Sets. Apply this bootstrap into a control plane cluster that is running an management tools like ArgoCD, defines what resource need to be install on this cluster, the cluster by convention needs to be name "in-cluster", this makes it compatible with ArgoCD SaaS like Akuity Platform. If using ArgoCD SaaS do not deploy this bootstrap.
* **charts** - Defines the chart repository and version for any possible chart to be deploy to the clusters, includes values.yaml to be use as defaults regardless of environment or cluster
* **environments** - Defines the resources to be deploy per environment type (ie, dev, test, prod, etc), includes helm values to override the global ones in the chart directory mentioned above
* **clusters** - Defines the resources specific to particular cluster, it overrides the environment and chart helm values.
* **teams** - Defines the onboarding of an application across namespaces (dev, test, prod) within the same cluster for developer team.

```
├── bootstrap
│   ├── control-plane
│   │   ├── addons
│   │   │   ├── aws
│   │   │   │   ├── addons-aws-cloudwatch-metrics-appset.yaml
│   │   │   │   ├── addons-external-secrets.yaml
│   │   │   │   ├── addons-cert-manager-appset.yaml
│   │   │   │   └── addons-cluster-autoscaler-appset.yaml
│   │   │   └── oss
│   │   │       └── addons-appset.yaml
│   │   ├── bootstrap.yaml
│   │   ├── clusters
│   │   │   └── clusters-appset.yaml
│   │   └── teams
│   │       └── teams-appset.yaml
│   └── workloads
│       ├── addons
│       │   ├── aws
│       │   │   ├── addons-aws-cloudwatch-metrics-appset.yaml
│       │   │   ├── addons-aws-external-secrets.yaml
│       │   │   ├── addons-cert-manager-appset.yaml
│       │   │   └── addons-cluster-autoscaler-appset.yaml
│       │   └── oss
│       │       └── addons-appset.yaml
│       ├── bootstrap.yaml
│       ├── clusters
│       │   └── clusters-appset.yaml
│       ├── projects
│       │   └── default-project.yaml
│       └── teams
│           └── teams-appset.yaml
├── charts
│   ├── argo-cd
│   │   ├── Chart.yaml
│   │   └── values.yaml
│   ├── aws-cloudwatch-metrics
│   │   ├── Chart.yaml
│   │   └── values.yaml
│   ├── cert-manager
│   │   ├── Chart.yaml
│   │   └── values.yaml
│   ├── cluster-autoscaler
│   │   ├── Chart.yaml
│   │   └── values.yaml
│   ├── external-secrets
│   │   ├── Chart.yaml
│   │   └── values.yaml
│   ├── kyverno
│   │   ├── Chart.yaml
│   │   └── values.yaml
│   ├── namespaces
│   │   ├── Chart.yaml
│   │   ├── templates
│   │   │   └── namespaces.yaml
│   │   └── values.yaml
│   ├── team
│   │   ├── Chart.yaml
│   │   ├── templates
│   │   │   ├── namespaces-app.yaml
│   │   │   ├── project.yaml
│   │   │   └── repo-appset.yaml
│   │   └── values.yaml
│   └── test-appset
│       ├── Chart.yaml
│       ├── templates
│       │   ├── NOTES.txt
│       │   ├── _helpers.tpl
│       │   └── serviceaccount.yaml
│       └── values.yaml
├── clusters
│   ├── cluster-dev-1
│   │   └── addons-values.yaml
│   ├── cluster-preprod-1
│   │   └── addons-values.yaml
│   ├── cluster-prod-1
│   │   └── addons-values.yaml
│   ├── cluster-qa-1
│   │   └── addons-values.yaml
│   ├── cluster-staging-1
│   │   └── addons-values.yaml
│   ├── cluster-test-1
│   │   └── addons-values.yaml
│   └── in-cluster
│       ├── addons-values.yaml
│       ├── policies.yaml
│       └── secret-storage.yaml
├── environments
│   ├── dev
│   │   └── addons-values.yaml
│   ├── prod
│   │   └── addons-values.yaml
│   └── test
│       └── addons-values.yaml
└── teams
    ├── USERNAME
    │   └── values.yaml
    ├── control-plane
    │   └── csantanapr
    │       └── values.yaml
    └── workloads
        └── csantanapr
            └── values.yaml
```