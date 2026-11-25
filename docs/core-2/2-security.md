<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [Core 2, Domain 1: Operating Systems](1-operating-systems.md) · Next: [Core 2, Domain 3: Software Troubleshooting](3-software-troubleshooting.md)
<!-- /nav:top -->

# Core 2, Domain 2: Security

**Weight:** 28% of the Core 2 exam (220-1202) (CompTIA's figure), tied with Operating Systems as the heaviest Core 2 domain. By our estimate that is roughly 25 of up to 90 questions. **Objectives:** 2.1 to 2.11.

This domain is the security side of a help desk job: locking down Windows, picking the right Wi-Fi settings, spotting malware and scams, cleaning an infected PC in the right order, securing phones and small office routers, and getting rid of old drives safely. Most questions are short scenarios where two answers sound sensible, and marks are lost by picking a control that is real but weaker, or a step that is right but out of order.

## What this domain measures

Eleven objectives, more than any other Core 2 domain. Several start with "Given a scenario", which means you must apply the idea to a situation, not just recognize the term.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 2.1 | Summarize security measures and their purposes | Bollards, access control vestibules, badge readers, cameras, alarms, locks, guards, fences, key fobs, smart cards, mobile digital keys, biometrics, lighting, magnetometers, least privilege, Zero Trust, ACLs, MFA methods, SAML, SSO, just-in-time access, PAM, MDM, DLP, IAM, directory services |
| 2.2 | Configure basic Windows security settings | Defender Antivirus, Windows Firewall, local vs Microsoft accounts, account types, sign-in options, Windows Hello, NTFS vs share permissions, attributes, inheritance, Run as administrator, UAC, BitLocker, BitLocker To Go, EFS, Active Directory tasks |
| 2.3 | Compare wireless security protocols and authentication | WPA2, WPA3, TKIP, AES, RADIUS, TACACS+, Kerberos, multifactor |
| 2.4 | Summarize malware and how to detect, remove and prevent it | Trojan, rootkit, virus, spyware, ransomware, keylogger, boot sector virus, cryptominer, stalkerware, fileless, adware, PUP, recovery console, EDR, MDR, XDR, antivirus, anti-malware, email gateway, software firewall, user education, OS reinstall |
| 2.5 | Compare social engineering, threats and vulnerabilities | Phishing types, shoulder surfing, tailgating, impersonation, dumpster diving, DoS, DDoS, evil twin, zero-day, spoofing, on-path, brute force, dictionary, insider threat, SQL injection, XSS, BEC, supply chain, non-compliant, unpatched, unprotected and EOL systems, BYOD |
| 2.6 | Carry out the SOHO malware removal procedure | The ten steps in order |
| 2.7 | Apply workstation hardening | Data-at-rest encryption, password rules, BIOS and UEFI passwords, end-user habits, account management, default admin account, AutoRun, unused services |
| 2.8 | Secure mobile devices | Encryption, screen locks, configuration profiles, patching, endpoint security, locator apps, remote wipe, remote backup, failed log-in limits, MDM, BYOD vs corporate-owned, profile requirements |
| 2.9 | Compare data destruction and disposal methods | Drilling, shredding, degaussing, incineration, wiping, low-level and standard formatting, third-party vendors, certificates of destruction, regulatory and environmental rules |
| 2.10 | Secure SOHO wired and wireless networks | Default passwords, IP filtering, firmware, content filtering, placement, UPnP, screened subnet, management access, SSID, encryption, guest access, unused ports, port forwarding |
| 2.11 | Configure browser security settings | Trusted sources and hashing, patching, extensions and plug-ins, password managers, valid certificates, pop-up blocker, clearing data and cache, private browsing, sync, ad blockers, proxy, secure DNS, feature management |

## Key concepts explained

### 2.1 Security measures

Security controls split into **physical** (keep people away from the hardware) and **logical** (control what people can do once they are on a system). Exam stems usually describe a problem, and you pick the control built for exactly that problem.

**Physical security.**

| Control | What it stops or does |
|---|---|
| Bollards | Short, strong posts that stop vehicles ramming a building entrance |
| Access control vestibule | Two doors with a small space between; the second will not open until the first closes. Stops tailgating. Older name: mantrap |
| Badge reader | Opens a door when an authorized badge is presented, and logs who entered |
| Video surveillance | Cameras that deter and record; detective, not preventive |
| Alarm systems | Alert when a door, window or zone is breached |
| Motion sensors | Detect movement in an area that should be empty, often to trigger alarms or lights |
| Door locks | Basic preventive control; can be keyed, keypad or electronic |
| Equipment locks | Cable locks for laptops, locked racks and cases for servers |
| Security guards | People who can judge a situation, check IDs and respond |
| Fences | Mark a boundary and slow down intruders |
| Lighting | Removes dark areas where people can hide and helps cameras |
| Magnetometers | Metal detectors at an entrance, to find weapons or devices |

**Physical access tokens.** **Key fobs** (proximity tokens you tap), **smart cards** (a card with a chip that stores a certificate, often used with a PIN), **mobile digital keys** (a phone app or wallet pass that opens the door), and ordinary **keys**.

**Biometrics** (something you are): retina scanner, fingerprint scanner, palm print scanner, facial recognition technology (FRT) and voice recognition. Biometrics are hard to share or forget, but you cannot change your fingerprint if the template leaks.

**Logical security.**

| Concept | Plain meaning |
|---|---|
| Principle of least privilege | Give each person only the access their job needs, nothing more |
| Zero Trust | Never trust a device or user just because it is inside the network; verify every request |
| Access control lists (ACLs) | Lists of who or what is allowed or denied, on files, routers and firewalls |
| MFA | Two or more factors from different categories: know, have, are |
| SAML | XML-based standard that lets an identity provider tell a web app "this user is signed in" |
| SSO | Sign in once, reach many applications without signing in again |
| Just-in-time access | Admin rights granted only for a task and removed afterwards, part of privileged access management (PAM) |
| MDM | Mobile device management: enroll, configure, lock and wipe phones and tablets centrally |
| DLP | Data loss prevention: detects and blocks sensitive data, such as card numbers, leaving by email, USB or upload |
| IAM | Identity and access management: creating, changing and removing user identities and their rights |
| Directory services | A central database of users, groups and computers, such as Active Directory |

**MFA methods named in the objectives.** Codes sent by **email**, **hardware tokens** (a key fob or USB security key), **authenticator applications** (codes or push approvals), **SMS** texts, **voice calls**, **TOTP** (time-based one-time passwords that change every 30 seconds or so) and **OTP** (a one-time password or passcode valid for a single use). All of these are "something you have". SMS is the weakest common method, because a phone number can be hijacked by SIM swapping.

A password plus a PIN is **not** MFA: both are something you know.

### 2.2 Windows security settings

**Microsoft Defender Antivirus.** Built into Windows, managed in **Windows Security > Virus & threat protection**.

- **Activate or deactivate:** you can toggle **Real-time protection** off for troubleshooting, but Windows turns it back on automatically after a short time. Installing a third-party antivirus puts Defender into a passive or disabled state on its own.
- **Update definitions:** definitions arrive through Windows Update, or manually with **Protection updates > Check for updates**. Out-of-date definitions are a classic reason a scan misses new malware.

**Windows Defender Firewall.** Managed in **Windows Security > Firewall & network protection**, or in detail with **Windows Defender Firewall with Advanced Security** (`wf.msc`).

- **Activate or deactivate** per network profile: Domain, Private and Public. Public should be the strictest.
- **Port security:** create inbound or outbound rules that allow or block a specific TCP or UDP port, for example allow inbound TCP 3389 for Remote Desktop only from the IT subnet.
- **Application security:** allow or block a specific program, for example "Allow an app through firewall" so a line-of-business app can receive connections.

**Users and groups.**

| Account type | What it can do |
|---|---|
| Local account | Exists only on this PC; nothing syncs |
| Microsoft account | Signs in with an online Microsoft identity; syncs settings, OneDrive and recovery options across devices |
| Standard account | Uses apps and changes own settings; cannot install software for everyone or change system settings without admin credentials |
| Administrator | Full control of the PC; should be used only when needed |
| Guest | Very limited temporary access; disabled by default in current Windows and should stay disabled |
| Power user | A legacy group kept for compatibility with old software; in modern Windows it grants little beyond a standard user |

For daily work, give people a **standard account** and keep a separate admin account. That is least privilege applied to Windows.

**Log-in options** (Settings > Accounts > Sign-in options): username and password, **PIN**, fingerprint, facial recognition, SSO in a domain, and **passwordless** sign-in with **Windows Hello**. A Windows Hello PIN is tied to that one device, so a stolen PIN is useless without the device. That makes it safer than a password reused on many sites.

**NTFS vs share permissions.** This is the most tested idea in 2.2.

| | Share permissions | NTFS permissions |
|---|---|---|
| Applies to | Access over the network only | Local access and network access |
| Levels | Read, Change, Full Control | Full control, Modify, Read and execute, List folder contents, Read, Write |
| Set on | Shared folders | Any file or folder on an NTFS volume |

Rules to learn:

1. Within one type, a user's permissions from all their groups **add up**, except that an explicit **Deny** beats an Allow.
2. When someone connects over the network, Windows works out the share result and the NTFS result, and the **more restrictive of the two wins**.
3. Sitting at the PC locally, only NTFS applies.

Worked example. A folder is shared with **Everyone: Read**. NTFS gives the **Sales** group **Modify**. Priya, in Sales, opens it over the network. Share result: Read. NTFS result: Modify. Effective: **Read**, the stricter one. Signed in at that PC, she gets Modify.

**Inheritance.** Files and subfolders inherit permissions from their parent folder by default. You can disable inheritance on a folder to set its own permissions. When files move:

| Action | Permissions |
|---|---|
| Copy, anywhere | Inherits the destination folder's permissions |
| Move within the same NTFS volume | Keeps its original permissions |
| Move to a different volume | Treated as a copy: inherits the destination's permissions |

**File and folder attributes**, seen in Properties: Read-only, Hidden, Archive (marked for backup) and System, plus Compress and Encrypt under Advanced. Attributes are not permissions: a hidden file is still readable by anyone with rights to it.

**Run as administrator vs standard user.** Right-click an app and pick **Run as administrator** to launch only that program with elevated rights. Everything else stays at standard level.

**User Account Control (UAC).** When something needs admin rights, UAC dims the screen and asks. An administrator sees a **consent prompt** (Yes or No). A standard user sees a **credential prompt** and must type an admin's username and password. UAC stops malware quietly making system changes in the background. Turning it off to stop the prompts is the wrong fix.

**Encryption options.**

| Feature | Protects | Key points |
|---|---|---|
| BitLocker | Whole internal drive | Usually uses the TPM chip; keep the 48-digit recovery key safe. Windows Pro, Enterprise and Education |
| BitLocker To Go | Removable drives such as USB sticks | Unlocked with a password or smart card |
| EFS (Encrypting File System) | Individual files and folders on NTFS | Tied to the user's account and certificate; another user on the same PC cannot open the file. Not in Windows Home |

The test pattern: stolen laptop, use **BitLocker**. Lost USB stick, use **BitLocker To Go**. Two people share one PC and one wants private files, use **EFS**.

**Active Directory tasks** (mostly in Active Directory Users and Computers on a domain controller).

| Task | What it means |
|---|---|
| Joining a domain | Settings > System > About > "Domain or workgroup" (or `sysdm.cpl`); needs Windows Pro or higher and domain admin credentials |
| Assigning a log-in script | A script that runs at sign-in, for example to map drives; set on the user's Profile tab or by Group Policy |
| Moving objects within OUs | Organizational units hold users and computers; moving an object to another OU changes which Group Policies apply |
| Assigning home folders | A personal network folder for each user, set on the Profile tab and often mapped to a drive letter |
| Applying Group Policy | Settings pushed to users and computers by OU; run `gpupdate /force` to apply now and `gpresult /r` to check what applied |
| Selecting security groups | Put users in groups and give permissions to the group, not the individual. Security groups carry permissions; distribution groups are only for email |
| Folder redirection | Moves folders like Documents and Desktop to a network share, so files are backed up and follow the user |

### 2.3 Wireless security protocols

**Protocols and encryption.**

| Protocol | Encryption | Status |
|---|---|---|
| WEP and WPA (original) | WPA used TKIP | Broken; never choose them |
| WPA2 | AES (CCMP); TKIP allowed only for old-device compatibility | Still common; Personal mode uses a pre-shared key, open to offline password guessing |
| WPA3 | AES (CCMP, or GCMP-256 in WPA3-Enterprise 192-bit mode) | Current best. Personal mode uses SAE, which resists offline guessing and gives forward secrecy; protected management frames are required |

- **TKIP** (Temporal Key Integrity Protocol) was a stopgap to fix WEP on old hardware. It is deprecated. If you see WPA2 with TKIP, change it to AES.
- **AES** (Advanced Encryption Standard) is the strong cipher behind WPA2 and WPA3.
- **Personal vs Enterprise.** Personal: everyone shares one passphrase. Enterprise: each user signs in with their own credentials through 802.1X and a RADIUS server, so one leaver does not mean changing the password for everyone.

**Authentication.**

| Method | How it works | Clue words |
|---|---|---|
| RADIUS | Central AAA server (authentication, authorization, accounting). UDP 1812 and 1813. Encrypts only the password | Enterprise Wi-Fi, VPN logins, 802.1X |
| TACACS+ | Cisco-developed AAA. TCP 49. Encrypts the whole packet and separates authentication, authorization and accounting, so each admin command can be authorized and logged | Logging in to routers and switches, network device administration |
| Kerberos | Ticket-based. Users get a ticket-granting ticket from the Key Distribution Center, then service tickets, so the password never crosses the network. TCP and UDP 88 | Active Directory domain logins, SSO inside a domain; clocks must be in sync |
| Multifactor | Two or more factor categories | Password plus authenticator code |

### 2.4 Malware types and tools

**Malware.**

| Type | What it does | Tell-tale sign |
|---|---|---|
| Trojan | Pretends to be useful software but carries a hidden payload | User installed a "free" tool, cracked game or fake update |
| Rootkit | Hides deep in the OS or firmware, often with admin or kernel-level access, and hides itself from tools | Antivirus finds nothing while Windows runs, but a scan from boot media does |
| Virus | Attaches to files or programs and spreads when they run | Infected files, needs a user to run something |
| Spyware | Watches activity and sends it to someone else | Unexplained data uploads, changed browser settings |
| Ransomware | Encrypts files and demands payment | Files renamed with a new extension, a ransom note |
| Keylogger | Records keystrokes to steal passwords | Accounts compromised after typing passwords on one PC |
| Boot sector virus | Infects the boot sector or boot record so it loads before the OS | Problems at startup, survives normal scans |
| Cryptominer | Uses your CPU or GPU to mine cryptocurrency for someone else | Constant high CPU or GPU use, hot and noisy machine |
| Stalkerware | Secretly installed on a phone or PC to track a person's messages and location | A partner or ex seems to know where the user went |
| Fileless | Runs in memory using built-in tools such as PowerShell, leaves few or no files | Odd scripts in memory, file scans find nothing |
| Adware | Pushes unwanted ads | Pop-ups, new toolbars, changed home page |
| PUP (potentially unwanted program) | Software the user technically agreed to, often bundled, that adds toolbars or junk | Came along with another installer |

**Tools and methods.**

| Tool | Use |
|---|---|
| Recovery console | Windows Recovery Environment (WinRE) and its command prompt, for repairing boot problems or working offline on an infected system |
| EDR (endpoint detection and response) | Software on each endpoint that watches behavior, not just signatures, and can isolate the device |
| MDR (managed detection and response) | An outside provider runs detection and response for you, usually around the clock. Fits a company with no security staff |
| XDR (extended detection and response) | Joins detection across endpoints, email, network and cloud into one view |
| Antivirus and anti-malware | Signature and behavior scanning for known threats. The terms overlap; anti-malware is the broader term |
| Email security gateway | Filters inbound mail for spam, phishing links and malicious attachments before users see them |
| Software firewalls | Host firewalls that block unwanted connections in and out |
| User education | Antiphishing training, so people recognize and report suspicious messages |
| OS reinstallation | The last resort when cleaning cannot be trusted, for example a rootkit; reinstall from known-good media after backing up user data |

### 2.5 Social engineering, threats and vulnerabilities

**Social engineering** tricks people rather than computers.

| Attack | How it works |
|---|---|
| Phishing | Fake email that gets people to click, open or type credentials |
| Vishing | Voice phishing: a phone call, for example a fake "bank fraud team" |
| Smishing | SMS phishing: a text message with a link |
| QR code phishing | A QR code (on a poster, parking meter or email) that leads to a fake site |
| Spear phishing | Phishing aimed at one specific person or team, using details about them |
| Whaling | Spear phishing aimed at senior executives |
| Shoulder surfing | Watching someone type a PIN or password, in person or through a camera |
| Tailgating | Following an authorized person through a secured door without badging |
| Impersonation | Pretending to be someone trusted, such as IT support, a courier or a manager |
| Dumpster diving | Searching trash for printouts, notes and old media |

**Threats.**

| Threat | Meaning |
|---|---|
| DoS | One source floods a service so real users cannot reach it |
| DDoS | Many sources, often a botnet, flood a service together |
| Evil twin | A rogue access point that copies a real network's SSID to capture traffic and logins |
| Zero-day | An attack on a flaw the vendor does not know about or has not patched yet |
| Spoofing | Faking an identity: an email sender, an IP address, a MAC address, a caller ID |
| On-path attack | The attacker sits between two parties and reads or changes traffic. Older name: man-in-the-middle |
| Brute-force attack | Tries every possible combination until a password works |
| Dictionary attack | Tries a list of common words and leaked passwords |
| Insider threat | A current or former employee or contractor who misuses access |
| SQL injection | Database commands typed into a web form or URL to read or change the database |
| Cross-site scripting (XSS) | Malicious script injected into a website so it runs in other visitors' browsers |
| Business email compromise (BEC) | A real business mailbox is taken over or convincingly faked to redirect payments or steal data, for example a "new bank details" invoice |
| Supply chain or pipeline attack | Compromising a vendor, software update or build process to reach its customers |

**Vulnerabilities** are weaknesses attackers use.

- **Non-compliant systems:** do not meet the company's security baseline (for example, no encryption).
- **Unpatched systems:** missing OS or app updates.
- **Unprotected systems:** antivirus or firewall missing or turned off.
- **EOL (end of life):** the vendor no longer releases security updates, so new flaws are never fixed. The fix is to upgrade or replace, or at least isolate.
- **BYOD:** personal devices the company does not fully control.

### 2.6 Malware removal procedure

Learn these ten steps in this exact order, as CompTIA's objective numbers them. (The objective says "in Windows Home" for the System Restore steps; System Restore is available in every Windows edition, and the steps apply the same way.) Ordering questions and "What should the technician do NEXT?" items come straight from this list.

1. **Investigate and verify malware symptoms.** Confirm it really is malware (pop-ups, slowness, changed home page, security alerts), not a hardware or driver fault.
2. **Quarantine the infected system.** Disconnect it from the network (unplug Ethernet, turn off Wi-Fi) so it cannot spread or send data out. Stop using shared drives and USB sticks with it.
3. **Disable System Restore in Windows Home.** Restore points can contain the malware, and a later restore could bring it back. Disabling System Restore deletes the old points.
4. **Remediate the infected systems.** This is the cleaning stage, done through steps 5 to 7:
5. **Update the anti-malware software.** Get the newest definitions first, from a clean source if the PC is offline.
6. **Scan and use removal techniques**, for example scanning in **Safe Mode** (fewer things load, so the malware is less able to defend itself) or from a **preinstallation environment** (WinPE boot media), which scans the drive while the infected OS is not running.
7. **Reimage or reinstall** if cleaning fails or the infection cannot be trusted as removed, for example a rootkit.
8. **Schedule scans and run updates.** Set regular scans and install OS and application updates.
9. **Enable System Restore and create a restore point in Windows Home.** Now that the system is clean, a fresh restore point is a good safe point.
10. **Educate the end user.** Explain what happened and how to avoid it next time: suspicious links, downloads, attachments.

Memory hook: **verify, isolate, no restore, clean (update, scan, reimage if needed), schedule, restore back on, teach.** The two System Restore steps bracket the cleaning: off before, on after.

### 2.7 Workstation hardening

**Data-at-rest encryption** protects data stored on the disk if the device is lost or stolen. On Windows that means BitLocker (whole drive) or EFS (files).

**Password considerations.**

| Factor | Good practice |
|---|---|
| Length | The biggest factor. Longer passphrases beat short complex ones |
| Character types | Mix upper and lower case, numbers and symbols |
| Uniqueness | A different password for each account, so one breach does not unlock everything |
| Complexity | Avoid dictionary words, names and simple patterns like `Password1!` |
| Expiration | Change after a set period or after a suspected breach, as policy requires |

**BIOS and UEFI passwords.** A **supervisor or administrator password** stops people changing firmware settings, such as the boot order (which would let them boot from a USB stick and bypass Windows). A **user or power-on password** must be entered before the PC boots at all.

**End-user best practices.**

- Use screensaver locks, and lock the screen when walking away (Windows key + L).
- Log off when not in use.
- Secure critical hardware: cable locks on laptops, lock them away at night.
- Protect PII and passwords: no passwords on sticky notes, no customer data left on the desk.
- Use a password manager to generate and store unique passwords.

**Account management.**

| Setting | Why |
|---|---|
| Restrict user permissions | Least privilege: standard accounts for daily work |
| Restrict log-in times | Block sign-in outside working hours |
| Disable guest account | Removes an easy, unaudited way in |
| Failed attempts lockout | Locks the account after a few wrong passwords, which defeats online brute force |
| Timeout or screen lock | Locks the session automatically after inactivity |
| Account expiration dates | Contractor and temp accounts switch off on their end date automatically |

**Other hardening.**

- **Change the default administrator account and password.** Rename or disable the built-in Administrator and use a strong password; attackers try default names first.
- **Disable AutoRun** (and limit AutoPlay), so inserting a USB stick or disc cannot launch code automatically. Set it in Settings > Bluetooth & devices > AutoPlay, or by Group Policy.
- **Disable unused services** in `services.msc`. Every running service is something an attacker could exploit.

### 2.8 Mobile device security

**Hardening techniques.**

- **Device encryption:** current iOS and Android encrypt storage when a screen lock is set.
- **Screen locks:** facial recognition, PIN codes, fingerprint, pattern and swipe. Swipe offers no security at all; a pattern can be guessed from smudges on the screen. A PIN or biometric is the usual minimum for work devices.
- **Configuration profiles:** settings packages, usually pushed by MDM, that set Wi-Fi, VPN, email, certificates and restrictions.

**Patch management:** keep **OS updates** and **application updates** current. Unsupported phones that no longer get updates are EOL devices.

**Endpoint security software:** antivirus and anti-malware apps, plus **content filtering** to block harmful or banned websites.

**If a device is lost or stolen.**

| Feature | What it does |
|---|---|
| Locator applications | Show the device on a map and can play a sound (Find My on Apple, Find Hub on Android) |
| Remote wipe | Erases the device from a distance so data cannot be read |
| Remote backup applications | Keep data in the cloud so it can be restored to a replacement |
| Failed log-in attempts restrictions | Lock the device, add delays, or wipe it after too many wrong PINs |

**Policies and procedures.**

- **MDM** enrolls devices and enforces policy: require a PIN, encryption and OS version, push apps, block jailbroken or rooted phones, and lock or wipe.
- **BYOD vs corporate-owned.** On a company-owned phone the company controls everything and can fully wipe it. On BYOD the employee owns the phone, so companies usually separate work data into a managed work profile or container and wipe only that part when someone leaves.
- **Profile security requirements:** the minimum a device must meet before it gets company email or apps, for example passcode set, encryption on, current OS.

### 2.9 Data destruction and disposal

First decide: will the drive be **reused** (inside the company, donated or resold) or **destroyed**? Reuse means wiping. Destruction means physical methods.

**Physical destruction of hard drives.**

| Method | How | Note |
|---|---|---|
| Drilling | Holes through the platters (or memory chips on an SSD) | Quick and cheap; undrilled parts may still hold data |
| Shredding | An industrial shredder cuts the drive into small pieces | Works for HDDs, SSDs, phones and tapes |
| Degaussing | A strong magnetic field scrambles magnetic media | Works on HDDs and tapes and leaves them unusable. **Does nothing to SSDs or flash**, which do not store data magnetically |
| Incineration | Burning in a furnace | Complete; often done by a specialist vendor, also used for paper |

**Recycling or repurposing.**

| Method | Effect |
|---|---|
| Erasing or wiping | Software overwrites every sector (for HDDs), or runs the drive's built-in secure erase (for SSDs). Data is not recoverable and the drive can be reused |
| Low-level formatting | Historically done at the factory. Today the term usually means a utility that writes zeros to the whole disk, which works as a wipe |
| Standard formatting | Rebuilds the file system so the drive looks empty. A quick format leaves the old data on the disk, where recovery tools can find it. Not a secure method |

**Outsourcing concepts.** A **third-party vendor** can collect and destroy drives. Ask for a **certificate of destruction or recycling**: the proof, listing the devices or serial numbers, that the job was done. Auditors ask for it.

**Regulatory and environmental requirements.** Laws and contracts can say how long data must be kept and how it must be destroyed. Electronics and batteries contain toxic materials, so dispose of them through approved e-waste recycling, never ordinary trash.

### 2.10 SOHO network security

A small office or home office (SOHO) usually has one wireless router doing everything. Harden it in this rough order.

**Router settings.**

| Setting | Why |
|---|---|
| Change default passwords | Default admin logins are published online; change this first |
| IP filtering | Allow or block traffic by IP address |
| Firmware updates | Fix known security flaws in the router itself |
| Content filtering | Block categories of websites, such as adult or malware sites |
| Physical placement and secure locations | Put the router where visitors cannot reach its reset button or ports, and centrally so the signal does not spill far outside |
| UPnP (Universal Plug and Play) | Lets devices open ports on the router automatically. Convenient but abused by malware; disable it and forward ports manually |
| Screened subnet | A separate zone for devices that the internet must reach. On SOHO routers a "DMZ host" setting exposes every port of one device, which is risky; prefer specific port forwarding |
| Configure secure management access | Manage the router over HTTPS, turn off remote (WAN-side) administration unless truly needed |

**Wireless-specific settings.**

- **Change the SSID** from the default, which can reveal the router model, and avoid names that identify the business or owner.
- **Disabling SSID broadcast** hides the name from casual lists, but the network is still easy to find with free tools. It is a weak control, never a substitute for encryption.
- **Encryption settings:** WPA3, or WPA2 with AES if older devices need it. Never WEP, WPA or TKIP.
- **Configuring guest access:** a separate guest network, isolated from office devices, with its own password.

**Firewall settings.**

- **Disable unused ports**, both physical switch ports on the router and open firewall ports.
- **Port forwarding or mapping** sends incoming traffic on one port to one internal device, for example TCP 443 to a small web server. Forward only the ports needed, only to that device.

### 2.11 Browser security

**Browser download and installation.** Download browsers only from **trusted sources**: the vendor's website or the OS app store. Installers from **untrusted sources**, such as pop-up ads and file-sharing sites, are a common way to get Trojans. **Hashing** proves a download was not altered: compare the file's hash with the one the vendor publishes. In PowerShell:

```
PS C:\Users\sam\Downloads> Get-FileHash .\BrowserSetup.exe -Algorithm SHA256

Algorithm   Hash                                                              Path
---------   ----                                                              ----
SHA256      9F2C...E41A                                                       C:\Users\sam\Downloads\BrowserSetup.exe
```

If the hash matches the vendor's published value exactly, the file is intact. If one character differs, do not run it.

**Browser patching.** Keep automatic updates on. Browsers are a top target, and patches close known holes.

**Extensions and plug-ins.** Install only from the official store and from developers you trust. An extension with "read and change all your data on all websites" can see everything you type. Remove ones you do not use.

**Password managers.** Built-in or third-party managers create and store unique passwords, and only fill them in on the real site, which helps against phishing.

**Secure connections and valid certificates.** HTTPS with a valid certificate means the connection is encrypted and the site is who its certificate says. A certificate warning (expired, wrong name, untrusted issuer) is a reason to stop, not to click through.

**Settings.**

| Setting | Use |
|---|---|
| Pop-up blocker | Stops sites opening new windows, which are often ads or scams |
| Clearing browsing data | Removes history, cookies and saved form data, for example on a shared PC |
| Clearing cache | Removes stored copies of pages; fixes sites that load old or broken versions |
| Private-browsing mode | Does not keep history, cookies or form data after the window closes. It does **not** hide you from your employer, ISP or the websites you visit |
| Sign-in and browser data synchronization | Syncs bookmarks, passwords and history to other devices through a browser account. Useful, but a compromised account exposes everything synced |
| Ad blockers | Block ads, including malicious ones (malvertising) |
| Proxy | Sends browser traffic through another server, often used by companies for filtering and logging |
| Secure DNS | DNS over HTTPS, which encrypts lookups so others on the network cannot read or tamper with them |

**Browser feature management.** You can enable or disable plug-ins, extensions and features (for example camera, microphone, location or pop-up permissions per site). In a business, Group Policy or MDM can enforce these settings across every browser.

## How questions look

Most items are short scenarios from a help desk day: a user's PC shows pop-ups, a manager wants a lost phone protected, a small office router needs setting up, a folder is "Read only" for someone in the right group. Watch the qualifiers: "BEST", "MOST secure", "FIRST" and "NEXT". Many "NEXT" items quote where the technician is in the malware removal procedure and ask for the following step. Expect matching items (malware type to symptom, attack to description, destruction method to drive type), and performance-based tasks such as putting malware removal steps in order, choosing Wi-Fi and router settings on a mock admin page, or working out effective permissions from a share and NTFS table. Some items ask you to "Choose two."

## A method for these questions

1. Name the objective first: physical, Windows setting, Wi-Fi, malware, scam, removal steps, hardening, mobile, disposal, SOHO router or browser. That shrinks the answer set.
2. For "FIRST" or "NEXT", find where the stem is on the ten-step malware procedure and pick the very next step, even if a later step sounds more useful.
3. For permissions, work out the share result and the NTFS result separately, then take the stricter one. Remember Deny wins.
4. For Wi-Fi and router items, pick the strongest current option: WPA3 over WPA2, AES over TKIP, port forwarding over DMZ host, UPnP off.
5. For disposal, decide reuse or destroy, then check the media type. Degaussing never fits an SSD.
6. For malware and attack types, find the single detail that separates them: hidden from the OS (rootkit), spreads via files (virus), pretends to be useful (Trojan), targets an executive (whaling), real vendor mailbox taken over (BEC).
7. Reject answers that turn security off to fix a nuisance, such as disabling UAC or the firewall.

## Traps that cost points

- **Cleaning before quarantining.** Scanning while the PC is still on the network lets the malware spread and keep sending data. Isolate it first.
- **System Restore steps swapped.** Disable it before cleaning, re-enable and create a new point after. Restoring an old point during cleanup can bring the infection back.
- **Adding share and NTFS permissions together.** Over the network the stricter result wins. Read share plus Modify NTFS gives Read.
- **Degaussing an SSD.** SSDs and flash store data electrically, so a degausser does nothing. Use secure erase, or shred.
- **Formatting as a wipe.** A standard quick format leaves the data recoverable. Use a wiping tool before reuse.
- **Hidden SSID as security.** Hiding the name does not stop anyone with a scanner. Encryption does.
- **Password plus security question as MFA.** Both are something you know. MFA needs a different category, such as an authenticator app.
- **RADIUS vs TACACS+ mixed up.** RADIUS for Wi-Fi and VPN user logins; TACACS+ for admins logging in to network devices, with each command authorized.
- **Private browsing as anonymity.** It only stops the browser saving local history. The network and the sites still see the traffic.

## Timing

Each Core 2 exam is one 90-minute block of up to 90 questions, so aim for about 1 minute per multiple-choice item on average, and allow more for performance-based questions. Definition-style items here (a malware type, an attack name) should take well under a minute, which banks time. Spend that time on permission tables and on malware removal ordering tasks, where one misplaced step costs the item. If a PBQ looks long, flag it and come back after the quick items.

## Practice items

These 2 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A user calls the help desk because her home PC shows constant pop-ups and her browser home page keeps changing. A technician remotes in and confirms an unknown program is running at startup and the symptoms match malware. What should the technician do NEXT?

A. Disable System Restore

B. Disconnect the PC from the network

C. Update the anti-malware definitions and scan in Safe Mode

D. Explain to the user how to avoid suspicious downloads

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Symptoms are verified, so the next step is to quarantine the system by cutting it off from the network so it cannot spread or send data out. (Objective 2.6)

- **A** is wrong because disabling System Restore is step 3 and comes after quarantine.
- **C** is wrong because updating and scanning are part of remediation, which comes later.
- **D** is wrong because educating the end user is the final step.

</details>

### Item 2

A user in the Accounting group says he can open files in a shared folder from his laptop but cannot save changes. The technician checks the folder's permissions.

```
Share permissions (\\FS01\Reports)
  Everyone            Read

NTFS permissions (D:\Reports)
  Accounting          Modify
  Administrators      Full control
```

What is the user's effective permission when he connects over the network, and what change would let him save files?

A. Modify; no change is needed

B. Full control; remove him from the Administrators group

C. Read; change the share permission to Change for the Accounting group

D. Read; give the Accounting group Full control in NTFS

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Over the network, the stricter of the share result (Read) and the NTFS result (Modify) applies, so he gets Read. Raising the share permission to Change lets the NTFS Modify permission take effect. (Objective 2.2)

- **A** is wrong because Modify is only his NTFS result; the Read share permission limits him over the network.
- **B** is wrong because nothing shows he is an administrator, and removing a group would not add rights.
- **D** is wrong because the share permission is still Read, so any NTFS change is capped at Read over the network.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 | 2 |
|---|---|---|
| Answer | B | C |
| Objective | 2.6 | 2.2 |

- **2 of 2:** strong. Keep this domain fresh with mixed practice, since it carries as much weight as any Core 2 domain.
- **1 of 2:** list the objectives you missed. Malware removal order, share vs NTFS permissions and disposal methods are the usual weak spots; reread those parts of [Key concepts](#key-concepts-explained).
- **0 of 2:** spend two study sessions here. Write the ten malware removal steps and the share vs NTFS rules from memory, then reread [2.6 Malware removal procedure](#26-malware-removal-procedure) and [2.2 Windows security settings](#22-windows-security-settings) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. On a Windows Pro PC or virtual machine, share a folder, give Everyone Read on the share and a test user Modify in NTFS, then try saving a file over the network and locally, and explain the difference. While you are there, open `wf.msc` and read one inbound rule.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [Core 2, Domain 1: Operating Systems](1-operating-systems.md) | Next: [Core 2, Domain 3: Software Troubleshooting](3-software-troubleshooting.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
