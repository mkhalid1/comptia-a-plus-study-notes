<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Core 1 (220-1201) overview](README.md) · Next: [Core 1, Domain 2: Networking](2-networking.md)<!-- /nav:top -->

# Core 1, Domain 1: Mobile Devices

**Weight:** 13% of the Core 1 exam (220-1201), CompTIA's figure. By our estimate that is roughly 11 of up to 90 questions. **Objectives:** 1.1 to 1.3.

This domain is the laptop, phone and tablet part of a help desk job: swapping a battery or a Wi-Fi card, getting a headset or a dock to work, pairing Bluetooth, setting up email and company apps on a phone. It is the lightest Core 1 domain, but the questions are practical and specific. Candidates lose marks by skipping a safety step, mixing up connectors, or not knowing which setting to change on a phone.

## What this domain measures

There are only three objectives, and each one is broad. Objective 1.1 is about the parts inside a laptop and how to replace them safely. Objective 1.2 is about what plugs into or connects to a mobile device. Objective 1.3 is about getting a phone or tablet onto networks and running company apps.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 1.1 | Monitor mobile device hardware and choose the right replacement technique | Battery, keyboard and keys, RAM, HDD and SSD, wireless cards, biometrics, near-field scanners, Wi-Fi antenna connectors and placement, camera, microphone |
| 1.2 | Compare accessories and connectivity options | USB, USB-C, microUSB, miniUSB, Lightning, NFC, Bluetooth, tethering and hotspot, stylus, headsets, speakers, webcam, docking station, port replicator, trackpad, drawing pad, track points |
| 1.3 | Configure basic mobile network connectivity and support apps | Cellular data (3G, 4G, 5G), hotspot, Wi-Fi, SIM and eSIM, Bluetooth pairing steps, GPS and cellular location, MDM for corporate and BYOD devices, synchronization, data caps, calendar, contacts, mail, cloud storage |

## Key concepts explained

### 1.1 Laptop hardware and replacement

**General replacement technique.** Most laptop repair questions reward the same habits. Learn them as a checklist.

1. Back up the user's data if the repair touches storage.
2. Shut down fully, unplug the charger, and disconnect or remove the battery before opening the case. Many modern laptops have an internal battery connector you unplug first.
3. Use ESD protection: an antistatic wrist strap or mat, and touch a grounded surface.
4. Get the manufacturer's service manual. It tells you which parts are user-replaceable and the order to remove them.
5. Use plastic pry tools (spudgers) on clips, not metal screwdrivers.
6. Keep screws organized, for example on a magnetic mat or labelled tray. Laptops use screws of different lengths, and a long screw in the wrong hole can pierce the board.
7. Photograph cable routing before you disconnect anything.
8. Use parts that match the manufacturer's specification.

**Battery.** Laptops and phones use lithium-ion or lithium-polymer batteries. They wear out with charge cycles, so capacity drops over time.

| What you see | What it means | What to do |
|---|---|---|
| Laptop runs for much less time than when new | Battery capacity has worn down | Check battery health, replace if capacity is well below design |
| Case bulging, trackpad lifting, screen not closing flat | Swollen battery, a fire risk | Stop using it, power off, unplug, replace it. Never puncture or press it. Recycle it as hazardous waste |
| Laptop only works on the charger | Battery dead or disconnected | Reseat the battery connector, then replace the battery |
| Laptop gets hot while charging | Possible battery or charging fault | Check the charger is the correct model and wattage; replace faulty parts |

To monitor battery health on Windows, run `powercfg /batteryreport` in a command prompt. It saves an HTML report showing **design capacity** (what the battery held when new), **full charge capacity** (what it holds now) and the **cycle count**. On iPhones, Settings shows battery health as a percentage. Many laptops also have a setting that limits charging to around 80% to slow wear on machines that stay plugged in.

**Keyboard and keys.** A single dead key may just need the keycap and its small scissor clip reseated. Several dead keys in a row, or a whole keyboard failing, usually points to the ribbon cable or a liquid spill. On some laptops the keyboard is a separate part held by screws and clips. On others it is riveted to the top case (palm rest), so you replace the whole top case. A quick workaround while waiting for the part is an external USB or Bluetooth keyboard.

**RAM.** Laptops use **SODIMM** modules (small outline DIMM), which are shorter than desktop DIMMs. Before buying, check:

- The DDR generation the laptop supports (DDR4 and DDR5 are not interchangeable).
- The maximum capacity and the number of slots.
- Whether some or all memory is soldered to the board. Many thin laptops have soldered RAM that cannot be upgraded.

To install, insert the module at an angle (about 30 to 45 degrees) into the slot, then press it down until the side clips lock.

**Storage: HDD and SSD.** Laptop drives are **2.5-inch** SATA drives (HDD or SSD), or **M.2** SSDs. Older laptops may have **mSATA**. An M.2 slot can be wired for SATA, NVMe or both, so check the manual before you buy an M.2 SSD. To upgrade a drive, clone the old drive to the new one or install a fresh OS and restore data from backup. An SSD is faster, quieter, uses less power and handles being dropped better than an HDD, which has spinning platters.

**Wireless cards.** Wi-Fi and Bluetooth usually share one small **M.2** card. Some laptops also have a cellular (WWAN) card. When replacing one, make sure the new card is supported by the laptop, and reconnect the antenna leads.

**Wi-Fi antenna connector and placement.** The Wi-Fi antennas are not on the card. They are thin cables that run from the card up into the **display lid**, usually around the screen bezel, because that is the highest point when the laptop is open. The leads clip onto small round connectors on the card, often labelled main and auxiliary. If you forget to reconnect a lead, or pinch it when reassembling the display, the laptop will see fewer networks and get a weak signal. The same applies after a screen replacement.

**Camera and webcam.** Built into the top of the display bezel, with a cable that runs through the hinge. If the webcam does not work, check in this order: a physical privacy shutter or a keyboard key that disables the camera, the OS privacy settings that allow apps to use the camera, the driver in Device Manager, then the cable after a screen repair.

**Microphone.** Usually in the display bezel or near the keyboard. Same checks as the webcam: a mute key, OS privacy permission for the app, the correct input device selected in sound settings, the driver, then hardware.

**Physical privacy and security components.**

| Component | What it does | Support notes |
|---|---|---|
| Fingerprint reader | Biometric login, often in the power button or near the trackpad | Re-enroll the finger if recognition fails; keep the sensor clean |
| Facial recognition camera | Biometric login using an infrared camera (Windows Hello face) | Needs the IR camera, not just a normal webcam |
| Near-field scanner (NFC reader) | Reads badges, smart cards or NFC tags held a few centimeters away | Used for badge login and tap-to-pair |
| Privacy shutter or screen filter | Physically blocks the camera, or narrows the screen's viewing angle | A closed shutter looks like a "broken" webcam |

### 1.2 Accessories and connectivity

**Wired connection methods.**

| Connector | Where you see it | Key facts |
|---|---|---|
| USB-C | Current Android phones, iPhone 15 and later, iPads, most new laptops | Reversible oval plug. Can carry data, charging (USB Power Delivery) and video, depending on the device |
| microUSB | Older Android phones, cheap accessories, power banks | Small, not reversible, data and charging |
| miniUSB | Very old cameras, GPS units, some game controllers | Larger than microUSB, not reversible, now rare |
| USB Type-A | Laptops, docks, chargers | The classic flat rectangle on the host side of a cable |
| Lightning | Apple iPhones before iPhone 15, older iPads and AirPods | Apple's proprietary 8-pin reversible connector |

Not every USB-C cable or port does everything. A cheap USB-C cable may only charge at low power or carry USB 2.0 data. If a USB-C monitor does not light up, check that the laptop port supports video (DisplayPort Alternate Mode or Thunderbolt).

**Wireless connection methods.**

| Method | Range | Typical use |
|---|---|---|
| NFC (near-field communication) | A few centimeters | Tap-to-pay, badge reading, tap-to-pair a headset |
| Bluetooth | About 10 meters for most devices | Headsets, speakers, keyboards, mice, car kits, wearables |
| Wi-Fi | Tens of meters indoors | Network and internet access |
| Tethering and hotspot | Depends on the link used | Sharing a phone's cellular data with a laptop |

**Tethering and hotspot.** Tethering shares a phone's cellular internet connection with another device. It can run over **USB** (a cable, which also charges the phone), **Bluetooth** (slow, low power) or **Wi-Fi**. A mobile hotspot is the Wi-Fi version: the phone acts as a small access point with its own network name and password. All of it uses the phone's data plan, so watch the data cap. Some carriers restrict or charge for hotspot use.

**Accessories.**

| Accessory | Notes |
|---|---|
| Stylus | Passive styluses work like a finger. Active styluses (pen digitizers) need a compatible screen and support pressure sensitivity and palm rejection. They may need charging or a battery |
| Headsets | Wired (3.5 mm, USB, USB-C) or Bluetooth. Check the headset is selected as both output and input device |
| Speakers | Wired or Bluetooth. If sound still plays from the laptop, change the default output device |
| Webcam | External USB webcams for better quality or when the built-in one fails |
| Trackpad | A separate touchpad, often Bluetooth |
| Drawing pad | A pen tablet used by designers, connected by USB or Bluetooth |
| Track point | The small pointing stick in the middle of some laptop keyboards, used with buttons under the space bar |

**Docking station vs port replicator.**

| | Docking station | Port replicator |
|---|---|---|
| What it does | Adds ports and often extra capability: multiple monitors, Ethernet, charging, sometimes drive bays or expansion slots | Simply duplicates the laptop's existing ports in one place |
| Connection | Traditionally a proprietary connector for one laptop family; now often USB-C or Thunderbolt | USB or a proprietary connector |
| Use case | A full desktop setup from one connection | Quick connect and disconnect of the same peripherals |

On the exam, the difference is that a dock usually **adds** functions, while a port replicator **copies** the ports the laptop already has. Modern USB-C docks blur the line, so read the question for words like "extends" or "duplicates".

### 1.3 Mobile networking and app support

**Cellular data.** Phones and tablets with a cellular radio connect to the carrier's network. You can turn cellular data on or off for the whole device or per app, and **airplane mode** turns off all radios (you can then turn Wi-Fi or Bluetooth back on).

| Generation | What to remember |
|---|---|
| 3G | Old, slow, being shut down by most carriers |
| 4G (LTE) | The common baseline for mobile broadband |
| 5G | Higher speeds and lower latency; coverage and speed vary a lot by location and band |

If a phone shows full bars but no data, check that cellular data is turned on, the phone is not in airplane mode, the plan has not hit its data cap, and the APN settings are correct (usually set automatically by the carrier).

**SIM and eSIM.** The **SIM** (subscriber identity module) identifies the subscriber to the carrier. A physical SIM is a small card in a tray. An **eSIM** is built into the phone and is set up by scanning a QR code from the carrier or through the carrier's app. A phone with an eSIM can still have a physical SIM slot, and many phones hold more than one line. If a user switches phones and has no service, check that the SIM was moved or the eSIM transferred and activated.

**Wi-Fi on a mobile device.** Select the network, enter the passphrase, or install a profile for enterprise Wi-Fi. If a phone keeps using cellular data at the office, check that Wi-Fi is turned on and the saved network is set to join automatically.

**Bluetooth pairing.** Learn the order, because it appears as an ordering question.

1. **Enable Bluetooth** on both devices.
2. **Enable pairing** on the accessory (often hold a button until a light flashes). This makes it discoverable.
3. **Find the device** in the phone's or laptop's Bluetooth list and select it.
4. **Enter the PIN** or confirm the matching code. Older headsets and car kits often use 0000 or 1234; newer devices show a code to confirm on both screens.
5. **Test connectivity**: play audio, type on the keyboard, make a call.

If pairing fails, check that the device is still in pairing mode, is in range, is not already connected to another phone, and has charge. Removing ("forgetting") the old pairing and starting again fixes many problems.

**Location services.**

| Method | How it works | Accuracy |
|---|---|---|
| GPS | Receives signals from satellites | Very accurate outdoors, weak indoors |
| Cellular location | Estimates position from nearby cell towers | Much less accurate, works where there is signal |
| Wi-Fi assisted location | Uses known nearby Wi-Fi networks | Helps indoors and in cities |

Location services can be turned on or off for the whole device and allowed or denied per app. If a delivery or field-service app shows the wrong position, check that location is on, the app has permission (often "precise location"), and GPS is not disabled.

**Mobile device management (MDM).** MDM lets the company enroll, configure and control phones and tablets centrally.

| MDM function | Examples |
|---|---|
| Device configuration | Push Wi-Fi profiles, email accounts, VPN settings, certificates |
| Corporate vs BYOD | Corporate devices: full control. BYOD (bring your own device): a separate work profile or container so the company manages only its own apps and data |
| Policy enforcement | Require a passcode or biometric lock, encryption, minimum OS version; block jailbroken or rooted devices |
| Corporate applications | Install, update and remove company apps from a managed app store |
| Remote actions | Locate, lock, full wipe (corporate devices), or selective wipe of only company data (BYOD) |

The BYOD point matters for scenarios: when an employee leaves, the company removes corporate data and apps without wiping personal photos.

**Mobile device synchronization.** Sync keeps data the same across phone, computer and cloud.

| Data | Common sync method |
|---|---|
| Mail | Exchange or Microsoft 365 account, Gmail, or IMAP. IMAP keeps mail on the server so it matches across devices; POP3 usually downloads and stores mail on one device |
| Calendar and contacts | Synced through the same account (Exchange, Google, iCloud) |
| Business apps and cloud storage | OneDrive, Google Drive, iCloud Drive, and company apps sync files and settings |

For manual mail setup, the common ports are IMAP 143 (993 secure), POP3 110 (995 secure) and SMTP for sending 25 or 587 (secure submission). These ports are tested in detail in Domain 2.

**Recognizing data caps.** Sync can burn through a limited mobile plan, especially photo and video backup and large file sync. Fix it by setting cloud backup to Wi-Fi only, turning off cellular data for heavy apps, or turning on low data mode. The phone's cellular settings show data used per app, which is the fastest way to find the culprit.

## How questions look

Most items are short scenarios: a user reports a symptom, and you choose the most likely cause, the best accessory, or the correct setting. Expect stems such as "A technician just replaced a component and now...", "Which connector should the technician order?", "What should the technician do FIRST?" and "Which feature allows the company to remove only corporate data?". Ordering items ask for the Bluetooth pairing steps or a safe battery replacement sequence. Exhibits can be a battery report, a list of phone settings, or a photo described in words (a bulging case, a connector shape). Performance-based questions may ask you to match connectors to devices or configure a phone's email and network settings.

## A method for these questions

1. Decide which objective you are in: inside the device (1.1), something that connects to it (1.2), or settings and apps (1.3).
2. For a symptom after a repair, assume the repair caused it. A weak Wi-Fi signal after a screen swap means an antenna lead. A dead webcam after a screen swap means the camera cable.
3. For hardware failures, look for the safety step first (power off, unplug, remove the battery, ESD), then the least invasive fix.
4. For connectors, match the device's age and brand: Lightning for older Apple, microUSB for older Android, USB-C for current devices.
5. For settings problems, check the simple toggles before blaming hardware: airplane mode, cellular data, Bluetooth, location permission, privacy switches.
6. For company phones, decide whether the device is corporate or BYOD. That decides between full wipe and selective wipe, and how much control MDM should take.

## Traps that cost points

- **Treating a swollen battery as a charging issue.** A bulging battery is a safety hazard. The fix is to stop using it and replace it, never to recalibrate, puncture or keep charging it.
- **Forgetting the antenna leads.** Wi-Fi antennas live in the display lid. Poor Wi-Fi right after a screen, Wi-Fi card or lid repair points to a loose or pinched antenna cable, not a bad router.
- **Buying the wrong RAM or SSD.** Laptops need SODIMM, the right DDR generation, and some have soldered memory. An M.2 slot may be SATA-only, so an NVMe drive will not be detected.
- **Mixing up NFC and Bluetooth.** NFC works at a few centimeters for taps, payments and badges. Bluetooth covers about 10 meters for headsets and keyboards.
- **Calling every Apple port Lightning.** iPhone 15 and later use USB-C. Read the device model in the stem.
- **Full wipe on a BYOD phone.** For personal devices, the correct choice is a selective wipe of corporate data through MDM.
- **Blaming hardware for a disabled setting.** A privacy shutter, mute key, airplane mode or denied app permission explains many "broken" webcams, microphones and connections.
- **Dock vs port replicator.** A dock adds capability; a port replicator duplicates the laptop's ports.
- **Ignoring data caps.** A phone that runs out of data early is often syncing photos or files over cellular. Set sync to Wi-Fi only.

## Timing

The exam is one 90-minute block with up to 90 questions, so aim for about a minute per multiple-choice item on average and leave extra time for performance-based questions. Items in this domain are usually short. Answer them quickly to bank time for the subnetting, RAID and troubleshooting questions elsewhere in Core 1. If a connector or setting question has you stuck between two options, pick the one that matches the device's age and type, flag it, and move on.

## Practice items

This item is original, written for these notes. It is not taken from CompTIA's exam or any prep provider.

### Item 1

A consultant is at a client site with no guest Wi-Fi. He needs internet on his laptop. His phone has a cellular data plan, and the client does not want any new wireless networks broadcasting in the building. What is the BEST option?

A. Turn on the phone's Wi-Fi hotspot

B. Use USB tethering from the phone to the laptop

C. Pair the laptop with the phone using NFC

D. Insert the phone's SIM card into the laptop's USB port

<details>
<summary>Answer and explanation</summary>

**Answer: B.** USB tethering shares the phone's cellular connection over a cable, so no new Wi-Fi network appears, and the phone charges at the same time. (Objective 1.2)

- **A** is wrong because a hotspot broadcasts a new Wi-Fi network, which the client does not allow.
- **C** is wrong because NFC is for short taps and pairing, not for sharing an internet connection.
- **D** is wrong because a SIM card does not plug into a USB port, and the laptop would need its own cellular modem.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 |
|---|---|
| Answer | B |
| Objective | 1.2 |

- **Correct:** strong. Keep this domain fresh with a few mixed questions a week and put your hours into Domains 2, 3 and 5, which carry far more weight.
- **Missed:** spend a study session here. Write the safe replacement checklist and the Bluetooth pairing steps from memory, build your own connector table, then read [1.3 Mobile networking and app support](#13-mobile-networking-and-app-support) again before redoing the item.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. On a Windows laptop, run `powercfg /batteryreport`, open the HTML file it saves, and work out the battery's health as full charge capacity divided by design capacity. Then open your phone's cellular settings and find the app that used the most data this month.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Core 1 (220-1201) overview](README.md) | Next: [Core 1, Domain 2: Networking](2-networking.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
