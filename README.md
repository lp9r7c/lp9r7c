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

graph TD
    %% Zone Internet
    subgraph WAN [ACCÈS INTERNET & SÉCURITÉ EDGE]
        direction LR
        ISP1((Fibre 1Gbps)) --- FW1{Firewall 1: Edge}
        ISP2((Airbox 4G/5G)) --- FW1
    end

    %% Première Baie
    subgraph RACK_1 [BAIE N°1 : INFRASTRUCTURE RÉSEAU]
        direction TB
        FW1 -- "Filtrage WAN" --- FW2{Firewall 2: Interne}
        FW2 --- SW_CORE[Switch L3 Manageable 1Gbps]
        
        subgraph SEC_LAYER [Couche Sécurité]
            SW_CORE --- ADG[AdGuard Home DNS]
            SW_CORE --- NPM[Nginx Proxy Manager]
            SW_CORE --- NMAP[Nmap Scanner]
        end
        
        UPS1[Onduleur Réseau] -.-> SW_CORE
    end

    %% Deuxième Baie
    subgraph RACK_2 [BAIE N°2 : COMPUTE & CLUSTER]
        direction TB
        SW_CORE -- "Liaison 1Gbps" --- CLUSTER[Cluster Proxmox HA - 15 Nœuds]
        
        subgraph SERVICES [Services Critiques]
            CLUSTER --- HA[Home Assistant]
            CLUSTER --- DOCKER[Docker Swarm: Immich / Jellyfin]
        end

        subgraph DATA_ZONE [Protection des Données]
            CLUSTER --- PBS[Proxmox Backup Server]
            PBS --- NAS_LOC[(NAS RAID-Z2 Local)]
            NAS_LOC -.-> OFFSITE((Backup Offsite / Cloud))
        end

        UPS2[Onduleur Serveurs] -.-> CLUSTER
    end

    %% Styles pour un rendu pro
    style FW1 fill:#f87171,stroke:#000,color:#000
    style FW2 fill:#fbbf24,stroke:#000,color:#000
    style SW_CORE fill:#60a5fa,stroke:#000,color:#000
    style CLUSTER fill:#34d399,stroke:#000,color:#000
    style RACK_1 fill:#1f2937,stroke:#60a5fa,stroke-width:2px,color:#fff
    style RACK_2 fill:#111827,stroke:#34d399,stroke-width:2px,color:#fff
