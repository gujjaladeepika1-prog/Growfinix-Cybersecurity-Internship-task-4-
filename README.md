# Task 3: Network Vulnerability Scanning

## Growfinix Cybersecurity Internship

## Objective
Perform a network vulnerability assessment using Nmap to identify open ports, running services, and possible security risks on an authorized local test system.

## Target
- Localhost (127.0.0.1)

## Tool Used
- Nmap 7.80

## Installation Verification

Nmap was installed and verified successfully.

Command:
```bash
nmap --version
```

Installation Path:
```text
C:\Program Files (x86)\Nmap\nmap.exe
```

## Scan Command
```bash
nmap -sV localhost -oN scan_results.txt
```

## Scan Results
The scan identified the following open services:

| Port | Service | Description |
|------|---------|-------------|
| 135/tcp | Microsoft Windows RPC | RPC service detected |
| 445/tcp | Microsoft-DS (SMB) | SMB service detected |
| 3306/tcp | MySQL | MySQL database service detected |

## Risk Assessment

| Issue | Severity |
|------|----------|
| SMB service exposed | Medium |
| RPC service exposed | Medium |
| MySQL service exposed | Medium |

## Recommendations

### SMB (Port 445)
- Restrict SMB access using firewall rules.
- Disable SMB if not required.
- Apply Windows security updates regularly.

### RPC (Port 135)
- Allow access only to trusted applications.
- Restrict unnecessary network exposure.

### MySQL (Port 3306)
- Keep MySQL updated.
- Avoid exposing database services unnecessarily.
- Use strong authentication methods.

## Screenshots
Screenshots included:

```text
screenshots/
├── nmap_version.png
└── nmap_scan.png
```

## Files Included

```text
Task-3/
├── scan_results.txt
├── vulnerability_report.md
├── README.md
└── screenshots/
    ├── nmap_version.png
    └── nmap_scan.png
```

## Conclusion
The Nmap scan successfully identified active services on the authorized local test system. The results show the exposed attack surface and provide recommendations to improve system security by restricting unnecessary services, applying updates, and following security best practices.
