# Case Study 01: Ransomware Recovery Attempt and Endpoint Restoration

## Summary

A client laptop was brought in after files became inaccessible. On inspection, the device showed signs of a ransomware infection consistent with CryptoWall 3.0 behavior, including ransom note artifacts in multiple formats and encrypted file contents across user data directories. Conventional recovery was attempted and was not successful. The system was restored to functional condition through storage replacement and a clean operating system installation, and the client was educated on backup practices to prevent a repeat incident.

---

## Client Privacy Notice

All client identifying information has been removed. References use generic language: "client laptop", "affected endpoint", "user data directory". Ransom note filenames are described in generic terms based on the pattern observed. No screenshots, file paths, or system identifiers that map back to a specific person or device are included.

---

## Reported Issue

The client brought in a laptop reporting that personal files would no longer open. Photos and documents that had previously worked were either failing to open, opening with errors, or displaying as corrupted. The client also mentioned that new files with strange names had appeared in folders where their data was stored.

---

## Initial Findings

Visual inspection of the file system in the user data directories revealed:

| Observation | Detail |
|-------------|--------|
| Ransom note artifacts | Files named in the HELP_DECRYPT pattern were present in multiple folders |
| Multiple note formats | The same instructions appeared as plain text, HTML, and image files |
| Original filenames preserved | User files still showed their original names rather than being renamed |
| File contents altered | Opening user files returned errors or displayed corrupted content |
| Images partially viewable | Some image files opened but showed scrambled or incorrect visual content, consistent with partial encryption |
| Spread across user data | Encryption affected documents, images, and other personal file types across several folders |

The combination of preserved filenames, the HELP_DECRYPT note pattern, multiple note formats, and partially corrupted image content was consistent with publicly documented CryptoWall 3.0 behavior.

---

## Diagnosis

The system showed clear evidence of a ransomware infection. The diagnostic conclusion was:

1. The malware had executed on the system and encrypted user data files.
2. The original ransomware binary may or may not have still been present, but the damage to file contents was already done.
3. Standard file recovery tools would not be able to restore encrypted contents without either a usable backup or a valid decryption key.
4. The client did not have a recent backup of the affected data.

The recovery posture at that point was clearly limited. The next steps were to document the evidence, communicate the limitations clearly to the client, and plan endpoint restoration.

---

## Tools and Methods Used

| Tool or Method | Purpose |
|----------------|---------|
| File system review | Visual identification of ransom note artifacts and affected file types |
| Windows Security and Malwarebytes | Scanning to identify and quarantine residual malicious components |
| CrystalDiskInfo | Verifying that the underlying storage was still healthy enough to retain forensic state during evidence review |
| Recuva | Attempted recovery of deleted file versions that may have predated encryption |
| PhotoRec | File carving on user data partitions to attempt recovery of unencrypted originals |
| TestDisk | Reviewed partition structures to confirm the file system itself was intact |
| Rufus | Created bootable Windows installation media |
| Tiny10 | Lightweight Windows variant used for the clean installation on older hardware |

---

## Work Performed

1. **Evidence documentation.** Captured the file naming patterns of the ransom notes, the directories affected, and the symptoms observed. This documentation was preserved for the client record.
2. **Malware containment.** The system was kept off the client network during diagnostics. Scans were run to identify any residual malicious binaries.
3. **Recovery attempts.** Recuva and PhotoRec were used in an attempt to recover earlier unencrypted copies of user files. The results were limited: small fragments of older content were recoverable, but the bulk of the user data could not be restored to a usable state. The client was informed of the result directly.
4. **Storage replacement.** The original storage was replaced with a 2.5-inch SATA SSD. This served two purposes: it eliminated any risk of residual malicious artifacts surviving on the original drive, and it gave the older laptop a significant usability improvement.
5. **Clean OS installation.** Tiny10 was installed on the new SSD. Tiny10 was selected because the laptop hardware was older and would not run a full Windows 10 or Windows 11 install comfortably. The lightweight variant provided a more usable experience on the available resources.
6. **Driver and update validation.** All required drivers were installed, Windows was fully updated within the limits of the variant in use, and core applications were verified to launch correctly.
7. **Backup discussion.** Before returning the laptop, the client was walked through a basic backup plan and the risks that had led to this incident.

---

## Outcome

| Aspect | Result |
|--------|--------|
| Original data recovery | Largely unsuccessful with available standard tools |
| Endpoint restoration | Successful, laptop returned to functional, usable condition |
| Malware removal | The compromised storage was physically removed from the system |
| Client experience | Laptop performance after the SSD upgrade was substantially better than its pre-infection state |
| Future risk reduction | Client left with a working backup plan and an understanding of how to maintain it |

The data loss was real and the client was clearly told that the original files could not be reliably recovered. The honesty of that conversation was as important as the technical work itself.

---

## Client Impact

The client left with a working laptop that was faster and more responsive than it had been even before the infection, due to the SSD upgrade. The encrypted personal files were a real loss, and the client understood that loss was a direct consequence of not having a backup. The conversation around backups was concrete: which files matter most, where they should be copied, how often, and how to verify a backup actually contains what is expected.

---

## Lessons Learned

| Lesson | Detail |
|--------|--------|
| Backups are the only reliable defense | Conventional recovery tools cannot reverse ransomware encryption. Backup planning prevents the worst-case outcome. |
| Document the evidence regardless of recoverability | Even when files cannot be recovered, the documentation gives the client a clear record of what happened. |
| Set expectations early and clearly | The earlier a client hears that recovery is unlikely, the less painful the conversation becomes. |
| Replacing storage after a ransomware case is good practice | It eliminates any uncertainty about residual artifacts and gives the client a usability win. |
| Lightweight Windows variants matter on older hardware | Installing a full modern Windows on a marginal laptop produces a worse experience than installing a lightweight variant tuned for the hardware. |

---

## Recommended Prevention and Follow-Up

The client was given the following written recommendations:

1. **Implement a 3-2-1 backup model.** Three copies of critical data, on two different storage types, with one copy stored off-site or in cloud storage.
2. **Verify backups actually contain the files that matter.** Schedule alone is not enough; the backup must be tested.
3. **Be cautious with email attachments and unfamiliar downloads.** Phishing is the most common entry point for ransomware on consumer endpoints.
4. **Keep Windows and applications up to date.** Many ransomware delivery techniques exploit known unpatched vulnerabilities.
5. **Maintain working antivirus or endpoint protection.** Windows Security is sufficient for most consumer use when kept current.
6. **Call early next time.** If files start behaving strangely, disconnecting the device from the network immediately limits how far an infection can spread.

A follow-up was offered to set up the backup configuration if the client wanted assistance.

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Ransomware impact assessment | Identification of CryptoWall 3.0-style artifacts and affected file scope |
| Evidence documentation | Captured ransom note patterns, affected directories, and symptom evidence for the client record |
| Recoverability evaluation | Realistic assessment of what could and could not be recovered with available tools |
| Conventional recovery attempt | Recuva, PhotoRec, and TestDisk used responsibly with documented results |
| Endpoint restoration | SSD replacement and clean OS installation |
| Lightweight Windows deployment | Tiny10 selected for hardware constraints |
| Client expectation management | Honest communication that recovery was unlikely before commitment to the work |
| Backup planning and education | 3-2-1 model explained in practical terms, with a concrete plan tied to the client's actual data |
| Cybersecurity awareness | Treating the case as an incident with evidence, containment, and prevention, not as a simple reinstall |
| Realistic expectation management | No false promises of full recovery, no overselling of services |

---

## Why This Case Matters for an IT Role

This case is the clearest demonstration of what a customer-facing IT technician actually does in the worst-case version of the job. It combines:

- Technical depth: ransomware behavior, recovery tooling, OS installation on constrained hardware.
- Operational discipline: documented evidence, structured recovery attempt, staged restoration.
- Customer service: honest expectation setting during a stressful incident, written recommendations, education that left the client better prepared than before.

These are the same skills required for help desk escalations, desktop support incidents, junior SOC analyst triage, and any role where a real user has a real problem and needs both a fix and an explanation they can act on.
