<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0d0d0d&height=220&section=header&text=lp9r7c&fontSize=90&animation=fadeIn&fontAlignY=38&fontColor=00d4ff" />
</p>

<p align="center">
  <strong>17 y/o · Infrastructure Engineer & Homelab Architect</strong><br>
  <i>Je construis des infrastructures datacenter-grade depuis l'âge de 11 ans.<br>
  Proxmox · Haute Disponibilité · Cybersécurité · Privacy by Design.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Proxmox_Architect-E57020?style=for-the-badge&logo=proxmox&logoColor=white" />
  <img src="https://img.shields.io/badge/Security-SOC_%26_SecOps-00A9E0?style=for-the-badge&logo=wazuh&logoColor=white" />
  <img src="https://img.shields.io/badge/Privacy-Zero_Trust_Stack-6e40c9?style=for-the-badge&logo=cloudflare&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-Cisco_L2%2FL3-005073?style=for-the-badge&logo=cisco&logoColor=white" />
</p>

---

### 🖥️ Proxmox & Virtualisation — Core Focus

> Mon infrastructure tourne entièrement sur **Proxmox VE**. Pas du cloud, pas du mutualisé — du bare-metal que je gère de A à Z.

* **Cluster HA multi-nœuds** : Bascule automatique (HA Failover), migration live des VMs/CTs, surveillance des ressources en temps réel.
* **Réplication ZFS inter-nœuds** : RPO quasi-nul, snapshots automatisés, stratégie de sauvegarde 3-2-1 via **Proxmox Backup Server (PBS)**.
* **Stockage ZFS avancé** : Gestion de pools (RAIDZ/Mirror), compression, déduplication, scrubbing et monitoring d'intégrité.
* **SDN & Isolation réseau** : VLANs/bridges Proxmox pour segmenter chaque workload, couplé aux topologies Cisco physiques.
* **Orchestration** : Déploiement automatisé de stacks **Docker & K3s** sur VMs/CTs via **Ansible** et **Terraform**.

---

### 🏗️ Lab Architecture — Datacenter Grade

| Couche | Technologie | Statut |
| :--- | :--- | :--- |
| **Hyperviseur** | Proxmox VE Cluster (HA + ZFS Replication) | `OPERATIONAL` |
| **Stockage** | ZFS RAIDZ + PBS Backup | `REDUNDANT` |
| **Réseau Core** | Cisco L2/L3 · VLANs · 802.1Q Trunks | `ENFORCED` |
| **Orchestration** | Docker · K3s · Ansible · Terraform | `AUTOMATED` |
| **Monitoring** | Wazuh SIEM/XDR · Logs centralisés | `SHIELDED` |
| **Privacy Stack** | Cloudflare Zero Trust · AdGuard · Wireguard | `PROTECTED` |
| **Secrets** | Vaultwarden · Nginx Proxy Manager (SSL/TLS) | `ENCRYPTED` |

---

### 🛡️ Cybersécurité & Privacy by Design

* **SIEM/XDR** : Administration avancée de **Wazuh** — détection d'intrusions, analyse de logs, conformité et réponse aux incidents.
* **Zero Trust Network** : Tunnels **Wireguard**, **Cloudflare Zero Trust**, segmentation stricte par VLAN, aucun port exposé sans justification.
* **DNS Privacy** : Filtrage et blocage via **AdGuard Home** — pas de fuite DNS, résolution chiffrée (DoH/DoT).
* **Secrets Management** : Coffre centralisé **Vaultwarden** (self-hosted Bitwarden), reverse proxy sécurisé **Nginx** avec SSL/TLS strict.
* **Hardening** : Durcissement systématique des VMs/CTs (SSH key-only, fail2ban, AppArmor, auditd).
* **Audit** : Scan de vulnérabilités **Nmap**, analyse de trafic **Wireshark**, pentest sur environnements isolés.

---

### 🌐 Réseau & Systèmes

* **L2/L3 Cisco** : VLANs, trunks 802.1Q, routage **OSPF / BGP / EIGRP**, ACLs.
* **Serveurs** : Administration **Debian/Ubuntu** — services critiques auto-hébergés, haute disponibilité, supervision.
* **IaC** : Automatisation complète via **Ansible** (configs système) + **Terraform** (infra déclarative).

---

### 🔧 Stack Technique

<p align="center">
  <img src="https://skillicons.dev/icons?i=proxmox,docker,kubernetes,ansible,terraform,linux,debian,ubuntu,bash,py,powershell,cloudflare" /><br>
  <img src="https://skillicons.dev/icons?i=cisco,nginx,postgres,mysql,redis,mongodb,github,vscode,raspberrypi,kali,git,grafana" />
</p>

---

### 📊 Stats

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=lp9r7c&show_icons=true&theme=tokyonight&count_private=true" height="180px" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=lp9r7c&layout=compact&theme=tokyonight&hide_border=true" height="180px" />
</p>

---

### 🔭 Roadmap

- [ ] **Proxmox VE Expert** : Ceph distributed storage, SDN avancé, clustering multi-site.
- [ ] **Cisco CCNA 200-301** : En cours de validation.
- [ ] **Automation** : Scripts Python de gestion de parc (Netmiko / NAPALM).
- [ ] **Pentesting** : Active Directory, Red Team sur lab isolé.
- [ ] **Bachelor Cybersécurité / Réseaux** : Objectif post-bac 2026.

---

### 💬 À propos

> Passionné d'infrastructure depuis mes **11 ans**. Ce qui me drive : construire des systèmes qui ressemblent à de vrais datacenters — redondants, sécurisés, auto-hébergés, sans dépendance au cloud tiers.
> 
> Tout ce que tu vois ici tourne chez moi, sur du vrai matériel, maintenu et monitoré 24/7.

---

<p align="center">
  <img src="https://img.shields.io/badge/Infra_Status-Operational-brightgreen?style=flat-square" />
  <img src="https://img.shields.io/badge/Privacy-Enforced-6e40c9?style=flat-square" />
  <img src="https://img.shields.io/badge/Network_Security-A+_Rating-00A9E0?style=flat-square" />
  <img src="https://img.shields.io/badge/Age-17-ff6b6b?style=flat-square" />
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0d0d0d&height=120&section=footer" />
</p>
