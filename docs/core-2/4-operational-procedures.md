<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [Core 2, Domain 3: Software Troubleshooting](3-software-troubleshooting.md) · Next: [Performance-based questions and pacing](../performance-based-questions.md)
<!-- /nav:top -->

# Core 2, Domain 4: Operational Procedures

**Weight:** 21% of the Core 2 exam (220-1202) (CompTIA's figure). By our estimate that is roughly 18 of up to 90 questions. **Objectives:** 4.1 to 4.10.

This domain is how a professional technician works, not which button to press: writing tickets others can follow, getting changes approved, keeping backups that actually restore, working safely, disposing of batteries and toner properly, handling licenses and private data, talking to upset users, and using scripts, remote tools and AI without causing harm. It has the most objectives in Core 2 and many of them feel like common sense, which is exactly why candidates lose marks: two answers sound reasonable, and only one follows the formal procedure.

## What this domain measures

Ten objectives. Some are "Given a scenario" (apply it to a situation) and some are "Explain" or "Summarize" (know what the term means and why it matters).

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 4.1 | Use documentation and support systems well | Ticketing (user and device details, issue description, categories, severity, escalation levels, clear notes), asset management (inventory, CMDB, asset tags, procurement life cycle, warranty, licensing, assigned users), incident reports, SOPs, onboarding and offboarding checklists, SLAs, knowledge base articles |
| 4.2 | Apply change management procedures | Documented business processes, rollback and backup plans, sandbox testing, responsible staff, request forms, purpose, scope, change types (standard, normal, emergency), date and time, change freeze, maintenance windows, affected systems, risk analysis, change board approval, implementation, peer review, end-user acceptance |
| 4.3 | Implement workstation backup and recovery | Full, incremental, differential and synthetic full backups, in-place and alternative location recovery, backup testing and frequency, onsite vs offsite, grandfather-father-son, 3-2-1 rule |
| 4.4 | Use common safety procedures | ESD straps and mats, equipment grounding, component handling and storage, antistatic bags, cable management, government regulations, disconnecting power, lifting, fire safety, goggles, air filter masks |
| 4.5 | Summarize environmental impacts and controls | MSDS for handling and disposal, battery, toner and device disposal, temperature, humidity, ventilation, equipment placement, dust cleanup, compressed air and vacuums, surges, brownouts, blackouts, UPS, surge suppressor |
| 4.6 | Explain prohibited content, privacy, licensing and policy | Incident response (chain of custody, informing management or law enforcement, drive copies, documentation, order of volatility), licensing, DRM, EULA, perpetual, personal vs corporate, open source, NDA and MNDA, regulated data (card data, government IDs, PII, healthcare), data retention, AUP, compliance, splash screens |
| 4.7 | Use proper communication and professionalism | Attire, plain language, positive attitude, active listening, cultural sensitivity, punctuality, avoiding distractions, difficult customers, open-ended questions, setting expectations, follow-up, handling confidential material |
| 4.8 | Explain the basics of scripting | .bat, .ps1, .vbs, .sh, .js, .py; use cases (automation, restarts, drive mapping, installs, backups, gathering data, updates); risks (malware, changed settings, crashes from mishandled resources) |
| 4.9 | Use remote access technologies | RDP, VPN, VNC, SSH, RMM, SPICE, WinRM, screen-sharing, videoconferencing, file transfer and desktop management tools, security of each |
| 4.10 | Explain basic AI concepts | Application integration, policy (appropriate use, plagiarism), limitations (bias, hallucinations, accuracy), private vs public AI (data security, data source, data privacy) |

## Key concepts explained

### 4.1 Documentation and ticketing

**What a good ticket holds.**

| Field | Example |
|---|---|
| User information | Name, department, contact number, location |
| Device information | Asset tag, hostname, model, OS version |
| Description of issue | What happens, when it started, error text, what the user already tried |
| Category | Hardware, software, network, account access, printer |
| Severity | How badly it hurts the business: one user with a cosmetic issue vs the whole sales floor offline |
| Escalation level | Tier 1 (help desk, first contact), Tier 2 (deeper technical support), Tier 3 (specialists, engineers or the vendor) |

**Clear, concise written communication** in three places:

- **Issue description:** facts, not guesses. "Outlook closes with error 0x800CCC0E when sending, since 09:00 today" beats "email broken".
- **Progress notes:** what you did, what you found, and what happens next, with times. Another technician should be able to pick up the ticket without calling you.
- **Issue resolution:** the cause and the fix, written so it can become a knowledge base article. "Replaced expired cached password in Credential Manager; user confirmed sending works" beats "fixed".

**Asset management.**

| Term | Meaning |
|---|---|
| Inventory list | A list of every device and its details |
| Configuration management database (CMDB) | A database of configuration items (hardware, software, services) and how they relate to each other, so you can see what a change will affect |
| Asset tags and IDs | Labels (barcode or ID number) that link a physical device to its record |
| Procurement life cycle | Request, approve, buy, receive, tag and deploy, maintain, then retire and dispose |
| Warranty and licensing | When support ends, and which software licenses are assigned to the device |
| Assigned users | Who has the device, so it can be recovered when they leave |

**Types of documents.**

| Document | Use |
|---|---|
| Incident report | A record of an unusual event (a security incident, an injury, a major outage): what happened, when, who was involved, what was done |
| Standard operating procedure (SOP) | Step-by-step instructions for a routine task, such as a custom software package installation |
| New user onboarding checklist | Account, email, group memberships, device, software, access badge, training, all ready by day one |
| User offboarding checklist | Disable accounts, collect devices and badges, transfer files and mailbox, remove access. Done on the person's last day |
| Service-level agreement (SLA) | Agreed response and resolution times. Internal SLAs are between IT and other departments; external or third-party SLAs are with vendors and service providers |
| Knowledge base articles | Searchable fixes for known problems, used by technicians and sometimes by users for self-help |

### 4.2 Change management

Change management makes sure nobody changes a production system on a whim. Every change is requested, assessed, approved, scheduled, tested and documented, with a way back if it fails.

**What a change request covers.**

| Part | Meaning |
|---|---|
| Request form | The formal document that starts the process |
| Purpose of the change | Why it is needed: the business reason |
| Scope of the change | Exactly what will change, and what will not |
| Date and time | When it happens. Usually inside a **maintenance window** (an agreed low-impact time, such as Sunday 02:00) and never during a **change freeze** (a period when no changes are allowed, such as year-end) |
| Affected systems and impact | Which systems, users and services will be touched, and how |
| Risk analysis and risk level | What could go wrong, how likely, how bad: low, medium, high |
| Responsible staff members | Who carries it out and who owns it |
| Rollback plan | How to undo the change if it fails |
| Backup plan | A backup taken before the change, so data can be restored |
| Sandbox testing | Trying the change first in an isolated test environment that matches production |

**Change types.**

| Type | When it applies | Approval |
|---|---|---|
| Standard change | Routine, low-risk, done often in the same way (for example, an approved monthly patch or adding a user to a printer) | Preapproved; follows the SOP |
| Normal change | Anything else that needs assessment (for example, upgrading the file server) | Reviewed and approved by the change board before it is scheduled |
| Emergency change | Must happen now to fix or prevent a serious outage or security problem | Fast-tracked approval by a smaller group, documented fully afterwards |

**The flow.** Request, then risk analysis and sandbox testing, then **change board approval** (often called the change advisory board, CAB), then implementation in the maintenance window, with **peer review** of the work, then **end-user acceptance** (users confirm things work), then documentation. If the change fails, follow the rollback plan.

**Documented business processes** are the written steps that the change process itself and all routine work follow, so everyone does it the same way.

### 4.3 Workstation backup and recovery

**Backup types.** The archive bit is a file attribute that Windows sets when a file changes. Backup software uses it, or its own catalog, to know what changed.

| Type | What it copies | Archive bit | Backup speed | Restore needs |
|---|---|---|---|---|
| Full | Everything selected | Cleared | Slowest, most space | Just the last full |
| Incremental | Changes since the last backup of any kind | Cleared | Fastest, least space | Last full plus every incremental since, in order |
| Differential | Changes since the last full | Not cleared, so each differential grows | Medium, grows each day | Last full plus the latest differential only |
| Synthetic full | A new full built on the backup system by combining the last full with later incrementals | Not applicable: the source is not read again | Light on the source PC and network | Restores like a normal full |

**Worked example.** A full backup runs Sunday night. A drive fails on Thursday morning, after Wednesday night's backup.

- With **incrementals** each night Monday to Wednesday, restore Sunday's full, then Monday's, Tuesday's and Wednesday's incrementals, in that order. That is 4 backup sets. If Tuesday's incremental is damaged, Wednesday's cannot be applied correctly either.
- With **differentials** each night, restore Sunday's full and Wednesday's differential. That is 2 backup sets, but Wednesday's differential holds everything changed since Sunday, so it took longer to make than Wednesday's incremental would have.

Rule of thumb: incremental is fast to back up and slow to restore; differential is the reverse.

**Recovery options.**

| Method | Meaning | Use when |
|---|---|---|
| In-place (overwrite) | Restore files to their original location, replacing what is there | The original is lost or corrupted and you want it back where it was |
| Alternative location | Restore to a different folder, drive or machine | You want to compare versions, avoid overwriting newer work, or the original hardware is gone |

**Backup testing.** A backup is only as good as its last successful restore. Test by restoring real files to an alternative location, on a regular schedule (frequency set by policy, for example monthly), and after any change to the backup system.

**Rotation schemes.**

| Scheme | Meaning |
|---|---|
| Onsite vs offsite | Onsite copies restore quickly. Offsite copies (another building, or cloud) survive fire, flood or theft at the main site. You want both |
| Grandfather-father-son (GFS) | Daily backups (son), weekly backups (father) and monthly backups (grandfather). Each level is kept for longer, for example dailies for a week, weeklies for a month, monthlies for a year. This gives many restore points without keeping every daily forever |
| 3-2-1 backup rule | At least 3 copies of the data, on 2 different types of media, with 1 copy offsite |

### 4.4 Safety procedures

**Electrostatic discharge (ESD).** Static you cannot even feel can damage chips.

- **ESD strap:** a wrist strap with a clip attached to an unpainted metal part of the computer chassis or to a ground point, so you and the PC stay at the same potential.
- **ESD mat:** a grounded mat you place components on while working.
- **Antistatic bags:** store and carry boards, RAM and drives inside them.
- **Proper handling:** hold cards and modules by the edges, never touch the contacts or chips, and work on a hard surface rather than carpet.

**Electrical safety.**

- **Disconnect power before repairing a PC.** Unplug it, then press the power button to drain any stored charge.
- **Equipment grounding:** devices with three-prong plugs connect their metal case to ground, which protects people if a fault happens. Never remove or bypass the ground pin.
- **Power supplies:** do not open a PSU. Its capacitors can hold a dangerous charge after it is unplugged. Replace the whole unit. Never wear an ESD strap while working near high voltage.

**Personal safety.**

| Hazard | Safe practice |
|---|---|
| Lifting | Bend your knees, keep your back straight, lift with your legs, keep the load close. Get help or a cart for heavy items such as servers and large printers |
| Fire | Know where the extinguishers and exits are. For electrical fires, use an extinguisher rated for electrical fires (Class C in the US, such as CO2). Never use water on electrical equipment |
| Eyes | Safety goggles when cutting cable, working with compressed air or cleaning dusty equipment |
| Lungs | An air filter mask when cleaning toner spills or heavy dust |
| Trips | Cable management: route cables along walls and through cable trays, use covers across walkways, tie cables neatly |

**Compliance with government regulations.** Workplaces must follow local health and safety laws (in the US, OSHA rules). When the company procedure and the law differ, follow the law.

### 4.5 Environmental impacts and controls

**Material safety data sheet (MSDS).** A document from the manufacturer for each hazardous product, describing safe handling, storage, first aid, spill cleanup and disposal. Newer documents use the name safety data sheet (SDS). When unsure how to dispose of something, read its MSDS.

| Item | Proper disposal |
|---|---|
| Batteries | Never in normal trash. Lithium-ion and other batteries go to a battery recycling point. Swollen batteries should be handled carefully and not punctured |
| Toner cartridges | Return to the manufacturer's recycling program or a recycler; follow the MSDS. Clean spills with a toner-rated vacuum, not a normal vacuum, which can spread the fine powder |
| Other devices and assets | Use certified e-waste recyclers, follow local rules, and wipe or destroy storage first (see Domain 2, Objective 2.9) |

**Temperature, humidity and ventilation.**

- Hot rooms shorten component life and cause shutdowns. Keep equipment cool and give it airflow.
- Low humidity increases static electricity (more ESD risk). High humidity can cause condensation and corrosion.
- **Location and placement:** keep PCs off the floor where dust collects, keep vents clear, keep equipment away from heaters, windows and water.
- **Dust cleanup:** use compressed air (held upright, in short bursts, outdoors or in a ventilated area) or an ESD-safe vacuum. Hold fan blades still while blowing them, so they do not spin too fast.

**Power problems.**

| Event | Meaning | Protection |
|---|---|---|
| Power surge | A short spike above normal voltage | Surge suppressor (rated in joules), or a UPS with surge protection |
| Brownout | A sustained drop below normal voltage | UPS, which supplies steady power from its battery |
| Blackout | Complete loss of power | UPS, to keep running long enough to save work and shut down cleanly |

A surge suppressor does nothing in a blackout. A UPS gives minutes, not hours, of runtime: enough to shut down gracefully.

### 4.6 Prohibited content, privacy, licensing and policy

**Incident response for prohibited content.** If you find illegal or prohibited content (for example on a PC you are repairing), your job is not to investigate it yourself.

1. Stop work and do not delete, move or open more files.
2. Inform management (and law enforcement, if policy or law requires it) following company policy.
3. Preserve the evidence. If a copy is needed, a **copy of the drive** is made as a forensic image and its hash recorded, so it can be proven unchanged (data integrity and preservation).
4. Keep the **chain of custody**: a written record of who had the evidence, when, and what they did with it. A gap makes the evidence less useful.
5. Write **incident documentation**: what you found, where, when, and what you did.

**Order of volatility.** Collect the evidence that disappears fastest first: CPU registers and cache, then RAM, then temporary files and swap space, then disk, then remote logs, and finally archived backups. Pulling the power loses everything in RAM.

**Licensing.**

| Term | Meaning |
|---|---|
| Valid license | Proof the software is legally licensed for this use. Unlicensed software is a legal and security risk |
| Perpetual license | Pay once, use that version indefinitely (upgrades may cost extra). Contrast with subscription licenses that stop working when payments stop |
| Personal-use license | For home, non-commercial use only. Using it at work breaks the license |
| Corporate-use license | For business use, often per user, per device or as a volume or site license |
| Open-source license | Source code is available and can be used, changed and shared under the license's terms, which can still have conditions |
| Digital rights management (DRM) | Technology that limits copying or use of software and media |
| End-user license agreement (EULA) | The contract the user accepts when installing; it sets what is allowed |

**Agreements and policies.**

- **NDA:** a non-disclosure agreement, where one side agrees to keep the other's information secret. An **MNDA** (mutual NDA) binds both sides.
- **Acceptable use policy (AUP):** the rules for what users may and may not do with company systems, such as no personal file sharing or no installing unapproved software.
- **Splash screens:** a banner shown at sign-in that states the system is for authorized use and may be monitored. It supports regulatory and business compliance requirements.

**Regulated data.**

| Type | Examples | Notes |
|---|---|---|
| Credit card payment information | Card numbers, expiry dates, security codes | Covered by the Payment Card Industry Data Security Standard (PCI DSS) |
| Personal government-issued information | Social Security numbers, passport and driver's license numbers | High identity-theft risk |
| PII (personally identifiable information) | Names with addresses, birth dates, phone numbers | Anything that identifies a person |
| Healthcare data | Medical records, insurance details | In the US, covered by HIPAA |
| Data retention requirements | Laws and policies that say how long data must be kept, and when it must be destroyed | Do not delete early, and do not keep longer than allowed |

### 4.7 Communication and professionalism

| Practice | What it looks like |
|---|---|
| Professional appearance | Match the attire to the setting: formal in a law office or executive meeting, business casual for most offices |
| Proper language | No jargon, acronyms or slang with users. "Your PC can't reach the internet" rather than "your DHCP lease failed" |
| Positive attitude | Show confidence that the problem will be solved |
| Active listening | Let the user finish, take notes, do not interrupt |
| Cultural sensitivity | Use proper professional titles (Dr., Professor) when applicable, and respect cultural differences |
| Be on time | If you will be late, contact the customer before the appointment time |
| Avoid distractions | No personal calls, texting or social media, no personal interruptions while with a customer |
| Difficult customers | Do not argue or get defensive, do not dismiss their issue, do not judge. Clarify with open-ended questions, restate the issue, and ask questions to confirm you understand |
| Set and meet expectations | Give a timeline and keep the customer informed of status. Offer repair or replacement options where they exist, and provide documentation of what you did |
| Follow up | Contact the user later to confirm the fix held and they are satisfied |
| Confidential material | Do not read, copy or comment on private documents on the desk, screen or printer. Use discretion when talking about what you saw at other customer sites |

**Open-ended vs closed questions.** Open-ended questions ("What happens when you try to print?") gather information and narrow the scope. Closed questions ("Is the printer turned on?") confirm a detail. Start open, then close.

### 4.8 Scripting basics

**Script file types.**

| Extension | Language | Runs on | Comment line starts with |
|---|---|---|---|
| `.bat` | Windows batch (Command Prompt) | Windows | `REM` or `::` |
| `.ps1` | PowerShell | Windows (PowerShell also runs on Linux and macOS) | `#` |
| `.vbs` | VBScript (Windows Script Host) | Windows | `'` |
| `.sh` | Shell script (such as Bash) | Linux and macOS | `#` |
| `.js` | JavaScript | Browsers, Node.js, or Windows Script Host | `//` |
| `.py` | Python | Any OS with Python installed | `#` |

On Windows, PowerShell's execution policy can stop `.ps1` scripts from running at all. That is a safety feature, not a fault.

**Use cases.** Basic automation of repeated tasks, restarting machines on a schedule, remapping network drives at sign-in, installing applications on many PCs, running automated backups, gathering information and data (inventory, disk space, installed software) and initiating updates.

**Other considerations.**

- **Unintentionally introducing malware:** a script downloaded from a forum can hide malicious commands. Read and understand any script before running it, and get scripts from trusted sources.
- **Inadvertently changing system settings:** a script that runs as admin can change the registry, firewall or services across every PC it touches. Test in a sandbox first.
- **Browser or system crashes due to mishandling of resources:** a loop that never ends, or a script that opens files or memory and never releases them, can freeze a browser or the whole system.

### 4.9 Remote access technologies

| Method | What it is | Default port | Security notes |
|---|---|---|---|
| RDP (Remote Desktop Protocol) | Full Windows desktop of a remote PC | TCP 3389 | Never expose directly to the internet. Put it behind a VPN or gateway, require Network Level Authentication and strong passwords or MFA |
| VPN (virtual private network) | An encrypted tunnel into the company network | Depends on the VPN type | Use MFA; a VPN gives network access, so keep the device secure |
| VNC (virtual network computing) | Shares a screen across platforms | TCP 5900 | Older setups use weak passwords and little encryption; tunnel it over SSH or VPN |
| SSH (Secure Shell) | Encrypted command-line access, mainly to Linux, network devices and servers | TCP 22 | Prefer key-based sign-in, disable direct root login |
| RMM (remote monitoring and management) | Agent software that lets a managed service provider monitor, patch, script and remote-control many client devices | Vendor specific | Very powerful: a stolen RMM login reaches every managed device, so protect it with MFA |
| SPICE (Simple Protocol for Independent Computing Environments) | A remote display protocol for virtual machines, often used with KVM and QEMU | Varies | Use encryption where offered and limit who can connect |
| WinRM (Windows Remote Management) | Runs commands and PowerShell remotely on Windows | TCP 5985 (HTTP), 5986 (HTTPS) | Restrict to admin hosts and prefer HTTPS |

**Third-party tools.**

| Tool type | Use | Security note |
|---|---|---|
| Screen-sharing software | Help desk views or controls a user's screen with consent | Scammers use the same tools: users should only accept sessions they requested from known IT staff |
| Videoconferencing software | Meetings that can also share screens | Control who can share and enter meetings |
| File transfer software | Moves files between systems | Use encrypted transfer and limit access |
| Desktop management software | Central management of software, settings and updates on many PCs | Admin rights over many devices, so protect accounts carefully |

**Choosing a tool.** Need a full Windows desktop: RDP. Need command line on a Linux server or switch: SSH. Need to run PowerShell on remote Windows machines: WinRM. Need to reach internal systems from home: VPN first. A managed service provider looking after hundreds of client PCs: RMM. Help a user who must watch what you do: screen sharing.

### 4.10 Artificial intelligence basics

**Application integration.** AI features now sit inside everyday tools: assistants in office suites, email drafting, ticket summaries, chatbots on help desk portals, code helpers. They can save time, but the user is still responsible for the result.

**Policy.**

- **Appropriate use:** company policy says which AI tools are approved, for what tasks, and with what data.
- **Plagiarism:** presenting AI output, or content it copied, as your own original work can break academic or company rules and copyright.

**Limitations.**

| Limitation | Meaning | Example |
|---|---|---|
| Bias | Output reflects bias in the training data | A screening tool that favors one group of applicants |
| Hallucinations | The AI states made-up facts with confidence | Inventing a PowerShell command or a registry key that does not exist |
| Accuracy | Answers may be outdated, incomplete or wrong | Instructions for an older version of the software |

Always verify AI output before acting on it, especially commands that change systems.

**Private vs public AI.**

| | Public AI | Private AI |
|---|---|---|
| Data security | What you type may be stored by the provider and used to train future models | Runs in the company's controlled environment or under a contract that keeps data in |
| Data source | Trained on broad internet data | Can be grounded in the company's own documents |
| Data privacy | Pasting PII, customer records or company secrets may break policy and regulations | Designed for company data, within the approved rules |

## How questions look

Expect short workplace scenarios: an angry user, a technician who finds something on a laptop, a server that keeps shutting down during storms, a backup schedule and a failed drive, a change that went wrong, a script someone found online. Watch the qualifiers: "FIRST", "BEST", "MOST appropriate" and "NEXT". Backup items often include a small schedule table and ask which backups to restore. Scripting items may show a few lines of a script and ask which file type it is or what it does. Performance-based tasks can ask you to match backup types to descriptions, match remote access tools to needs, order change management steps, or pick the right disposal method for each item. Some items ask you to "Choose two."

## A method for these questions

1. Identify the objective. Ticket, change, backup, safety, environment, policy, communication, script, remote tool or AI: each has its own "right way".
2. Look for the formal process. Exam answers follow procedure: documented, approved, tested, preserved. An answer that skips approval or documentation is usually wrong, even if it is fast.
3. For backup restores, write the schedule as a list, mark the failure point, then count: full plus every incremental since, or full plus the latest differential.
4. For safety, pick the answer that protects the person first, then the equipment.
5. For prohibited content, the technician stops, reports and preserves. Never deletes, never investigates alone.
6. For communication, choose the response that listens, stays calm, uses plain words and sets a clear next step.
7. For remote access, match the tool to the platform and need, then pick the more secure way to use it.

## Traps that cost points

- **Restoring only the last incremental.** Incrementals depend on each other: you need the full plus every incremental since, in order. Only differentials need just full plus the latest one.
- **Picking a surge suppressor for brownouts.** A surge suppressor only absorbs spikes. Sustained low voltage or a blackout needs a UPS.
- **Skipping the change board because it is "only small".** Only preapproved standard changes skip review. Anything else needs approval, and emergencies are documented afterwards.
- **No rollback plan.** A change without a way back is incomplete, even if it was tested.
- **Deleting prohibited content.** That destroys evidence and can make the technician part of the problem. Stop, report, preserve.
- **Shutting down first during an investigation.** Pulling power loses RAM contents. Order of volatility puts RAM before disk.
- **Wearing an ESD strap near high voltage.** ESD straps are for low-voltage components. Never open a power supply.
- **Exposing RDP to the internet.** Port forwarding 3389 invites brute force. Require a VPN or gateway first.
- **Using a personal-use license at work.** It may install fine, but it breaks the license. Business use needs a corporate license.

## Timing

Each Core 2 exam is one 90-minute block of up to 90 questions, so aim for about 1 minute per multiple-choice item on average, with extra time for performance-based questions. Communication, safety and policy items are quick if you trust the "formal procedure" rule. Bank that time for backup schedule tables and script exhibits, where it pays to write the days down on your scratch material and count carefully.

## Practice items

These 2 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A small office uses this backup schedule on its main workstation:

```
Sunday 23:00     Full
Monday 23:00     Incremental
Tuesday 23:00    Incremental
Wednesday 23:00  Incremental
Thursday 23:00   Incremental
```

The drive fails on Thursday at 14:00. Which backups must be restored to recover the most recent data?

A. Sunday's full, then Monday's, Tuesday's and Wednesday's incrementals, in that order

B. Sunday's full and Wednesday's incremental only

C. Wednesday's incremental only

D. Sunday's full only

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Each incremental holds only the changes since the backup before it, so you need the full plus every incremental since, applied in order. Thursday's backup has not run yet. (Objective 4.3)

- **B** is wrong because that is the method for differential backups; it would lose Monday's and Tuesday's changes.
- **C** is wrong because an incremental cannot be restored on its own without the full.
- **D** is wrong because it loses three days of work.

</details>

### Item 2

While repairing a laptop for a staff member, a technician opens a folder to check a sync error and sees images that appear to be illegal. What should the technician do FIRST?

A. Delete the images so no one else sees them

B. Stop working on the laptop and report it to management, following company policy

C. Copy the images to a USB drive to show the user's manager as proof

D. Finish the repair quickly and return the laptop without comment

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The technician should stop, not touch anything further, and report through the proper channel so the evidence is preserved and chain of custody can begin. (Objective 4.6)

- **A** is wrong because deleting destroys evidence.
- **C** is wrong because copying spreads the content and breaks the chain of custody.
- **D** is wrong because ignoring it fails the company's policy and possibly the law.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 | 2 |
|---|---|---|
| Answer | A | B |
| Objective | 4.3 | 4.6 |

- **2 of 2:** strong. Keep the backup maths and remote access ports fresh with mixed practice.
- **1 of 2:** note which objectives you missed. Backup restores and change order are the usual slips: redo the worked example in [4.3 Workstation backup and recovery](#43-workstation-backup-and-recovery) and reread [4.2 Change management](#42-change-management).
- **0 of 2:** spend two study sessions here. Write the backup types table and the remote access table from memory, then reread [4.4 Safety procedures](#44-safety-procedures), [4.6 Prohibited content, privacy, licensing and policy](#46-prohibited-content-privacy-licensing-and-policy) and [4.9 Remote access technologies](#49-remote-access-technologies) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Write a one-week backup schedule on paper (full on Sunday, then incrementals, then differentials), pick a failure day and list exactly which sets you would restore for each. Then write a three-line `.bat` file that runs `ipconfig /all > C:\temp\ipinfo.txt`, run it on a test PC, and read the output.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [Core 2, Domain 3: Software Troubleshooting](3-software-troubleshooting.md) | Next: [Performance-based questions and pacing](../performance-based-questions.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
