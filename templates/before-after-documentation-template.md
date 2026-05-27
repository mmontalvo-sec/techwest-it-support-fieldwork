# Before-After Documentation Template

Used to capture measurable changes from a service in a way that demonstrates value to the client and produces clean documentation suitable for a sanitized case study.

---

## Engagement

- Ticket or job number:
- Date:
- Device:
- Service performed:

---

## What Was Measured

State explicitly which metrics were captured before and after the work. Examples include:

- Boot time
- Application launch time
- Idle CPU temperature
- Load CPU temperature
- Idle memory usage
- Free disk space
- Disk read/write performance
- SMART status

Only include metrics that are relevant to the work performed.

---

## Baseline Capture (Before)

| Metric | Value | Tool Used |
|--------|-------|-----------|
| Example: Boot to desktop | [VERIFY exact time] seconds | Stopwatch from power button to login prompt |
| Example: Idle CPU temperature | [VERIFY exact value] °C | HWiNFO |
| Example: Idle memory usage | [VERIFY exact value] | Task Manager |

Capture the baseline before any change is made. A baseline taken after the first step of work is not a baseline.

---

## Post-Service Capture (After)

| Metric | Value | Tool Used |
|--------|-------|-----------|
| Example: Boot to desktop | [VERIFY exact time] seconds | Stopwatch |
| Example: Idle CPU temperature | [VERIFY exact value] °C | HWiNFO |
| Example: Idle memory usage | [VERIFY exact value] | Task Manager |

Use the same tools and the same measurement methodology as the baseline. A different tool can produce a different number for the same condition.

---

## Comparison

| Metric | Before | After | Change |
|--------|--------|-------|--------|
| Example: Boot to desktop | 220 seconds [VERIFY] | 30 seconds [VERIFY] | Substantially reduced |

For values where exact numbers are not available, use generic comparative language ("substantially reduced", "noticeably improved") rather than inventing numbers.

---

## Visual Evidence (If Captured)

| Asset | Description |
|-------|-------------|
| [Image filename] | [What it shows] |

If screenshots or photos are included, ensure they are sanitized: no client filenames, no identifying information, no visible serial numbers or asset tags.

---

## Honesty Note

If a metric did not improve, or improved less than expected, say so. The portfolio is more credible with honest results than with inflated ones.

---

## What This Demonstrates

Tie the measurable change back to the value delivered to the client.

Example:
"The boot time reduction means the client can start working substantially faster each morning, with no additional spending on new hardware."
