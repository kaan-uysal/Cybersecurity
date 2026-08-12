## 1.1 ISO-OSI Model

OSI model layers:

* **Top-Down (Layer 7 → Layer 1):**
  > **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing
  > *(Application, Presentation, Session, Transport, Network, Data Link, Physical)*

* **Bottom-Up (Layer 1 → Layer 7):**
  > **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way
  > *(Physical, Data Link, Network, Transport, Session, Presentation, Application)*

| Layer Number | Layer Name | Main Function | Example protocols and standards |
| :--- | :--- | :--- | :--- |
| `Layer 7` | Application Layer | Providing services and interfaces to applications | HTTP, FTP, DNS, POP3, SMTP, IMAP |
| `Layer 6` | Presentation Layer | Data encoding, encryption, and compression | Unicode, MIME, JPEG,PNG ,MPEG |
| `Layer 5` | Session Layer | Establishing, maintaining, and synchronising sessions | NFS, RPC |
| `Layer 4` | Transport Layer | End-to-end communication and data segmentation | UDP, TCP
| `Layer 3` | Network Layer | Logical addressing and routing between networks | IP, ICMP, IPSec |
| `Layer 2` | Data-Link Layer | Reliable data transfer between adjacent nodes | Ethernet (802.3), WiFi (802.11) |
| `Layer 1` | Physical Layer | Physical data transmission media | Electrical, optical, and wireless signals |

## 1.2 TCP/IP Model

TCP/IP Model and ISO/OSI Model altogether:

| Layer Number | ISO/OSI Model | TCP/IP Model (RFC 1112) | Protocols |
| :--- | :--- | :--- | :--- |
| `Layer 7` | Application Layer | Application Layer | HTTP, FTP, DNS, POP3, SMTP, IMAP |
| `Layer 6` | Presentation Layer |  |  |
| `Layer 5` | Session Layer |  | |
| `Layer 4` | Transport Layer | Transport Layer | UDP, TCP
| `Layer 3` | Network Layer | Internet Layer | IP, ICMP, IPSec |
| `Layer 2` | Data-Link Layer | Link Layer | Ethernet (802.3), WiFi (802.11) |
| `Layer 1` | Physical Layer |  |  |

* *Application layer equals 3 ISO/OSI layer i.e application layer itself, presentation layer and session layer.*
* *Network layer becomes internet layer and data-link layer simply becomes link layer, whereas transport layer maintains same.*
