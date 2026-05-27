# Backup Checklist

Used during any client engagement involving backup planning, configuration, or validation.

---

## 1. Data Inventory

- [ ] Walk through the client's files together
- [ ] Identify the folders that genuinely need backup
- [ ] Identify the folders that do not need backup (system files, application installs, downloads, etc.)
- [ ] Estimate total backup data size
- [ ] Confirm whether any large or unusual file types need special handling

---

## 2. Backup Strategy

- [ ] Apply the 3-2-1 model where feasible:
  - 3 copies of important data
  - 2 different storage types
  - 1 copy off-site or in the cloud
- [ ] Identify the primary backup destination (typically an external drive)
- [ ] Identify the off-site or cloud destination
- [ ] Confirm both destinations have sufficient capacity, with room to grow

---

## 3. Local Backup Configuration

- [ ] External drive selected, formatted, and labeled clearly
- [ ] File History or equivalent backup tool configured
- [ ] Backup schedule appropriate to how the client uses the device
- [ ] First full backup completed and verified

---

## 4. Cloud Backup Configuration

- [ ] Cloud backup tool selected appropriate to the client's needs
- [ ] Account created or existing account verified
- [ ] Folders to back up explicitly selected (not defaulting to everything)
- [ ] First sync completed
- [ ] Sync state visible to the client without requiring technical knowledge

---

## 5. Restore Validation

This step is mandatory. A backup that has never been restored is not a backup.

- [ ] Select a sample file from the backed-up data
- [ ] Restore it from the local backup target to a different location
- [ ] Verify the restored file opens correctly
- [ ] Repeat the process from the cloud backup target
- [ ] Confirm both restores work end to end

---

## 6. Client Education

- [ ] Show the client what is being backed up
- [ ] Show the client where it is being backed up to
- [ ] Show the client how to check the backup is running
- [ ] Show the client how to perform a basic file restore themselves
- [ ] Explain why the off-site or cloud copy specifically defends against ransomware

---

## 7. Documentation

- [ ] Provide a one-page reference covering:
  - What is being backed up
  - Where each copy is stored
  - How to verify the backup is running
  - How to restore a single file
  - Who to contact for issues

---

## 8. Ongoing Recommendations

- [ ] Schedule a restore test every few months
- [ ] Disconnect the external drive when not in active backup use
- [ ] Notify the technician when new important data is created so the backup plan can adjust
- [ ] Review the backup at the same time as any major Windows or hardware change
