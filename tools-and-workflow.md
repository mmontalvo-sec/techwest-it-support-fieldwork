# Tools and Workflow

This document covers the tools, methodologies, and operational workflow used during Tech West PC Repair engagements. It is intentionally specific to demonstrate that the work follows a repeatable, documented process.

---

## Windows Built-in Tools

| Tool | Purpose |
|------|---------|
| Event Viewer | Reviewing system, application, and security logs to identify error patterns |
| Reliability Monitor | Visual timeline of system stability for narrowing the start date of recurring issues |
| Device Manager | Identifying driver conflicts, missing drivers, and hardware recognition issues |
| Disk Management | Reviewing partitions, drive letters, and volume health |
| Task Manager | Reviewing CPU, memory, disk, and network usage; checking startup impact |
| Startup Apps | Disabling unnecessary startup applications |
| Windows Update | Applying pending updates and resolving stuck or failed updates |
| System Restore | Reverting recent system changes when a known good state exists |
| Windows Security | Running scans, reviewing protection status, validating quarantine actions |
| Command Prompt | Running diagnostic and repair commands |
| PowerShell | Running scripted diagnostics, file operations, and system queries |

---

## Active Directory and Help Desk Tools

| Tool | Purpose |
|------|---------|
| Active Directory Users and Computers (ADUC) | User account management: create, unlock, reset, disable, OU move, group assignment |
| Event Viewer (Security log, Event ID 4740) | Identifying account lockout source from the domain controller's security event log |
| PowerShell AD module | `Get-ADUser`, `Set-ADAccountPassword`, `New-ADUser`, `Disable-ADAccount`, `Add-ADGroupMember`, `Get-ADGroupMember` |
| Group Policy Management Console (GPMC) | Reviewing GPO assignments and troubleshooting policy application issues |
| `gpresult /r` | Confirming which Group Policy Objects are applied to a specific user or computer |
| `gpupdate /force` | Forcing an immediate Group Policy refresh on a workstation |
| RSAT (Remote Server Administration Tools) | Managing AD, DNS, and DHCP remotely from a workstation |
| Windows Credential Manager | Identifying cached credentials that cause account lockouts after a password change |

---

## Network Diagnostics and DNS/DHCP Tools

| Tool | Purpose |
|------|---------|
| `ipconfig /all` | Full network adapter configuration including IP, subnet, gateway, DNS servers, and DHCP lease |
| `ipconfig /release` and `/renew` | Releasing and renewing a DHCP lease to resolve APIPA or stale lease issues |
| `ipconfig /flushdns` | Clearing the local DNS resolver cache |
| `ipconfig /registerdns` | Re-registering the client's DNS record with the DNS server |
| `nslookup` | Testing DNS resolution against configured or specified DNS servers |
| `ping` | ICMP reachability testing for gateway, DNS server, and external hosts |
| `tracert` | Tracing the network path to a destination to identify where connectivity fails |
| `arp -a` | Viewing the ARP table to map MAC addresses to IP addresses on the local segment |
| `netstat -an` | Viewing active connections and listening ports |
| DHCP Manager (Windows Server) | Scope management, active lease review, stale lease deletion, exclusion range configuration |
| DNS Manager (Windows Server) | Forward and reverse lookup zone review, record management, stale record cleanup |

---

## Diagnostic Utilities

| Tool | Purpose |
|------|---------|
| CrystalDiskInfo | SMART health review for HDDs and SSDs |
| MemTest86 | Bootable memory testing across multiple passes |
| HWiNFO | Detailed hardware inventory, sensor data, temperatures, and component identification |
| CPU-Z | CPU, memory, and motherboard identification |
| CHKDSK | File system and logical disk error scanning and repair |
| SFC | System file checker to identify and repair corrupted Windows system files |
| DISM | Image servicing and deeper Windows component repair when SFC alone is insufficient |
| SMART checks | Direct review of drive health attributes |

---

## Recovery and Boot Utilities

| Tool | Purpose |
|------|---------|
| Medicat USB | Multi-tool bootable USB for diagnostics, recovery, and offline work |
| Hiren BootCD PE | Bootable WinPE environment for offline troubleshooting and recovery |
| Rufus | Creating bootable USB media from ISO images |
| TestDisk | Recovering lost partitions and repairing damaged partition tables |
| PhotoRec | File carving for recovering files from damaged or formatted storage |
| Recuva | Recovering recently deleted files when the file system is still intact |

---

## Hardware Work

| Task | Description |
|------|-------------|
| SSD replacement | Cloning or clean installing onto SATA and NVMe SSDs |
| RAM testing | MemTest86 with multiple passes to confirm fault isolation |
| RAM replacement | Replacing failed modules with compatible parts |
| Thermal paste replacement | Cleaning old paste from CPU and applying fresh paste during repaste services |
| Internal dust cleaning | Removing dust from fans, heatsinks, and intake vents |
| Cable and connector inspection | Visual inspection for damaged cables, bent pins, or loose connectors |
| Fan and airflow review | Verifying fan operation and identifying obstructed airflow paths |

---

## Business Workflow

Every engagement follows a consistent ten-step workflow:

1. **Receive client issue.** Listen to the reported symptoms in the client's own words.
2. **Ask diagnostic questions.** Clarify when the issue started, what changed before it started, and what has already been tried.
3. **Inspect device condition.** Visual inspection for damage, dust, missing screws, or anything unusual.
4. **Check obvious hardware and software problems.** Power, cabling, peripherals, recent updates, recent installs.
5. **Run diagnostics.** Use the appropriate built-in or third-party tools to confirm or rule out causes.
6. **Document findings.** Capture symptoms, observations, and test results in a structured log.
7. **Explain options to the client.** Present what the issue is, what can be done, and the cost or effort of each option.
8. **Perform approved work.** Execute the agreed scope only.
9. **Validate functionality.** Confirm the original issue is resolved and that no new issues were introduced.
10. **Provide recommendations.** Written or verbal post-service guidance, plus an invoice or service report.

---

## Communication Workflow

| Stage | Practice |
|-------|---------|
| Intake | Listen first, take notes, restate the issue back to the client to confirm understanding |
| During diagnostics | Avoid speculation; share findings only after they are confirmed |
| Repair authorization | Explain options, costs, and likely outcomes before starting work |
| If recovery is uncertain | State honestly that an outcome is not guaranteed before the client commits |
| After repair | Show the client what was done, demonstrate the system working, hand off documentation |
| Recommendations | Provide actionable next steps, especially for backups and prevention |

---

## Documentation Workflow

Every job produces documentation. Even routine maintenance generates a record so the client and the technician have a clear history. The documentation set typically includes:

- A short intake summary capturing reported symptoms and client priorities
- A diagnostic log capturing tests run and their results
- A service report capturing work performed, parts replaced, and validation steps
- A recommendations document summarizing what the client should do next

Templates for each of these are available in the [templates](templates/) folder.
