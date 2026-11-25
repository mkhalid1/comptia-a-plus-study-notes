<!-- nav:top -->
[Contents](../README.md#contents) · Previous: [How CompTIA A+ works](a-plus-overview.md) · Next: [Core 1 (220-1201) overview](core-1/README.md)
<!-- /nav:top -->

# Diagnostic: Core 1 and Core 2

Nine original items, one from each of the nine A+ domains, to show you where to start. Parts A to E are Core 1 (220-1201), 5 items: allow 5 minutes. Parts F to I are Core 2 (220-1202), 4 items: allow 4 minutes. Do only the part for the core you are sitting next, or both if you are planning the whole certification. Answer without looking anything up, then check each answer and use the tables at the bottom.

These items are original, written for these notes. They are not taken from CompTIA's exams or any prep provider. They are different from the practice items on the domain pages, so you can still use those afterwards.

If you would rather start with a full timed run, take the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) instead, then come back here.

## Part A: Core 1, Domain 1, Mobile Devices

### D1

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

### D2

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

### D3

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

### D4

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

### D5

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

### D6

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

## Part G: Core 2, Domain 2, Security

### D7

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

### D8

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

### D9

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

## Answer key

| Part | Items | Answers |
|---|---|---|
| Part A | D1 | D |
| Part B | D2 | A |
| Part C | D3 | D |
| Part D | D4 | A |
| Part E | D5 | D |
| Part F | D6 | C |
| Part G | D7 | B |
| Part H | D8 | A |
| Part I | D9 | C |

## What your result means

Note which parts you got right and which you missed.

### Core 1 (220-1201)

| Part | Domain weight | Missed | Correct |
|---|---|---|---|
| A. [Mobile Devices](core-1/1-mobile-devices.md) | 13% | Study the full guide | Light review only |
| B. [Networking](core-1/2-networking.md) | 23% | High priority: learn the ports and Wi-Fi tables | Light review only |
| C. [Hardware](core-1/3-hardware.md) | 25% | High priority: cables, RAM, storage and printers | Light review only |
| D. [Virtualization and Cloud Computing](core-1/4-virtualization-and-cloud-computing.md) | 11% | Study the full guide | Light review only |
| E. [Hardware and Network Troubleshooting](core-1/5-hardware-and-network-troubleshooting.md) | 28% | Top priority: the heaviest Core 1 domain | Still do the items: it is over a quarter of Core 1 |

### Core 2 (220-1202)

| Part | Domain weight | Missed | Correct |
|---|---|---|---|
| F. [Operating Systems](core-2/1-operating-systems.md) | 28% | Top priority: tools and commands | Still do the command items |
| G. [Security](core-2/2-security.md) | 28% | Top priority: malware removal steps and Windows security | Still do the items |
| H. [Software Troubleshooting](core-2/3-software-troubleshooting.md) | 23% | Study the symptom tables | Light review only |
| I. [Operational Procedures](core-2/4-operational-procedures.md) | 21% | Study the full guide | Light review only |

If two domains tie, start with the one with the higher weight.

Then pick a plan: the [7-day plan](study-plans.md#7-day-plan) if you have a week per core, or the [2-day plan](study-plans.md#2-day-plan) if your exam is close.

---

<!-- nav:bottom -->
← Previous: [How CompTIA A+ works](a-plus-overview.md) | Next: [Core 1 (220-1201) overview](core-1/README.md) → | [Back to contents](../README.md#contents)
<!-- /nav:bottom -->
