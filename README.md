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
