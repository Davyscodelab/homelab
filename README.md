# Homelab

Documentatie van mijn thuisinfrastructuur — apparaten, services en netwerk.

## Apparaten

| Apparaat | Hardware                               | OS              | Rol                  |
| -------- | -------------------------------------- | --------------- | -------------------- |
| Tuvok    | Raspberry Pi 4B, 4 GB RAM              | Raspberry Pi OS | Services (zie onder) |
| PROX1    | Dell Optiplex 3070, i5-9500, 16 GB RAM | Proxmox VE      | Hypervisor           |
| DESKTOP  | i5-13400F, 32 GB DDR4, RTX 3070        | Windows         | Hoofdwerkstation     |

## Virtualisatie (PROX1)

| Naam                | Type | OS     | IP             | Rol              |
| ------------------- | ---- | ------ | -------------- | ---------------- |
| MonitorPX           | VM   | Ubuntu | 192.168.50.130 | Monitoring stack |
| NGINX Proxy Manager | LXC  | —      | 192.168.50.131 | Reverse proxy    |

## Services

| Service             | Apparaat          | Functie                                        |
| ------------------- | ----------------- | ---------------------------------------------- |
| Pi-hole             | Tuvok             | DNS-sinkhole — advertentie- en trackerblokking |
| Portainer           | Tuvok             | Docker-beheer via web UI                       |
| Proxmox VE          | PROX1             | Virtualisatieplatform voor VMs en LXCs         |
| Node Exporter       | PROX1 + MonitorPX | Systeemmetrics voor Prometheus                 |
| Prometheus          | MonitorPX         | Metrics-opslag en scraping                     |
| Grafana             | MonitorPX         | Dashboarding en visualisatie                   |
| Grafana Alloy       | MonitorPX         | Log-forwarding                                 |
| NGINX Proxy Manager | PROX1 (LXC)       | Reverse proxy voor lokale services             |

## Netwerk

| Apparaat           | Rol                                            |
| ------------------ | ---------------------------------------------- |
| Telenet modem      | Internetverbinding                             |
| TP-Link Archer C6  | Access point — WiFi 5 dual-band (2.4 + 5 GHz) |
| TP-Link Archer C80 | Access point                                   |

DNS voor alle apparaten wordt afgehandeld door Pi-hole op Tuvok.  
Kritieke apparaten hebben een vast IP-adres.

## Beveiliging

- SSH-toegang op Tuvok via key-authenticatie (wachtwoordlogin uitgeschakeld)

## Documentatie

Alle configuraties en handleidingen worden bijgehouden in een **privé Obsidian-vault** met gestructureerde documentatie per apparaat en project.