# Case Study 05: RAM Diagnostics and System Stability

## Summary

A client desktop running Windows 10 was brought in with a complaint of intermittent freezes, occasional blue screen errors, and unpredictable crashes. Diagnostic testing identified a memory module that was failing under load. The faulty module was replaced with a compatible part, and the system was validated through extended testing before return.

---

## Client Privacy Notice

Client identifying information has been removed.

---

## Reported Issue

The client reported:

- Random freezes that required a hard reboot
- Occasional blue screen errors with varying error codes
- Crashes seemed unrelated to specific applications
- The issue had been getting worse over the past few weeks

---

## Initial Findings

| Observation | Detail |
|-------------|--------|
| Reliability Monitor | Multiple critical events over the past several weeks, with no consistent application source |
| Event Viewer | WHEA-Logger and Kernel-Power entries consistent with hardware-related crashes |
| Storage health | SMART data via CrystalDiskInfo reported the drive as healthy |
| Temperature readings | CPU and GPU temperatures via HWiNFO were within normal ranges |
| Memory configuration | Two memory modules installed, matching capacity |
| Visual inspection | No physical damage or unusual marks on hardware |

The pattern, errors that move around between applications and produce hardware-level event log entries, pointed toward memory or another core hardware component rather than software.

---

## Diagnosis

Memory was the most likely culprit based on the symptom pattern. To confirm, a MemTest86 run was scheduled on the existing configuration.

---

## Tools and Methods Used

| Tool | Purpose |
|------|---------|
| Reliability Monitor | Reviewing the timeline of crashes for patterns |
| Event Viewer | Reading WHEA-Logger and Kernel-Power entries for hardware-related signatures |
| HWiNFO | Reviewing system temperatures and component status |
| CrystalDiskInfo | Confirming the storage was not the cause |
| MemTest86 | Bootable memory testing across multiple passes |
| Rufus | Creating the MemTest86 bootable USB |

---

## Work Performed

1. **Initial test pass.** Ran MemTest86 with both memory modules installed. The test reported errors on a specific address range after a partial pass.
2. **Isolation.** Removed one module and ran MemTest86 again with only the remaining module. No errors were reported. Reinstalled the suspect module alone in the same slot, and errors returned at the same address range.
3. **Slot test.** Moved the suspect module to a different slot to rule out a slot issue. Errors continued to appear, confirming the module itself was the fault.
4. **Replacement.** Sourced a compatible replacement module matching the specifications of the working module.
5. **Validation pass.** Ran MemTest86 again on the new configuration for multiple passes with zero errors reported.
6. **Stability testing.** Booted into Windows and ran typical client workloads for an extended session. No crashes, freezes, or blue screens occurred during the test period.

---

## Outcome

| Aspect | Result |
|--------|--------|
| Faulty module | Identified, isolated, and replaced |
| Memory test result | Zero errors after replacement |
| Crash reproduction | No crashes during extended Windows-side testing |
| Client confidence | The structured testing approach gave the client clear evidence that the issue was actually addressed |

---

## Client Impact

The system was returned to stable operation. The client had been losing work to unexpected crashes and was relieved to have a clear, evidence-based explanation of the cause. The cost of the replacement module was significantly less than the cost of replacing the entire system, which the client had been considering.

---

## Lessons Learned

- The crash error code on a blue screen is often not as useful as the pattern of errors over time. Reliability Monitor and Event Viewer together produce a much clearer picture than a single crash dump.
- MemTest86 needs to be allowed to run through multiple full passes. Some errors only appear after the test has heated the modules and exercised the full address range.
- Slot testing is important. A failing memory slot can produce identical symptoms to a failing module, and the fix is very different.

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Run MemTest86 if crashes return | Any recurrence should start with another full memory test |
| Avoid mismatched memory | If a future memory upgrade is needed, match speed, capacity, and timings |
| Maintain Windows updates | Some crash patterns are addressed by kernel updates |
| Reach out at first sign of recurrence | Memory failures often happen gradually and rarely fix themselves |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Symptom pattern analysis | Reliability Monitor and Event Viewer used to identify a hardware-class problem |
| MemTest86 use | Bootable memory testing across multiple passes |
| Hardware fault isolation | Slot-by-slot and module-by-module testing to confirm the actual fault |
| Compatibility evaluation | Replacement module matched to the working module's specifications |
| Extended validation | Stability testing beyond just a working boot |
| Client communication | Evidence-based explanation of the diagnosis and the result |
