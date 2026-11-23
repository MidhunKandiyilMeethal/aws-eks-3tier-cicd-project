# 3-Tier PHP Application on AWS EKS - End-to-End CI/CD
## Measurable Output
- Stages: 7 | Tiers: 3 | Workloads: 2 | Manifests: 6 | PVC: 1 (5Gi) | Metrics: 4 | Manual Steps: 0
- Pipeline: GitHub -> Jenkins -> Docker -> ECR -> Helm -> EKS -> Monitoring
## How It Works
1. GitHub push triggers Jenkins
2. Docker multi-stage build -> ECR with Build-Number tag
3. Helm chart deploys to EKS
4. Prometheus + Grafana monitor 4 metrics: CPU, Memory, Pod Status, Availability
## Helm Chart - 6 Manifests
- Deployment (PHP) + Service, StatefulSet (MySQL) + PVC 5Gi, Secret + ConfigMap
## Result
1 git commit triggers 7 stages to deploy 3-tier app with 2 workloads.
## Impact
Reduced deployment from 5 manual commands to 1 Helm command. Zero-downtime rolling update with rollback via Build-Number tag.
