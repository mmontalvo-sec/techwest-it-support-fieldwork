# Printer Troubleshooting Checklist

Used for any reported issue involving printing on a Windows endpoint. Covers USB, network, and Wi-Fi printer scenarios.

---

## 1. Confirm the Symptom

- [ ] Reproduce the issue with the client present, if possible
- [ ] Confirm whether the issue affects all applications or just one
- [ ] Confirm whether other devices on the network can print to the same printer
- [ ] Confirm the printer is powered on and not in an error or paper-jam state

---

## 2. Printer Hardware Check

- [ ] Display panel shows no error
- [ ] Paper tray loaded
- [ ] Toner or ink not depleted
- [ ] No paper jam visible
- [ ] Power cycle the printer

---

## 3. Connection Check

### USB

- [ ] Cable is fully seated on both ends
- [ ] Cable tested or substituted if doubt exists
- [ ] USB port functional (test by plugging another device)

### Network or Wi-Fi

- [ ] Printer reachable on the network: `ping <printer-ip>`
- [ ] Printer on the same subnet as the client device
- [ ] Wi-Fi printers connected to the correct SSID
- [ ] Printer IP not changed (static or reservation recommended)

---

## 4. Windows-Side Diagnostics

- [ ] `Settings > Printers & scanners` lists the printer
- [ ] Printer status shows as "Ready" or "Online", not "Offline" or "Paused"
- [ ] Correct printer is set as default
- [ ] "Let Windows manage my default printer" is disabled in environments with multiple printers
- [ ] Print queue reviewed for stuck jobs

---

## 5. Print Spooler

- [ ] Print Spooler service is running (`services.msc`)
- [ ] If stuck jobs are present:
  - [ ] Stop the Print Spooler service
  - [ ] Clear contents of `C:\Windows\System32\spool\PRINTERS\`
  - [ ] Restart the Print Spooler service

---

## 6. Driver Check

- [ ] Current driver identified via Device Manager
- [ ] If driver is corrupt or generic, remove the printer and the associated driver
- [ ] Download the current driver directly from the manufacturer
- [ ] Reinstall the driver as administrator
- [ ] Add the printer fresh

---

## 7. Test

- [ ] Windows test page printed successfully
- [ ] Real document from the client's most-used application printed successfully
- [ ] Duplex (if applicable) works as expected
- [ ] Color printing (if applicable) renders correctly

---

## 8. Configuration

- [ ] Default printer locked to the correct device
- [ ] Default duplex setting matches client preference
- [ ] Default paper size correct
- [ ] Default tray correct

---

## 9. Client Education

- [ ] Show the client how to view the Print Queue
- [ ] Show the client how to clear a single stuck job
- [ ] Show the client how to set the default printer
- [ ] Provide a brief written summary of basic recovery actions

---

## 10. Documentation

- [ ] Service report completed
- [ ] Printer model and driver version recorded
- [ ] Configuration choices noted
- [ ] Recommendations provided
