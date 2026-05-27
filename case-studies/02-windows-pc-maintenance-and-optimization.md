# Case Study 02: Windows PC Maintenance and Optimization

## Summary

A client desktop running Windows 10 was brought in with a complaint of slow performance, long boot times, and general unresponsiveness during normal use. The system was diagnosed, cleaned up, optimized, and validated. The client was provided with a written recommendations document covering routine maintenance going forward.

---

## Client Privacy Notice

All client identifying information has been removed. References use generic terms.

---

## Reported Issue

The client reported:

- Slow startup, taking several minutes to reach a usable state
- Programs taking a long time to open
- Browser feeling sluggish even on simple websites
- Occasional unresponsiveness when switching between applications
- The system was not displaying error messages or crashing, just consistently slow

---

## Initial Findings

| Observation | Detail |
|-------------|--------|
| Startup applications | A large number of third-party applications were configured to launch at startup |
| Temporary files | Multiple gigabytes of accumulated temporary files in user and system locations |
| Pending updates | Several Windows updates were pending |
| Browser state | Multiple browser extensions installed, several of which were unused |
| Disk health | SMART data via CrystalDiskInfo reported healthy status |
| Event Viewer | Recurring entries pointing to a service that was retrying on a known unstable schedule |
| Memory usage at idle | Higher than expected for the hardware profile, consistent with the startup application count |

---

## Diagnosis

The system was not failing. It was suffering from accumulated overhead: too many things starting at boot, too many resident applications, and a backlog of pending updates. No single component was at fault. The cumulative effect of normal use over time had degraded responsiveness.

---

## Tools and Methods Used

| Tool | Purpose |
|------|---------|
| Task Manager (Startup tab) | Identifying and disabling unnecessary startup applications |
| Settings > Apps | Reviewing installed applications and removing unused entries |
| Event Viewer | Identifying recurring errors and their root cause |
| Disk Cleanup and Storage Sense | Removing temporary files and Windows Update cache |
| Windows Update | Applying pending updates and validating completion |
| Windows Security | Running a full malware scan as a baseline check |
| Malwarebytes | Secondary scan to confirm no PUPs or adware were present |
| CrystalDiskInfo | Verifying that the storage was healthy and not a hidden cause of slowness |
| HWiNFO | Reviewing CPU and memory load patterns during baseline use |

---

## Work Performed

1. **Startup cleanup.** Disabled startup applications that did not need to launch automatically. Kept security software, audio drivers, and essential utilities enabled.
2. **Application audit.** Uninstalled unused applications, including expired trial software and pre-installed bloatware.
3. **Browser cleanup.** Removed unused extensions, cleared cache, and reviewed installed search providers.
4. **Temporary file removal.** Cleared Windows temp, browser caches, and Windows Update download cache.
5. **Windows updates.** Applied all pending feature and security updates. Validated post-update stability with a clean reboot cycle.
6. **Event Viewer review.** Identified the recurring service error and addressed it by disabling the unused service that was causing the entries.
7. **Malware baseline scan.** Confirmed no malicious software was present.
8. **Validation.** Rebooted and timed boot to desktop. Opened the applications the client used daily and confirmed they launched in a reasonable time.

---

## Outcome

| Aspect | Result |
|--------|--------|
| Boot time | Reduced from approximately 120 seconds to approximately 45 seconds after startup cleanup |
| Idle memory usage | Lowered by removing unnecessary startup applications |
| Application launch | Noticeably faster for the client's daily applications |
| Pending updates | None outstanding at handoff |
| Malware status | Clean |

The client confirmed the system felt significantly more responsive during a brief test session at handoff.

---

## Client Impact

The client got back the device they originally bought, performing closer to its original state. No hardware was replaced and no money was spent on parts. The work was a labor service producing a meaningful daily quality of life improvement.

---

## Lessons Learned

- Maintenance is preventive work. Performing this kind of cleanup once or twice a year prevents the cumulative slowdown that drives clients to assume they need a new computer.
- Startup applications are the largest single contributor to slow boot times on otherwise healthy hardware.
- Event Viewer is underused. Recurring errors that the user never sees often point to real causes of background instability.

---

## Recommended Prevention and Follow-Up

| Recommendation | Why |
|----------------|-----|
| Schedule routine cleanup every 6 to 12 months | Prevents accumulated overhead from returning |
| Review startup applications quarterly | Catches new applications that quietly add themselves to startup |
| Keep Windows updates current | Avoids the buildup of pending updates that consume resources |
| Avoid installing software unless needed | Each install increases startup load and disk usage |
| Reboot weekly | Clears memory state and applies pending updates that require restart |

---

## Skills Demonstrated

| Skill | Where in This Case |
|-------|-------------------|
| Windows performance diagnostics | Identification of startup, update, and event log contributors |
| Event Viewer interpretation | Locating recurring errors that affected baseline stability |
| System cleanup | Targeted removal of unused applications, files, and startup entries |
| Update management | Resolving pending updates and validating system stability afterward |
| Malware baseline scanning | Windows Security and Malwarebytes as a confirmation step |
| Client communication | Explaining why the system was slow in language tied to specific causes |
| Preventive recommendations | Written maintenance guidance for the client to follow going forward |
