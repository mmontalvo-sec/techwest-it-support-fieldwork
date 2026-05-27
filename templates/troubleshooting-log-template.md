# Troubleshooting Log Template

A working document used during diagnostics. Captures what was tried, in what order, and what the result was. This becomes the basis for the eventual service report.

---

## Header

- Ticket or job number:
- Device:
- Operating system:
- Date started:
- Technician:

---

## Reported Issue

A one-sentence summary of the symptom.

---

## Hypothesis Tracking

| Hypothesis | Reason to Believe | Test Plan | Result |
|------------|------------------|-----------|--------|
| Example: Failing memory module | Crashes appear across multiple apps; WHEA-Logger errors in Event Viewer | MemTest86 multi-pass on each module | Errors confirmed on module B at consistent address range |

Use one row per hypothesis. Each hypothesis must have a clear test plan, not just a belief.

---

## Step-by-Step Log

| Step | Time | Action | Result |
|------|------|--------|--------|
| 1 | | | |
| 2 | | | |
| 3 | | | |

Fill rows as work proceeds. The log is most useful when it is honest, including dead ends and failed tests.

---

## Tools Used

List of every tool actually used during diagnostics.

---

## Confirmed Findings

What is now known for certain after diagnostics. Distinguish between confirmed facts and remaining hypotheses.

---

## Remaining Uncertainty

What is still not known, and why.

---

## Recommendation

The next step based on what is now known.

---

## Notes for Service Report

Any items from this log that should be carried into the final service report delivered to the client.
