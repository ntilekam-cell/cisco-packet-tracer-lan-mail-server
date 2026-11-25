# Enterprise LAN Scaling & Internal Mail Server Simulation (Cisco Packet Tracer)

A hands-on networking infrastructure project demonstrating two-switch distribution layer scaling, static server addressing, DHCP lease management, and end-to-end internal SMTP/POP3 email services in Cisco Packet Tracer.

## 📂 Repository Files
* **[Enterprise-LAN-Mail-Server.pkt](./Enterprise-LAN-Mail-Server.pkt)** — Interactive Cisco Packet Tracer topology file (requires Cisco Packet Tracer 8.x or newer).
* **[Enterprise-LAN-Mail-Server-Lab.pdf](./Enterprise-LAN-Mail-Server-Lab.pdf)** — Complete technical report, IP addressing tables, CLI commands, and SMTP/POP3 verification screenshots.

## 🏗️ Architecture & Key Implementations
* **Distribution Layer Scaling & Inter-Switch Trunking:** Expanded network capacity for 8 additional workstations by introducing `Switch1` and installing a `PT-SWITCH-NM-1CFE` FastEthernet hardware expansion module on `Switch0`.
* **Physical & Data Link Troubleshooting:** Resolved auto-MDIX pin mismatches using a Copper Cross-Over uplink (`FastEthernet9/1` to `FastEthernet0/1`) and activated administratively shut down expansion interfaces via Cisco IOS (`no shutdown`).
* **Deterministic Server Addressing:** Migrated `Server0` from dynamic DHCP to a static IPv4 configuration (`192.168.0.106`) to maintain reliable gateway access for client email services.
* **Application Layer (SMTP & POP3):** Configured internal domain email services (`lab.com`), provisioned user mailboxes, and verified end-to-end `"Send Success"` and `"Receive Mail Success"` loops across scaled workstations.
* **Dynamic Client Allocation:** Verified automated DHCP IPv4 lease assignment across all newly added endpoints.

## 🧪 Testing the Simulation (`.pkt`)
To test internal email delivery in Cisco Packet Tracer:
1. Open **`Enterprise-LAN-Mail-Server.pkt`**.
2. Open **Desktop > Email** on either configured client workstation:
   * **Client 1:** `staff1@lab.com` | **Username:** `staff1` | **Password:** `1234`
   * **Client 2:** `staff2@lab.com` | **Username:** `staff2` | **Password:** `1234`
   * **Mail Server IP (SMTP/POP3):** `192.168.0.106`
3. Compose and send a message between `staff1@lab.com` and `staff2@lab.com` to verify delivery.

## 💡 Key Skills Demonstrated
* **Networking Protocols:** IPv4/IPv6 Addressing, DHCP, SMTP, POP3
* **Hardware & Media:** Cisco Switches, Modular Expansion Cards, Cross-Over vs. Straight-Through Cabling
* **Tools:** Cisco Packet Tracer, Cisco IOS CLI
