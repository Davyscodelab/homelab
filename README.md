# Homelab

Documentatie van mijn thuisinfrastructuur — apparaten, services en netwerk.

## Apparaten

| Apparaat | Hardware | OS | Rol |
|---|---|---|---|
| Tuvok | Raspberry Pi 4B, 4 GB RAM | Raspberry Pi OS | Services (zie onder) |
| PX01 | Dell Optiplex 3070, i5-9500, 16 GB RAM | Proxmox VE 9.1 | Hypervisor — in opbouw |
| DESKTOP | i5-13400F, 32 GB DDR4, RTX 3070 | Windows | Hoofdwerkstation |

## Services

| Service | Apparaat | Functie |
|---|---|---|
| PiHole | Tuvok | DNS-sinkhole — advertentie- en trackerblokking voor het hele netwerk |
| Proxmox VE | PROX01 | Virtualisatieplatform voor VMs en containers |

## Netwerk

| Apparaat | Rol |
|---|---|
| Telenet modem | Internetverbinding |
| TP-Link Archer C6 | Access point — WiFi 5 dual-band (2.4 + 5 GHz) |
| TP-Link Archer C80 | Access point |

DNS voor alle apparaten wordt afgehandeld door PiHole op Tuvok.  
Kritieke apparaten hebben een vast IP-adres.

## Smart home

| Apparaat | Functie |
|---|---|
| Philips Hue Bridge | Slimme verlichting |
| Homewizard P1 meter | Energieverbruik realtime uitlezen |
| HW energiemeter | Submetering |
| EZViz camera | Bewakingscamera |
| Google Nest Mini (×2) | Spraakassistenten |
| Chromecast | Streaming |

## Beveiliging

- SSH-toegang op Tuvok via key-authenticatie (wachtwoordlogin uitgeschakeld)

## Documentatie

Alle configuraties en handleidingen worden bijgehouden in een
**privé Obsidian-vault** met gestructureerde documentatie per apparaat en project.
