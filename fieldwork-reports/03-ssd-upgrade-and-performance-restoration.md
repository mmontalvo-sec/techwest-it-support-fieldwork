# Case Study 03: SSD Upgrade and Performance Restoration

## Summary

A client laptop running Windows 10 was brought in for evaluation due to long boot times and slow application response. Diagnosis identified the original mechanical hard drive as the primary cause. The drive was replaced with a SATA SSD, the operating system was reinstalled cleanly, drivers were validated, and the system was returned to the client with substantially improved responsiveness and an extended useful service life.

---

## Client Privacy Notice

Client identifying information has been removed.

---

## Reported Issue

The client reported:

- Long boot times, often several minutes from power on to a usable desktop
- Applications taking 30 seconds or more to open
- General sluggishness during normal use
- The client had been considering replacing the laptop entirely

---

## Initial Findings

| Observation | Detail |
|-------------|--------|
| Storage type | Original 2.5-inch SATA HDD |
| Drive health | SMART status reported healthy with no failing sectors |
| Drive performance | Read and write speeds consistent with an aging mechanical drive |
| Memory and CPU | Adequate for the client's daily use, not bottlenecked |
| Operating system | Windows 10, fully updated |
| Visible damage | None |

The hardware was not failing. It was simply mechanically limited compared to what modern Windows expects.

---

## Diagnosis

The original mechanical hard drive was the dominant cause of the system's slowness. Modern Windows is significantly more disk-intensive than older versions, and mechanical drives that were adequate at purchase struggle under that load years later. The remaining hardware was adequate for the client's use case.

The client was informed that replacing the laptop was not necessary. An SSD upgrade would produce a meaningful improvement at a fraction of the cost of a new device.

---

## Tools and Methods Used

| Tool | Purpose |
|------|---------|
| CrystalDiskInfo | Confirming the original drive was not failing, only slow |
| HWiNFO | Verifying the laptop's storage interface supported a 2.5-inch SATA SSD |
| Rufus | Creating a bootable Windows installation USB |
| Windows installer | Clean OS installation onto the new SSD |
| Device Manager | Validating that all drivers loaded after the clean install |
| Windows Update | Bringing the new install fully current |

---

## Work Performed

1. **Hardware compatibility check.** Confirmed the laptop's drive bay accepted a 2.5-inch SATA SSD and that the existing data cable was compatible.
2. **Backup of user data.** Before any work began, the client's personal data was copied off the original drive to ensure nothing was lost during the swap.
3. **SSD installation.** Physical replacement of the HDD with a SATA SSD.
4. **Clean OS installation.** A clean install of Windows 10 was performed on the new SSD. Clean install was preferred over cloning to remove accumulated cruft from the original install.
5. **Driver installation.** All required drivers were installed and validated through Device Manager.
6. **Updates.** Windows was brought fully current.
7. **Data restoration.** Client personal data was copied back to the new install in the appropriate user folders.
8. **Validation.** Boot times, application launch times, and general responsiveness were tested. The client was shown the new boot time at handoff.

---

## Outcome

| Aspect | Result |
|--------|--------|
| Boot time | Reduced from approximately 3 minutes to approximately 20 seconds with the SSD and clean install |
| Application launch | Major improvement across all daily-use applications |
| Overall responsiveness | Comparable to a modern entry-level machine |
| Data preserved | All client personal files preserved through the upgrade |
| Cost vs. new laptop | Substantially lower than the cost of replacement |
| Useful service life | Extended by several years on existing hardware |

---

## Client Impact

The client kept their existing laptop, kept their existing software environment, and avoided the cost and disruption of buying a new device. The improvement was immediately visible at handoff, so the value of the work was clear to the client without needing technical explanation.

---

## Lessons Learned

- An SSD upgrade is the single highest-impact upgrade available for most aged consumer laptops that still have adequate CPU and memory.
- Clean installs produce better long-term results than cloning, particularly on systems that have accumulated years of leftover software.
- Backing up client data before any hardware work is a non-negotiable habit, regardless of how routine the work appears.

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Keep regular backups | The new SSD will eventually fail, like any drive |
| Avoid filling the SSD to capacity | SSD performance degrades when the drive is nearly full |
| Maintain Windows updates | The new install benefits from staying current |
| Reach out when something changes | Catching issues early extends the value of the work |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Hardware compatibility evaluation | Confirmed drive bay, interface, and connector compatibility before recommending the part |
| Storage health diagnosis | Distinguished a slow but healthy drive from a failing one |
| OS migration | Clean install with driver and update validation |
| Data preservation | Pre-work backup ensured no data loss during the swap |
| Driver management | Full driver installation and validation after a clean OS install |
| Client cost-benefit communication | Presented the upgrade as an alternative to buying a new laptop, with clear reasoning |
| Hardware lifecycle extension | Restored a machine the client was considering replacing |
