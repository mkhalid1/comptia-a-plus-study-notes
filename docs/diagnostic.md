<!-- nav:top -->[Contents](../README.md#contents) · Previous: [How CompTIA A+ works](a-plus-overview.md) · Next: [Core 1 (220-1201) overview](core-1/README.md)<!-- /nav:top -->

# Diagnostic: Core 1 and Core 2

Twenty-seven original items, three from each of the nine A+ domains, to show you where to start. Parts A to E are Core 1 (220-1201), 15 items: allow 15 minutes. Parts F to I are Core 2 (220-1202), 12 items: allow 12 minutes. Do only the part for the core you are sitting next, or both if you are planning the whole certification. Answer without looking anything up, then check each answer and use the tables at the bottom.

These items are original, written for these notes. They are not taken from CompTIA's exams or any prep provider. They are different from the practice items on the domain pages, so you can still use those afterwards.

If you would rather start with a full timed run, take the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) instead, then come back here.

## Part A: Core 1, Domain 1, Mobile Devices

### D1

A user buys a new Android phone and a new laptop. She wants one cable type that is reversible and can charge both devices, move files, and connect the laptop to a monitor. Which connector should she look for?

A. microUSB

B. miniUSB

C. USB-C

D. Lightning

<details>
<summary>Answer and explanation</summary>

**Answer: C.** USB-C is reversible and, on ports that support it, carries charging, data and video. (Objective 1.2)

- **A** is wrong because microUSB is not reversible and does not carry video on current devices.
- **B** is wrong because miniUSB is an old connector found on old cameras and similar devices.
- **D** is wrong because Lightning is Apple's own connector and is not used on Android phones or laptops.

</details>

### D2

A technician is upgrading the memory in a thin business laptop. The laptop has one empty memory slot. What should the technician check before ordering the module?

A. That the module is a SODIMM of the DDR generation the laptop supports, and that the laptop's maximum capacity allows it

B. That the module is a full-size DIMM with a heat spreader

C. That the module is ECC, because laptops require error correction

D. That the module matches the speed of the laptop's SSD

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Laptops use SODIMM modules, DDR generations are not interchangeable, and each laptop has a maximum supported capacity. (Objective 1.1)

- **B** is wrong because full-size DIMMs are for desktops and will not fit a laptop slot.
- **C** is wrong because almost all laptops use non-ECC memory.
- **D** is wrong because SSD speed has nothing to do with choosing memory.

</details>

### D3

An employee gets a new phone that has no SIM card tray. The carrier emails a QR code for her line. She has no cellular service yet. What should the technician help her do?

A. Move the physical SIM card from her old phone into the new one

B. Turn on the Wi-Fi hotspot so the phone can find the carrier

C. Pair the phone with her laptop over Bluetooth to transfer the line

D. Scan the QR code in the phone's cellular settings to add and activate the eSIM

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A phone without a SIM tray uses an eSIM, which is set up by scanning the carrier's QR code or using the carrier's app. (Objective 1.3)

- **A** is wrong because the new phone has no tray for a physical SIM.
- **B** is wrong because a hotspot shares an existing cellular connection; it cannot create one.
- **C** is wrong because Bluetooth pairing does not transfer or activate a cellular line.

</details>

## Part B: Core 1, Domain 2, Networking

### D4

Users reach the company website at an address starting with `https://`. Which port must the web server's firewall allow for this traffic?

A. TCP 80

B. TCP 443

C. TCP 445

D. UDP 53

<details>
<summary>Answer and explanation</summary>

**Answer: B.** HTTPS uses TCP 443. (Objective 2.1)

- **A** is wrong because TCP 80 is unencrypted HTTP.
- **C** is wrong because TCP 445 is SMB file sharing.
- **D** is wrong because UDP 53 is DNS, which finds the server's address but does not carry the web traffic.

</details>

### D5

A family's new internet service is fiber to the home. The installer brings the fiber line into the house. Which device converts the fiber signal to Ethernet so the family's router can connect?

A. Cable modem

B. DSL modem

C. PoE injector

D. Optical network terminal (ONT)

<details>
<summary>Answer and explanation</summary>

**Answer: D.** An ONT terminates the provider's fiber line and provides an Ethernet connection for the router. (Objective 2.5)

- **A** is wrong because a cable modem connects to the cable provider's coax network.
- **B** is wrong because a DSL modem connects over telephone lines.
- **C** is wrong because a PoE injector adds power to an Ethernet cable; it does not convert fiber.

</details>

### D6

Mail servers keep rejecting the company's newsletters, saying the sending server is not authorized for the domain. The newsletters are sent by a marketing service the company started using last month. What should the administrator update?

A. The SPF TXT record, to include the marketing service's sending servers

B. The MX record, to point at the marketing service

C. The A record for the company website

D. The DHCP scope options

<details>
<summary>Answer and explanation</summary>

**Answer: A.** SPF, published as a TXT record, lists which servers may send mail for the domain. The new service is not on that list yet. (Objective 2.4)

- **B** is wrong because MX controls where incoming mail is delivered, and pointing it at a newsletter service would break the company's inbound email.
- **C** is wrong because the A record maps the website name to an IPv4 address and plays no part in sender checks.
- **D** is wrong because DHCP scope options configure local clients, not email authentication.

</details>

## Part C: Core 1, Domain 3, Hardware

### D7

A company is buying a new database server. The vendor recommends memory that can detect and correct single-bit errors automatically so data is not silently corrupted. Which memory should the company order?

A. Non-ECC SODIMM

B. ECC memory supported by the server's motherboard and CPU

C. The fastest non-ECC DIMMs available

D. DDR3 modules, because they are the most reliable generation

<details>
<summary>Answer and explanation</summary>

**Answer: B.** ECC memory detects and corrects single-bit errors, and the board and CPU must support it. (Objective 3.3)

- **A** is wrong because non-ECC memory has no error correction, and SODIMMs are laptop modules.
- **C** is wrong because speed does not provide error correction.
- **D** is wrong because a DDR generation must match the board's slots, and no generation corrects errors on its own without ECC.

</details>

### D8

An eight-year-old laptop's screen has become so dark that it looks off. When the technician shines a flashlight at the screen, a faint image is visible. The laptop uses a CCFL-backlit LCD. Which part is the MOST likely cause?

A. The digitizer

B. The graphics driver

C. The inverter

D. The Wi-Fi antenna

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A visible but very dark image means the LCD is drawing the picture but the backlight is not lit. On a CCFL display, the inverter powers the backlight and is a common failure. (Objective 3.1)

- **A** is wrong because the digitizer senses touch; it does not light the screen.
- **B** is wrong because a driver fault would not leave a faint but correct image that only shows under a flashlight.
- **D** is wrong because the Wi-Fi antennas run through the lid but have nothing to do with the display.

</details>

### D9

A server has six 2 TB drives configured as RAID 10. How much usable storage does the array provide?

A. 2 TB

B. 8 TB

C. 10 TB

D. 6 TB

<details>
<summary>Answer and explanation</summary>

**Answer: D.** RAID 10 mirrors drives in pairs and stripes across the pairs, so half of the raw space is usable: 6 x 2 TB = 12 TB raw, divided by 2 = 6 TB. (Objective 3.4)

- **A** is wrong because 2 TB is the capacity of one drive, which is what a simple two-drive mirror would give.
- **B** is wrong because 8 TB is the RAID 6 result, (6 minus 2) x 2 TB.
- **C** is wrong because 10 TB is the RAID 5 result, (6 minus 1) x 2 TB.

</details>

## Part D: Core 1, Domain 4, Virtualization and Cloud Computing

### D10

A small office wants email, shared calendars and office apps that staff use through a web browser. The provider runs and updates everything; the office only manages its user accounts and data. Which service model is this?

A. IaaS

B. SaaS

C. PaaS

D. Private cloud

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Software as a service delivers a finished application. The customer manages users, settings and data, and the provider manages everything else. (Objective 4.2)

- **A** is wrong because with IaaS the office would have to install and run the OS and applications itself.
- **C** is wrong because PaaS is for deploying your own code, and the office is not writing any.
- **D** is wrong because private cloud describes who uses the infrastructure, not what service is delivered, and this provider serves many customers.

</details>

### D11

A technician has built five Windows VMs on a fully patched host. A manager says the VMs do not need their own updates or antivirus because "the host already has them". What is the BEST response?

A. Agree, because the hypervisor scans every guest automatically

B. Agree, as long as each VM has a recent snapshot

C. Disagree only for VMs running on a Type 2 hypervisor

D. Disagree, because each guest OS needs its own patches and endpoint protection

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Each guest is a separate operating system with its own vulnerabilities. Patching the host does not patch the guests, whatever the hypervisor type. (Objective 4.1)

- **A** is wrong because hypervisors do not patch or scan guest operating systems for you.
- **B** is wrong because a snapshot is a rollback point, not protection against attack.
- **C** is wrong because guests on Type 1 and Type 2 hypervisors both need their own updates and protection.

</details>

### D12

A company started serving training videos to customers directly from its public cloud storage. Its next monthly bill is much higher. The summary is shown.

```
Line item                  Last month   This month
Compute (VM hours)         720 h        720 h
Storage                    2 TB-month   2.1 TB-month
Data transfer in           3 TB         3 TB
Data transfer out          1 TB         18 TB
```

Which line BEST explains the increase, and what is it called?

A. Data transfer out, known as egress

B. Data transfer in, known as ingress

C. Storage, caused by multitenancy

D. Compute, caused by elasticity

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Streaming videos to customers moves data out of the cloud. That is egress, which is metered, and it is the only line that grew sharply. (Objective 4.2)

- **B** is wrong because data coming in stayed at 3 TB.
- **C** is wrong because storage barely changed, and multitenancy is about customers sharing infrastructure, not billing growth.
- **D** is wrong because compute hours did not change, so no extra capacity was added.

</details>

## Part E: Core 1, Domain 5, Hardware and Network Troubleshooting

### D13

A technician adds a new, blank SSD to a desktop to give the user more storage. Now the PC shows "Bootable device not found" at start-up. When the new SSD is unplugged, Windows starts normally from the original drive. What is the MOST likely cause?

A. The original drive has failed

B. The CMOS battery is dead

C. The firmware boot order now points at the new, blank SSD

D. The RAID array is missing

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The PC boots fine without the new drive, so the original drive and Windows are healthy. The firmware is trying to boot from the blank SSD. Set the original drive first in the UEFI boot order. (Objective 5.2)

- **A** is wrong because the original drive boots Windows normally when the SSD is removed.
- **B** is wrong because a dead CMOS battery causes wrong dates and lost settings after power loss, and nothing here points to that.
- **D** is wrong because no RAID array is configured in this scenario.

</details>

### D14

An office replaces its printer with a newer model. Users keep printing with the old printer's driver, and pages now come out full of random symbols and odd characters. What should the technician do?

A. Install the correct driver for the new printer model

B. Replace the toner cartridge

C. Replace the pickup rollers

D. Empty the hole punch waste bin

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Garbled print is a classic sign of the wrong or corrupt driver. The printer is receiving instructions it does not understand. (Objective 5.6)

- **B** is wrong because toner problems cause faded, streaked or speckled pages, not random characters.
- **C** is wrong because pickup rollers affect paper feeding, not what is printed.
- **D** is wrong because the hole punch bin affects finishing, not the content of the page.

</details>

### D15

A user reports "limited connectivity" and cannot open any websites or network shares. Coworkers on the same switch are working normally. The technician runs `ipconfig` on the user's PC.

```
Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . :
   Autoconfiguration IPv4 Address. . : 169.254.37.112
   Subnet Mask . . . . . . . . . . . : 255.255.0.0
   Default Gateway . . . . . . . . . :
```

What is the MOST likely problem?

A. The company's DNS server is down

B. The internet service provider has an outage

C. The PC has an IP address conflict with the default gateway

D. The PC could not get an address from a DHCP server

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A 169.254.x.x address is an APIPA address: Windows assigned it to itself because no DHCP server answered. With coworkers working, check this PC's cable, wall port and switch port, then run `ipconfig /renew`. (Objective 5.5)

- **A** is wrong because a DNS outage would leave the PC with a normal address and would affect coworkers too.
- **B** is wrong because an ISP outage would affect everyone and would not stop the PC getting a local address.
- **C** is wrong because the PC has no gateway configured at all, and its address is not on the gateway's network.

</details>

## Part F: Core 2, Domain 1, Operating Systems

### D16

A user follows a support guide that says to open a folder named AppData inside their user profile, but the folder does not appear in File Explorer. What should the technician change?

A. Indexing Options, to add the user profile to the search index

B. File Explorer Options, View tab, to show hidden files, folders, and drives

C. User Accounts, to make the user a local administrator

D. Programs and Features, to turn on a Windows feature

<details>
<summary>Answer and explanation</summary>

**Answer: B.** AppData is a hidden folder. Turning on "Show hidden files, folders, and drives" in File Explorer Options makes it visible. (Objective 1.6)

- **A** is wrong because indexing affects search speed and results, not whether hidden folders show in File Explorer.
- **C** is wrong because users can already open their own AppData folder; it is hidden, not blocked.
- **D** is wrong because AppData is not a Windows feature that can be turned on.

</details>

### D17

A Linux server's monitoring alert says the /var file system is 95% full. The technician wants to find which folders under /var are using the most space. Which command should the technician run?

A. `df -h`

B. `ps aux`

C. `du -sh /var/*`

D. `top`

<details>
<summary>Answer and explanation</summary>

**Answer: C.** `du` reports disk usage per file or folder, and `-sh` gives one readable total for each item under /var. (Objective 1.9)

- **A** is wrong because `df -h` shows how full each file system is, which the alert already said, not which folders fill it.
- **B** is wrong because `ps aux` lists running processes, not disk usage.
- **D** is wrong because `top` shows live CPU and memory use by process.

</details>

### D18

A technician set up a scheduled task that runs this command every night at 11 p.m.:

```
robocopy D:\Projects \\nas01\backup\Projects /mir /z /log:C:\logs\backup.txt
```

On Monday afternoon a user accidentally deleted a spreadsheet from D:\Projects. On Tuesday morning the spreadsheet is also missing from the NAS. What explains this?

A. The /mir switch deletes files at the destination that no longer exist at the source

B. The /z switch only copies files that have changed since the last run

C. The /log switch replaces the copy with a log file when an error occurs

D. Robocopy cannot copy to a UNC path, so the job has never worked

<details>
<summary>Answer and explanation</summary>

**Answer: A.** `/mir` mirrors the source, so Monday night's run removed the deleted spreadsheet from the NAS too. For a backup that keeps deleted files, use `/e` instead, or a real backup tool with versions. (Objective 1.5)

- **B** is wrong because `/z` is restartable mode for interrupted copies; it does not remove files.
- **C** is wrong because `/log` only writes the output to a file.
- **D** is wrong because robocopy works with UNC paths, and the job's normal copying is not in question.

</details>

## Part G: Core 2, Domain 2, Security

### D19

An employee holds the badge-controlled office door open for a person carrying a stack of boxes who says he is "from the copier company." The person has no badge and is not on the visitor list. Which social engineering techniques are being used?

A. Shoulder surfing and dumpster diving

B. Vishing and whaling

C. Tailgating and impersonation

D. Spoofing and smishing

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Following someone through a secured door without badging is tailgating, and posing as a copier technician is impersonation. (Objective 2.5)

- **A** is wrong because nobody is watching a screen or searching trash.
- **B** is wrong because there is no phone call and no executive is targeted.
- **D** is wrong because spoofing fakes a digital identity and smishing uses text messages; this happens in person.

</details>

### D20

A network team wants a central server that authenticates administrators logging in to routers and switches. It must encrypt the entire exchange, run over TCP, and authorize and log each command an admin enters. Which protocol fits BEST?

A. TACACS+

B. RADIUS

C. Kerberos

D. WPA3-Enterprise

<details>
<summary>Answer and explanation</summary>

**Answer: A.** TACACS+ runs over TCP 49, encrypts the whole packet and separates authentication, authorization and accounting, so each command can be authorized and logged. It is built for network device administration. (Objective 2.3)

- **B** is wrong because RADIUS uses UDP, encrypts only the password and combines authentication with authorization; it suits Wi-Fi and VPN user logins.
- **C** is wrong because Kerberos issues tickets for domain logins; it does not authorize individual router commands.
- **D** is wrong because WPA3-Enterprise secures Wi-Fi connections, not admin logins to network devices.

</details>

### D21

A law firm is retiring 25 laptops with solid-state drives that held client files. The drives will not be reused. A technician proposes degaussing them and then sending them to e-waste. What is the BEST response?

A. Approve the plan, because degaussing destroys data on all drive types

B. Have the drives shredded by a vendor that provides a certificate of destruction

C. Perform a standard format on each drive, then send them to e-waste

D. Throw the drives in the general trash after removing them from the laptops

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Degaussing does not affect SSDs, which store data electrically. Shredding destroys any drive type, and the certificate gives the firm proof for its records. (Objective 2.9)

- **A** is wrong because a degausser only affects magnetic media such as hard disk drives and tapes.
- **C** is wrong because a standard format leaves data recoverable.
- **D** is wrong because it leaves the data readable and breaks environmental disposal rules for electronics.

</details>

## Part H: Core 2, Domain 3, Software Troubleshooting

### D22

A user plugs a webcam, a headset, a keyboard, a mouse and an external drive into a USB hub on one front port of her desktop. Windows shows a message that there are not enough USB controller resources, and the webcam stops working. What should the technician try FIRST?

A. Replace the motherboard

B. Move some of the devices to ports on a different USB controller, such as the rear ports

C. Reinstall Windows

D. Disable the webcam in Device Manager

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The controller behind that port has run out of resources for all the devices on the hub. Spreading devices across ports on another controller is the quick fix. (Objective 3.1)

- **A** is wrong because the controller works; it is simply overloaded.
- **C** is wrong because the OS is not at fault.
- **D** is wrong because the user needs the webcam working, not switched off.

</details>

### D23

Since a phone OS update last week, a user's battery drains by midday. The battery usage screen shows a navigation app at 41% of battery use, though she has not opened it in days. What should the technician do?

A. Replace the battery immediately

B. Factory reset the phone

C. Turn on airplane mode during the day

D. Change the navigation app's location access to "While using the app" and limit its background activity

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The app is using location and running in the background even when closed. Limiting its location access and background activity stops the drain while keeping the app usable. (Objective 3.2)

- **A** is wrong because the usage screen points to an app, not a worn-out battery.
- **B** is wrong because a reset is too drastic when one app is the clear cause.
- **C** is wrong because airplane mode cuts calls and data, which is not a fix.

</details>

### D24

A Windows PC cannot reach the Windows Update servers or the antivirus vendor's website, and updates fail every night. The technician opens the proxy settings and finds a manual proxy at `127.0.0.1:8080` that the IT department never set. No proxy is used in the office. What is the MOST likely explanation?

A. Malware set a local proxy to block or intercept security and update traffic

B. The PC's network adapter driver is outdated

C. Windows Update is turned off by company policy

D. The PC's clock has drifted

<details>
<summary>Answer and explanation</summary>

**Answer: A.** An unexpected proxy pointing at the PC itself, combined with blocked update and antivirus sites, is a classic malware trick to stop the PC from being cleaned or patched. The technician should follow the malware removal procedure and remove the proxy setting. (Objective 3.4)

- **B** is wrong because a driver problem would not add a proxy setting or pick out security sites.
- **C** is wrong because a policy would not block the antivirus vendor's website, and IT says it did not set this.
- **D** is wrong because a wrong clock causes certificate errors, not a new proxy setting.

</details>

## Part I: Core 2, Domain 4, Operational Procedures

### D25

A small business keeps its working files on the office PC and a second copy on a USB drive in the same desk drawer. What should it add to meet the 3-2-1 backup rule?

A. A second USB drive in the same drawer

B. A RAID 1 mirror inside the office PC

C. A third copy kept offsite, such as in a cloud backup service

D. A daily full backup to the same USB drive

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The rule asks for 3 copies, on 2 types of media, with 1 offsite. The business has 2 copies, both in the office, so it needs a third copy stored somewhere else. (Objective 4.3)

- **A** is wrong because it is still onsite; a fire or theft takes every copy.
- **B** is wrong because a mirror protects against a drive failure but is not a separate offsite copy.
- **D** is wrong because more backups to the same drive still leave everything in one place.

</details>

### D26

An administrator needs to run PowerShell commands on 40 Windows servers from her workstation, without opening a desktop session on each one. Which remote access method fits BEST?

A. Windows Remote Management (WinRM)

B. Virtual network computer (VNC)

C. Remote Desktop Protocol (RDP)

D. Screen-sharing software

<details>
<summary>Answer and explanation</summary>

**Answer: A.** WinRM is built for running commands and PowerShell remotely on Windows machines, and it can target many servers at once without a graphical session. (Objective 4.9)

- **B** is wrong because VNC shares a full screen, one machine at a time.
- **C** is wrong because RDP opens a desktop session on each server, which she wants to avoid.
- **D** is wrong because screen sharing is for showing or controlling one user's screen.

</details>

### D27

A security team is collecting evidence from a running server that is suspected of being compromised. In which order should they collect these items, according to the order of volatility?

```
1. Archived backup tapes
2. Contents of the hard drive
3. Contents of RAM
4. Remote logs on the central log server
```

A. 2, 3, 4, 1

B. 1, 4, 2, 3

C. 3, 4, 2, 1

D. 3, 2, 4, 1

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Collect what disappears fastest first. RAM is lost at power off, the local disk comes next, then remote logs, which change more slowly and are kept elsewhere, and archived backups last. (Objective 4.6)

- **A** is wrong because it takes the disk before RAM, and RAM may be lost meanwhile.
- **B** is wrong because it is the reverse order, leaving the most volatile item until last.
- **C** is wrong because it puts remote logs before the local disk, which is more volatile.

</details>

## Answer key

| Part | Items | Answers |
|---|---|---|
| Part A | D1 to D3 | C, A, D |
| Part B | D4 to D6 | B, D, A |
| Part C | D7 to D9 | B, C, D |
| Part D | D10 to D12 | B, D, A |
| Part E | D13 to D15 | C, A, D |
| Part F | D16 to D18 | B, C, A |
| Part G | D19 to D21 | C, A, B |
| Part H | D22 to D24 | B, D, A |
| Part I | D25 to D27 | C, A, D |

## What your result means

Count your correct answers in each part. A choose-two item counts only if both choices are right.

### Core 1 (220-1201)

| Part | Domain weight | Score 0 or 1 | Score 2 | Score 3 |
|---|---|---|---|---|
| A. [Mobile Devices](core-1/1-mobile-devices.md) | 13% | Study the full guide | Do its practice items | Light review only |
| B. [Networking](core-1/2-networking.md) | 23% | High priority: learn the ports and Wi-Fi tables | Do its 12 items | Light review only |
| C. [Hardware](core-1/3-hardware.md) | 25% | High priority: cables, RAM, storage and printers | Do its 12 items | Light review only |
| D. [Virtualization and Cloud Computing](core-1/4-virtualization-and-cloud-computing.md) | 11% | Study the full guide | Do its practice items | Light review only |
| E. [Hardware and Network Troubleshooting](core-1/5-hardware-and-network-troubleshooting.md) | 28% | Top priority: the heaviest Core 1 domain | Read the symptom tables, then all 14 items | Still do the items: it is over a quarter of Core 1 |

### Core 2 (220-1202)

| Part | Domain weight | Score 0 or 1 | Score 2 | Score 3 |
|---|---|---|---|---|
| F. [Operating Systems](core-2/1-operating-systems.md) | 28% | Top priority: tools and commands | Do all 14 items | Still do the command items |
| G. [Security](core-2/2-security.md) | 28% | Top priority: malware removal steps and Windows security | Do all 14 items | Still do the items |
| H. [Software Troubleshooting](core-2/3-software-troubleshooting.md) | 23% | Study the symptom tables | Do its 12 items | Light review only |
| I. [Operational Procedures](core-2/4-operational-procedures.md) | 21% | Study the full guide | Do its practice items | Light review only |

If two domains tie, start with the one with the higher weight.

Then pick a plan: the [7-day plan](study-plans.md#7-day-plan) if you have a week per core, or the [2-day plan](study-plans.md#2-day-plan) if your exam is close.

---

<!-- nav:bottom -->← Previous: [How CompTIA A+ works](a-plus-overview.md) | Next: [Core 1 (220-1201) overview](core-1/README.md) → | [Back to contents](../README.md#contents)<!-- /nav:bottom -->
