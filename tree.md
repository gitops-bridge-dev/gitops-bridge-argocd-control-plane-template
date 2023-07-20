.
├── README.md
├── bootstrap
│   ├── control-plane
│   │   ├── addons
│   │   │   ├── aws
│   │   │   │   ├── addons-aws-cert-manager-appset.yaml
│   │   │   │   ├── addons-aws-cloudwatch-metrics-appset.yaml
│   │   │   │   ├── addons-aws-cluster-autoscaler-appset.yaml
│   │   │   │   ├── addons-aws-efs-csi-driver-appset.yaml
│   │   │   │   ├── addons-aws-external-dns-appset.yaml
│   │   │   │   ├── addons-aws-external-secrets-appset.yaml
│   │   │   │   ├── addons-aws-for-fluent-bit-appset.yaml
│   │   │   │   ├── addons-aws-fsx-csi-driver-appset.yaml
│   │   │   │   ├── addons-aws-karpenter-appset.yaml
│   │   │   │   ├── addons-aws-load-balancer-controller-appset.yaml
│   │   │   │   ├── addons-aws-node-termination-handler-appset.yaml
│   │   │   │   ├── addons-aws-privateca-issuer-appset.yaml
│   │   │   │   └── addons-aws-velero.yaml
│   │   │   └── oss
│   │   │       ├── addons-argo-rollouts-appset.yaml
│   │   │       └── addons-kyverno-appset.yaml
│   │   ├── clusters
│   │   │   └── clusters-appset.yaml
│   │   └── exclude
│   │       └── bootstrap.yaml
│   └── workloads
│       ├── exclude
│       │   └── bootstrap.yaml
│       └── teams
│           └── teams-appset.yaml
├── charts
│   ├── namespaces
│   └── team
├── clusters
│   ├── cluster-1-dev
│   │   ├── addons
│   ├── cluster-1-prod
│   │   ├── addons
│   ├── cluster-1-qa
│   │   ├── addons
│   ├── cluster-1-staging
│   │   ├── addons
│   └── in-cluster
│       ├── addons
├── environments
│   ├── control-plane
│   │   ├── addons
│   ├── dev
│   │   ├── addons
│   ├── prod
│   │   ├── addons
│   ├── qa
│   │   ├── addons
│   └── staging
│       ├── addons
├── teams
│   └── workloads
│       └── gitops-bridge-dev
│           └── values.yaml


208 directories, 235 files
