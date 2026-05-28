# Case Study 06: Thermal Maintenance and Repaste

## Summary

A client laptop was brought in with complaints of running hot, fans running loudly, and the system slowing down under sustained workload. Diagnosis identified accumulated internal dust and degraded thermal paste as the primary causes. The laptop was opened, cleaned internally, and re-pasted. Post-service testing confirmed measurable improvements in idle and load temperatures.

---

## Client Privacy Notice

Client identifying information has been removed.

---

## Reported Issue

The client reported:

- The laptop felt hot to the touch during normal use
- Fans were noticeably loud, often running at high speed even when the system was idle
- The laptop slowed down significantly after 10 or 15 minutes of use, then recovered after sitting idle
- The behavior had been getting worse over months

These symptoms are characteristic of thermal throttling caused by accumulated dust and degraded thermal paste.

---

## Initial Findings

| Observation | Detail |
|-------------|--------|
| External vents | Visibly clogged with dust |
| Idle temperatures | Approximately 72°C at idle, elevated for the hardware class |
| Load temperatures | Reached thermal throttle threshold quickly under sustained load |
| Fan behavior | Constant high RPM consistent with sustained thermal pressure |
| Age of laptop | Several years old, no record of prior internal cleaning |
| Battery condition | Adequate, not contributing to the thermal issue |

---

## Diagnosis

The laptop was thermally constrained. Two cumulative factors were responsible:

1. Heavy internal dust accumulation blocking airflow through the heatsink fins.
2. Dried, cracked thermal paste between the CPU and the heatsink, reducing thermal transfer efficiency.

Both are normal consequences of years of use without preventive maintenance.

---

## Tools and Methods Used

| Tool | Purpose |
|------|---------|
| HWiNFO | Recording baseline idle and load temperatures before service |
| Stress workload | Running the system under load to confirm thermal throttling pattern |
| Compressed air | Removing loose dust from the heatsink and fan assembly |
| Soft brush | Loosening compacted dust before removal |
| Isopropyl alcohol (99%) | Cleaning old thermal paste from CPU and heatsink contact surfaces |
| Microfiber cloth | Cleaning surfaces after isopropyl |
| Quality thermal paste | Reapplication on the CPU contact area |
| Standard precision toolkit | Disassembly and reassembly |

---

## Work Performed

1. **Baseline capture.** Recorded idle and load temperatures via HWiNFO before any work.
2. **Disassembly.** Removed the bottom cover and accessed the cooling assembly carefully, taking photos at each step to ensure reassembly accuracy.
3. **Dust removal.** Cleared heavy dust accumulation from the fan, heatsink fins, and intake vents. Compressed air was used in short bursts; the fan was held in place to prevent overspin damage.
4. **Heatsink removal.** Removed the heatsink to access the CPU contact area.
5. **Paste cleaning.** Cleaned old thermal paste from both the CPU die and the heatsink contact surface using isopropyl and a soft cloth.
6. **Paste application.** Applied a fresh layer of quality thermal paste in an appropriate pattern for the CPU package.
7. **Reassembly.** Reseated the heatsink with proper screw sequence and torque, reattached the fan, and replaced the bottom cover.
8. **Validation.** Powered on, ran HWiNFO, captured new idle and load temperatures. Confirmed throttling no longer occurred under the same workload.

---

## Outcome

| Aspect | Result |
|--------|--------|
| Idle temperature | Reduced from approximately 72°C to approximately 45°C |
| Load temperature | Reduced from approximately 98°C to approximately 78°C, no longer reaching the throttle threshold under the same workload |
| Load temperature | Reduced, no longer reaching throttle threshold under the same workload |
| Fan noise | Significantly lower at idle, lower under load |
| Sustained performance | The laptop maintained performance during extended workloads rather than throttling after 10 to 15 minutes |
| Hardware status | No damage during disassembly or reassembly |

---

## Client Impact

The laptop went from being uncomfortable to use to performing as expected for its age. The client avoided the cost of replacing a machine that simply needed maintenance. The fix is a non-permanent improvement, since dust will accumulate again over time, but it bought the client several more years of useful service from the device.

---

## Lessons Learned

- Thermal issues are easy to misdiagnose as software problems or hardware failure. Capturing temperatures with HWiNFO before opening the laptop saved time and confirmed the diagnosis early.
- Internal cleaning every 12 to 18 months on laptops used in dusty environments significantly extends useful service life.
- Photos during disassembly are valuable. Laptops often have non-obvious screw layouts, cable routing, and ribbon connections that are easy to forget under pressure.
- Quality thermal paste matters less than proper application and a clean contact surface.

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Schedule cleaning every 12 to 18 months | Dust accumulation is the most common laptop reliability issue over time |
| Use the laptop on hard surfaces | Soft surfaces like beds and couches block intake vents |
| Avoid running near pet hair sources | Pet hair clogs fans much faster than dust alone |
| Monitor fan noise | Sustained loud fans during normal use are usually an early warning |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Thermal diagnosis | Distinguished thermal throttling from other performance issues |
| Pre-work measurement | Baseline temperatures captured before any change |
| Laptop disassembly | Safe disassembly and reassembly with documentation along the way |
| Internal cleaning | Proper dust removal without damaging fan or heatsink |
| Thermal paste replacement | Cleaning, application, and reseating |
| Post-work validation | Measured temperatures and confirmed improvement under load |
| Client communication | Explained why the laptop was slowing down in concrete terms tied to the work performed |
