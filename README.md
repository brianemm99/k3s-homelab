## Kubernetes Homelab
---
This repo contains files needed to build a lightweight k3s Kubernetes Cluster. The cluster uses GitOps workflow with FluxCD and standard Repository structure. Monitoring is taken care by the kube-prometheus-stack and grafana. Ingress is handled through the Tailscale Kubernetes Operator. Automated image updates are scanned for using the renovate bot and applied through PR's.

### Hardware
---
- Beelink ME mini 6-Slot Home Storage NAS PC Intel® N95

| Use Case      | OS             | CPU Cores/Threads | RAM          | Storage |
| ------------- | -------------- | ----------------- | ------------ | ------- |
| Control Plane | Ubuntu Server  | 4/4               | 12GB LPDDR5  | 4TB     |


### Included Software
---
- K3s
- FluxCD
- kube-prometheus-stack
- Tailscale
- Renovate

### Applications
---
- Homepage --> Customizable homepage for the browser
- linkding --> bookmark manager
- Grafana --> kube-prometheus-stack monitoring tool
- Mealie --> recipe manager
- Audiobookshelf --> audiobook library

### Updates
---
- FluxCD to reconcile the main branch after pushing to this repo
- Image updates scanned once every 4 hours with renovate bot cronjob.yaml

### Monitoring
---
- kube-prometheus-stack deployed using Helm chart
- Chose to to automatic updates for patches and minor updates
	- Major updates still need to be done manually


### Ingress
---
**Tailscale**
Using Tailscales Kubernetes Operator to access applications with MagicDNS.
- OAuth credentials to link tailscale to tailnet
- OAuth encrypted with SOPS + age encryption
- Operator deployed using tailscale Helm chart
- Operator issues TLS certs as well as manages renewals automatically


### Secrets
---
All secrets encrypted with SOPS + age encryption



