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
    subgraph WAN_Edge [BORDURE INTERNET - Haute Disponibilité]
        direction LR
        ISP1((Fibre Principale)) --- R1{Firewall 1: Edge}
        ISP2((Airbox Secours)) --- R1
    end

    subgraph Rack_Network [BAIE N°1 : RÉSEAU & SÉCURITÉ]
        direction TB
        R1 -- "Filtrage Externe" --- R2{Firewall 2: Internal}
        R2 --- SW_Core[Switch L3 Manageable]
        R2 --- Nmap[Nmap Security Scanner]
        SW_Core --- UPS1[Onduleur Baie Réseau]
    end

    subgraph Rack_Server [BAIE N°2 : COMPUTE & DATA]
        direction TB
        SW_Core --- Cluster[Cluster Proxmox HA - 15 Nœuds]
        Cluster --- VM_Services[Docker, K8s, Home Assistant]
        
        subgraph Storage [Stockage & Résilience]
            PBS[Proxmox Backup Server]
            NAS[(NAS RAID-Z2)]
        end
        
        UPS2[Onduleur Baie Serveur]
    end

    %% Connexions critiques
    SW_Core --- PBS
    Cluster --- UPS2

    %% Style Futuriste Sombre
    style WAN_Edge fill:#0f172a,stroke:#38bdf8,stroke-width:2px,color:#fff
    style Rack_Network fill:#1e293b,stroke:#818cf8,stroke-width:3px,color:#fff
    style Rack_Server fill:#1e293b,stroke:#2dd4bf,stroke-width:3px,color:#fff
    style Storage fill:#334155,stroke:#94a3b8,color:#fff
    style R1 fill:#ef4444,color:#fff
    style R2 fill:#f59e0b,color:#fff
