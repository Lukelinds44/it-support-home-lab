# IT Support & Security Home Lab

Hands-on lab work I'm building to move into IT helpdesk and, from there, cybersecurity. Everything here runs on a MacBook (Apple silicon) using free tools, and every project is documented the way I would document a real support ticket: symptoms, diagnosis, root cause, fix, and verification.

## About me
- Finance degree, 4 months of self-directed study in IT and security
- TryHackMe: [tryhackme.com/p/lukeclindsay62](https://tryhackme.com/p/lukeclindsay62)
- Currently studying for: CompTIA A+ (exam not yet taken)
- Goal: IT helpdesk role, then security (SOC / GRC)

## Lab environment
| Item | Detail |
|---|---|
| Host | MacBook (Apple silicon), 8 GB RAM |
| Hypervisor | UTM (free) |
| Guest OS | Windows 11 Pro (ARM64) |
| Safety net | Clean cloned backup of the VM, restored when something breaks |

## Projects

| # | Project | Skills shown | Status |
|---|---|---|---|
| 1 | [Windows 11 Helpdesk Lab](projects/01-windows-helpdesk-lab/) | VM setup, driver install, Windows Update, backups, break/fix troubleshooting | In progress |
| 2 | Ticketing system (osTicket / GLPI) | ITSM workflow, ticket documentation | Planned |
| 3 | Identity and account management (Entra ID) | User accounts, groups, password resets, MFA | Planned |
| 4 | Network basics with Wireshark | DHCP, DNS, packet capture | Planned |
| 5 | Security monitoring with Wazuh | Log monitoring, alerts, detection | Planned |
| 6 | Scripting (PowerShell / Bash) | Automation, log parsing | Planned |

## Featured write-ups
- [Websites won't load: DNS troubleshooting](projects/01-windows-helpdesk-lab/dns-troubleshooting.md)
- [VM crash and recovery from backup](projects/01-windows-helpdesk-lab/crash-recovery.md)
- [Locked-out user: account unlock and password reset](projects/01-windows-helpdesk-lab/locked-out-user.md)

## How I document
Each scenario uses the same format: **Ticket, Symptoms, Diagnosis, Root cause, Fix, Verification, Notes.** I include what did not work, because that is where most of the learning happens.
