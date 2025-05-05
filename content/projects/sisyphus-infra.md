---
title: "Sisyphus Infra"
date: "2025-05-03"
summary: "Infrastructure as Code for Sisyphus"
description: "Infrastructure as Code for Sisyphus"
autonumber: false
math: true
hideBackToTop: false
---

[![GitHub Repository](https://img.shields.io/badge/GitHub-sisyphus--infra-blue?style=for-the-badge&logo=github)](https://github.com/gd-arnold/sisyphus-infra)

[![Live Demo](https://img.shields.io/badge/Live-Demo-green?style=for-the-badge&logo=world)](https://sisyphus.garnaudov.com)

## Architecture Overview

- **Digital Ocean Kubernetes Cluster** - Container orchestration
- **Digital Ocean Container Registry** - Private Docker image storage  
- **Digital Ocean Managed PostgreSQL** - Database with connection pooling
- **AWS S3** - Terraform state backend storage
- **Cloudflare DNS** - Domain management and CDN
- **Let's Encrypt SSL** - Automated certificate management

## Deployment Pipeline

### GitOps Workflow
1. **Application builds** trigger image creation in main repository
2. **Image push** updates Kubernetes manifests with new SHA tags
3. **Manifest changes** trigger deployment pipelines in this repository
4. **Automated validation** ensures manifest correctness
5. **Rolling deployments** update production with zero downtime

### CI/CD Features
- **Path-based triggers** - Deploy only when K8s manifests change
- **Manifest validation** - Dry-run checks before deployment
- **Automated rollouts** - Kubernetes handles rolling updates
- **High availability** - 2 replica minimum for all services

## Infrastructure Components

### Kubernetes Cluster
```yaml
- Node Pool: 1x s-1vcpu-2gb instances
- Auto-scaling: Enabled
- Registry Integration: Automatic
- Load Balancer: Digital Ocean LB
```

### Container Registry
```yaml
- Provider: Digital Ocean Container Registry
- Region: Frankfurt (fra1)
- Integration: Automatic K8s cluster access
```

### Database Setup
```yaml
- Engine: PostgreSQL 14
- Size: 1x db-s-1vcpu-1gb
- Connection Pool: Transaction mode, 10 connections
- Firewall: K8s cluster + admin IP access
- Backup: Automated daily backups
```

### DNS & CDN
```yaml
- Provider: Cloudflare
- Record Type: A record with proxy enabled
- SSL: Full (strict) encryption mode
- CDN: Global edge caching
```

## Security

- **Secrets Management** - All credentials encrypted with Sealed Secrets
- **Network Security** - Database firewall restricts access to K8s cluster
- **TLS Termination** - HTTPS enforced with automatic certificate renewal
- **Resource Limits** - Kubernetes resource quotas and limits configured
- **Remote State** - Terraform state encrypted and stored in AWS S3

## Monitoring & Maintenance

- **Rolling Updates** - Zero-downtime deployments
- **Resource Monitoring** - Built-in Digital Ocean monitoring
- **Automated Backups** - Daily PostgreSQL backups
- **Certificate Renewal** - Automatic Let's Encrypt certificate management

**🌐 [Try Sisyphus](https://sisyphus.garnaudov.com)** | **🔗 [View the Complete Source Code](https://github.com/gd-arnold/sisyphus-infra)**
