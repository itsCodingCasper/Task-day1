# Task-day1
Network port scan results and analysis

## Overview

This project contains the results and security analysis of a local network port scan performed to understand network exposure. The objective was to identify open TCP ports, research their associated services, and assess potential security risks using tools like Nmap and Wireshark.

---

## Steps Taken

- Used Nmap to scan my local network for open ports.
- Analyzed the scan output to find active services.
- Assessed security risks for discovered open ports.
- Used Wireshark to observe SYN packets generated during scanning.

---

## Findings

The following ports were discovered open on my local Windows machine. Each corresponds to standard Windows networking services that can pose certain security risks if exposed.

| Port | Service      | Function             | Security Risk                                  |
|------|--------------|----------------------|-----------------------------------------------|
| 135  | msrpc        | Windows RPC          | Vulnerable to remote exploits if exposed     |
| 139  | netbios-ssn  | Network shares       | Information leakage and legacy system risks  |
| 445  | microsoft-ds | SMB file sharing     | Common target for ransomware and worms       |

> These ports are typical in local Windows environments but should be protected behind a firewall or restricted to trusted networks only.

---

## Screenshots

- **Nmap Scan Result:** Shows the open ports detected on my network.
  ![Nmap Scan Result]
  <img width="783" height="265" alt="Screenshot 2025-10-20 214740" src="https://github.com/user-attachments/assets/2d69a35a-499f-4b3f-b9ce-2ba1e5e202e9" />
 
- **Wireshark SYN Packets:** Capture showing TCP SYN packets sent during the scan.
  ![Wireshark SYN Packets]
  <img width="1919" height="1079" alt="Screenshot 2025-10-20 214429" src="https://github.com/user-attachments/assets/3ac6c728-b096-4e13-b964-fae79f8de321" />


---

## Tools Used

- Nmap (network scanning)
- Wireshark (packet analysis)

---

## Conclusion

This scan revealed common Windows networking ports open on the local machine. These services are needed for local file and printer sharing but can become major security risks if exposed to public networks. It is highly recommended to firewall these ports, restrict sharing, and monitor for vulnerabilities.

---

## Research Insights

### 1. What is an open port?
An open port is a network port on a device that is configured to accept incoming connections or data packets. It means a service or application is actively listening on that port and will respond to network traffic.

### 2. How does Nmap perform a TCP SYN scan?
Nmap’s TCP SYN scan (`-sS`) sends a SYN packet to the target port. If the port is open, the target replies with a SYN-ACK. Nmap then sends an RST (reset) to avoid completing the handshake, making the scan stealthy since no full TCP connection is established.

### 3. What risks are associated with open ports?
Open ports can make a system vulnerable to:
- Unauthorized access if unsecured services are running
- Attacks exploiting outdated or misconfigured services
- Malware or ransomware propagation (e.g., via SMB)
- Information leakage about available services or the OS

### 4. Explain the difference between TCP and UDP scanning.
-**TCP scanning** works by trying to establish a connection using a "handshake" process. This helps the scanner quickly tell if a port is open (connection accepted), closed (connection refused), or filtered (no response).

-**UDP scanning** is trickier because UDP does not establish connections. The scanner sends packets and waits for responses or error messages. No response could mean the port is open or filtered, while an error usually means it’s closed.

### 5. How can open ports be secured?
- Close unused ports/services
- Keep software up to date
- Use firewalls to block/filter traffic
- Enforce authentication and access controls
- Use encryption for exposed services

### 6. What is a firewall's role regarding ports?
A firewall filters network traffic and enforces rules about which ports can send or receive data, helping prevent unauthorized access and limit exposure.

### 7. What is a port scan and why do attackers perform it?
A port scan probes multiple ports to see which are open, closed, or filtered on a device. Attackers use scans to map assets and locate vulnerable services.

### 8. How does Wireshark complement port scanning?
Wireshark captures live network packets and helps visualize the results of port scans, showing the raw SYN, SYN-ACK, and RST traffic for analysis or troubleshooting.
