# Scenario: VM crash and recovery from backup

**Environment:** Windows 11 Pro (ARM64) virtual machine in UTM on an Apple silicon MacBook.
**Category:** System crash / boot failure / backup restore

---

## Ticket
While practicing a break/fix scenario, I tried to disable the Ethernet adapter. The whole VM shut down, and afterward Windows would not recover.

## Symptoms
- Clicking **Disable** on the Ethernet adapter in Network Connections shut the VM down immediately. The VM restarted to the UTM boot logo.
- The same crash happened on a second attempt, so it was reproducible.
- After force-stopping the VM, Windows showed an error saying it could not be recovered, along with more recovery options.

## Diagnosis steps
1. Confirmed I was working in the lab VM and not the clean backup.
2. Waited for the VM to finish restarting after the first crash instead of interrupting it.
3. Reproduced the crash a second time to confirm it was tied to disabling the adapter, then stopped testing that action.
4. Tried the recovery options Windows offered. They did not get the VM booting again, so I moved to restoring from my backup.

## Root cause
Not proven. Two likely causes:
- Disabling the adapter appears to crash the VM's virtual network driver, which was reproducible in this setup.
- A forced shutdown during a crash can leave Windows boot files in a damaged state.

## Fix
Deleted the broken VM and cloned my clean backup (Win11-CLEAN-BACKUP) into a new lab VM. ![Backup and restored VM in UTM](screenshots/13-utm-backup-clone.png)

## Verification
- The new VM booted to the Windows desktop and I could log in.
- Edge loaded a website.

## Notes and lessons learned
- **Backups are what make a lab safe.** I made the clean clone before breaking anything, so recovery took minutes instead of a full reinstall.
- **Stop repeating an action that crashes the system.** After the second crash I stopped and used a different method to simulate a network problem (see [dns-troubleshooting.md](dns-troubleshooting.md)).
- **Record the evidence before recovering.** I did not capture the error code or check Event Viewer, so I can't prove the root cause. Next time I will screenshot the error screen and review the System log first.
- **Shut down from inside Windows** (Start > Power > Shut down) rather than using the VM stop button, except in an emergency.
- **Avoid force-stopping during writes.** Hard stops risk corrupting boot files.
