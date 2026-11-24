<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Core 2, Domain 2: Security](2-security.md) · Next: [Core 2, Domain 4: Operational Procedures](4-operational-procedures.md)<!-- /nav:top -->

# Core 2, Domain 3: Software Troubleshooting

**Weight:** 23% of the Core 2 exam (220-1202) (CompTIA's figure). By our estimate that is roughly 20 of up to 90 questions. **Objectives:** 3.1 to 3.4.

This domain is the help desk queue on a normal Monday: a PC that shows a blue screen, a laptop that says "No operating system found", a phone app that will not update, a phone that suddenly eats its data allowance, a browser that keeps jumping to strange sites. Every objective starts with "Given a scenario", so the exam describes a symptom and asks for the cause or the fix. Candidates lose marks by jumping to the biggest fix (reinstall, factory reset) when a smaller, safer step comes first, or by treating a security symptom as an ordinary fault.

## What this domain measures

Four objectives, all scenario-based. Two cover ordinary faults (Windows, then phones and apps) and two cover the same devices when the cause is security related. Learn each one as a symptom-to-fix table.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 3.1 | Troubleshoot common Windows OS issues | BSOD, degraded performance, boot issues, frequent shutdowns, services not starting, applications crashing, low memory warnings, USB controller resource warnings, system instability, no OS found, slow profile load, time drift |
| 3.2 | Troubleshoot common mobile OS and application issues | Apps that fail to launch, close, update or install, slow response, OS update failures, battery life, random reboots, Bluetooth, Wi-Fi and NFC connectivity, screen not autorotating |
| 3.3 | Troubleshoot mobile OS and application security issues | Unofficial app stores, developer mode, root access and jailbreak, malicious apps and application spoofing, high network traffic, slow response, data-usage warnings, limited or no internet, many ads, fake security warnings, unexpected app behavior, leaked data |
| 3.4 | Troubleshoot common PC security issues | Cannot reach the network, desktop alerts, false antivirus alerts, missing, renamed or locked files, unwanted OS notifications, OS update failures, pop-ups, certificate warnings, redirection, slow browser |

## Key concepts explained

The exam expects you to fix problems the way a careful technician would: gather information, try the least disruptive fix first, and keep the user's data safe. A useful ladder for software faults, from smallest to biggest:

1. Restart the app, or reboot the device.
2. Restart a service, or close what is using too many resources.
3. Update, repair, or uninstall and reinstall the app.
4. Roll back the most recent change: a driver, a Windows update, an app version.
5. Run repair tools: `sfc /scannow`, `DISM`, `chkdsk`, Startup Repair.
6. Use System Restore to go back to a working restore point.
7. Rebuild the user profile.
8. Reset or reimage the OS, after backing up data.

Most "BEST" or "FIRST" answers sit near the top of this ladder unless the stem says the smaller steps already failed.

### 3.1 Windows OS issues

**Tools you will use in this objective.**

| Tool | How to open it | What it tells you or does |
|---|---|---|
| Event Viewer | `eventvwr.msc` | System and Application logs with errors, warnings and event IDs |
| Reliability Monitor | `perfmon /rel`, or search "reliability history" | A day-by-day timeline of app crashes, Windows failures and updates |
| Task Manager | Ctrl+Shift+Esc | CPU, memory and disk use per process; Startup apps tab |
| Resource Monitor | `resmon` | Deeper view of which process uses disk, network and memory |
| Services | `services.msc` | Start, stop, startup type, log-on account and dependencies of each service |
| System Configuration | `msconfig` | Selective startup and boot options, such as Safe boot |
| Windows Memory Diagnostic | `mdsched.exe` | Tests RAM on the next restart |
| System File Checker | `sfc /scannow` (admin prompt) | Checks and repairs protected Windows system files |
| DISM | `DISM /Online /Cleanup-Image /RestoreHealth` | Repairs the Windows image that SFC uses as its source |
| Check Disk | `chkdsk C: /f` or `/r` | Fixes file system errors; `/r` also looks for bad sectors |
| Windows Recovery Environment (WinRE) | Settings > System > Recovery > Advanced startup, or it opens after failed boots | Startup Repair, System Restore, uninstall updates, Command Prompt, Safe Mode |

**Symptom-to-fix table.**

| Symptom | Likely causes | What to do |
|---|---|---|
| Blue screen of death (BSOD) | A bad or new driver, a faulty Windows update, failing RAM, disk errors, overheating | Write down the stop code. Undo the recent change: roll back the driver in Device Manager or uninstall the update, using Safe Mode if Windows will not stay up. Test RAM with `mdsched.exe`, run `chkdsk` and `sfc /scannow`. Crash dump files go to `C:\Windows\Minidump` |
| Degraded performance | Too many startup apps, a process using 100% disk or CPU, low free disk space, malware, too little RAM | Check Task Manager. Disable unneeded startup apps, free disk space with Disk Cleanup or Storage Sense, scan for malware, optimize (defragment) a hard disk, add RAM if memory is always full |
| Boot issues | Damaged boot files, failed update, wrong boot order, disk failure | Let WinRE run Startup Repair. From the WinRE Command Prompt use `bootrec /fixmbr`, `bootrec /fixboot` and `bootrec /rebuildbcd`. Try System Restore or uninstalling the latest update |
| Frequent shutdowns | Overheating (dust, failed fan), a failing power supply, power settings | Check temperatures and clean dust, check fans, test or swap the PSU. In Event Viewer, Kernel-Power event ID 41 means Windows shut down without a clean shutdown |
| Services not starting | A dependency service is stopped, the service account's password changed, a corrupted install | Open `services.msc`, read the Dependencies tab, start the dependency first, check the Log On tab, read the System log for the error. Set the startup type correctly (Automatic, Automatic (Delayed Start), Manual, Disabled) |
| Applications crashing | Bug in the app, missing update, corrupt app files, incompatibility | Check Reliability Monitor or the Application log, update the app, use the app's Repair option in Settings > Apps, reinstall, try compatibility mode for old software |
| Low memory warnings | Too many programs open, a memory leak in one app, a page file that is too small or disabled | Close programs, find the leaking process in Task Manager, let Windows manage the page file (virtual memory), add RAM |
| USB controller resource warnings | Too many USB devices on one controller, often through a hub on a USB 3 port. Windows says the controller is out of resources | Move some devices to ports on a different controller (for example rear ports or a USB 2 port), remove the hub, update chipset and USB drivers |
| System instability | Random freezes and errors from failing RAM, overheating, bad drivers or damaged system files | Test RAM, check temperatures, update or roll back drivers, run `sfc /scannow` and then DISM if SFC cannot repair |
| No OS found | BIOS or UEFI is trying to boot from the wrong device (a USB stick or data disk), the boot drive is not detected, damaged boot records | Remove USB drives and discs, check the boot order in UEFI setup, confirm the drive is detected there, then repair boot files with Startup Repair or `bootrec`. If the drive is not detected, it is a hardware issue |
| Slow profile load | Large roaming profile copying over the network, slow link to the domain controller, a corrupted profile | Check network and domain connectivity, reduce roaming profile size or use folder redirection, and rebuild a corrupted profile (new profile, copy the user's data across) |
| Time drift | A weak CMOS battery, or time sync (NTP) not working | Resync with `w32tm /resync`, check the time zone and Internet Time settings, replace the CMOS battery if the clock resets after power off |

**How to tell similar symptoms apart.**

- "Operating system not found" or "No boot device" right after power on, before the Windows logo, points at boot order or the drive. A Windows logo that then fails, or a repair loop, points at damaged Windows boot files or a bad update.
- A BSOD right after a driver or update install is a software cause: undo the change. A BSOD at random times with different stop codes points at hardware, especially RAM.
- Shutdowns with no blue screen, often under load, point at heat or power.
- If a user gets a "temporary profile" message or a blank desktop at sign-in, the profile is damaged. Slow but normal sign-in is more often network or roaming profile size.

**Why time drift matters.** Domain sign-in uses Kerberos, which by default rejects a clock that is more than 5 minutes off from the domain controller. A drifting clock also makes valid website certificates look "not yet valid" or "expired". So a wrong clock can show up as sign-in failures and certificate warnings, not just a wrong time on the taskbar.

**Safe Mode.** Starts Windows with a minimal set of drivers and services. If the fault disappears in Safe Mode, a driver, startup app or service is the cause. Reach it from WinRE (Troubleshoot > Advanced options > Startup Settings) or with `msconfig` > Boot > Safe boot.

### 3.2 Mobile OS and application issues

**App faults.**

| Symptom | Likely causes | What to do, in order |
|---|---|---|
| App fails to launch | App bug, corrupted cache, app or OS out of date, full storage | Force stop and reopen, restart the phone, update the app, clear the app cache (Android), reinstall |
| App fails to close or crashes | App bug or corrupted data | Force stop, update the app and the OS, clear cache, then clear app data or reinstall |
| App fails to update | Storage nearly full, no Wi-Fi when updates are set to Wi-Fi only, app store account signed out, the new version needs a newer OS | Free storage, connect to Wi-Fi, sign back in to the store, restart the store app (on Android clear the Play Store cache), update the OS |
| App fails to install | Not enough storage, the device or OS version is not supported, MDM policy blocks it, store region or account issues | Check storage and compatibility, check MDM restrictions with IT, check the store account |
| Slow to respond | Storage almost full, many background apps, overheating, low-power mode, old OS | Close apps, restart, free storage, update, let an overheated phone cool down |
| OS fails to update | Not enough storage, low battery, no Wi-Fi, device no longer supported, update deferred by MDM | Free storage, plug in the charger, use Wi-Fi, check whether the model still gets updates, check MDM settings |
| Battery life issues | High screen brightness, apps running in the background, location services, weak cell signal, an ageing battery | Check the battery usage screen to find the app, lower brightness, limit background activity and location, check battery health; replace the battery if health is poor |
| Random reboots | Overheating, a faulty app, a failing battery, an OS bug | Update the OS and apps, remove recently installed apps, check battery health, test in Android safe mode, back up and factory reset as a last step |
| Screen does not autorotate | Rotation lock is on, the app only supports portrait, a faulty motion sensor | Turn off rotation lock (Control Center on iPhone, quick settings on Android), test in an app that supports landscape, then suspect the sensor |

**Platform notes.** On Android you can clear one app's cache or data in Settings > Apps. iOS has no per-app cache button: the options are offload the app (removes the app but keeps its documents and data) or delete and reinstall it. Android **safe mode** starts the phone with third-party apps disabled, which shows whether an installed app causes crashes or reboots.

**Connectivity.**

| Connection | Checks |
|---|---|
| Wi-Fi | Airplane mode off, Wi-Fi on, correct network and password, captive portal sign-in on hotel or guest Wi-Fi, "forget" the network and rejoin, restart the router if many devices fail, reset network settings as a later step |
| Bluetooth | Bluetooth on at both ends, device charged and in pairing mode, within range, remove (forget) the pairing on both devices and pair again, check the device is not connected to another phone |
| NFC | NFC turned on, the right default payment app chosen, phone held within a few centimeters of the reader, a thick or metal case removed |

**Reset network settings** clears saved Wi-Fi networks, Bluetooth pairings and VPN settings but keeps the user's data. A **factory reset** erases everything, so it comes only after a backup and after smaller steps fail.

### 3.3 Mobile OS and application security issues

**Security concerns.** These are the conditions that open a phone up to attack. An exam stem often mentions one of them in passing, and that detail is the clue.

| Concern | What it means | Why it is risky |
|---|---|---|
| Application source or unofficial app stores | Installing apps from outside Google Play or the Apple App Store, called sideloading (on Android, installing an APK file) | Those apps skip the store's review, so malware is far more common |
| Developer mode | Developer options on Android (including USB debugging), or developer mode on iOS | Lets a connected computer install apps and change settings; should be off on normal user devices |
| Root access or jailbreak | Removing the OS's built-in limits to get full control (root on Android, jailbreak on iOS) | Breaks the app sandbox, stops some security updates, and lets malware run with full rights. MDM usually marks the device non-compliant |
| Unauthorized or malicious application | An app the company has not approved, or one that is malware | Can steal data, show ads, use the camera or microphone, or send texts |
| Application spoofing | A fake app made to look like a real one, with a similar name and icon | Users install it thinking it is the bank or messaging app, and give it their passwords |

**Common symptoms of a compromised phone.**

| Symptom | What it suggests |
|---|---|
| High network traffic | An app is sending data out (spyware, a botnet client) or downloading ads |
| Degraded response time | Malware or a cryptominer is using CPU in the background |
| Data-usage limit notification | Far more mobile data used than normal: something is uploading or downloading constantly |
| Limited or no internet connectivity | Malware changed proxy, DNS or VPN settings, or a rogue profile is routing traffic |
| High number of ads | Adware, often inside a free app installed recently |
| Fake security warnings | Pop-ups saying "Your phone is infected, install this cleaner": scareware trying to get another malicious app installed |
| Unexpected application behavior | Apps opening by themselves, settings changing, texts sent that the user did not write |
| Leaked personal files or data | Photos, contacts or messages appearing elsewhere: spyware or stalkerware, or an over-permissioned app |

**Fixing it.** Look at what changed recently and what is using data and battery:

1. Check the data usage and battery screens to find the app responsible.
2. Remove apps the user does not recognize or that came from outside the official store. Check app permissions for anything with camera, microphone, SMS, accessibility or device administrator rights.
3. Remove unknown configuration profiles (iOS) or device admin apps (Android), and turn off developer mode.
4. Update the OS and run a reputable mobile anti-malware app.
5. If the device is rooted or jailbroken, or symptoms continue, back up the user's personal data, factory reset, and reinstall apps only from the official store. Do not restore a full device backup that may contain the malware.
6. Change passwords for accounts used on the phone, from a different, clean device.
7. On company devices, tell IT security and check MDM compliance.

### 3.4 PC security issues

These symptoms usually mean malware. Once you recognize them, the response is the malware removal procedure from Domain 2 (Objective 2.6): investigate and verify, quarantine, disable System Restore, remediate, schedule scans and updates, re-enable System Restore and create a restore point, educate the user.

**System symptoms.**

| Symptom | What is usually behind it | First checks |
|---|---|---|
| Unable to access the network | Malware has changed the proxy settings, DNS servers or the hosts file; ransomware; the PC was quarantined by network access control | Check proxy settings, DNS settings in the adapter, and `C:\Windows\System32\drivers\etc\hosts` |
| Desktop alerts | Messages about infections, warnings or "call this number" that do not come from the installed security software | Check whether the alert comes from Windows Security or the real antivirus; if not, treat it as malware or a scam |
| False alerts regarding antivirus protection | Rogue antivirus (scareware) claiming the PC is infected and asking for payment or a download | Do not click. Identify and remove the rogue program, run the real antivirus |
| Altered system or personal files: missing or renamed files | Ransomware renaming files with a new extension, or malware deleting files | Disconnect from the network first, then investigate |
| Altered files: inability to access files | Ransomware encryption, or changed permissions | Same: isolate, then restore from a known-good backup after cleaning |
| Unwanted notifications within the OS | A website the user allowed to send browser notifications, or adware | Remove the site from the browser's notification permissions, check for adware |
| OS update failures | Malware blocking Windows Update or security sites; also low disk space or corrupted update files | Scan for malware, check free space, run the Windows Update troubleshooter |

**Browser-related symptoms.**

| Symptom | Likely cause | Fix |
|---|---|---|
| Random or frequent pop-ups | Adware, a malicious extension, or a site allowed to show pop-ups or notifications | Remove unknown extensions, turn the pop-up blocker on, reset browser settings, scan for malware |
| Certificate warnings | Wrong system date and time, an expired or self-signed certificate, or an on-path attack intercepting HTTPS | Check the clock first. If warnings appear for well-known sites on one network, suspect interception and leave that network. Never tell users to click through |
| Redirection | A browser hijacker extension, changed search engine or home page, edited hosts file, or rogue DNS settings | Remove the extension, reset the browser, check the hosts file and DNS settings |
| Degraded browser performance | Too many extensions, a cryptomining script or extension, a huge cache | Disable extensions one at a time, clear cache, scan for malware |

**How to tell a real certificate problem from a local one.** If every HTTPS site shows a certificate warning, check the PC's date and time first: a wrong clock breaks all of them. If only one site shows it, that site's certificate may be expired or mismatched. If big, well-known sites show warnings only on one Wi-Fi network, something on that network may be intercepting traffic.

**Reading a hosts file.** Windows checks this file before DNS. A line maps a name to an address. Lines starting with `#` are comments. A normal file has no active entries, or only `127.0.0.1 localhost`. Malware adds entries that send real site names to the attacker's server.

## How questions look

Most items describe one user's symptom and ask for the MOST likely cause, the BEST fix or the FIRST step. Expect a lot of "a user reports..." stems with one key detail, such as "after installing a driver", "from a link in a text message", "only on hotel Wi-Fi" or "the clock is wrong". Some items show a short exhibit: Event Viewer lines, a hosts file, Task Manager numbers, a phone's data-usage screen. Performance-based tasks can ask you to match symptoms to fixes, pick the right repair tool from a list, or walk through a troubleshooting flow on a simulated PC or phone. A few items ask you to "Choose two."

## A method for these questions

1. Decide first: is this an ordinary fault or a security problem? Unknown apps, ads, redirects, data spikes, renamed files and fake alerts all mean security.
2. Find the change. Most stems hide one recent event: an update, a new driver, a new app, a USB stick left in, a new network. The fix usually undoes that change.
3. Match the symptom to its table row, then rule out answers that fix a different symptom.
4. For "FIRST", pick the quickest, least destructive step that tests the likely cause. Check boot order before rebuilding boot files. Restart before reinstalling.
5. For security symptoms, isolate before you clean, and never pick an answer that tells the user to click through a warning or pay a ransom.
6. Prefer answers that keep the user's data safe: back up before reset, reset network settings before factory reset.
7. Reject answers that are real fixes but too big for the stem, such as reimaging for one crashing app.

## Traps that cost points

- **Reimaging or factory resetting first.** It may fix the issue but destroys data and time. Exams want the smallest step that fits, unless smaller steps already failed.
- **Treating "No OS found" as a dead drive.** A USB stick or wrong boot order causes it far more often. Check boot order and detection in UEFI first.
- **Ignoring the clock.** Wrong time causes domain sign-in failures and certificate warnings on every site. Fix time sync or the CMOS battery.
- **Running `sfc` before `DISM` when SFC already failed.** If SFC reports it cannot repair files, run DISM to repair the image, then run SFC again.
- **Calling a data spike a carrier problem.** A sudden data-usage warning on a phone with new unofficial apps is a security symptom. Find and remove the app.
- **Trusting the "virus found" pop-up.** Alerts that ask for payment or a download are scareware. The real antivirus does not ask you to call a number.
- **Clicking through certificate warnings.** A warning on a known site can mean an on-path attack. Find the cause instead.
- **Restoring a full backup onto a rooted or infected phone.** That can bring the malware back. Reset, then reinstall apps from the official store.
- **Forgetting dependencies.** A service that will not start often depends on another stopped service. Check the Dependencies tab.

## Timing

Each Core 2 exam is one 90-minute block of up to 90 questions, so aim for about 1 minute per multiple-choice item on average, with extra time for performance-based questions. Most items in this domain are short symptom stems: read the last sentence first to see whether it asks for a cause, a fix or a first step, then scan the stem for the one key detail. If an exhibit appears (a hosts file, Event Viewer lines), find the odd line rather than reading every line in full.

## Practice items

These 12 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A user installed an updated graphics driver yesterday. Since then, Windows shows a blue screen with the same stop code within a few minutes of every sign-in. What should the technician do?

A. Replace the RAM, because blue screens are caused by memory faults

B. Reinstall Windows from recovery media

C. Boot into Safe Mode and roll back the graphics driver in Device Manager

D. Run `chkdsk C: /r` to look for bad sectors

<details>
<summary>Answer and explanation</summary>

**Answer: C.** The crashes started right after the driver update, so the driver is the most likely cause. Safe Mode loads a basic display driver, so Windows stays up long enough to roll the driver back. (Objective 3.1)

- **A** is wrong because RAM can cause blue screens, but nothing points to memory here and the timing points to the driver.
- **B** is wrong because reinstalling Windows is far bigger than needed for one bad driver.
- **D** is wrong because disk errors do not match a fault that began with a driver install.

</details>

### Item 2

A domain user cannot sign in on one desktop, and Chrome on that desktop shows certificate errors for every HTTPS site. Other PCs work normally. The technician runs a command and sees this:

```
C:\> time /t
09:47
C:\> w32tm /query /source
Local CMOS Clock
```

The real time is 10:02. The clock was correct after the last resync but loses time again after the PC is unplugged overnight. What should the technician do?

A. Replace the CMOS battery, then resync the time with the domain

B. Delete the user's profile and sign in again

C. Clear the browser cache and cookies

D. Remove the desktop from the domain and rejoin it

<details>
<summary>Answer and explanation</summary>

**Answer: A.** The clock is 15 minutes slow, beyond the 5 minutes Kerberos allows by default, which blocks domain sign-in and makes certificates look invalid. It drifts when the PC has no power, so the CMOS battery is failing and should be replaced, then the time resynced. (Objective 3.1)

- **B** is wrong because the profile is not the problem; the clock is.
- **C** is wrong because the certificate errors come from the wrong date and time, not cached data.
- **D** is wrong because rejoining the domain does not fix a clock that keeps drifting.

</details>

### Item 3

A user's desktop showed "No operating system found" this morning. It worked yesterday, and she mentions she left a USB stick in the front port to copy photos. What should the technician do FIRST?

A. Run `bootrec /rebuildbcd` from the Windows Recovery Environment

B. Replace the hard drive

C. Reinstall Windows from recovery media

D. Remove the USB stick and restart, then check the boot order if needed

<details>
<summary>Answer and explanation</summary>

**Answer: D.** The PC is probably trying to boot from the USB stick, which has no OS. Removing it and restarting is the quickest test, and checking the boot order in UEFI comes next if it still fails. (Objective 3.1)

- **A** is wrong because rebuilding boot data is a later step, after ruling out the boot device.
- **B** is wrong because nothing shows the drive has failed.
- **C** is wrong because reinstalling destroys time and possibly data for a fault that may take seconds to fix.

</details>

### Item 4

A user says the banking app on her phone will not update. The app store shows the update but stops with an error. The phone's storage screen shows:

```
Storage: 127.4 GB of 128 GB used
Photos and videos   88.2 GB
Apps                31.6 GB
System               7.6 GB
```

What should the technician do?

A. Factory reset the phone and restore from backup

B. Free up storage by offloading unused apps or moving photos to cloud storage

C. Turn on airplane mode and retry the update

D. Enable developer mode to force the update

<details>
<summary>Answer and explanation</summary>

**Answer: B.** The phone has well under 1 GB free, and updates need room to download and install. Freeing storage fixes the cause. (Objective 3.2)

- **A** is wrong because a reset is far too big, and restoring would bring the full storage back.
- **C** is wrong because airplane mode cuts the connection the update needs.
- **D** is wrong because developer mode does not affect store updates and adds a security risk.

</details>

### Item 5

A user's new phone works with NFC payment terminals at home but not at work, where she keeps the phone in a heavy metal-backed card case. NFC is enabled and the payment app is set as the default. What is the MOST likely fix?

A. Take the phone out of the case when paying

B. Turn on Bluetooth before paying

C. Reset network settings on the phone

D. Install a second payment app as a backup

<details>
<summary>Answer and explanation</summary>

**Answer: A.** NFC works only within a few centimeters, and a thick or metal case can block the signal. The settings are already right, so the case is the likely cause. (Objective 3.2)

- **B** is wrong because NFC payments do not use Bluetooth.
- **C** is wrong because resetting network settings clears Wi-Fi and Bluetooth but does not fix a physical block.
- **D** is wrong because a second app faces the same blocked signal.

</details>

### Item 6

A user reports that videos and photos on her tablet stay in portrait when she turns it sideways. Yesterday they rotated normally. Nothing new was installed. What should the technician check FIRST?

A. Whether the motion sensor needs replacing

B. Whether the tablet needs a factory reset

C. Whether rotation lock is turned on in the quick settings or Control Center

D. Whether the OS is due for an update

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Rotation lock is easy to turn on by accident from the quick settings, and it stops all rotation. It takes seconds to check. (Objective 3.2)

- **A** is wrong because a sensor fault is possible but comes after ruling out the simple setting.
- **B** is wrong because a reset is far too drastic for this symptom.
- **D** is wrong because nothing changed and an update is not the likely cause.

</details>

### Item 7

A salesperson's Android phone has started showing full-screen ads over other apps, and he received a "90% of data plan used" text halfway through the month. Last week he installed a free video editor from a website link because it was not in the Play Store. Choose two actions the technician should take.

A. Increase his mobile data allowance with the carrier

B. Check the data usage screen and uninstall the sideloaded video editor

C. Turn on developer options to view background processes

D. Root the phone so a stronger antivirus can run

E. Run a reputable mobile anti-malware scan and update the OS

<details>
<summary>Answer and explanation</summary>

**Answer: B and E.** The sideloaded app is the likely source of the adware and data use, so it should be found on the data usage screen and removed, then the phone scanned and updated to catch anything left behind. (Objective 3.3)

- **A** is wrong because more data treats the symptom and lets the malware keep running.
- **C** is wrong because developer options add risk and are not needed to remove the app.
- **D** is wrong because rooting removes the OS protections and makes the phone less secure.

</details>

### Item 8

An employee clicked a link in a text message that said her messaging app needed a "security update". She installed what looked like the app, with the same icon and a similar name, and signed in with her work account. Now contacts say they are receiving strange messages from her. What has MOST likely happened?

A. The phone has been jailbroken

B. The phone is out of storage

C. The company Wi-Fi is down

D. She installed a spoofed application that captured her credentials

<details>
<summary>Answer and explanation</summary>

**Answer: D.** A fake app that copies a real app's name and icon is application spoofing. It collected her sign-in and is now sending messages from her account. (Objective 3.3)

- **A** is wrong because nothing in the stem describes removing the OS's restrictions.
- **B** is wrong because full storage does not send messages to contacts.
- **C** is wrong because a Wi-Fi outage would stop messages, not send strange ones.

</details>

### Item 9

The MDM console flags a company-owned Android phone as non-compliant. The user says nothing is wrong. The report shows "Developer options: enabled, USB debugging: on". What should the technician do?

A. Turn off developer options and USB debugging, then check the device's compliance again

B. Remove the phone from MDM so the warning stops

C. Leave it, because developer options only matter for app developers

D. Replace the phone with a new one

<details>
<summary>Answer and explanation</summary>

**Answer: A.** Developer mode and USB debugging let a connected computer install apps and change settings, so they should be off on a user's work phone. Turning them off fixes the cause of the alert. (Objective 3.3)

- **B** is wrong because removing MDM hides the problem and removes company protection.
- **C** is wrong because developer mode is a real security concern on ordinary user devices.
- **D** is wrong because a setting change fixes it; the hardware is fine.

</details>

### Item 10

A user at a coffee shop gets browser certificate warnings when visiting her bank, her email and a major search engine. At home on the same laptop, all three load without warnings, and the laptop's clock is correct. What is the MOST likely cause?

A. The bank's certificate has expired

B. The browser cache is full

C. Something on the coffee shop network is intercepting HTTPS traffic

D. The laptop's CMOS battery is failing

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Several large sites fail only on one network while the clock is right, which points at an on-path attack on that network. She should disconnect and not click through the warnings. (Objective 3.4)

- **A** is wrong because the bank site works at home, and the other sites fail too.
- **B** is wrong because a full cache does not cause certificate errors.
- **D** is wrong because the clock is correct, and a clock fault would affect every network.

</details>

### Item 11

A user says that typing his bank's address always lands on a site that looks slightly different and asks for his card number. The technician opens the hosts file on the PC:

```
# Copyright (c) 1993-2009 Microsoft Corp.
# localhost name resolution is handled within DNS itself.
#       127.0.0.1       localhost
203.0.113.45    www.examplebank.com
203.0.113.45    examplebank.com
```

What is the cause of the redirection?

A. The bank's DNS servers are down

B. The browser's pop-up blocker is turned off

C. The user's browser cache holds an old version of the site

D. Malware added hosts file entries that send the bank's name to another server

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Windows reads the hosts file before asking DNS. The two active lines send the bank's names to a different address, so every visit goes to the fake site. The entries must be removed and the PC cleaned of the malware that added them. (Objective 3.4)

- **A** is wrong because a DNS outage would stop the site loading, not send it to a lookalike.
- **B** is wrong because pop-ups do not change where an address goes.
- **C** is wrong because an old cached page would still be the real bank site.

</details>

### Item 12

An office worker calls to say that the files in her Documents folder now end in `.locked` and will not open, and a text file on the desktop demands payment for a key. Her PC is on the office network with a mapped drive to the file server. What should the technician do FIRST?

A. Pay the demand so the files can be recovered quickly

B. Disconnect the PC from the network

C. Restore her Documents folder from last night's backup

D. Run a full antivirus scan while she keeps working

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Renamed, unreadable files and a ransom note mean ransomware. The first job is to cut the PC off the network so it cannot encrypt the file server through the mapped drive. (Objective 3.4)

- **A** is wrong because paying does not guarantee recovery and funds the attackers; the company decides on incident response, not the technician.
- **C** is wrong because restoring before the malware is removed lets it encrypt the restored files again.
- **D** is wrong because scanning while the PC stays on the network lets the ransomware keep spreading.

</details>

## Score yourself

| Item | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| Answer | C | A | D | B | A | C | B, E | D | A | C | D | B |
| Objective | 3.1 | 3.1 | 3.1 | 3.2 | 3.2 | 3.2 | 3.3 | 3.3 | 3.3 | 3.4 | 3.4 | 3.4 |

- **11 to 12:** strong. Keep the symptom tables fresh with mixed practice, since this domain is almost a quarter of Core 2.
- **8 to 10:** list which objectives you missed. If you picked big fixes (reset, reimage) too early, practice the fix ladder at the top of [Key concepts](#key-concepts-explained). If you missed security items, reread [3.3 Mobile OS and application security issues](#33-mobile-os-and-application-security-issues) and [3.4 PC security issues](#34-pc-security-issues).
- **7 or fewer:** spend two study sessions here. Write the 3.1 symptom table from memory (symptom, cause, fix), then reread [3.1 Windows OS issues](#31-windows-os-issues) and [3.2 Mobile OS and application issues](#32-mobile-os-and-application-issues) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. On a Windows PC or virtual machine, open Reliability Monitor and Event Viewer and find the last app crash and the last unexpected shutdown, run `sfc /scannow` from an admin prompt, and open the hosts file in Notepad to see what a clean one looks like. On your phone, open the battery usage and data usage screens and name the top three apps on each.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Core 2, Domain 2: Security](2-security.md) | Next: [Core 2, Domain 4: Operational Procedures](4-operational-procedures.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
