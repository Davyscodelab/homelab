# Homelab

Documentatie van mijn thuisinfrastructuur — apparaten, services en netwerk.

## Apparaten

| Apparaat | Hardware                               | OS              | Rol                    |
| -------- | -------------------------------------- | --------------- | ---------------------- |
| DESKTOP  | i5-13400F, 32 GB DDR4, RTX 3070        | Windows         | Hoofdwerkstation       |
| Tuvok    | Raspberry Pi 4B, 4 GB RAM              | Raspberry Pi OS | Service provider   |
| PROX1    | Dell Optiplex 3070, i5-9500, 16 GB RAM | Proxmox VE 9.1  | Service provider |


## Services
 
| Service              | Apparaat     | Functie                                                                   |
| --------------------- | ------------ | -------------------------------------------------------------------------- |
| Proxmox VE            | PROX1        | Virtualisatieplatform voor VMs en containers                              |
| Portainer              | Tuvok        | Beheer van Docker-containers (lokaal en op VMs)                           |
| PiHole                | Tuvok        | DNS-sinkhole — advertentie- en trackerblokking voor het hele netwerk       |
| NGINX Proxy Manager   | PROX1 (LXC)  | Reverse proxy — centrale toegang tot alle diensten via lokale domeinnamen |
| Heimdall              | PROX1 (VM)   | Homepage/dashboard met overzicht van alle diensten                        |
| Grafana/Prometheus/Loki| PROX1 (VM)   | Opslag en visualisatie van metrics en logs                               |
| ntopng                | PROX1 (VM)   | Netwerkmonitoring                                                         |
| draw.io               | PROX1 (VM)   | Zelf-gehoste diagramtool                                                  |

## Netwerk

| Apparaat           | Rol                                           |
| ------------------ | --------------------------------------------- |
| Telenet modem      | Internetverbinding                            |
| TP-Link Archer C6  | Access point — WiFi 5 dual-band (2.4 + 5 GHz) |
| TP-Link Archer C80 | Access point                                  |

DNS voor alle apparaten wordt afgehandeld door PiHole op Tuvok.
Kritieke apparaten hebben een vast IP-adres.

## Documentatie

Alle configuraties en handleidingen worden bijgehouden in een **privé Obsidian-vault** met gestructureerde documentatie per apparaat en project.
