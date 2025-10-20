# Task-day1
Network port scan results and analysis

# Cyber Security Local Port Scan

## Steps Taken
- Used Nmap to scan my local network for open ports.
- Analyzed scan output for open ports and their services.
- Assessed security risks for discovered open ports.
- (Optional) Used Wireshark to observe scan traffic.

## Results
| Port | Service    | Function              | Security Risk |
|------|------------|-----------------------|---------------|
| 135  | msrpc      | Windows RPC           | Vulnerable to remote exploits |
| 139  | netbios-ssn| Network shares        | Info leaks, legacy risks      |
| 445  | microsoft-ds| SMB file sharing     | Target for ransomware/worms   |

**Summary:**
Open ports were found associated with Windows networking and file sharing. These should only be accessible within a trusted network and not exposed publicly.

## Screenshots
![Nmap Scan Result]<img width="783" height="265" alt="image" src="https://github.com/user-attachments/assets/65c81323-9e57-449c-8d59-6cfb910b1e4d" />

![Wireshark SYN Packets]<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/ed18c722-d0b4-406a-9897-c3a1334a3146" />

