<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [Core 1, Domain 2: Networking](2-networking.md) · Next: [Core 1, Domain 4: Virtualization and Cloud Computing](4-virtualization-and-cloud-computing.md)
<!-- /nav:top -->

# Core 1, Domain 3: Hardware

**Weight:** 25% of the Core 1 exam (220-1201), CompTIA's figure. By our estimate that is roughly 22 of up to 90 questions. **Objectives:** 3.1 to 3.8.

This is the "build, upgrade and maintain the box" domain: screens, cables and connectors, memory, drives and RAID, motherboards and CPUs, power supplies, and printers. It is the second heaviest domain on Core 1 and it is wide. Most misses come from small facts: a connector name, a RAM generation, the usable capacity of a RAID array, or which printer part a maintenance kit replaces. The tables below are the facts the questions are built on.

## What this domain measures

Objectives 3.1 to 3.4 ask you to compare and recognize components. Objectives 3.5 to 3.8 are "given a scenario": choose and install the right board, CPU, card or power supply, set up a printer, and maintain the four printer types.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 3.1 | Compare display components and attributes | LCD (IPS, TN, VA), OLED, Mini-LED, touch screen and digitizer, inverter, pixel density, refresh rate, resolution, color gamut |
| 3.2 | Summarize cable types, connectors and their purposes | Copper categories, T568A and T568B, coax, STP, UTP, direct burial, plenum, single-mode and multimode fiber, USB, serial, Thunderbolt, HDMI, DisplayPort, DVI, VGA, USB-C, SATA, eSATA, adapters, RJ11, RJ45, F-type, ST, SC, LC, punchdown block, microUSB, miniUSB, Molex, Lightning, DB9 |
| 3.3 | Compare RAM characteristics | SODIMM, DIMM, DDR generations, ECC vs non-ECC, channel configurations |
| 3.4 | Compare storage devices | Spindle speeds, 2.5 and 3.5-inch drives, NVMe, SATA, PCIe, SAS, M.2, mSATA, RAID 0, 1, 5, 6, 10, flash drives, memory cards, optical drives |
| 3.5 | Install and configure motherboards, CPUs and add-on cards | ATX, microATX, ITX, PCI, PCIe, power connectors, headers, M.2, sockets, BIOS and UEFI settings, TPM, HSM, Secure Boot, virtualization, x86, x64, ARM, cores, expansion cards, cooling |
| 3.6 | Install the appropriate power supply | 110 to 120 VAC vs 220 to 240 VAC input, 3.3V, 5V and 12V outputs, 20+4 pin connector, redundant, modular, wattage, efficiency |
| 3.7 | Deploy and configure multifunction devices and printers | Unboxing and location, drivers (PCL vs PostScript), firmware, USB, Ethernet and wireless, sharing and print servers, duplex, orientation, trays, quality, authentication, badging, audit logs, secured prints, scan to email, SMB and cloud, ADF and flatbed |
| 3.8 | Perform printer maintenance | Laser, inkjet, thermal and impact printer parts and maintenance tasks |

## Key concepts explained

### 3.1 Displays

**Display types.**

| Type | How it makes light | Strengths | Weaknesses |
|---|---|---|---|
| LCD, IPS (in-plane switching) | Liquid crystals in front of a backlight | Best color accuracy and widest viewing angles of the LCD types | Weaker contrast than VA, can show "IPS glow" |
| LCD, TN (twisted nematic) | Same | Fastest response, cheapest | Poor viewing angles and color |
| LCD, VA (vertical alignment) | Same | Best contrast (deep blacks) of the LCD types | Viewing angles and response between IPS and TN |
| OLED (organic LED) | Each pixel makes its own light, no backlight | True black, very high contrast, thin | Can suffer burn-in from static images, usually costs more |
| Mini-LED | An LCD whose backlight is thousands of tiny LEDs in local dimming zones | Bright, good contrast for an LCD | Some blooming (halo) around bright objects |

A quick rule: designers who care about color want **IPS** (or OLED), competitive gamers on a budget may pick **TN** for speed, and someone watching films in a dark room likes **VA** or **OLED** contrast.

**Touch screen and digitizer.** The **digitizer** is the layer that senses touch or stylus input and turns it into coordinates. It is separate from the display panel, so a cracked digitizer can stop touch working while the picture is fine, or the other way round. On many phones and laptops the two are fused into one assembly you replace together.

**Inverter.** Older LCDs used a **CCFL** (cold cathode fluorescent lamp) backlight that needs high-voltage AC. The **inverter** converts the laptop's DC power to that AC. A failed inverter or CCFL gives a very dim screen where you can still see a faint image if you shine a flashlight at it. LED-backlit displays do not need an inverter.

**Display attributes.**

| Attribute | Meaning | Examples |
|---|---|---|
| Screen resolution | Number of pixels across and down | 1920 x 1080 (Full HD), 2560 x 1440 (QHD), 3840 x 2160 (4K UHD) |
| Pixel density | Pixels per inch (PPI). Same resolution on a smaller screen looks sharper | A 14-inch 4K laptop screen has higher PPI than a 32-inch 4K monitor |
| Refresh rate | How many times per second the image is redrawn, in hertz | 60 Hz for office work, 120 Hz to 240 Hz for smooth gaming |
| Color gamut | The range of colors the display can show | Often given as a percentage of sRGB or DCI-P3 |

If the picture looks stretched or blurry, set the OS to the panel's **native resolution**.

### 3.2 Cables and connectors

**Copper network cable categories.**

| Category | Maximum speed | Maximum length at that speed |
|---|---|---|
| Cat 5 | 100 Mbps | 100 m |
| Cat 5e | 1 Gbps | 100 m |
| Cat 6 | 1 Gbps at 100 m; 10 Gbps | 10 Gbps up to about 55 m |
| Cat 6a | 10 Gbps | 100 m |
| Cat 8 | 25 or 40 Gbps | 30 m (data center use) |

**T568A and T568B.** The two wiring standards for the eight wires in an RJ45 connector, pin 1 to pin 8 with the clip facing away from you:

| Pin | T568A | T568B |
|---|---|---|
| 1 | White and green | White and orange |
| 2 | Green | Orange |
| 3 | White and orange | White and green |
| 4 | Blue | Blue |
| 5 | White and blue | White and blue |
| 6 | Orange | Green |
| 7 | White and brown | White and brown |
| 8 | Brown | Brown |

The only change is that the orange and green pairs swap places. A **straight-through** cable uses the same standard at both ends (normally T568B). A **crossover** cable has T568A at one end and T568B at the other. Modern ports detect and adjust for this automatically (auto MDI-X), but the exam still expects you to know it.

**Other copper cable features.**

| Term | Meaning |
|---|---|
| UTP (unshielded twisted pair) | The normal office cable. Twisting the pairs cuts interference |
| STP (shielded twisted pair) | Adds foil or braid shielding for areas with heavy electrical interference, such as factories near motors |
| Direct burial | Cable with a tough, waterproof jacket designed to be buried in the ground without a conduit |
| Coaxial | A central copper conductor with a shield around it. RG6 with an F-type connector is used for cable internet and TV |
| Plenum-rated | Jacket that produces less toxic smoke when burning. Required in plenum spaces (above drop ceilings or under raised floors used for air circulation). Normal PVC jacket cable must not run there |

**Fiber optic cable.**

| Type | Light source and core | Distance | Common jacket color |
|---|---|---|---|
| Single-mode | Laser, very thin core | Long, up to many kilometers | Often yellow |
| Multimode | LED or VCSEL, thicker core | Shorter, up to hundreds of meters | Often orange or aqua |

Fiber is immune to electrical interference and is hard to tap.

**Peripheral cables.**

| Cable | Key facts |
|---|---|
| USB 2.0 | Up to 480 Mbps |
| USB 3.0 (renamed USB 3.2 Gen 1) | Up to 5 Gbps. Type-A ports are often blue inside |
| Serial (RS-232) | Old, slow, usually a DB9 connector. Still used for console cables on network equipment |
| Thunderbolt | Thunderbolt 3 and 4 use the USB-C connector and run up to 40 Gbps, carrying data, video and power over one cable. Earlier versions used the Mini DisplayPort connector |

**Video cables.**

| Cable | Signal | Notes |
|---|---|---|
| HDMI | Digital video and audio | TVs, monitors, projectors. Full size, mini and micro connectors |
| DisplayPort | Digital video and audio | Monitors and PCs. Can daisy-chain monitors (MST). Also Mini DisplayPort |
| DVI | DVI-D digital, DVI-A analog, DVI-I both | Older monitors. No audio |
| VGA | Analog video only | Old. 15-pin connector in three rows, often blue. Image can blur at high resolutions |
| USB-C | Video through DisplayPort Alternate Mode or Thunderbolt | Only if the port supports it |

**Hard drive cables.** **SATA** uses a thin 7-pin data cable and a separate 15-pin SATA power connector. SATA III runs at 6 Gbps. **eSATA** is the external version with a sturdier connector; it carries data but not power.

**Adapters.** Convert one connector to another: USB-C to HDMI, DisplayPort to HDMI, DVI to HDMI (works because both are digital), USB to Ethernet, USB to serial. An adapter from a digital output to analog VGA needs an active converter.

**Connector recognition.**

| Connector | What it looks like and where it is used |
|---|---|
| RJ11 | Small 6-position modular plug, phone lines and DSL |
| RJ45 | Larger 8-position modular plug (8P8C), Ethernet |
| F-type | Screw-on coax connector, cable modems and TV |
| ST (straight tip) | Round fiber connector with a bayonet twist lock |
| SC (subscriber connector) | Square fiber connector, push and pull |
| LC (Lucent connector) | Small fiber connector with a latch, often in pairs (duplex). Common on switch SFP modules |
| Punchdown block | Where wires are punched into contacts: 66 blocks (older phone wiring) and 110 blocks (data and patch panels) |
| microUSB | Small trapezoid, older Android phones and accessories |
| miniUSB | Slightly larger, old cameras and devices |
| USB-C | Small reversible oval, current devices |
| Molex | 4-pin power connector (12V and 5V) for older drives and fans |
| Lightning | Apple's 8-pin reversible connector on iPhones before iPhone 15 |
| DB9 | 9-pin D-shaped serial connector |

Memory hooks for fiber: **ST** is "stick and twist", **SC** is "square connector", **LC** is "little connector".

### 3.3 RAM

**Form factors.** **DIMM** modules go in desktops and servers. **SODIMM** modules are shorter and go in laptops, mini PCs and some all-in-ones.

**DDR generations.** Each generation has a notch in a different place, so a module only fits its own generation of slot. They are never interchangeable.

| Generation | DIMM pins | SODIMM pins | Standard voltage |
|---|---|---|---|
| DDR3 | 240 | 204 | 1.5 V (DDR3L 1.35 V) |
| DDR4 | 288 | 260 | 1.2 V |
| DDR5 | 288 (different notch from DDR4) | 262 | 1.1 V |

DDR5 also moves power regulation onto the module and splits each module into two independent subchannels.

**ECC vs non-ECC.** **ECC** (error-correcting code) memory detects and corrects single-bit errors, so it is used in servers and workstations where a silent memory error could corrupt data. The motherboard and CPU must support ECC. Ordinary desktops and laptops use **non-ECC** memory. Do not mix them.

**Channel configurations.** A memory controller can read and write several channels at once. In **dual-channel** mode two matched modules work in parallel, which gives more bandwidth than one larger module. Higher-end boards support triple-channel or quad-channel. To get dual-channel, install modules in the slot pairs the motherboard manual names, often the same-colored slots (for example A2 and B2). Putting both modules on the same channel (A1 and A2) leaves the system in single-channel mode. Matching size and speed gives the best results; mixed modules run at the speed of the slowest.

### 3.4 Storage devices and RAID

**Hard disk drives.** Spinning magnetic platters and a moving head.

| Spindle speed | Typical use |
|---|---|
| 5,400 rpm | Laptops and low-power external drives: quieter, slower |
| 7,200 rpm | Standard desktop drives |
| 10,000 and 15,000 rpm | Older enterprise server drives: fast, loud, small capacity |

Form factors: **3.5-inch** for desktops and servers, **2.5-inch** for laptops (and many SSDs).

**Solid-state drives.** No moving parts, so faster, quieter and more shock resistant.

| Interface | Notes |
|---|---|
| SATA | Up to 6 Gbps (about 600 MB/s). Same interface as hard drives, so a 2.5-inch SATA SSD is an easy upgrade |
| NVMe over PCIe | Talks to the CPU over PCIe lanes. Several times faster than SATA, with speed rising each PCIe generation |
| SAS (Serial Attached SCSI) | Enterprise interface, commonly 12 Gbps, dual-ported for reliability. A SAS controller can run SATA drives, but a SATA controller cannot run SAS drives |

**SSD form factors.** **M.2** is a small card that screws flat to the board. Sizes are named by width and length in millimeters: 2280 is 22 mm wide and 80 mm long, and 2242 is 22 by 42. An M.2 slot can be wired for SATA, NVMe or both. **M key** slots usually support NVMe (PCIe x4). **B key** slots are typically SATA. A SATA M.2 SSD and an NVMe M.2 SSD look almost the same, so always check what the slot supports. **mSATA** is an older, smaller SATA card used in older laptops.

**RAID levels.** RAID combines drives for speed, redundancy or both. RAID is not a backup: deleted or encrypted files are deleted or encrypted on every drive.

| Level | How it works | Minimum drives | Usable capacity | Survives |
|---|---|---|---|---|
| RAID 0 | Striping: data split across drives | 2 | All drives (n x size) | No failures. Losing one drive loses everything |
| RAID 1 | Mirroring: identical copies | 2 | One drive's worth | One drive (in a two-drive mirror) |
| RAID 5 | Striping with parity spread across drives | 3 | (n minus 1) x size | One drive |
| RAID 6 | Striping with double parity | 4 | (n minus 2) x size | Any two drives |
| RAID 10 | A stripe of mirrors (RAID 1 + 0) | 4 | Half of all drives | One drive in each mirrored pair. Losing both drives of one pair loses the array |

**Worked example: four 4 TB drives.**

| Level | Calculation | Usable |
|---|---|---|
| RAID 0 | 4 x 4 TB | 16 TB, no protection |
| RAID 5 | (4 minus 1) x 4 TB | 12 TB, survives one failure |
| RAID 6 | (4 minus 2) x 4 TB | 8 TB, survives any two failures |
| RAID 10 | 4 x 4 TB divided by 2 | 8 TB, survives one failure per pair, and is faster at writes than RAID 6 |

**Mixed drive sizes.** Most RAID treats every drive as the size of the smallest one. Three drives of 2 TB, 2 TB and 1 TB in RAID 5 give (3 minus 1) x 1 TB = 2 TB.

**Removable storage.**

| Type | Notes |
|---|---|
| Flash drives | USB thumb drives |
| Memory cards | SD, microSD and similar cards in cameras, phones and readers. Check the card type and capacity class the device supports |
| Optical drives | CD about 700 MB; DVD 4.7 GB single layer, 8.5 GB dual layer; Blu-ray 25 GB single layer, 50 GB dual layer |

### 3.5 Motherboards, CPUs and add-on cards

**Motherboard form factors.**

| Form factor | Size | Expansion slots | Notes |
|---|---|---|---|
| ATX | 305 x 244 mm (12 x 9.6 inches) | Up to 7 | Standard full-size desktop |
| microATX | 244 x 244 mm (9.6 x 9.6 inches) | Up to 4 | Fits in most ATX cases (mounting holes line up) |
| Mini-ITX | 170 x 170 mm (6.7 x 6.7 inches) | 1 | Small form factor PCs, home theater PCs |

The case must support the board's form factor, and a smaller board fits a bigger case, not the reverse.

**Motherboard connectors.**

| Connector | Purpose |
|---|---|
| PCI | Legacy parallel expansion slot, mostly gone from new boards |
| PCIe | Current expansion slot in x1, x4, x8 and x16 sizes (lanes). A card fits in a slot of its size or larger, and PCIe generations are backward compatible. Graphics cards use x16 |
| Power connectors | 24-pin (20+4) main ATX connector, 4-pin or 8-pin (4+4) CPU power near the socket |
| SATA | Data ports for drives |
| eSATA | External SATA port on the back panel of some boards |
| Headers | Pin connectors for the case's front panel (power switch, reset, LEDs), front USB, front audio, fans (3-pin or 4-pin PWM), RGB lighting |
| M.2 | Slots for SSDs (and Wi-Fi cards on some boards) |

**Compatibility.** The CPU must match the board's **socket** and chipset. Intel desktop CPUs use LGA sockets (pins in the socket, flat pads on the CPU). AMD's AM4 socket is PGA (pins on the CPU), and AM5 is LGA. A board's support list also matters: a socket match does not guarantee a CPU works without a BIOS update. **Multisocket** server boards hold two or more CPUs.

**BIOS and UEFI settings.** UEFI is the modern replacement for BIOS firmware: it supports large GPT drives, a graphical interface and Secure Boot.

| Setting | What it does |
|---|---|
| Boot options | Boot order (SSD, USB, network PXE), and UEFI vs legacy boot mode |
| USB permissions | Enable or disable USB ports or booting from USB |
| TPM security features | Turn on the TPM chip or firmware TPM. Windows 11 requires TPM 2.0 |
| Fan considerations | Fan curves and speed control |
| Secure Boot | Only lets bootloaders signed with trusted keys start, blocking boot-level malware (rootkits) |
| Boot password | A password asked for before the OS starts |
| BIOS password | Also called a supervisor or setup password: needed to change firmware settings |
| Temperature monitoring | Shows CPU and system temperatures, can alarm or shut down when too hot |
| Virtualization support | Intel VT-x or AMD-V (SVM). Must be enabled for hypervisors such as Hyper-V |

**Encryption hardware.** A **TPM** (Trusted Platform Module) is a chip on the motherboard (or built into the CPU firmware) that stores encryption keys securely for one computer, used by BitLocker and Windows Hello. An **HSM** (hardware security module) is a separate, dedicated device, such as a plug-in card or network appliance, that generates and stores keys for many systems, for example for a certificate authority or payment system.

**CPU architecture.**

| Term | Meaning |
|---|---|
| x86 | 32-bit Intel and AMD architecture. A 32-bit OS can use only about 4 GB of RAM |
| x64 | 64-bit extension of x86. Runs 64-bit and 32-bit software and addresses far more memory |
| ARM | A RISC design that is very power efficient. Phones, tablets, Apple silicon Macs and some Windows laptops. Software must be built for ARM or run through emulation |
| Core configurations | Multiple cores on one chip. Simultaneous multithreading (Intel Hyper-Threading) lets one core run two threads. Some CPUs mix performance and efficiency cores |

**Expansion cards.**

| Card | Use |
|---|---|
| Video card | Dedicated graphics. Usually PCIe x16, often needs 6-pin, 8-pin or 16-pin PCIe power from the power supply |
| Sound card | Better audio, more inputs and outputs than onboard audio |
| Capture card | Records or streams video from a camera or game console |
| Network interface card | Adds ports, faster speeds (10 Gbps), fiber or Wi-Fi |

After installing a card: disable the onboard equivalent in UEFI if needed, install the driver, and check Device Manager.

**Cooling.**

| Method | Notes |
|---|---|
| Fans | Case fans move air front to back and bottom to top; CPU and GPU fans sit on heat sinks |
| Heat sink | Metal fins that draw heat away from a chip |
| Thermal paste and pads | Fill the tiny gaps between chip and heat sink. Apply fresh paste whenever you remove a CPU cooler |
| Liquid | A pump moves coolant through a block on the CPU to a radiator with fans. All-in-one units are common |

A PC that shuts down after a few minutes under load, especially after a CPU was reseated, usually means the cooler is not seated or there is no thermal paste.

### 3.6 Power supplies

**Input voltage.** North America uses **110 to 120 VAC**, much of Europe and Asia use **220 to 240 VAC**. Most modern power supplies are auto-switching. Some older or cheaper units have a manual voltage switch; setting 115 V on a 230 V supply can destroy the unit.

**Output voltages.**

| Rail | What uses it |
|---|---|
| 12 V | The biggest load: CPU, graphics card, drive motors, fans |
| 5 V | USB ports, drive electronics, some older components |
| 3.3 V | Chipset logic, M.2 slots and some expansion cards (RAM runs at 1.1 to 1.5 V, made on the motherboard) |

**Connectors.** The **20+4 pin** main connector plugs into the motherboard; the extra 4 pins detach for older 20-pin boards. Others: 4+4 pin CPU power, 6+2 pin PCIe for graphics cards, 15-pin SATA power, Molex for older devices.

**Types and ratings.**

| Feature | Meaning |
|---|---|
| Redundant power supply | Two or more units in one system, usually hot-swappable. If one fails, the other keeps the server running. Connect each to a different power circuit |
| Modular power supply | Cables detach, so you connect only the ones you need. Better airflow and tidier builds. Semi-modular keeps the main cables fixed |
| Wattage rating | The maximum continuous power it can supply. Add up the components' needs and leave headroom |
| Energy efficiency | How much input power reaches the components rather than becoming heat. 80 PLUS ratings: Bronze, Silver, Gold, Platinum and Titanium, in rising order of efficiency |

**Worked example: sizing a power supply.** A build has a CPU rated 105 W, a graphics card rated 285 W, and roughly 90 W for the board, RAM, drives and fans. Total: 105 + 285 + 90 = 480 W. A power supply should not run near its limit all the time, so add headroom of about 30 to 50%: 480 x 1.4 is about 670 W. A 750 W unit with an 80 PLUS Gold rating is a sensible choice. Also check the graphics card maker's recommended wattage and that the unit has the right PCIe power connectors.

### 3.7 Multifunction devices and printers

**Unboxing and location.** Follow the setup guide, remove all shipping tape and locks (many laser printers ship with orange tabs or locks on the toner and scanner), and lift heavy printers with two people or correct lifting technique. Put the device on a stable surface near power and the network, with space for ventilation, trays and service doors, away from direct sunlight, heat and damp.

**Drivers.** Install the driver that matches the operating system and its architecture (x64 or ARM).

| Driver language | Best for |
|---|---|
| PCL (Printer Control Language) | General office printing. Printer-specific, fast, common on Windows |
| PostScript | Graphics, design and publishing. Device-independent, so output looks the same on different printers; common with macOS and design software |

**Firmware.** Update it to fix bugs and security issues, ideally from the manufacturer's site or the device's admin page.

**Device connectivity.** **USB** for one computer. **Ethernet** for a shared office printer with a fixed or reserved IP address. **Wireless** (Wi-Fi, or Wi-Fi Direct for printing without an access point) where cables are not practical.

**Sharing.** A **printer share** is a printer connected to one computer and shared from it: if that computer is off, nobody can print. A **print server** centralizes queues, drivers and permissions for many printers and users.

**Configuration settings.**

| Setting | Meaning |
|---|---|
| Duplex | Print on both sides of the paper. Saves paper; needs a duplexer |
| Orientation | Portrait or landscape |
| Tray settings | Which tray holds which paper size and type, and the default tray |
| Quality | Resolution (dpi), draft vs best, color vs grayscale |

**Security.**

| Feature | What it does |
|---|---|
| User authentication | Users log in at the device or the driver sends credentials |
| Badging | Users tap an ID badge on the printer's reader to log in or release jobs |
| Audit logs | Records who printed, copied, scanned or faxed what and when |
| Secured prints | The job is held until the user enters a PIN or badges in at the printer, so confidential pages are not left in the tray |

**Network scan services.**

| Service | How it works |
|---|---|
| Scan to email | The device sends the scan as an attachment through an SMTP server |
| Scan to SMB | Saves the scan to a shared network folder. Needs the share path and an account with write permission |
| Scan to cloud | Sends the scan to a cloud storage service |

**ADF vs flatbed.** The **automatic document feeder** pulls a stack of loose pages through the scanner one by one. The **flatbed** is the glass for books, photos, fragile or odd-sized items.

### 3.8 Printer maintenance

**Laser printers.** The imaging process, in order:

1. **Processing:** the printer builds the page image in memory.
2. **Charging:** the primary charge roller (or corona wire) puts a uniform negative charge on the imaging drum.
3. **Exposing:** a laser writes the image by neutralizing the charge where toner should go.
4. **Developing:** toner sticks to the exposed areas of the drum.
5. **Transferring:** the transfer roller (or belt) pulls the toner from the drum onto the paper.
6. **Fusing:** the fuser's heat and pressure melt the toner into the paper.
7. **Cleaning:** a blade wipes leftover toner off the drum and the charge is removed, ready for the next page.

| Task | Details |
|---|---|
| Replace toner | When pages fade or the printer reports low toner. Many toner cartridges include the drum |
| Apply maintenance kit | At the page count the manufacturer specifies. Usually a new fuser, transfer roller and pickup rollers or separation pads. Reset the maintenance counter afterwards |
| Calibrate | Aligns color registration and density, run from the printer's menu |
| Clean | Use a toner vacuum (not a normal vacuum, since toner is fine enough to pass through ordinary filters) and lint-free cloths. Let the fuser cool first: it is very hot |

Symptom hooks: toner that smears or rubs off means a fusing problem; a repeating mark at regular intervals down the page points to a roller or drum; paper jams and multiple sheets feeding at once point to worn pickup rollers or separation pads.

**Inkjet printers.** Parts: **ink cartridge**, **printhead** (sometimes built into the cartridge), **roller** and **feeder**. Maintenance: run the **clean printheads** utility for streaks or missing colors, **replace cartridges**, **calibrate** (align) the printheads when lines look jagged or colors misaligned, and **clear jams** gently in the direction of paper travel. Unused inkjets can clog, so regular use helps.

**Thermal printers.** Used for receipts, labels and tickets. They heat **special thermal paper** that darkens where heated, so no ink or toner. The **feed assembly** moves the paper past the heating element. Maintenance: **replace the paper** (with the heat-sensitive side facing the element), **clean the heating element** with isopropyl alcohol when output fades or streaks, and **remove debris** such as dust and label adhesive. Blank output right after a new roll usually means the roll is in the wrong way round or is not thermal paper.

**Impact printers.** Dot matrix printers strike an inked **ribbon** with pins to mark the paper. Their main reason to exist today is **multipart paper** (carbon or carbonless copies), because the impact prints all layers at once. They often use tractor-feed paper with holes along the sides. Maintenance: **replace the ribbon** when print fades, **replace the printhead** when dots are missing in a line across characters, and **replace or reload the paper**, keeping the tractor feed aligned.

## How questions look

Expect recognition items ("Which connector is shown or described?"), comparison items ("Which display type gives the best viewing angles?") and plenty of scenarios: a user upgrading RAM, a drive not detected, a server needing redundancy, a PC that shuts down when hot, a new printer that must hold confidential jobs, a laser printer that smears. RAID questions often give drive counts and sizes and ask for usable capacity or which level meets a requirement. Exhibits can be a pinout, a component list with wattages, or a printer status page. Performance-based questions may ask you to match connectors to cables, choose components for a build, order the laser imaging steps, or pick the right RAID level.

## A method for these questions

1. Identify the objective: display, cable, RAM, storage, board and CPU, power, printer setup or printer maintenance.
2. Underline the requirement words: "best color", "survive two failures", "most capacity", "least cost", "in the ceiling", "confidential".
3. For component choices, check compatibility in this order: form factor and physical fit, interface or socket, generation (DDR, PCIe, SATA vs NVMe), then capacity or speed.
4. For RAID, write the formula for each option and calculate usable space, then check how many failures each survives. Pick the one that meets the requirement, not the biggest number.
5. For power supplies, add up the load, add headroom, and check connectors and input voltage.
6. For printers, name the printer type first, then match the symptom to the part: fuser, rollers, printhead, heating element or ribbon.
7. Rule out answers that skip safety: unplugging, letting the fuser cool, ESD precautions.

## Traps that cost points

- **RAID as a backup.** RAID protects against drive failure, not deletion, ransomware or fire. A question about recovering deleted files wants a backup.
- **Counting RAID 10 as surviving any two failures.** It survives two only if they are in different mirrored pairs. RAID 6 survives any two.
- **M.2 means NVMe.** An M.2 slot or drive can be SATA or NVMe. A mismatch means the drive is not detected.
- **Mixing DDR generations.** DDR4 and DDR5 modules do not fit each other's slots. Laptops need SODIMM.
- **Dual-channel slots wrong.** Two modules on the same channel run single-channel. Follow the manual's slot pairs.
- **PVC cable in the ceiling.** Air-handling spaces require plenum-rated cable.
- **Mixing up fiber connectors.** ST twists, SC is square and pushes in, LC is the small latched one.
- **Normal vacuum for toner.** Toner passes through ordinary vacuum filters and can be a fire risk. Use a toner vacuum, and let the fuser cool.
- **Undersized power supply.** A PSU running at its limit fails early or causes random shutdowns under load. Leave headroom.

## Timing

The exam is one 90-minute block with up to 90 questions, so plan for about a minute per multiple-choice item on average and more for performance-based questions. Recognition items here should take seconds if you know the tables. RAID and power supply items need a quick calculation: write the numbers down rather than doing them in your head, which usually takes under a minute. If a build or connector-matching PBQ looks long, flag it and return after the quick multiple-choice items.

## Practice items

These 2 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A small business buys a storage server with four 4 TB drives. The owner's requirements are:

```
1. The array must keep working if ANY two drives fail at the same time.
2. Within that rule, give the most usable space.
```

Which configuration meets both requirements?

A. RAID 0, 16 TB usable

B. RAID 5, 12 TB usable

C. RAID 10, 8 TB usable

D. RAID 6, 8 TB usable

<details>
<summary>Answer and explanation</summary>

**Answer: D.** RAID 6 uses two drives' worth of parity, so (4 minus 2) x 4 TB = 8 TB usable, and it survives any two drive failures. (Objective 3.4)

- **A** is wrong because RAID 0 has no redundancy; one failure loses all data.
- **B** is wrong because RAID 5 survives only one failure.
- **C** is wrong because RAID 10 survives two failures only if they are in different mirrored pairs. If both drives of one pair fail, the array is lost.

</details>

### Item 2

A technician installs a new M.2 NVMe SSD in a laptop. The drive does not appear in UEFI or in Windows Disk Management. The laptop's manual says its M.2 slot supports "SATA M.2 2280 drives". What is the MOST likely cause?

A. The drive needs to be formatted before UEFI can see it

B. The slot only supports SATA, so the NVMe drive is not compatible

C. The SSD is the wrong length for the slot

D. The laptop needs more RAM to detect an NVMe drive

<details>
<summary>Answer and explanation</summary>

**Answer: B.** An M.2 slot can be wired for SATA, NVMe or both. This slot is SATA-only, so an NVMe drive will not be detected. (Objective 3.4)

- **A** is wrong because firmware detects drives before they are formatted; formatting happens afterwards in the OS.
- **C** is wrong because nothing suggests a size problem, and a wrong-length drive would not mount properly in the first place.
- **D** is wrong because RAM amount does not affect whether a drive is detected.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 | 2 |
|---|---|---|
| Answer | D | B |
| Objective | 3.4 | 3.4 |

- **2 of 2:** strong. Keep the connector and RAID tables fresh, because this is the heaviest hardware block on Core 1.
- **1 of 2:** list the objectives you missed. RAID misses mean redo the worked example in [3.4 Storage devices and RAID](#34-storage-devices-and-raid); printer misses mean reread [3.8 Printer maintenance](#38-printer-maintenance).
- **0 of 2:** spend two study sessions here. Draw the T568A and T568B pinouts, the RAID table and the DDR table from memory, then reread [3.2 Cables and connectors](#32-cables-and-connectors) and [3.5 Motherboards, CPUs and add-on cards](#35-motherboards-cpus-and-add-on-cards) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Open a desktop PC (powered off, unplugged, with an antistatic strap) or find your own PC's specifications, and name every part: the motherboard form factor, CPU socket, RAM type and slot layout, M.2 slot type, PSU connectors and wattage. Then work out the usable capacity of RAID 0, 1, 5, 6 and 10 with six 2 TB drives.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [Core 1, Domain 2: Networking](2-networking.md) | Next: [Core 1, Domain 4: Virtualization and Cloud Computing](4-virtualization-and-cloud-computing.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
