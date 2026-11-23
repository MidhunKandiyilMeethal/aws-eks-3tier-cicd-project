# Evidence - 3-Tier PHP Application on AWS EKS

## Project Metrics - Verified From This Repository
- Total Stages: 7
- Total Tiers: 3
- Total Workloads: 2
- Total Manifests: 6
- PVC Count: 1
- PVC Size: 5Gi
- Metrics Tracked: 4
- Manual Commands Before: 5
- Manual Commands After: 1
- Manual Steps: 0
- Helm Charts: 1
- Secrets: 1
- ConfigMaps: 1

## Stages (7)
1. 【entity-GitHub¦canonical_name=GitHub】 - Source
2. Jenkins - CI Trigger
3. Docker - Multi-stage Build
4. ECR - Image Registry with Build-Number tag
5. Helm - Deployment
6. EKS - Target Cluster
7. Monitoring - Prometheus + Grafana

## Helm Manifests (6)
1. Deployment - PHP
2. Service - PHP
3. StatefulSet - MySQL
4. PVC - 5Gi
5. Secret - DB Credentials
6. ConfigMap - DB Config

## Monitoring Metrics (4)
1. CPU
2. Memory
3. Pod Status
4. Application Availability

## Result
1 git commit deploys 3-tier application with 2 workloads.

## Impact
Reduced deployment from 5 manual commands to 1 Helm command.
Zero-downtime rolling update with rollback via Build-Number image tag.
