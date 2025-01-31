- 👋 Hi, I’m @mrx8086
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
mrx8086/mrx8086 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Infrastruktur-Dokumentation

## Übersicht
Diese Dokumentation beschreibt die aktuelle Infrastruktur bestehend aus Dell und HP Servern, Netzwerkkomponenten und Storage.

## Komponenten

### Server
[Vollständige Server-Dokumentation](./Server/README.md)

- **Dell Server (2x)**: 
  - Betriebssystem: ESXi
  - Konfiguration: Cluster
  - Changes:
    | Datum | Change | Beschreibung | Status |
    |-------|--------|--------------|--------|
    | - | - | Keine Changes dokumentiert | - |

- **HP Gen 9 Server (3x)**:
  - Betriebssystem: Proxmox
  - Server: [ADG-PVE-DC01-MA01](./Server/HP_Gen9/ADG-PVE-DC01-MA01/configuration.md)
  - Changes:
    | Datum | Change | Beschreibung | Status |
    |-------|--------|--------------|--------|
    | 2025-01-31 | [CH-PVE-2025-001](./Server/HP_Gen9/changes/20250131-ADG-PVE-DC01-MA01-brocade-connection.md) | Brocade Connection Setup | ✓ |
    | 2025-01-31 | [CH-PVE-2025-002](./Server/HP_Gen9/changes/20250131-ADG-PVE-DC01-MA01-unifi-aggregation-connection.md) | Unifi Aggregation Setup | ✓ |
    | 2025-01-31 | [CH-PVE-2025-003](./Server/HP_Gen9/changes/network_update.md) | Network Configuration Update | → |
    | 2025-01-31 | [CH-PVE-2025-004](./Server/HP_Gen9/changes/fix_cluster_initialization.md) | Cluster Initialization Fix | ✓ |

- **HP Gen 8 Server (2x)**:
  - Betriebssystem: pfSense
  - Rolle: Firewall
  - Server: [ADG-FW-DC01-01](./Server/HP_Gen8/ADG-FW-DC01-01/configuration.md)
  - Changes:
    | Datum | Change | Beschreibung | Status |
    |-------|--------|--------------|--------|
    | - | - | Keine Changes dokumentiert | - |

### Netzwerk
- **Unify WS 48 Pro**
- **Unify WUSW Pro Aggregation**
- **Brocade 300**

### Storage
- **HP MSA 2050**

### Netzwerkkarten
- **FC Karten**: In jedem Server
- **10 GB Netzwerkkarten**: In jedem Server

## Implementierung
Beschreiben Sie die Schritte zur Implementierung der Infrastruktur, einschließlich der Installation und Konfiguration der Server, Netzwerkkomponenten und Storage.

### Fibre Channel Konfiguration
Die FC-Konfiguration für die Proxmox Server ist dokumentiert unter:
- [Proxmox FC Configuration](./Server/HP_Gen9/proxmox_fc_config.md)

## Wartung
Beschreiben Sie die Wartungsprozesse und -richtlinien, um die Infrastruktur auf dem neuesten Stand zu halten und Ausfallzeiten zu minimieren.

## Backup
Beschreiben Sie die Backup-Strategien und -verfahren, um Datenverlust zu verhindern und die Wiederherstellung im Falle eines Ausfalls zu gewährleisten.

## Anhang
Fügen Sie Diagramme, Konfigurationsdateien und andere relevante Dokumente hinzu.

## HP MSA 2050 Einrichtung
Beschreiben Sie die Schritte zur Einrichtung des HP MSA 2050 Storage-Systems, einschließlich der Konfiguration von Volumes, RAID-Gruppen und der Netzwerkanbindung.

## HP MSA 2050 Konfiguration
Die detaillierte Konfiguration des HP MSA 2050 finden Sie in der Datei [configuration.md](./Storage/HP_MSA_2050/configuration.md).

## Netzwerk
Die detaillierte Netzwerkdokumentation finden Sie in der Datei [network.md](./Netzwerk/network.md).

## Namensgebung
Definieren Sie die Namenskonventionen für Hardware und virtuelle Dienste.

### Hardware
- **Proxmox Server**: ADG-PVE-DC01-<Nummer>
  - Beispiel: ADG-PVE-DC01-01
  - Hostnamen: Siehe [server_names.md](./Server/HP_Gen9/server_names.md)
- **ESXi Server**: ADG-ESX-DC01-<Nummer>
  - Beispiel: ADG-ESX-DC01-01
- **Firewall**: ADG-FW-DC01-<Nummer>
  - Beispiel: ADG-FW-DC01-01
- **Switches**: 
  - FC Switches: ADG-SWF-DC01-<Nummer>
    - Beispiel: ADG-SWF-DC01-01
  - Aggregation Switches: ADG-SWA-DC01-<Nummer>
    - Beispiel: ADG-SWA-DC01-01
  - Access Switches: ADG-SWD-DC01-<Nummer>
    - Beispiel: ADG-SWD-DC01-01
- **Storage**: ADG-STG-DC01-<Nummer>
  - Beispiel: ADG-STG-DC01-01

### Virtuelle Dienste
- **Virtuelle Maschinen**: ADG-VM-<Service>-<Nummer>
  - Beispiel: ADG-VM-WEB-01
- **Datenbanken**: ADG-DB-<Service>-<Nummer>
  - Beispiel: ADG-DB-MYSQL-01
- **Anwendungen**: ADG-APP-<Service>-<Nummer>
  - Beispiel: ADG-APP-CRM-01

## Dokumentation
Alle Dokumentationen folgen den definierten Standards in der [documentation-standards.md](./documentation-standards.md).

## Ordnerstruktur
Empfohlene Ordnerstruktur für die Projektdokumentation:

```
/home/mrx8086/Skynet-Blueprints/
├── README.md
├── Server/
│   ├── Dell/
│   │   ├── changes/
│   │   └── ADG-ESX-DC01-01/
│   │       ├── configuration.md
│   │       └── driver_info/
│   ├── HP_Gen9/
│   │   ├── changes/
│   │   └── ADG-PVE-DC01-MA01/
│   │       ├── configuration.md
│   │       └── driver_info/
│   │           └── qla2xxx_driver_info.txt
│   ├── HP_Gen8/
│       ├── changes/
│       ├── ADG-FW-DC01-01/
│       │   ├── configuration.md
│       │   └── driver_info/
│       ├── ADG-FW-DC01-02/
│       │   ├── configuration.md
│       │   └── driver_info/
│       └── server_list.md
├── Netzwerk/
│   ├── Unify/
│   │   └── changes/
│   ├── Brocade/
│   │   └── changes/
│   └── network.md
├── Storage/
│   └── HP_MSA_2050/
│       ├── changes/
│       └── configuration.md
├── Netzwerkkarten/
│   └── changes/
├── Implementierung/
├── Wartung/
└── Backup/

## Change Management
Alle Änderungen an der Infrastruktur werden in den entsprechenden changes/-Ordnern dokumentiert:
- Format der Change-ID: CH-[Bereich]-[Jahr]-[laufende Nummer]
  - Beispiel: CH-PVE-2024-001
- Jeder Change wird in einer separaten Markdown-Datei dokumentiert
- Changes werden nach Komponenten gruppiert (Server, Netzwerk, Storage)

## TODO
Liste der noch ausstehenden Aufgaben:

- ✓ Ersten Proxmox Server an Brocade 300 anschließen
- → Change CH-PVE-2024-001: Umbenennung Proxmox Server 1 (geplant)
- Restliche Proxmox Server umbenennen
- Restliche Proxmox Server an Brocade 300 anschließen
- Netzwerk auf der Firewall und den Switches konfigurieren
- VLANs und IP-Adressierung gemäß [network.md](./Netzwerk/network.md) einrichten
- Tests zur Überprüfung der Netzwerkkonfiguration durchführen
