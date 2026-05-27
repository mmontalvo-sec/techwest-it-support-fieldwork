# PC Maintenance Checklist

Routine maintenance pass for a Windows endpoint. This is the baseline applied during a PC maintenance engagement, regardless of the original complaint.

---

## Pre-Work

- [ ] Backup of critical client data confirmed before any modifications
- [ ] Restore point created (Windows System Restore)
- [ ] Baseline metrics noted: boot time, idle memory usage, free disk space

---

## Software Cleanup

- [ ] Startup applications reviewed; unnecessary entries disabled
- [ ] Installed applications reviewed; unused programs uninstalled
- [ ] Browser extensions reviewed; unused extensions removed
- [ ] Browser caches cleared
- [ ] Windows temporary files cleared
- [ ] Windows Update download cache cleared
- [ ] Recycle Bin emptied (after client confirmation)

---

## System Health

- [ ] SFC `/scannow` run; results reviewed
- [ ] DISM `/Online /Cleanup-Image /RestoreHealth` run if SFC reports issues
- [ ] CHKDSK on system drive (read-only first, full scan if needed)
- [ ] Event Viewer reviewed for recurring System and Application errors
- [ ] Reliability Monitor reviewed for stability trend

---

## Updates

- [ ] Windows Update run; all pending updates applied
- [ ] Driver updates reviewed via Device Manager
- [ ] Vendor-specific update tools run if applicable (Dell, HP, Lenovo)
- [ ] Application updates applied for critical software

---

## Security

- [ ] Windows Security definitions updated
- [ ] Full Windows Security scan completed
- [ ] Secondary scan with Malwarebytes
- [ ] Browser pop-up and notification permissions reviewed
- [ ] Suspicious scheduled tasks reviewed

---

## Storage

- [ ] CrystalDiskInfo run; SMART status reviewed
- [ ] Free space on system drive within acceptable range
- [ ] Large folders identified if disk space is constrained
- [ ] Storage Sense configured if appropriate

---

## Hardware

- [ ] External dust visible at vents removed (compressed air)
- [ ] Cables inspected
- [ ] Fan noise observed during a brief load test
- [ ] CPU and GPU temperatures noted via HWiNFO

---

## Post-Work Validation

- [ ] Reboot to confirm clean boot
- [ ] Boot time noted; compared to baseline
- [ ] Idle memory usage noted; compared to baseline
- [ ] Client's main applications launched and confirmed working
- [ ] Internet connectivity confirmed
- [ ] Printer functionality confirmed if applicable

---

## Documentation and Handoff

- [ ] Service report completed listing each step performed
- [ ] Findings explained to client in plain language
- [ ] Written recommendations provided for future maintenance
- [ ] Backup recommendation provided if not already in place
- [ ] Restore point retained for client safety net
