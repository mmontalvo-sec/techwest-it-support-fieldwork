# Case Study 08: Client Backup and Data Protection Setup

## Summary

A client requested help setting up a reliable backup solution after a near-miss involving accidental file deletion. A structured backup plan was implemented following the 3-2-1 model, combining external storage and cloud backup. Restore testing confirmed the backup was functional before the engagement was closed. The client was educated on how to verify their own backups going forward.

---

## Client Privacy Notice

Client identifying information has been removed.

---

## Reported Issue

The client reported:

- A recent incident had nearly resulted in loss of important personal files
- The client did not currently have any backup
- The client was unsure what counted as a "backup" and what did not
- The client wanted something that would protect against accidental deletion, hardware failure, and ransomware

---

## Initial Findings

| Observation | Detail |
|-------------|--------|
| Existing backup | None |
| Important data location | User profile folders (Documents, Pictures, Desktop), plus a few specific application folders |
| Approximate data size | Approximately 150 GB, comfortably within a 1 TB external drive |
| Cloud storage in use | One free-tier cloud account, used inconsistently and not configured as a backup |
| Client technical comfort | Comfortable with basic operations, not comfortable with technical configuration |

---

## Diagnosis

The client needed a backup plan that was:

1. **Reliable.** Runs automatically without depending on the client to remember.
2. **Recoverable.** Can be restored from when needed, not just written to.
3. **Defensive.** Protects against multiple threat types, not just hardware failure.
4. **Understandable.** The client needs to know what is being backed up, where it is going, and how to verify it.

The 3-2-1 backup model fits all four requirements:

- **3** copies of important data
- **2** different storage types
- **1** copy off-site (or in the cloud)

---

## Tools and Methods Used

| Tool | Purpose |
|------|---------|
| External USB drive | Local backup destination |
| File History (Windows built-in) | Automated incremental backup to the external drive |
| Cloud backup service | Off-site copy of the most important folders |
| Restore validation | Pulling files back from each backup target to confirm functionality |

---

## Work Performed

1. **Data inventory.** Walked through the client's actual data with them. Identified which folders genuinely needed backup and which did not.
2. **Local backup setup.** Configured Windows File History to back up the identified folders to an external USB drive on a regular schedule. Explained how the schedule worked and how to verify it was running.
3. **Cloud backup setup.** Configured a cloud backup tool to mirror the highest-priority folders to off-site storage. Selected a tool that ran automatically without requiring the client to manually copy files.
4. **Restore validation.** Selected a sample file from each backup target and restored it back to the system to confirm both backup paths actually worked. This step is the single most important part of a backup setup: a backup that has never been restored is not a backup.
5. **Documentation.** Provided the client with a one-page summary listing what was being backed up, where it was being backed up to, and how to verify a backup or pull a file back themselves.
6. **Education.** Walked through what a ransomware-style incident looks like and why the cloud copy matters in that scenario, since malware that encrypts files locally will also encrypt files on a connected external drive.

---

## Outcome

| Aspect | Result |
|--------|--------|
| Local backup | Configured, running, and verified |
| Cloud backup | Configured, running, and verified |
| Restore testing | Confirmed for both targets |
| Client documentation | One-page reference provided |
| Client understanding | Confirmed at handoff: client could state what was backed up, where it went, and how to check it |

---

## Client Impact

The client moved from having no backup to having a functioning 3-2-1-style backup with verified restore capability. The conversation about ransomware was particularly impactful because it explained why a single connected external drive is not a complete solution.

---

## Lessons Learned

- Restore testing is non-negotiable. Many "backup setups" written about online stop at the configuration step, which is the easy part. The hard part is confirming the backup actually contains what was expected and can be restored from.
- Clients often have inconsistent data inventory. Walking through the actual folders together produces a much better backup plan than asking the client to describe what should be backed up.
- One-page documentation is the right length. A 10-page manual will not be read. A single page covering what, where, and how to check fits on the side of a fridge and gets used.
- Cloud copies are not optional. A purely local backup does not protect against ransomware that encrypts connected drives.

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Periodic restore test | Pull a file back every few months to confirm the backup still works |
| Check the indicator light | The cloud backup tool shows a clear running state; checking it weekly is enough |
| Disconnect the external drive when not in use | An always-connected backup drive is also always at risk |
| Tell the technician if anything changes | New folder, new device, new important data, the backup plan should adjust |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Backup planning | 3-2-1 model implemented in a way the client could maintain |
| Data inventory | Identified what actually needed backup vs. what did not |
| Windows File History | Configured for incremental backup to local storage |
| Cloud backup configuration | Off-site mirror of priority folders |
| Restore validation | Confirmed both backup targets actually restored data |
| Client documentation | One-page reference covering what, where, and how to verify |
| Security-aware planning | Cloud copy specifically positioned as the ransomware defense |
| Client education | The client left the engagement understanding the plan, not just having it |
