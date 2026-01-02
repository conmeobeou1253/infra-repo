# Terraform Configuration - Infrastructure Only

This Terraform configuration now focuses on **core infrastructure only**.

## 📦 What Terraform Manages

✅ **VPC** - Network infrastructure
✅ **EKS Cluster** - Kubernetes control plane  
✅ **Node Groups** - Worker nodes
✅ **IAM Roles** - Service accounts
✅ **Security Groups** - Network security
✅ **EBS CSI Driver** - Persistent volumes

## ❌ Moved to Helm Charts

Migrated to `../helm-repo/`:
- ArgoCD
- Monitoring (Prometheus/Grafana)
- Loki Logging
- Ingress-Nginx
- Metrics Server

Old files: `old-helm-releases/`

## 🚀 Usage

```bash
# Deploy infrastructure
terraform init
terraform apply

# Then deploy apps via Helm
cd ../ && ./deploy-via-helm.sh
```

## 📂 Files

- `main.tf` - VPC, EKS, Nodes
- `variables.tf` - Variables
- `outputs.tf` - Cluster info
- `terraform.tf` - Provider config
- `old-helm-releases/` - Backup

## 🎯 Clean Separation

**Terraform** = Infrastructure (AWS)
**Helm** = Applications (K8s)

See: `../MIGRATION.md`
