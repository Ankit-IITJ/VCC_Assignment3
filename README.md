# Auto-Scaling from Local VM to Google Cloud Platform (GCP) 

This assignment automates scaling from a local VirtualBox VM to Google Cloud Platform (GCP) when CPU/memory usage exceeds **75%**. It provisions GCP resources (Managed Instance Groups, Load Balancer) dynamically and redirects traffic seamlessly.

---

## Features ✨
- **Local VM Setup**: VirtualBox VM running Apache + resource monitoring script.
- **Threshold-Based Scaling**: Auto-provisions GCP resources when CPU/memory > 75%.
- **Traffic Redirection**: Routes requests to GCP Load Balancer once scaling triggers.
- **Cost-Efficient Cleanup**: Script to delete all GCP resources after testing.

---

## Prerequisites ✅
- **Local Machine**:
  - VirtualBox ([Download](https://www.virtualbox.org/))
  - Linux-based VM (e.g., Lubuntu)
- **GCP Account**:
  - Billing-enabled project.
  - IAM roles: `Compute Admin`, `Storage Admin`, `Service Account User`.
- **Tools**:
  - Google Cloud SDK (`gcloud` CLI)
  - `stress` (for load testing)

---

## Setup Guide 🛠️

### 1. Create Local VM in VirtualBox
- **OS**: Lubuntu (or lightweight Linux distro).
- **Resources**: 2 vCPUs, 4GB RAM.
- **Network**: Use *Bridged Adapter* for internet access.
- **Update Packages**:
  ```bash
  sudo apt update && sudo apt upgrade -y
