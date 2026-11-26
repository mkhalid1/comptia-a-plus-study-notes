<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [Core 1, Domain 4: Virtualization and Cloud Computing](4-virtualization-and-cloud-computing.md) · Next: [Core 2 (220-1202) overview](../core-2/README.md)
<!-- /nav:top -->

# Core 1, Domain 5: Hardware and Network Troubleshooting

**Weight:** 28% of the Core 1 exam (220-1201), CompTIA's figure, the heaviest Core 1 domain. By our estimate that is roughly 25 of up to 90 questions. **Objectives:** 5.1 to 5.6.

This is the help desk job itself: a PC that will not turn on, a drive that clicks, a projector that dies mid-meeting, a phone that will not charge, Wi-Fi that drops, a printer that streaks. Every objective here starts with "Given a scenario", so the exam describes a symptom and asks for the most likely cause or the best next action. Marks are lost by jumping to an expensive fix before checking the simple, likely cause, and by mixing up symptoms that sound alike.

## What this domain measures

Each objective is a list of symptoms. Your job is to link each symptom to its likely causes and to the safe, sensible first fix.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 5.1 | Troubleshoot motherboards, RAM, CPUs and power | POST beeps, proprietary crash screens, blank screen, no power, sluggish performance, overheating, burning smell, random shutdown, application crashes, unusual noise, capacitor swelling, inaccurate date and time |
| 5.2 | Troubleshoot drive and RAID issues | LED status indicators, grinding and clicking, bootable device not found, data loss or corruption, RAID failure, S.M.A.R.T. failure, extended read and write times, low IOPS, missing drives in the OS, array missing, audible alarms |
| 5.3 | Troubleshoot video, projector and display issues | Incorrect input source, cabling, burnt-out bulb, fuzzy image, burn-in, dead pixels, flashing screen, incorrect color, audio issues, dim image, intermittent projector shutdown, sizing issues, distorted image |
| 5.4 | Troubleshoot common mobile device issues | Battery health, swollen battery, broken screen, improper charging, poor or no connectivity, liquid damage, overheating, digitizer issues, damaged ports, malware, cursor drift and touch calibration, app install failures, stylus problems, degraded performance |
| 5.5 | Troubleshoot network issues | Intermittent wireless, slow speeds, limited connectivity, jitter, poor VoIP quality, port flapping, high latency, external interference, authentication failures, intermittent internet |
| 5.6 | Troubleshoot printer issues | Lines, garbled print, jams, faded prints, feed and misfeed problems, pending and frozen queues, speckling, double images, grinding, finishing (staples, hole punch), orientation, tray not recognized, connectivity |

## Key concepts explained

### The troubleshooting methodology

CompTIA's objectives document for Core 1 lists a troubleshooting methodology as a recommended best practice for people starting in IT. It says the methodology itself will not be tested and is not a formal objective, but troubleshooting in the job role still is. Learn it anyway: the scenario items in this domain reward exactly this order of thinking. The steps, in CompTIA's order:

1. **Identify the problem.** Talk to the user, find out what they see and what changed recently, and try to reproduce it. Back up data before you change anything that could lose it.
2. **Establish a theory of probable cause, and question the obvious.** Is it plugged in, switched on, on the right input, connected to the right network? Research the knowledge base or the internet if that helps.
3. **Test the theory to determine the cause.** Swap the cable, try a known-good part, check the setting. If the test disproves the theory, go back and form a new one, or escalate.
4. **Establish a plan of action to resolve the problem and implement the solution.** Think about the impact (downtime, data, other users), get approval where needed, then make the fix.
5. **Verify full system functionality and, if applicable, implement preventive measures.** Confirm with the user that everything works, not just the part you fixed. Prevent a repeat (clean the vents, add a surge protector, schedule backups).
6. **Document findings, lessons learned, actions and outcomes.** Write it in the ticket so the next technician, or you in six months, can fix it faster.

Two habits from this list win points in scenario questions: **check the simple, likely cause first**, and **protect the user's data before risky work**.

**Safety first.** Before opening any computer: power it off, unplug it, and use an ESD strap or mat. Never open a power supply or a CRT; they hold dangerous charges even when unplugged. A burning smell, smoke or a swollen battery means stop and remove power before you diagnose further.

### 5.1 Motherboards, RAM, CPUs and power

| Symptom | Likely causes | What to check or do |
|---|---|---|
| No power (no fans, no lights) | Outlet or power strip off, PSU switch off, bad power cable, failed PSU, front power button cable loose | Check the outlet with a known-good device, check the PSU switch and cable, test the PSU with a power supply tester or swap in a known-good PSU |
| POST beeps | The firmware found a hardware fault before video started: often RAM, video or CPU | Beep patterns differ by firmware vendor and board maker, so look the pattern up in the motherboard manual. Then reseat RAM and expansion cards |
| Blank screen with fans running | Monitor off or on the wrong input, loose video cable, RAM not seated, failed video card, failed motherboard | Check the monitor and cable first, then reseat RAM and the video card, then test with minimal hardware |
| Proprietary crash screens | The OS stopped to protect itself: Windows stop error (blue screen), macOS kernel panic. Often a driver, failing RAM or overheating | Note the stop code, check recent driver or hardware changes, run a memory test, check temperatures |
| Random shutdown | Overheating (thermal protection), failing PSU, loose power connector | Check fans, dust and heat sink contact, then test the PSU |
| Overheating | Dust in vents and heat sinks, failed fan, dried thermal paste, blocked airflow | Clean with compressed air, replace failed fans, reapply thermal paste, keep the case closed so airflow works as designed |
| Sluggish performance | Thermal throttling, not enough RAM, failing drive, background processes or malware | Check temperatures and Task Manager, add RAM, check drive health |
| Application crashes | Faulty RAM, overheating, bad driver or a corrupt app install | If many unrelated apps crash, suspect hardware (RAM, heat). If one app crashes, suspect the app |
| Burning smell | Failing component or PSU, shorted circuit | Power off and unplug immediately. Inspect for scorched parts. Replace the damaged part, often the PSU |
| Unusual noise | Fan bearings (grinding or rattling), loose cable touching a fan, clicking hard drive, high-pitched coil whine | Find the source by listening closely; replace noisy fans; a clicking HDD is a 5.2 problem |
| Capacitor swelling | Bulging or leaking capacitors on the motherboard or PSU, from age or heat | Replace the motherboard or PSU. Do not try to keep running a board with swollen capacitors |
| Inaccurate system date and time | Dead CMOS battery (the coin cell on the motherboard), especially if the clock resets after the PC is unplugged | Replace the CMOS battery (commonly a CR2032), then set the date and time and check firmware settings |

How to tell heat from power: overheating shutdowns usually happen **under load** (games, rendering, video calls) and after some time. A failing PSU can also cut out under load, but if the vents are full of dust and temperatures are high, clean first, because it is the cheaper and likelier fix. A wrong clock also causes certificate errors on websites, so "HTTPS sites show security warnings every morning" can be a CMOS battery question.

**Minimal configuration test.** When a PC will not POST, strip it to the essentials (motherboard, CPU with cooler, one RAM module, PSU, video) and add parts back one at a time. The part you add when it fails again is the suspect.

### 5.2 Drives and RAID

**Drive symptoms.**

| Symptom | Likely causes | What to check or do |
|---|---|---|
| Clicking sounds | Failing HDD read and write heads (mechanical failure) | Back up the data immediately, then replace the drive. Do not run long stress tests first |
| Grinding noises | Failing HDD bearings or platters | Same as clicking: back up first, then replace |
| S.M.A.R.T. failure warning | The drive's own monitoring reports it is likely to fail (reallocated sectors, read errors) | Treat as a warning before failure: back up now and replace |
| Bootable device not found | Boot order points at the wrong drive, a USB stick is left in, boot drive not detected, corrupt boot files, failed drive | Check the boot order in UEFI, remove external media, check whether the drive is detected in firmware, then repair the boot loader or replace the drive |
| Data loss or corruption | Failing drive, sudden power loss, malware, bad cable | Check S.M.A.R.T. status, restore from backup, check file systems (for example `chkdsk` in Windows) once data is safe |
| Extended read and write times | Failing drive retrying bad sectors, nearly full drive, fragmentation on an HDD | Check drive health and free space |
| Low IOPS (input/output operations per second) | An HDD used where an SSD is needed, a degraded or rebuilding RAID array, a slow interface | Move busy workloads to SSD or NVMe, check array status |
| Missing drives in OS | New drive not initialized or partitioned, no drive letter, cable or power not connected, disabled in firmware | Check firmware detection, then Disk Management in Windows to initialize, partition, format and assign a letter |
| LED status indicators | Activity and status lights on drives and RAID enclosures. Amber or red often means a fault, a steady or blinking pattern means activity or rebuild | Check the vendor's LED meanings for the enclosure, then the RAID management software |

**RAID symptoms.**

| Symptom | Likely causes | What to check or do |
|---|---|---|
| RAID failure (degraded array) | One drive failed in an array that has redundancy. The array still works but has no protection left | Confirm backups, replace the failed drive with a matching one, let the array rebuild |
| Array missing | Controller failure, more drives failed than the RAID level tolerates, controller settings reset, cabling | Check the controller and its configuration, cables and power. Do not create a new array over the old disks, because that can destroy the data |
| Audible alarms | Many RAID controllers and storage enclosures beep when an array is degraded or a drive has failed | Open the RAID management tool to find which drive failed. Silencing the alarm does not fix anything |

**How much failure each RAID level survives.** You need this to know whether data is still safe.

| RAID level | Minimum drives | Survives | Usable capacity, 2 TB drives |
|---|---|---|---|
| RAID 0 (striping) | 2 | No drive failure | Four drives: 8 TB |
| RAID 1 (mirroring) | 2 | One drive of the pair | Two drives: 2 TB |
| RAID 5 (striping with parity) | 3 | One drive | Four drives: 6 TB (one drive's worth goes to parity) |
| RAID 10 (mirrored stripes) | 4 | One drive per mirror pair | Four drives: 4 TB |

A degraded RAID 5 still serves data, but a second failure before the rebuild finishes loses the array. That is why the first step is to make sure a backup exists, then replace the failed drive. Remember that RAID is not a backup: deletion and ransomware affect every disk at once.

### 5.3 Video, projectors and displays

| Symptom | Likely causes | What to check or do |
|---|---|---|
| Incorrect input source | Monitor or projector set to HDMI 2 while the cable is in DisplayPort, or similar | Use the input or source button. "No signal" with a working device is often this |
| Physical cabling issues | Loose, damaged or wrong cable, bent pins, an adapter that does not support the resolution | Reseat, swap with a known-good cable, check adapters |
| Burnt-out bulb | Projector lamp at end of life | No image, often with a lamp warning light. Replace the lamp, let the projector cool first, and reset the lamp hour counter |
| Fuzzy image | Not running at the display's native resolution, projector out of focus | Set the native resolution; adjust the projector's focus |
| Display burn-in | A static image (logo, taskbar, dashboard) left for long periods leaves a permanent ghost, mainly on OLED and older plasma screens | Prevention: screen savers, auto-off, moving content. Real burn-in is usually permanent |
| Dead pixels | A pixel that stays black (dead) or one color (stuck) | Stuck pixels sometimes recover with pixel-cycling tools; dead pixels need a panel replacement if over the warranty limit |
| Flashing screen | Loose cable, wrong refresh rate, failing backlight, display driver problem | Reseat or swap the cable, set a supported refresh rate, update or roll back the driver |
| Incorrect color display | Damaged cable or bent pin, wrong color profile or settings, failing panel | Swap the cable, reset color settings or the monitor to factory defaults |
| Audio issues | HDMI and DisplayPort carry audio, so the OS may send sound to the monitor or projector | Check the default playback device in the OS, the display's volume and mute |
| Dim image | Brightness turned down or power-saving mode on, failing backlight, aging projector lamp, projector in eco mode | Check brightness and power settings; a laptop screen that is very dim but faintly visible with a flashlight points to a failed backlight |
| Intermittent projector shutdown | Overheating from a clogged filter, blocked vents or a failed fan; thermal protection shuts it down | Clean or replace the filter, clear the vents, give it space |
| Sizing issues | Wrong resolution or scaling, aspect ratio mismatch, overscan on a TV | Set the native resolution, adjust scaling and aspect ratio, turn off overscan |
| Distorted image | Projector at an angle (trapezoid shape), wrong aspect ratio, damaged cable or panel | Use keystone correction or reposition the projector, set the right aspect ratio |

How to tell a projector bulb from overheating: a **burnt-out bulb** gives no image from the start. **Overheating** gives a good image that shuts off after a while, often with a temperature warning light.

### 5.4 Mobile devices

| Symptom | Likely causes | What to check or do |
|---|---|---|
| Poor battery health | Battery worn by charge cycles and heat; reduced maximum capacity | Check battery health in settings; replace the battery when capacity is low |
| Swollen battery | A failing lithium-ion battery swelling inside the device: the screen lifts, the case bulges, the device rocks on a desk | Stop using and charging it, do not puncture or press it, power off if safe, replace the battery and dispose of the old one through proper battery recycling |
| Broken screen | Physical damage to the glass, the display or both | Back up data, replace the screen assembly; a cracked digitizer can cause ghost touches |
| Improper charging | Bad cable or charger, too low a charger wattage, lint or debris in the port, damaged port, worn battery | Try a known-good cable and charger, inspect and gently clean the port with a non-conductive tool |
| Poor or no connectivity | Airplane mode, Wi-Fi or Bluetooth turned off, weak signal, wrong saved network details, damaged antenna | Toggle airplane mode, forget and rejoin the network, check signal, restart the device |
| Liquid damage | Water or other liquid inside the device | Power off, do not charge, do not use heat to dry it. Many devices have liquid contact indicators technicians can check |
| Overheating | Heavy apps, charging while gaming, sun or a hot car, failing battery, malware | Close heavy apps, remove the case, cool down; persistent heat with a bulge points to the battery |
| Digitizer issues | The touch layer is damaged or failing: touches not registering, or ghost touches | Clean the screen, remove a poor screen protector, restart; replace the digitizer if hardware has failed |
| Physically damaged ports | Bent, loose or broken charging or data port | Repair or replace the port or device; use wireless charging as a stopgap if supported |
| Malware | Pop-ups, unknown apps, fast battery drain, high data use, overheating | Remove unknown apps, update the OS, install apps only from the official store, restore to factory settings if needed |
| Cursor drift or touch calibration | Touches land in the wrong spot or the pointer moves by itself | Clean the screen, remove the protector, restart, use calibration tools if the device has them |
| Unable to install new applications | Storage full, OS version too old for the app, store account issue, restrictions set by MDM or parental controls | Free up space, update the OS, check account and policy restrictions |
| Stylus does not work | Active stylus battery flat or not paired, wrong stylus for the screen, worn tip | Charge and pair the stylus, confirm it is supported, replace the tip |
| Degraded performance | Nearly full storage, too many background apps, thermal throttling, aging battery, outdated OS | Free space, close or remove apps, update the OS, check battery health |

### 5.5 Network issues

Start network problems with the tools you know from Domain 2: `ipconfig` (Windows) or `ip addr` (Linux) to see the address, `ping` to test reachability and timing, `tracert` or `traceroute` to see where along the path delay or loss begins, and `nslookup` for name resolution. For cabling, a cable tester, and for Wi-Fi, a Wi-Fi analyzer.

| Symptom | Likely causes | What to check or do |
|---|---|---|
| Intermittent wireless connectivity | Distance from the access point, walls, interference, overlapping channels, devices roaming badly between APs | Check signal strength with a Wi-Fi analyzer, move closer, change channels, add or move APs |
| Slow network speeds | Congestion, a damaged cable that only links at 100 Mbps, duplex mismatch, weak Wi-Fi, a busy uplink or an old switch | Check the link speed on the NIC, replace the cable, check Wi-Fi signal and channel |
| Limited connectivity | The device has no valid IP configuration. A Windows PC that cannot reach a DHCP server gives itself an APIPA address in 169.254.x.x and can talk only to the local segment | Check the cable and port, then `ipconfig /release` and `ipconfig /renew`, then the DHCP server |
| Jitter | The time between packets arriving varies a lot, even when the average delay is fine | Hurts voice and video. Prioritize real-time traffic with QoS, reduce congestion, use wired connections |
| Poor VoIP quality | High latency, jitter or packet loss: choppy, robotic or delayed voice, dropped calls | Apply QoS for voice, put phones on wired links or a separate VLAN, check bandwidth |
| Port flapping | A switch port goes up and down repeatedly: bad patch cable, failing NIC or transceiver, auto-negotiation problems | Check the switch log for that port, replace the patch cable, test the NIC, set speed and duplex correctly |
| High latency | Long delay: congestion, a slow or distant link, an overloaded device on the path | Use `ping` for timing and `tracert` to find which hop adds the delay |
| External interference | 2.4 GHz Wi-Fi shares the band with microwaves, cordless phones and Bluetooth; copper cables near motors, fluorescent lights or power lines pick up electrical interference | Move the AP or the source, use 5 GHz or 6 GHz, change channel; reroute copper cable or use shielded twisted pair |
| Authentication failures | Wrong Wi-Fi passphrase, expired or locked account, wrong security type, an expired certificate for 802.1X, wrong system time | Re-enter credentials, check the account, check the network's security settings and the device clock |
| Intermittent internet connectivity | ISP or modem problem, overheating or failing router, DNS issues, a failing line | Check whether the LAN still works while the internet drops, power-cycle the modem and router, check the ISP status, test DNS with `nslookup` |

**Reading ping output.** Steady times with no loss mean the path is healthy. High but steady times mean latency. Times that swing widely mean jitter. "Request timed out" for some replies means packet loss.

```
Reply from 10.10.1.1: bytes=32 time=18ms TTL=64
Reply from 10.10.1.1: bytes=32 time=212ms TTL=64
Reply from 10.10.1.1: bytes=32 time=21ms TTL=64
Reply from 10.10.1.1: bytes=32 time=164ms TTL=64
```

This output shows large swings between replies with no loss: jitter. Voice calls over this link would sound choppy. A common rule of thumb for voice is one-way delay under about 150 ms.

**How to tell limited connectivity from an internet outage.** If the PC has a 169.254.x.x address, the problem is local: cable, port or DHCP. If it has a normal address and can reach the gateway but not websites, look at the router, ISP or DNS.

### 5.6 Printers

Most printer symptoms point at one part of the printer. Learning the link between symptom and part is most of this objective.

| Symptom | Likely causes | What to check or do |
|---|---|---|
| Lines down the printed pages | Laser: scratched or dirty imaging drum, or dirty corona or charge roller. Inkjet: clogged print head nozzles | Laser: replace the toner cartridge or imaging drum. Inkjet: run the head cleaning utility, then replace the cartridge or head |
| Garbled print | Wrong or corrupt printer driver, a corrupted job, a language mismatch (for example sending PostScript to a printer expecting PCL) | Install the correct driver for the exact model, cancel and resend the job, power-cycle the printer |
| Paper jams | Wrong paper type or weight, damp or curled paper, worn rollers, a torn scrap left in the path | Remove all paper scraps following the path, use the right paper, clean or replace rollers |
| Faded prints | Low toner or ink, toner-save or draft mode, density setting too low; on thermal printers, a worn head or wrong heat setting | Replace toner or ink, check print quality and density settings |
| Paper not feeding | Worn or dirty pickup rollers, tray guides set wrong, tray overfilled, wrong paper size set | Clean or replace the pickup roller, adjust guides, load paper correctly |
| Multipage misfeed (several sheets at once) | Worn separation pad, humid paper sticking together, overfilled tray | Fan the paper before loading, store it dry, replace the separation pad |
| Multiple prints pending in queue | Printer offline or paused, a stuck job blocking the rest, wrong port | Check that the printer is online and not paused, clear the job at the front of the queue |
| Frozen print queue | The Windows Print Spooler service has hung on a job | Stop the Print Spooler service, delete the stuck files in `C:\Windows\System32\spool\PRINTERS`, start the service again |
| Speckling on printed pages | Laser: loose toner from a leaking cartridge, dirty drum or toner inside the printer | Replace the toner cartridge, clean the inside with a toner-rated vacuum, not a normal vacuum |
| Double or echo images (ghosting) | Laser: the drum is not fully cleaned or discharged between rotations, or a worn imaging unit or fuser | Replace the imaging drum or toner cartridge; check the fuser if the problem stays |
| Grinding noise | Stripped or damaged gears, failing fuser or motor, an object in the paper path | Check for foreign objects, then service or replace the gear assembly or fuser |
| Finishing issues: staple jams | Jammed staple cartridge, wrong staple cartridge, too many sheets for the stapler | Clear the jam, use the right cartridge, stay within the stapler's sheet limit |
| Finishing issues: hole punch | Hole punch waste bin full, wrong alignment settings | Empty the punch waste bin, check finisher settings in the driver |
| Incorrect page orientation | Portrait or landscape set wrong in the app or driver, or the driver defaults differ from the job | Check the application's page setup and the driver's printing preferences |
| Tray not recognized | Tray not seated, tray or finisher not enabled in the driver's installable options, sensor fault | Reseat the tray, enable the tray in the driver's device settings, check the printer's own tray status |
| Connectivity issues | Printer's IP address changed, Wi-Fi dropped, wrong port in the driver, firewall, USB cable | Print a configuration page to see the printer's IP, give network printers a static address or DHCP reservation, check the port in the driver |

How to tell toner problems from fuser problems: if toner **smears or rubs off**, the fuser is not bonding it to the paper. If marks are **lines or spots in the same place on every page**, look at the drum or cartridge.

## How questions look

Almost every item is a symptom scenario. Common stems: "A user reports... What is the MOST likely cause?", "Which should the technician do FIRST?", "Which is the BEST way to resolve...?" and "Choose two" items asking for two valid fixes. Exhibits include `ping` and `ipconfig` output, switch logs, RAID controller status screens and S.M.A.R.T. reports. Performance-based questions may give you a set of symptoms to match to causes, ask you to put the actions for a scenario in a sensible order, or ask you to pick fixes for a misbehaving printer or network.

## A method for these questions

1. Name the symptom in one plain phrase (no power, clicking drive, no signal, swollen battery, jitter, lines on the page), and note when it happens: at start-up, under load, after an hour, when the microwave runs.
2. Check safety and data first. Burning smell, swelling or liquid means remove power. Clicking or a S.M.A.R.T. warning means back up before anything else.
3. Question the obvious: power, cables, input source, airplane mode, paper, toner.
4. Choose the most likely cause for the exact symptom, not every possible one. "No image" and "image that shuts off after 30 minutes" have different causes.
5. Prefer the cheapest, least disruptive test that confirms the theory: swap a cable, try a known-good part, check a setting.
6. For "FIRST" items, place the scenario on the methodology: identify, theorize, test, plan and fix, verify, document. Pick the step that comes next.
7. For exhibits, read every line: an APIPA address, a "Failed" disk, swinging ping times or a port going up and down usually gives the answer away.

## Traps that cost points

- **Replacing parts before checking the obvious.** Swapping a motherboard when the monitor was on the wrong input wastes time and money. Check power, cables and inputs first.
- **Testing a failing drive before saving the data.** Long scans and defragmentation can finish off a clicking drive. Back up first.
- **Treating a degraded RAID as safe.** It still works, but one more failure can lose everything. Confirm backups and replace the failed drive now.
- **Creating a new array when the old one goes missing.** That can wipe the data. Check the controller, cables and settings first.
- **Charging or pressing a swollen battery.** It is a fire risk. Stop charging and arrange a safe replacement.
- **Confusing latency and jitter.** Latency is how long packets take. Jitter is how much that delay varies. Voice suffers from both, and QoS is the usual fix.
- **Blaming the ISP for a 169.254 address.** APIPA means the PC never got an address from DHCP. The fault is local.
- **Confusing a bulb with overheating.** No image at all suggests the bulb. A good image that shuts off later suggests heat and a clogged filter.
- **Fuser vs drum mix-ups.** Smearing toner is the fuser. Repeating lines or spots are the drum or cartridge. Garbled characters are the driver.

## Timing

Across the whole exam, plan on about a minute per multiple-choice item, and longer for performance-based questions. With roughly a quarter of Core 1 here, steady pace matters. Most symptom items can be answered in under a minute once you name the symptom. Exhibit items (ping, switch logs, RAID status) take a little longer, so read the exhibit before the options. If a PBQ asks you to match many symptoms to causes, do the ones you are sure of first and come back for the rest.

## Practice items

These 2 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A file server in a back office is beeping. The technician opens the RAID management tool and sees the following.

```
Controller alarm ..... ON
Array 0 .............. RAID 5, 4 x 2 TB, Status: DEGRADED
  Disk 0 ............. Online
  Disk 1 ............. Online
  Disk 2 ............. FAILED
  Disk 3 ............. Online
Volume ............... Accessible
```

Recent backups are confirmed. What should the technician do next?

A. Replace Disk 2 with a matching drive and let the array rebuild

B. Delete Array 0 and create a new RAID 5 array from the remaining disks

C. Replace all four disks at once

D. Silence the alarm and schedule a check in a few months

<details>
<summary>Answer and explanation</summary>

**Answer: A.** RAID 5 survives one failed drive, so the data is still accessible, but there is no protection left. Replacing the failed disk and rebuilding restores redundancy. (Objective 5.2)

- **B** is wrong because deleting the array destroys the data on it.
- **C** is wrong because only one disk has failed; pulling the healthy ones would break the array.
- **D** is wrong because a second failure before repair would lose the array. Silencing the alarm fixes nothing.

</details>

### Item 2

Laptops in a break room lose their Wi-Fi connection whenever the microwave is running. The access point is mounted on the wall right next to the microwave and broadcasts only on 2.4 GHz. Which two actions would BEST fix this? Choose two.

A. Lengthen the DHCP lease time

B. Replace the wired switch that feeds the access point

C. Enable 5 GHz on the access point and connect the laptops to it

D. Rename the wireless network

E. Move the access point away from the microwave

<details>
<summary>Answer and explanation</summary>

**Answer: C and E.** Microwave ovens interfere with the 2.4 GHz band. Moving the clients to 5 GHz avoids that band, and moving the AP away reduces the interference. (Objective 5.5)

- **A** is wrong because the drop is caused by radio interference, not by addresses expiring.
- **B** is wrong because the wired side works; the problem appears only when the microwave runs.
- **D** is wrong because the network name has no effect on radio interference.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=vv7axy&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 | 2 |
|---|---|---|
| Answer | A | C, E |
| Objective | 5.2 | 5.5 |

- **2 of 2:** strong. This is the heaviest Core 1 domain, so keep it warm with mixed symptom drills from every objective.
- **1 of 2:** list the objectives you missed. RAID status, ping output and printer parts are the usual weak spots; reread those tables in [Key concepts](#key-concepts-explained).
- **0 of 2:** spend two study sessions here. Write the six methodology steps and the RAID table from memory, then reread [5.2 Drives and RAID](#52-drives-and-raid), [5.5 Network issues](#55-network-issues) and [5.6 Printers](#56-printers) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. On a Windows PC, run `ping -n 50` to your router and then to a website, and `tracert` to the same site. Note the lowest, highest and average times and say whether you see latency, jitter or loss. Then open Services, find Print Spooler, and practice the stop, clear and start sequence on a test machine.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=vv7axy&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [Core 1, Domain 4: Virtualization and Cloud Computing](4-virtualization-and-cloud-computing.md) | Next: [Core 2 (220-1202) overview](../core-2/README.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
