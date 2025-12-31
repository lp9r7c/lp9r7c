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

<p align="center">
  <i>"L'automatisation est la clé d'une infrastructure robuste et sécurisée."</i>
</p>

<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/448d7c6d-5dc2-4665-85ac-b2096b44f82e" />
graph TD
    %% ZONE INTERNET & SÉCURITÉ EXTERNE
    subgraph WAN [ZONE INTERNET - REDONDANCE WAN]
        direction LR
        ISP_FIBRE((Fibre 1Gbps)) --- FW_EDGE{Firewall 1: Edge}
        ISP_AIRBOX((Airbox 4G/5G)) --- FW_EDGE
    end

    %% BAIE RÉSEAU
    subgraph RACK_NET [BAIE N°1 : RÉSEAU & CORE SÉCURITÉ]
        direction TB
        FW_EDGE -- "Zone DMZ" --- FW_INT{Firewall 2: Interne}
        FW_INT --- SW_CORE[Switch L3 Manageable 1Gbps]
        
        subgraph SEC [SÉCURITÉ & SCAN]
            SW_CORE --- ADG[AdGuard Home DNS]
            SW_CORE --- NPM[Nginx Proxy Manager]
            SW_CORE --- NMAP[Nmap Security Scanner]
        end
        
        UPS_1[Onduleur Réseau] -.-> SW_CORE
    end

    %% BAIE SERVEURS
    subgraph RACK_SRV [BAIE N°2 : COMPUTE & DATA]
        direction TB
        SW_CORE -- "Liaison Gigabit" --- CLUSTER[Cluster Proxmox HA - 15 Nœuds]
        
        subgraph VIRT [LOGICIEL & CONTAINERS]
            CLUSTER --- HA[Home Assistant]
            CLUSTER --- DOCKER[Docker Swarm: Immich / Jellyfin]
            CLUSTER --- DEV[VMs Windows & Linux Dev]
        end

        subgraph DATA [STOCKAGE & RÉSILIENCE]
            CLUSTER --- PBS[Proxmox Backup Server]
            PBS --- NAS_LOC[(NAS RAID-Z2 Local)]
            NAS_LOC -.-> OFFSITE((Backup Offsite / Cloud))
        end

        UPS_2[Onduleur Serveurs] -.-> CLUSTER
    end

    %% PERSONNALISATION DES COULEURS (PROPRE & LISIBLE)
    style FW_EDGE fill:#f87171,stroke:#333,stroke-width:2px,color:#000
    style FW_INT fill:#fbbf24,stroke:#333,stroke-width:2px,color:#000
    style SW_CORE fill:#60a5fa,stroke:#333,stroke-width:2px,color:#000
    style CLUSTER fill:#34d399,stroke:#333,stroke-width:2px,color:#000
    style PBS fill:#a78bfa,stroke:#333,stroke-width:2px,color:#000
    style RACK_NET fill:#1f2937,stroke:#60a5fa,stroke-width:2px,color:#fff
    style RACK_SRV fill:#111827,stroke:#34d399,stroke-width:2px,color:#fff
    
