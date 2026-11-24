<!-- nav:top -->[Contents](../README.md#contents) · Previous: [Core 2, Domain 4: Operational Procedures](core-2/4-operational-procedures.md) · Next: [How A+ scoring works](scoring.md)<!-- /nav:top -->

# Performance-based questions and pacing

Both A+ exams, Core 1 (220-1201) and Core 2 (220-1202), mix multiple-choice and drag-and-drop questions with performance-based questions (PBQs). PBQs are where many candidates lose time, not because they are impossible but because they often appear early and people spend too long on them.

## What PBQs are

A PBQ asks you to do something rather than pick a letter. In our own words, the common shapes on A+ are:

**Core 1 (220-1201)**

- **Match:** ports to protocols, connectors to cable types, RAID levels to descriptions, cloud service models to examples.
- **Configure:** set up a SOHO router (SSID, DHCP, port forwarding) or a mobile device's connectivity.
- **Choose parts:** pick the RAM, storage, power supply or adapter that fits a requirement.
- **Troubleshoot:** read symptoms from a PC, printer, display or network and choose the cause or the fix.

**Core 2 (220-1202)**

- **Pick the tool:** match a task to the right Windows utility or command-line tool.
- **Order the steps:** put the malware removal procedure, a backup routine or a change process in sequence.
- **Configure:** apply Windows security settings, account settings, wireless security or browser settings.
- **Troubleshoot:** read an OS, app or mobile security symptom and choose what to do.

CompTIA lists multiple-choice, drag-and-drop and performance-based questions for both cores. It does not publish how many PBQs appear on a given exam or how they are weighted in the score, so treat any number you read online as hearsay.

## A pacing plan for 90 minutes

The same plan works for either core: up to 90 questions in 90 minutes.

| Time on the clock | Where you should be |
|---|---|
| 0 to 2 minutes | Read the instructions. If the first questions are PBQs, read each one, make a quick attempt only if it is obviously short, and flag it |
| By 30 minutes | Roughly a third of the multiple-choice questions done |
| By 60 minutes | Roughly two thirds of the multiple-choice questions done |
| By 75 minutes | All multiple-choice questions answered, including guesses on the hard ones |
| 75 to 88 minutes | Return to the flagged PBQs and finish them |
| Last 2 minutes | Make sure nothing is left blank |

The reasoning is simple. A PBQ might be worth more than one multiple-choice item, but nobody outside CompTIA knows how much more. Fifteen quick questions you never reached because you were stuck on one PBQ are a certain loss. So bank the quick points first, then give the PBQs the time that is left. Some candidates prefer to do PBQs first while fresh; that works if you set a hard limit, such as 4 to 5 minutes each, and move on when it is up.

On average you have about one minute per question. A+ has many short recall items (a port number, a connector, a command), which often take 30 seconds and buy time for PBQs.

## How to approach a PBQ

1. **Read the whole task first,** including every tab, panel and drop-down, before you click anything.
2. **Write the goal in one line** on your notepad: "Secure the SOHO Wi-Fi and give the printer a fixed address" or "Order the malware steps".
3. **Do the parts you are sure of first.** Partial progress on a matching task is better than a blank screen.
4. **Check every constraint** the task gives you, such as "the user must keep their files" or "only one free slot", against each choice.
5. **Look for a reset button** before experimenting, and note the original state.
6. **Stop at your time limit,** make your best choices, and move on.

## Practice task 1: match ports to protocols (Core 1)

A technician is reviewing firewall rules for a small office. Match each port to its protocol. Each protocol is used once, and one protocol is left over.

Ports: **22, 25, 53, 143, 445, 3389**

Protocols: DNS, IMAP, RDP, SMB, SMTP, SSH, Telnet

<details>
<summary>Answer</summary>

| Port | Protocol |
|---|---|
| 22 | SSH (Secure Shell) |
| 25 | SMTP (sending mail) |
| 53 | DNS (name resolution) |
| 143 | IMAP (reading mail kept on the server) |
| 445 | SMB (file and printer sharing, also listed as CIFS) |
| 3389 | RDP (Remote Desktop) |

Telnet is left over: it uses port 23, and it sends everything, including passwords, in plain text, which is why SSH replaced it. A common miss is swapping the mail ports: SMTP 25 sends, POP3 110 and IMAP 143 retrieve. See [Core 1, Domain 2](core-1/2-networking.md#key-concepts-explained).

</details>

## Practice task 2: order the malware removal steps (Core 2)

A user's Windows 11 Home laptop shows pop-ups and a browser that opens to an unknown search page. Put these actions in the order CompTIA's malware removal procedure uses:

- Enable System Restore and create a restore point
- Quarantine the laptop by disconnecting it from the network
- Show the user how the infection probably happened and how to avoid it
- Confirm the symptoms are caused by malware
- Update the anti-malware software
- Disable System Restore
- Schedule scans and run updates
- Scan and remove the malware, using safe mode if needed

<details>
<summary>Answer</summary>

1. Confirm the symptoms are caused by malware (investigate and verify)
2. Quarantine the laptop by disconnecting it from the network
3. Disable System Restore (so the infection is not saved in, or restored from, a restore point)
4. Update the anti-malware software
5. Scan and remove the malware, using safe mode if needed
6. Schedule scans and run updates
7. Enable System Restore and create a restore point
8. Show the user how the infection probably happened and how to avoid it (educate the end user)

The objectives group steps 4 and 5 under "remediate infected systems" and also list reimaging or reinstalling as a remediation option when removal fails. The usual trap is updating or scanning before quarantining, which lets the malware spread while you work. See [Core 2, Domain 2](core-2/2-security.md#key-concepts-explained).

</details>

## Practice under time

PBQ skill improves fastest with timed practice. Work through the practice items on the domain pages, then take the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) and check your pace against the plan above. Next, read [how A+ scoring works](scoring.md).

---

<!-- nav:bottom -->← Previous: [Core 2, Domain 4: Operational Procedures](core-2/4-operational-procedures.md) | Next: [How A+ scoring works](scoring.md) → | [Back to contents](../README.md#contents)<!-- /nav:bottom -->
