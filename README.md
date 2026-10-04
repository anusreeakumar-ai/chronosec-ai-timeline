# ChronoSec AI: Automated Incident Reconstruction & 3D Geospatial Threat Intelligence Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-emerald.svg)](LICENSE)
[![Frontend](https://img.shields.io/badge/Stack-Tailwind_CSS_|_Three.js_|_Vanilla_JS-06b6d4)](#-technical-specifications)
[![Platform](https://img.shields.io/badge/Deployment-GitHub_Pages-blue)](#-deployment-github-pages)

**ChronoSec AI** is a browser-native Security Operations Center (SOC) investigation and forensic intelligence platform. It resolves multi-source log fragmentation by parsing heterogeneous security telemetry (Firewall, Sysmon/EDR, Active Directory, and VPC Flow Logs), compensating for system clock skew, clustering interdependent stages across the cyber kill chain, and projecting multi-hop ballistic attack trajectories across an interactive 3D geospatial environment.

---

## 📌 Table of Contents
- [Key Modules & Architecture](#-key-modules--architecture)
- [Technical Specifications](#-technical-specifications)
- [Telemetry Pipeline](#-telemetry-pipeline)
- [Getting Started](#-getting-started)
- [Deployment (GitHub Pages)](#-deployment-github-pages)
- [License](#-license)

---

## 🛡️ Key Modules & Architecture

### 1. Dedicated Clearance & Authentication Portal
* **Session Gatekeeper**: Implements an investigator authentication portal requiring analyst handle, clearance tier classification, and target dispatch email.
* **Context Preservation**: Maintains persistent investigator identity and clearance tags throughout report exports and navigation states.

### 2. 3D Geospatial Real Estate & Ballistic Arc Engine
* **Interactive Threat Mapping**: Built with Three.js WebGL (with Google Maps 3D Vector integration support), rendering real-world server nodes across Bucharest, Frankfurt, Dallas, and St. Petersburg.
* **Ballistic Trajectory Modeling**: Projects Bezier curves across geographic coordinates with real-time animated particle beams illustrating payload trajectory.
* **Directional Flow Telemetry**: Explicitly tracks host-to-host attribution:
  * **Sender Entity** $\rightarrow$ **Receiver Entity**
  * **Transport Protocol & Target Port** (HTTP POST, Kerberos TGS-REQ, SMBv2, TLS)
  * **Payload Transfer Volume** (e.g., buffer overflow strings to 3.2 GB encrypted bursts)

### 3. Attack Graph & Heuristic Explainability Drawer
* **Topological Relationship View**: SVG node-link network map demonstrating lateral movement paths between perimeter gateways, web instances, Domain Controllers, and data vaults.
* **Correlation Justification**: Exposes the logic behind automated log clustering:
  * **NTP Drift Normalization**: Dynamic sliding-window compensation across disparate time zones.
  * **ECS Pattern Matching**: Process tree parent-child lineage tracking (`w3wp.exe` $\rightarrow$ `powershell.exe`).
  * **MITRE ATT&CK Mapping**: Heuristic categorization into techniques (T1190, T1059.001, T1078, T1021.002, T1567).

### 4. Forensic Evidence Vault & Path Synthesizer
* **Artifact Ingestion**: Allows investigators to attach memory dump hex snippets, Wireshark PCAPs, and screenshot artifacts.
* **Dynamic Chain Synthesis**: Ingesting custom evidence triggers dynamic recalculation, inserting new milestones directly into the global attack chain and spatial map.

### 5. Automated PDF Dossier Compilation & Email Dispatch
* **Client-Side Generation**: Leverages `jsPDF` and `jspdf-autotable` to format dark-header, executive-ready forensic incident reports containing timestamps, mitigations, and affected assets.
* **SMTP Relay Integration**: Directly dispatches incident dossiers and remediation steps to the investigator's email address via Web3Forms API.

---

## ⚙️ Technical Specifications

| Component | Implementation |
|---|---|
| **Architecture** | Zero-dependency, single-file frontend (`index.html`) |
| **Styling & Icons** | Tailwind CSS CDN, Lucide Icons |
| **3D Graphics** | Three.js (r128), OrbitControls, Quadratic Bezier Curves |
| **Geospatial Layer** | Custom WebGL spherical projection / Google Maps Vector API |
| **Document Compiler** | jsPDF 2.5.1 + AutoTable 3.5.31 |
| **Email Gateway** | Web3Forms REST API (Direct client-side async dispatch) |

---

## 🔄 Telemetry Pipeline

```text
[ Raw Multi-Source Telemetry ]
  ├── Perimeter Firewalls (Palo Alto Networks)
  ├── Endpoint EDR & Process Trees (Sysmon)
  ├── Directory Services (Active Directory Kerberos)
  └── Cloud Network Logs (AWS VPC Flow)
            │
            ▼
[ Ingestion & Normalization Engine ]
  └── Elastic Common Schema (ECS) standard alignment
  └── NTP clock skew compensation (±1.04s threshold)
            │
            ▼
[ Automated Attack Reconstruction ]
  └── Event correlation via sliding-window heuristics
  └── MITRE ATT&CK technique mapping
            │
            ▼
[ Dual Presentation Layer ]
  ├── 3D Ballistic Geospatial Real Estate Map
  └── Dynamic SVG Topology Graph + Explainability Engine
            │
            ▼
[ Reporting & Incident Response ]
  ├── Client-side compiled PDF incident dossier
  └── Encrypted dispatch to investigator email
