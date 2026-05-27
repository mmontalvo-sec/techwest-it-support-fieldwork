# Diagnostic Checklist

A repeatable checklist used at the start of every Tech West PC Repair engagement. The goal is to gather enough information to choose the right next step without wasting time on unrelated tests.

---

## 1. Intake

- [ ] Issue described in the client's own words
- [ ] Time the issue started or was first noticed
- [ ] What changed before the issue started (new software, new hardware, recent updates, recent power events)
- [ ] What the client has already tried
- [ ] How urgent the repair is for the client
- [ ] Whether any data on the system is at risk or already lost

---

## 2. Visual Inspection

- [ ] Visible physical damage
- [ ] Dust accumulation in vents or fans
- [ ] Loose or missing screws
- [ ] Damaged cables or connectors
- [ ] Liquid damage indicators
- [ ] Storage devices physically present and seated
- [ ] Power adapter condition

---

## 3. Power and Boot

- [ ] System powers on
- [ ] POST completes
- [ ] Boot drive detected in BIOS or boot menu
- [ ] Boot reaches Windows login or recovery
- [ ] Any audible fan noise or pattern abnormalities

---

## 4. Operating System State

- [ ] Windows version and edition
- [ ] Pending Windows updates
- [ ] Last successful boot
- [ ] Reliability Monitor reviewed for recent critical events
- [ ] Event Viewer reviewed for recurring System and Application errors
- [ ] Device Manager reviewed for missing or error-flagged devices

---

## 5. Hardware Health

- [ ] CrystalDiskInfo run against each drive
- [ ] SMART status reviewed
- [ ] Free space on system drive
- [ ] Memory configuration (modules, capacity, speed)
- [ ] CPU and GPU temperatures via HWiNFO at idle
- [ ] Battery health (for laptops)

---

## 6. Software Audit

- [ ] Startup applications listed
- [ ] Recently installed applications reviewed
- [ ] Browser extensions reviewed
- [ ] Antivirus or endpoint protection status confirmed
- [ ] Pending software updates noted

---

## 7. Network

- [ ] Connected to expected network
- [ ] DNS resolution working
- [ ] Basic internet connectivity confirmed
- [ ] Printer or shared peripheral reachability (if relevant)

---

## 8. Security Posture

- [ ] No obvious signs of malware
- [ ] No ransom note artifacts present
- [ ] No suspicious processes in Task Manager
- [ ] No unfamiliar scheduled tasks
- [ ] Windows Security definitions current

---

## 9. Decision Point

After completing the checklist, the technician decides whether the issue can be:

- [ ] Resolved on the spot
- [ ] Resolved with deeper diagnostics (MemTest86, sector scans, etc.)
- [ ] Resolved with parts replacement
- [ ] Resolved with operating system reinstallation
- [ ] Escalated to a different service tier
- [ ] Declined with a clear explanation of why

---

## 10. Communication

- [ ] Findings explained to client in plain language
- [ ] Options presented with cost and time estimates
- [ ] Client authorization obtained before any chargeable work
- [ ] Expectations set clearly, especially for outcomes that are not guaranteed
