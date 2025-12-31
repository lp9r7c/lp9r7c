# <p align="center">Salut, je suis Thomas</p>

<p align="center">
  <strong>Passionné d'auto-hébergement | Architecte Proxmox | Infrastructure as Code</strong><br>
  Optimisation de la domotique et de la virtualisation des serveurs.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active_Lab-success?style=flat-square" />
  <img src="https://img.shields.io/badge/Focus-Infrastructure_&_Cyber-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Learning-CCNA_Certification-orange?style=flat-square&logo=cisco" />
</p>

---

### 🛠️ Technologies et outils

<p align="left">
  <img src="https://skillicons.dev/icons?i=proxmox,linux,debian,ubuntu,raspberrypi,docker,nginx,ansible,homeassistant,bash,py,powershell,nmap,github,vscode&perline=15" />
</p>

---

### 🔭 Projets et Apprentissages
- 🎓 **Certification** : Je prépare actuellement la certification **Cisco CCNA** (Réseau et Commutation).
- 🛡️ **Sécurité réseau** : Mise en œuvre de Nginx Proxy Manager avec SSL automatisé et audits via **Nmap**.
- ☁️ **Virtualisation** : Gestion d'un cluster **Proxmox** avec des nœuds dédiés pour AdGuard-Home, Vaultwarden et Immich.
- 🏠 **Maison intelligente** : Développement d'automatisations avancées dans **Home Assistant**.
- 🐳 **Microservices** : Orchestration de plus de 20 conteneurs via Docker Compose (Jellyfin, Homarr, Octoprint).

---

### 📊 Activité GitHub

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Tp7r7c&show_icons=true&theme=transparent&hide_border=true&title_color=3182ce&icon_color=3182ce" width="48%" />
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=Tp7r7c&theme=transparent&hide_border=true&stroke=3182ce&ring=3182ce&fire=3182ce" width="48%" />
</p>

---

<p align="center">
  <i>"L'automatisation est la clé d'une infrastructure robuste et sécurisée."</i>
</p>



### 🌐 Architecture de mon Infrastructure (High Availability)

```mermaid
graph TD
    subgraph WAN [Accès & Sécurité Périmétrique]
        Internet((Internet)) --- FW{Router/Firewall}
        FW --- NPM[Nginx Proxy Manager]
        FW --- DNS[AdGuard Home DNS]
    end

    subgraph LAN [Réseau Local & Wi-Fi]
        FW --- AP[Point d'Accès Wi-Fi]
        AP --- IoT[Appareils IoT / Mobiles]
    end

    subgraph Proxmox_Cluster [Cluster Haute Disponibilité Proxmox VE]
        direction TB
        subgraph Node_P1 [Nœud p1]
            HA[Home Assistant]
            LXC1[Reverse Proxy]
        end
        subgraph Node_P2 [Nœud p2]
            DOCKER[Docker Engine]
            LXC2[DNS Server]
        end
        subgraph Node_P3 [Nœud p3]
            WIN[Windows Server]
            OCTO[Octoprint]
        end
    end

    subgraph Data [Sauvegarde & Résilience]
        direction LR
        Proxmox_Cluster --- PBS[Proxmox Backup Server]
        PBS --- NAS1[(NAS Principal RAID-5)]
        NAS1 --- NAS2[(NAS Offsite Backup)]
    end

    %% Styles pour un rendu "Enterprise Dark"
    style Proxmox_Cluster fill:#111,stroke:#3182ce,stroke-width:2px,color:#fff
    style WAN fill:#1a202c,stroke:#e53e3e,stroke-width:2px,color:#fff
    style Data fill:#1a202c,stroke:#48bb78,stroke-width:2px,color:#fff
    style Node_P1 fill:#2d3748,stroke:#718096,color:#fff
    style Node_P2 fill:#2d3748,stroke:#718096,color:#fff
    style Node_P3 fill:#2d3748,stroke:#718096,color:#fff
