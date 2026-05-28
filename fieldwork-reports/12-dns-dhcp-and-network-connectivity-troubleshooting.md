# Case Study 12: DNS, DHCP, and Network Connectivity Troubleshooting

## Summary

This case study documents hands-on experience with DNS resolution failures, DHCP lease issues, IP address conflicts, and basic network connectivity troubleshooting. Work covered includes diagnosing APIPA addresses, resolving DHCP scope exhaustion, clearing stale DNS records, correcting static IP conflicts, and restoring internet connectivity for endpoints that had lost name resolution. This experience was developed through lab work and applied support in small-office network environments.

---

## Environment Note

DNS and DHCP troubleshooting documented here applies to small-office environments running Windows Server DHCP and DNS roles, as well as consumer routers that handle DHCP for home and small-office clients. Both are practical help desk scenarios.

---

## Reported Issues (Composite)

This case study covers multiple network troubleshooting scenarios. Each section documents one category of work.

---

## 1. Endpoint Showing APIPA Address (169.254.x.x)

### Reported Issue

A workstation lost network connectivity. The user reported being unable to browse the internet or reach shared drives.

### Diagnostic Steps

| Step | Command | What It Shows |
|------|---------|---------------|
| Check current IP address | `ipconfig /all` | IP, subnet mask, gateway, DNS servers, DHCP lease status |
| Identify APIPA address | IP starts with 169.254 | Confirms the machine could not reach the DHCP server |
| Check physical connection | Look at NIC indicator lights | Rules out a cable or switch port issue |
| Test DHCP server reachability | `ping` the default gateway IP | Confirms basic layer 3 reachability |
| Release and renew | `ipconfig /release` then `ipconfig /renew` | Forces a new DHCP lease attempt |

### Resolution

After confirming the physical connection was intact, released the old address and renewed. The DHCP server responded and assigned a valid lease. The workstation regained network access immediately.

If `ipconfig /renew` fails, next steps include:

1. Check whether other machines on the same switch port or VLAN are affected.
2. Confirm the DHCP server service is running.
3. Check the DHCP scope for exhaustion (no leases available).

---

## 2. DHCP Scope Exhaustion

### Reported Issue

Multiple workstations in a small office began showing APIPA addresses around the same time. Individual renew attempts failed.

### Diagnostic Steps

1. Confirmed multiple machines were affected simultaneously, which rules out individual NIC or cable issues.
2. Accessed the DHCP server console to review the active scope.
3. Found the scope's address pool was exhausted: all available leases were assigned, many to devices no longer on the network.
4. Identified stale leases assigned to MAC addresses not seen recently.

### Resolution

1. Deleted stale leases associated with devices confirmed to be off the network.
2. Freed enough addresses for active workstations to renew.
3. Ran `ipconfig /renew` on affected machines; all obtained valid leases.
4. Expanded the scope address range to provide additional headroom going forward.

### Tools Used

| Tool | Purpose |
|------|---------|
| DHCP Manager (Windows Server) | Scope review, active lease review, stale lease deletion |
| `ipconfig /all` | Client-side lease status |
| `arp -a` | Cross-referencing active MAC addresses on the network |

---

## 3. DNS Resolution Failure

### Reported Issue

A workstation could reach the internet by IP address but not by domain name. Browsing to websites by URL failed; pinging by IP succeeded.

### Diagnostic Steps

| Step | Command | Result Interpretation |
|------|---------|----------------------|
| Test name resolution | `nslookup google.com` | Timeout or "server failed" confirms DNS is the issue |
| Check configured DNS servers | `ipconfig /all` | Incorrect DNS server IP is the most common cause |
| Test the DNS server directly | `nslookup google.com <dns-server-ip>` | Confirms whether the server itself responds |
| Flush the DNS cache | `ipconfig /flushdns` | Clears stale cached entries |
| Re-register DNS | `ipconfig /registerdns` | Re-advertises the client's hostname to the DNS server |
| Check alternate DNS | Temporarily set 8.8.8.8 as DNS and test | Isolates whether the issue is the internal DNS server |

### Resolution

The workstation had a manually configured DNS server address that was no longer valid after a network change. Corrected the DNS server address to match the current DNS server IP. Resolution was restored immediately. Flushed the cache to clear any stale entries and confirmed `nslookup` returned correct results.

---

## 4. IP Address Conflict

### Reported Issue

A workstation began showing intermittent connectivity drops. Windows displayed a notification about a duplicate IP address on the network.

### Diagnostic Steps

1. Confirmed the address conflict using `ipconfig /all` and checking the IP against the DHCP server's active lease list.
2. Identified the conflict: a static IP had been manually assigned to another device that overlapped with the DHCP scope range.
3. Verified which device was holding the conflicting static assignment using `arp -a` and `ping`.

### Resolution

1. Changed the DHCP scope to exclude the address range used by statically assigned devices.
2. Or reassigned the static device to an address outside the DHCP scope.
3. Released and renewed the DHCP lease on the affected workstation.
4. Confirmed the conflict notification no longer appeared.

### Best Practice Applied

Static IP addresses should always use addresses either outside the DHCP scope or in an exclusion range within the scope. Mixing static and DHCP addresses in the same range without exclusions is the most common cause of IP conflicts in small-office environments.

---

## 5. General Connectivity Checklist (OSI Reference)

When a workstation reports "no internet" or "can't reach the server," the diagnostic sequence runs from physical to application:

| Layer | Check | Command |
|-------|-------|---------|
| Physical | NIC indicator lights, cable seat | Visual inspection |
| Link | NIC shows connected in Windows | Network adapter status |
| IP | Valid IP assigned, not APIPA | `ipconfig /all` |
| Gateway | Default gateway reachable | `ping <gateway>` |
| DNS | Name resolution working | `nslookup <domain>` |
| Remote host | Remote host reachable | `ping <destination>` |
| Application | Application-level errors | Application logs, browser console |

This sequence avoids wasted time and prevents incorrect assumptions about the cause.

---

## Tools Used Across All Scenarios

| Tool | Purpose |
|------|---------|
| `ipconfig /all` | Full network configuration view including DHCP lease, DNS servers, gateway |
| `ipconfig /release` | Release current DHCP lease |
| `ipconfig /renew` | Request a new DHCP lease |
| `ipconfig /flushdns` | Clear the local DNS resolver cache |
| `ipconfig /registerdns` | Force re-registration of the client's DNS record |
| `nslookup` | DNS query testing against configured or specified servers |
| `ping` | ICMP reachability testing for gateway, DNS server, and external hosts |
| `arp -a` | View the ARP table to identify MAC-to-IP mappings on the local segment |
| `tracert` | Trace the path to a remote host; identifies where connectivity breaks |
| `netstat -an` | View active connections and listening ports |
| DHCP Manager (Windows Server) | Scope management, lease review, exclusion ranges |
| DNS Manager (Windows Server) | Forward and reverse lookup zone review, record management |
| Event Viewer (System log) | DHCP client errors, DNS client errors |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| APIPA diagnosis | Identified APIPA as a DHCP reachability failure rather than a hardware fault |
| DHCP scope management | Reviewed scope, identified exhaustion, deleted stale leases, expanded scope |
| DNS troubleshooting | Isolated DNS from connectivity using nslookup and IP-based ping |
| DNS cache management | `ipconfig /flushdns` and `/registerdns` applied correctly |
| IP conflict resolution | Identified overlap between static and DHCP ranges; applied exclusion best practice |
| OSI-layer structured thinking | Applied a top-down diagnostic sequence to avoid assuming the wrong layer |
| Windows command-line networking | `ipconfig`, `ping`, `nslookup`, `arp`, `tracert`, `netstat` |
| Windows Server DHCP and DNS roles | Console navigation, scope management, record review |
| Client communication | Explained each issue and fix in plain language tied to the user's experience |

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Set DHCP exclusion ranges for all static devices | Prevents IP conflicts without manual tracking |
| Monitor DHCP scope utilization periodically | Scope exhaustion causes widespread outages quickly |
| Use internal DNS for all domain-joined clients | Prevents name resolution failures when clients point to external DNS |
| Document static IP assignments | Makes conflict resolution faster when duplicates appear |
| Consider DHCP reservations for devices that need consistent IPs | Combines the predictability of static IPs with DHCP management |
