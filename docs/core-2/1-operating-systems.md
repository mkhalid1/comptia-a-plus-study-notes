<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Core 2 (220-1202) overview](README.md) · Next: [Core 2, Domain 2: Security](2-security.md)<!-- /nav:top -->

# Core 2, Domain 1: Operating Systems

**Weight:** 28% of the Core 2 exam (220-1202, CompTIA's figure), tied with Security as the heaviest Core 2 domain. By our estimate that is roughly 25 of up to 90 questions. **Objectives:** 1.1 to 1.11.

This domain is the help desk technician's toolbox: installing and upgrading Windows, knowing which edition can do what, finding the right console or Settings page, typing the right command with the right switch, and getting by on a Mac or a Linux box when a ticket lands there. It has eleven objectives, tied with Security for the most in A+, and most of the marks are lost on small exact details: a switch, a file system limit, an edition feature, or which tool shows which information.

## What this domain measures

The objectives move from "what is out there" (OS types, file systems, editions) to "use it on a live machine" (Windows tools, commands, settings and networking), then to macOS and Linux, installing applications, and cloud productivity suites. Seven of the eleven objectives start with "Given a scenario", so expect a user's problem in the stem and a tool or setting as the answer.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 1.1 | Explain common OS types and their purposes | Windows, Linux, macOS, ChromeOS, iOS, iPadOS, Android, NTFS, ReFS, FAT32, ext4, XFS, APFS, exFAT, end-of-life, update limits, compatibility |
| 1.2 | Perform OS installations and upgrades | Boot methods (USB, network, internet-based, partition, multiboot), clean install, upgrade, image and zero-touch deployment, recovery partition, repair install, third-party drivers, GPT vs MBR, upgrade considerations, feature updates |
| 1.3 | Compare Windows editions | Windows 10 Home, Pro, Pro for Workstations, Enterprise; Windows 11 Home, Pro, Enterprise; N versions; domain vs workgroup; RDP; RAM limits; BitLocker; gpedit.msc; upgrade paths; TPM and UEFI |
| 1.4 | Use Windows features and tools | Task Manager tabs, MMC snap-ins (.msc consoles), msinfo32, resmon, msconfig, cleanmgr, dfrgui, regedit |
| 1.5 | Use Windows command-line tools | cd, dir, ipconfig, ping, netstat, nslookup, net use, tracert, pathping, chkdsk, format, diskpart, md, rmdir, robocopy, hostname, net user, winver, whoami, /?, gpupdate, gpresult, sfc |
| 1.6 | Configure Windows settings | Control Panel items, File Explorer Options, Power Options, the Settings app categories |
| 1.7 | Configure Windows client networking | Domain vs workgroup, shared resources, firewall rules, IP, subnet mask, gateway, DNS, static vs dynamic, VPN, Wi-Fi, wired, cellular, proxy, public vs private, network paths, metered connections |
| 1.8 | Explain macOS features and tools | .dmg, .pkg, .app, App Store, uninstalling, system folders, Apple ID, System Preferences, Disk Utility, FileVault, Terminal, Force Quit, Mission Control, Keychain, Spotlight, iCloud, Continuity, backups, Rapid Security Response |
| 1.9 | Identify Linux features and tools | ls, pwd, mv, cp, rm, chmod, chown, grep, find, fsck, mount, su, sudo, apt, dnf, ip, curl, dig, traceroute, man, cat, top, ps, du, df, nano, key /etc files, systemd, kernel, bootloader, root |
| 1.10 | Install applications to requirements | 32-bit vs 64-bit, GPU and VRAM, RAM, CPU, hardware tokens, storage, OS compatibility, ISO vs physical media, packages, image deployment, impact on device, network, operations and business |
| 1.11 | Install and configure cloud productivity tools | Email, cloud storage and sync settings, collaboration apps, identity synchronization, license assignment |

## Key concepts explained

### 1.1 OS types and file systems

**Workstation operating systems.**

| OS | Who makes it | Where you meet it | Points to remember |
|---|---|---|---|
| Windows | Microsoft | Most business desktops and laptops | Widest software and hardware support, domain management with Active Directory |
| macOS | Apple | Mac computers only | Unix-based, tight hardware and software integration |
| Linux | Open source (many distributions such as Ubuntu, Fedora, Debian) | Servers, developer machines, older PCs | Free to use, highly configurable, command line is central |
| ChromeOS | Google | Chromebooks, schools, kiosks | Browser-centered, built on a Linux kernel, runs web and Android apps, updates itself automatically |

**Mobile operating systems.**

| OS | Hardware | App source |
|---|---|---|
| iOS | iPhone only | Apple App Store |
| iPadOS | iPad only (split from iOS to add tablet multitasking) | Apple App Store |
| Android | Many manufacturers (Samsung, Google Pixel and others) | Google Play, plus other stores and sideloading |

**File systems.** This table is worth memorizing, because scenario items hinge on file size limits and which OS can read what.

| File system | Typical home | Key facts |
|---|---|---|
| NTFS | Windows system and data drives | Permissions, EFS encryption, compression, disk quotas, journaling, very large files. macOS reads NTFS but cannot write to it without extra software |
| ReFS (Resilient File System) | Mainly servers and large data volumes | Built for integrity and large volumes, detects and repairs corruption when used with Storage Spaces |
| FAT32 | Older USB drives, small cards, cross-device use | Read and write on almost everything. Maximum file size 4 GB |
| exFAT | USB flash drives, SDXC cards, drives shared between Windows and macOS | No practical file size limit for desktop use, read and write on Windows and macOS. No permissions or journaling |
| ext4 | Default on many Linux distributions (Ubuntu, Debian) | Journaling, large files and volumes. Windows cannot read it natively |
| XFS | Default on Red Hat Enterprise Linux and its relatives | High-performance journaling for large files and volumes. Can grow but cannot shrink |
| APFS (Apple File System) | macOS, iOS and iPadOS | Built for SSDs, snapshots (used by Time Machine), built-in encryption, space-sharing volumes. Windows cannot read it natively |

**Vendor life-cycle limitations.** Once an OS reaches **end-of-life (EOL)**, the vendor stops releasing security patches. The machine still boots, but every new vulnerability stays open forever. Microsoft ended support for Windows 10 on October 14, 2025, with paid Extended Security Updates as a stopgap. **Update limitations** also hit hardware: older phones and tablets stop receiving new OS versions, and apps then stop supporting those versions. Chromebooks have an automatic update expiration date.

**Compatibility concerns between operating systems.** File systems (above), file formats, applications that exist on only one platform, peripheral drivers, and line endings or paths in scripts. A common help desk answer is a web or cloud version of an app that works on every OS.

### 1.2 Installing and upgrading

**Boot methods for installing an OS.**

| Method | How it works |
|---|---|
| USB | A bootable flash drive made with Microsoft's Media Creation Tool or similar. The most common method for a single PC |
| Network | The PC boots with PXE (Preboot Execution Environment) from the network card and pulls the installer from a deployment server |
| Solid-state or flash drives | Any bootable SSD or flash media, internal or external |
| Internet-based | The installer downloads over the internet, such as macOS Recovery over the internet or Windows "Reset this PC" with cloud download |
| External or hot-swappable drive | Boot from a USB or Thunderbolt external drive that holds the installer or an image |
| Internal hard drive (partition) | Boot from an installer or recovery image stored on its own partition |
| Multiboot | Two or more operating systems on one machine, with a boot menu at startup to choose one |

You choose the boot device in the UEFI setup or a one-time boot menu.

**Types of installations.**

| Type | What happens | When to use it |
|---|---|---|
| Clean install | Wipe the drive and install fresh. Apps and data must be restored afterward | New drive, badly broken system, changing from 32-bit to 64-bit, removing malware completely |
| Upgrade (in-place) | Install the new version over the old one, keeping files, settings and apps | Moving a working PC to a newer version |
| Image deployment | Install a prepared, captured image (OS, apps, settings) onto many PCs | Rolling out identical machines in a company |
| Remote network installation | Install over the network from a deployment server, usually with PXE | Many PCs without carrying USB drives around |
| Zero-touch deployment | The device ships straight to the user and configures itself on first sign-in by enrolling in the company's management service (Windows Autopilot is Microsoft's version) | Remote workers, large rollouts |
| Recovery partition | A hidden partition from the manufacturer that restores the PC to factory state | Reset to how it came out of the box. Data is lost |
| Repair installation | Reinstall Windows over itself, keeping files and apps, to replace damaged system files | Windows is broken but the data and apps should stay |

**Third-party drivers.** If setup cannot see the drive, it usually needs a storage controller driver (RAID or some NVMe controllers). Use the **Load driver** option in Windows Setup and point it at the driver on a USB stick.

**Partitioning: MBR vs GPT.**

| | MBR (Master Boot Record) | GPT (GUID Partition Table) |
|---|---|---|
| Firmware | Legacy BIOS | UEFI |
| Maximum disk size | 2 TB | Far beyond any disk you will meet |
| Partitions | 4 primary, or 3 primary plus 1 extended holding logical drives | Up to 128 in Windows |
| Resilience | One partition table at the start of the disk | Backup copy of the table at the end of the disk, with checksums |
| Windows 11 system disk | Not supported | Required (Windows 11 needs UEFI) |

If a 4 TB disk shows only 2 TB usable, it was initialized as MBR. Convert it to GPT (this erases the partitions on it, so back up first).

**Drive format.** A **quick format** writes a new empty file system. A **full format** also checks every sector for errors and, on modern Windows, overwrites the data with zeros, so it takes much longer.

**Upgrade considerations.**

- **Back up files and user preferences** first. Upgrades usually keep data, but you do not bet a user's files on "usually".
- **Application and driver support and backward compatibility:** check that critical apps and drivers support the new version.
- **Hardware compatibility:** for Windows 11, run the PC Health Check app or confirm TPM 2.0, UEFI with Secure Boot, and a supported CPU.

**Feature updates and the product life cycle.** Windows gets monthly **quality updates** (security and bug fixes, released on the second Tuesday of the month) and an annual **feature update** that adds features and resets the support clock. A PC that falls behind on feature updates eventually stops getting security updates even though the product line is still supported.

### 1.3 Windows editions

**Feature comparison.**

| Feature | Home | Pro | Pro for Workstations (Windows 10) | Enterprise |
|---|---|---|---|---|
| Join a domain | No (workgroup only) | Yes | Yes | Yes |
| Host Remote Desktop (be connected to) | No (can only connect out as a client) | Yes | Yes | Yes |
| BitLocker | No (some hardware offers simpler "device encryption") | Yes | Yes | Yes |
| gpedit.msc (Local Group Policy Editor) | No | Yes | Yes | Yes |
| Maximum RAM (64-bit) | 128 GB | 2 TB | 6 TB | 6 TB |
| Extras | | Hyper-V, domain Group Policy | ReFS volumes, persistent memory support, up to 4 CPUs, faster file sharing (SMB Direct) | Volume licensing, advanced security and management features (for example AppLocker, Credential Guard) |
| How you get it | Retail or preinstalled | Retail, preinstalled, or upgrade from Home | Workstation PCs | Volume licensing through an organization |

Windows 11 has Home, Pro and Enterprise (plus Pro for Workstations and Education, which the objectives do not list). The feature split is the same as above. Any 32-bit edition of Windows 10 can use at most 4 GB of RAM; Windows 11 is 64-bit only.

**N versions.** Editions sold mainly in Europe without Windows Media Player and related media apps, because of a competition ruling. Media playback features can be added with the free Media Feature Pack. If a user on an "N" edition says videos or some apps will not play media, this is the reason.

**Domain vs workgroup.** In a **workgroup**, every PC keeps its own user accounts, and sharing is peer to peer. Fine for a home or a handful of PCs. In a **domain**, a server running Active Directory holds the accounts, so users sign in anywhere with one account and IT pushes settings with Group Policy. Home edition cannot join a domain, which is the classic exam fact.

**Desktop styles and user interface.** Windows 10 has a left-aligned Start menu with live tiles and an optional tablet mode. Windows 11 centers the taskbar and Start menu by default, replaces live tiles with pinned apps and widgets, and adds snap layouts for arranging windows.

**Upgrade paths.**

- **In-place upgrade:** Windows 10 to Windows 11 on supported hardware, keeping files and apps, as long as you stay within an edition family (Home to Home, Pro to Pro).
- **Edition upgrade:** Home to Pro by entering a Pro product key or buying the upgrade in Settings. No reinstall, files and apps stay.
- **Clean install:** required when changing from 32-bit to 64-bit, when moving to a lower edition, or when the hardware or system is a mess.

**Hardware requirements.**

| Requirement | Windows 10 | Windows 11 |
|---|---|---|
| CPU | 1 GHz | 1 GHz, 2 or more cores, 64-bit, on Microsoft's supported list |
| RAM | 1 GB (32-bit), 2 GB (64-bit) | 4 GB |
| Storage | 32 GB (32-bit and 64-bit, for current versions) | 64 GB |
| Firmware | BIOS or UEFI | UEFI with Secure Boot capability |
| TPM | Not required | TPM 2.0 |

**TPM** (Trusted Platform Module) is a security chip, or firmware equivalent, that stores encryption keys and checks boot integrity. BitLocker uses it. **UEFI** is the modern replacement for BIOS, supports GPT disks and Secure Boot. If an upgrade check fails, look in UEFI setup first: TPM (often labelled PTT on Intel or fTPM on AMD) and Secure Boot are sometimes simply turned off.

### 1.4 Windows tools

**Task Manager** (Ctrl+Shift+Esc, or right-click the Start button).

| Tab | What you use it for |
|---|---|
| Processes | See which apps and background processes use CPU, memory, disk and network. End a frozen app |
| Performance | Live graphs of CPU, memory, disk, network and GPU. Shows uptime and how much RAM is installed and in use |
| Startup (Startup apps in Windows 11) | Enable or disable programs that launch at sign-in, with a "startup impact" rating. First stop for slow boots |
| Users | Who is signed in and what each user is using. Sign out a user |
| Services | Start, stop and restart Windows services, with a link to the full Services console |

There are also App history and Details tabs (Details shows process IDs).

**Microsoft Management Console (MMC) snap-ins.** Type the file name in the Run box (Win+R) or Start search.

| Console | Opens | Use it when |
|---|---|---|
| Event Viewer | eventvwr.msc | You need to know what happened and when: crashes, failed services, failed sign-ins. Main logs: Application, Security, Setup, System. Levels: Information, Warning, Error, Critical |
| Disk Management | diskmgmt.msc | Initialize a new disk (MBR or GPT), create, format, extend or shrink volumes, change drive letters |
| Task Scheduler | taskschd.msc | Run a program or script on a schedule or trigger (at sign-in, at startup, on an event) |
| Device Manager | devmgmt.msc | Update, roll back, disable or uninstall drivers. A yellow warning mark means a problem device; a down arrow means disabled |
| Certificate Manager | certmgr.msc | View, import, export or delete the current user's certificates |
| Local Users and Groups | lusrmgr.msc | Create local accounts, reset passwords, add users to groups such as Administrators. Not available on Home |
| Performance Monitor | perfmon.msc | Track performance counters over time with data collector sets and reports, for problems that come and go |
| Group Policy Editor | gpedit.msc | Set local policies on one machine, such as password rules or blocking USB storage. Not on Home |

**Additional tools.**

| Tool | Opens | Use it when |
|---|---|---|
| System Information | msinfo32.exe | You need a full hardware and software inventory: OS version, BIOS mode (UEFI or Legacy), Secure Boot state, installed RAM, drivers |
| Resource Monitor | resmon.exe | Task Manager shows heavy CPU, disk or network use and you need detail: which process is reading which file, which process talks to which address |
| System Configuration | msconfig.exe | Set up a clean boot (hide Microsoft services, then disable the rest), boot into Safe Mode with the Boot tab's "Safe boot" option. Its Startup tab now points to Task Manager |
| Disk Cleanup | cleanmgr.exe | Free space by removing temporary files, the Recycle Bin, old Windows Update files and previous Windows installations |
| Disk Defragment (Optimize Drives) | dfrgui.exe | Defragment hard disk drives and send TRIM to SSDs. Do not manually defragment an SSD |
| Registry Editor | regedit.exe | Change a setting that has no other interface. Main hives: HKEY_LOCAL_MACHINE (machine-wide) and HKEY_CURRENT_USER (the signed-in user). Export a backup of the key before editing |

### 1.5 Command-line tools

Open Command Prompt, or Windows Terminal, as administrator (right-click, Run as administrator) for chkdsk, format, diskpart, sfc and the `-b` switch of netstat. Add `/?` to any command to see its help, for example `robocopy /?`.

| Group | Command | Purpose | Key switches and examples |
|---|---|---|---|
| Navigation | cd | Change directory | `cd ..` up one level, `cd \` to the root, `cd /d D:\Data` to change drive and folder together |
| Navigation | dir | List folder contents | `/a` include hidden and system files, `/s` include subfolders, `/p` pause each screen, `/w` wide list |
| Network | ipconfig | Show IP configuration | `/all` full detail (MAC, DHCP server, DNS servers, lease), `/release` and `/renew` drop and request a DHCP address, `/flushdns` clear the DNS cache, `/displaydns` show it |
| Network | ping | Test reachability with ICMP echo | `-t` keep pinging until Ctrl+C, `-n 10` send 10 pings (default 4), `-l 1500` set packet size, `-a` resolve the address to a name, `-4` or `-6` force IPv4 or IPv6 |
| Network | netstat | Show connections and listening ports | `-a` all connections and listening ports, `-n` numbers instead of names, `-o` show the process ID, `-b` show the program name (needs admin), `-r` routing table |
| Network | nslookup | Query DNS | `nslookup www.example.com` uses your DNS server, `nslookup www.example.com 8.8.8.8` asks a specific server, `nslookup -type=mx example.com` looks up mail servers |
| Network | net use | Map or remove network drives | `net use Z: \\fs01\sales` maps a drive, `/persistent:yes` reconnects at sign-in, `/user:CORP\maria` connects as another account, `net use Z: /delete` removes it, `net use` alone lists mappings |
| Network | tracert | Show each router hop to a destination | `-d` skip name lookups (faster), `-h 15` limit to 15 hops (default 30), `-w` set the timeout per reply |
| Network | pathping | Trace the route, then measure packet loss at every hop | `-n` skip name lookups. Takes several minutes, but shows exactly which hop is dropping packets |
| Disk | chkdsk | Check a volume for file system errors | Alone: read-only check. `/f` fix errors, `/r` find bad sectors and recover readable data (includes /f), `/x` dismount the volume first. On the system drive it offers to run at the next restart |
| Disk | format | Create a new file system on a volume (erases it) | `format E: /fs:ntfs`, `/fs:exfat` or `/fs:fat32`, `/q` quick format, `/v:BACKUP` set the volume label |
| Disk | diskpart | Interactive disk and partition tool | `list disk`, `select disk 1`, `clean` (wipes the partition table), `convert gpt`, `create partition primary`, `format fs=ntfs quick`, `assign letter=E`, `list volume`. Always check which disk is selected before `clean` |
| File | md (mkdir) | Make a directory | `md C:\Reports\2026` creates missing parent folders too |
| File | rmdir (rd) | Remove a directory | Alone: only empty folders. `/s` remove the folder and everything in it, `/q` do not ask for confirmation |
| File | robocopy | Robust copy of folders, resumes and retries | `robocopy D:\Data E:\Backup /e` copy subfolders including empty ones, `/s` subfolders but skip empty ones, `/mir` mirror (copies and also deletes files at the destination that no longer exist at the source), `/z` restartable mode for flaky links, `/mt` multithreaded, `/copyall` keep permissions and ownership, `/log:C:\copy.txt` write a log |
| Info | hostname | Show the computer's name | No switches needed |
| Info | net user | Manage local user accounts | `net user` lists accounts, `net user maria` shows details (last sign-in, groups, password expiry), `net user maria *` prompts for a new password, `net user temp1 P@ssw0rd /add` creates one, `/delete` removes one, `/active:no` disables one, `/domain` runs against the domain |
| Info | winver | Show the Windows version and build in a small window | No switches. Quick way to read the exact build, such as 24H2 |
| Info | whoami | Show the signed-in account | `/groups` group memberships, `/priv` privileges, `/all` everything |
| Info | [command] /? | Show help for any command | `ipconfig /?`, `chkdsk /?` |
| OS | gpupdate | Apply Group Policy now instead of waiting for the next refresh | `/force` reapply every setting, not only changed ones, `/target:computer` or `/target:user`, `/boot` or `/logoff` restart or sign out if a setting needs it |
| OS | gpresult | Show which policies were applied (Resultant Set of Policy) | `/r` summary, `/scope user` or `/scope computer`, `/v` verbose, `/h report.html` save an HTML report |
| OS | sfc | System File Checker: find and replace corrupted Windows system files | `/scannow` scan and repair, `/verifyonly` scan without repairing, `/scanfile=` check one file. Needs an elevated prompt. |

### 1.6 Windows settings

Windows has two places for settings: the older **Control Panel** and the newer **Settings** app (Win+I). Microsoft keeps moving items into Settings, but Control Panel items still open and still appear on the exam.

**Control Panel items.**

| Item | What you do there |
|---|---|
| Internet Options (inetcpl.cpl) | Security zones, proxy (LAN settings), clear browsing data, certificates, reset settings. Applies system-wide, not only to one browser |
| Devices and Printers | Add printers and devices, set the default printer, open printer properties and queues |
| Programs and Features (appwiz.cpl) | Uninstall or repair desktop programs, view installed updates, "Turn Windows features on or off" (Hyper-V, Telnet client, .NET versions) |
| Network and Sharing Center | View the active network and its profile, change adapter settings (ncpa.cpl), change advanced sharing settings |
| System | Computer name, edition, activation. "Advanced system settings" (sysdm.cpl) holds performance options, virtual memory, System Protection (restore points), Remote settings and environment variables |
| Windows Defender Firewall (firewall.cpl) | Turn the firewall on or off per profile, allow an app through, open Advanced Settings (wf.msc) for inbound and outbound rules |
| Mail | Create and repair Outlook mail profiles. Appears only when the Outlook desktop app is installed |
| Sound (mmsys.cpl) | Playback and recording devices, set the default device, levels and enhancements |
| User Accounts | Change account type (Standard or Administrator), manage credentials, User Account Control (UAC) level |
| Device Manager | Same console as devmgmt.msc |
| Indexing Options | Choose which locations Windows Search indexes, rebuild the index when search results are missing or wrong |
| Administrative Tools (Windows Tools in Windows 11) | One folder of shortcuts to the consoles from 1.4 and more |

**File Explorer Options.**

| Tab | Settings to know |
|---|---|
| General | Open File Explorer to Home, Quick access or This PC; single-click or double-click; privacy (recent files) |
| View | **Show hidden files, folders, and drives** (needed to see AppData); **Hide extensions for known file types** (turn this off so users can spot `invoice.pdf.exe`); hide protected operating system files |
| Search | How File Explorer searches non-indexed locations |

**Power Options.**

| Setting | What it does |
|---|---|
| Power plans | Balanced (default), Power saver, High performance. Each plan holds timeouts and advanced settings |
| Sleep, suspend or standby | Keeps the session in RAM with low power. Wakes in seconds. Loses the session if power is lost completely |
| Hibernate | Writes RAM to the disk (hiberfil.sys) and powers off. Slower to wake, uses no power, survives a dead battery |
| Choose what closing the lid does | Do nothing, Sleep, Hibernate or Shut down, set separately for battery and plugged in. "Do nothing" is the fix for docked laptops used with the lid closed |
| Turn on fast startup | Shutdown saves the Windows kernel session to disk so the next boot is quicker. It means "shut down" is not a full restart; turn it off when troubleshooting, dual booting, or when changes need a true cold boot. Restart always does a full restart |
| USB selective suspend | In the plan's advanced settings. Lets Windows cut power to idle USB ports to save battery. Disable it when USB devices keep disconnecting |

**Settings app categories.**

| Category | Typical tasks |
|---|---|
| System | Display, sound, notifications, power, storage, About (device name, specs) |
| Devices (Bluetooth and devices in Windows 11) | Pair Bluetooth, printers and scanners, mouse, touchpad |
| Network and Internet | Wi-Fi, Ethernet, VPN, proxy, cellular, network profile, metered connection, data usage |
| Personalization | Background, colors, lock screen, themes, Start and taskbar |
| Apps | Uninstall apps, default apps, startup apps, optional features |
| Accounts | Your account, email accounts, sign-in options (PIN, Windows Hello), family, access work or school |
| Time and Language | Time zone, date and time sync, region, language, keyboard |
| Gaming | Game Bar, captures, Game Mode |
| Ease of Access (Accessibility in Windows 11) | Text size, magnifier, high contrast, narrator, captions |
| Privacy (Privacy and security in Windows 11) | App permissions for camera, microphone and location; diagnostic data |
| Update and Security (Windows Update in Windows 11) | Check for updates, pause updates, active hours, recovery and reset in Windows 10. In Windows 11, Windows Security and recovery live under System and Privacy and security |

### 1.7 Windows networking

**Domain joined vs workgroup.** A domain-joined PC signs users in with Active Directory accounts and gets policies, drive mappings and printers from the domain. To join: Settings, System, About, "Domain or workgroup" (or sysdm.cpl, Computer Name tab), then enter the domain name and an account allowed to join computers. A workgroup PC keeps its own accounts and shares directly with other PCs.

**Shared resources.** **Printers** can be shared from a PC or published by a print server. **File servers** hold shared folders that users reach by path. **Mapped drives** give a share a drive letter (`net use`, or File Explorer's "Map network drive", or Group Policy in a domain).

**Network paths in File Explorer.** Shares use UNC (Universal Naming Convention) paths: `\\server\share\folder`, for example `\\fs01\sales\reports`. An IP address also works: `\\10.0.5.20\sales`. Type it in the address bar or the Run box.

**Local OS firewall settings.** Windows Defender Firewall filters traffic per network profile (Domain, Private, Public).

- **Application restrictions and exceptions:** "Allow an app through firewall" lets a specific program receive connections. Prefer an app or port exception over turning the firewall off.
- **Configuration:** Advanced Settings (wf.msc) has inbound and outbound rules by program, port, protocol and address. By default inbound is blocked unless a rule allows it, and outbound is allowed.

**Client network configuration.**

| Setting | What it means | What goes wrong |
|---|---|---|
| IP address | The host's address, for example 192.168.1.50 | Duplicate address conflicts; a 169.254.x.x address (APIPA) means DHCP failed |
| Subnet mask | Which part of the address is the network, for example 255.255.255.0 | Wrong mask: some local hosts seem remote, or the reverse |
| Gateway | The router used to reach other networks | Missing or wrong gateway: local resources work, internet does not |
| DNS settings | Servers that turn names into IP addresses | Wrong DNS: `ping 8.8.8.8` works but websites by name fail |
| Static vs dynamic | Static is typed in by hand; dynamic comes from DHCP | Static suits servers and printers. A laptop with a static address from one office fails at another |

To set these: Settings, Network and Internet, the adapter, IP assignment, Edit, or the adapter's IPv4 properties in ncpa.cpl.

**Establishing network connections.**

| Connection | How |
|---|---|
| VPN | Settings, Network and Internet, VPN, Add VPN: server address, VPN type (IKEv2, L2TP/IPsec, SSTP and others) and sign-in method. Many companies use their own VPN client app instead |
| Wireless | Choose the SSID, enter the key or sign in for enterprise Wi-Fi. For hidden networks, add the network manually with the exact SSID and security type |
| Wired | Plug in; DHCP usually does the rest. Check the link light and adapter status if not |
| WWAN or cellular | A built-in modem or USB dongle with a SIM or eSIM from a carrier. Shows under Cellular in Settings |

**Proxy settings.** Settings, Network and Internet, Proxy: automatic detection, a setup script address (a PAC file), or a manual proxy server and port, with a list of addresses to bypass. Wrong proxy settings are a classic reason one PC cannot browse while everything else works, and are also a sign of malware.

**Public vs private network.** **Public** profile: the PC is hidden, network discovery and file sharing are off. Use for cafés, hotels and airports. **Private** profile: the PC can be seen and can share files and printers. Use for trusted home or office networks. If a home PC cannot see other PCs or a shared printer, check that the profile is Private.

**Metered connections and limitations.** Marking a connection as metered (for example, a phone hotspot) tells Windows to save data: most Windows Updates wait, some apps pause background downloads, and OneDrive may pause syncing. It explains "my updates are not downloading" on a hotspot.

### 1.8 macOS

**Installing and uninstalling applications.**

| Type | What it is | How it installs |
|---|---|---|
| .dmg | Disk image. Opens like a virtual drive | Usually drag the app into the Applications folder, then eject the image |
| .pkg | Installer package | Runs the Installer, which can place files in several locations and ask for an admin password |
| .app | The application itself (a bundle: a folder that looks like one file) | Lives in /Applications. Double-click to run |
| App Store | Apple's store | Install with an Apple ID; updates come through the store |

**Uninstallation process:** quit the app and drag the .app to the Trash (or, for App Store apps, press and hold in Launchpad and click the X). Apps installed from a .pkg may include their own uninstaller. Leftover settings sit in the user's Library folder.

**System folders.**

| Folder | Holds |
|---|---|
| /Applications | Apps available to all users |
| /Users | Each user's home folder (Desktop, Documents, Downloads) |
| /Library | Shared resources for all users: fonts, preferences, app support files |
| /System | macOS itself. Protected; users and admins do not change it |
| /Users/username/Library (shown as ~/Library) | One user's preferences, caches and app data. Hidden by default |

**Apple ID and corporate restrictions.** The Apple ID (Apple now calls it an Apple Account) signs in to the App Store, iCloud, iMessage and FaceTime. Companies use device management (MDM) and Managed Apple IDs to control which apps are allowed and to keep company data out of personal iCloud storage.

**System Preferences** (called **System Settings** since macOS Ventura).

| Pane | Use |
|---|---|
| Displays | Resolution, arrangement of multiple monitors, Night Shift |
| Network | Wi-Fi, Ethernet, VPN, IP and DNS settings |
| Printers and Scanners | Add printers and scanners, set the default printer |
| Privacy (Privacy and Security) | App access to camera, microphone, files, location; FileVault; which app sources Gatekeeper allows |
| Accessibility | VoiceOver, zoom, display and pointer options |
| Time Machine | Choose a backup disk and turn on automatic backups |

**Tools.**

| Tool | Use |
|---|---|
| Disk Utility | First Aid (check and repair a disk), erase and format, partition, APFS volumes, create disk images |
| FileVault | Full-disk encryption of the startup disk. Keep the recovery key safe |
| Terminal | The command line (zsh is the default shell). Many Linux commands from 1.9 work here |
| Force Quit | Cmd+Option+Esc, or the Apple menu. Closes an app that is not responding |

**Features.**

| Feature | What it does |
|---|---|
| Multiple desktops (Spaces) and Mission Control | Mission Control shows all open windows and desktops at once; add Spaces to separate work |
| Keychain | Stores passwords, certificates and keys. Keychain Access app; iCloud Keychain syncs passwords across devices |
| Spotlight | Cmd+Space to search files, apps and settings |
| iCloud | Apple's cloud: iMessage, FaceTime, iCloud Drive file storage, Photos, backups of iPhone and iPad |
| Gestures | Trackpad multi-finger swipes and pinches, set in Trackpad settings |
| Finder | The file manager, like File Explorer |
| Dock | The bar of pinned and running apps |
| Continuity | Features across Apple devices signed in to the same Apple ID: Handoff, Universal Clipboard, AirDrop, phone calls and texts on the Mac, iPhone as webcam |

**Best practices.**

- **Backups:** Time Machine to an external or network disk, taking hourly snapshots and keeping older versions.
- **Antivirus:** macOS includes XProtect and Gatekeeper, and companies often add a third-party endpoint product. Macs are not immune to malware.
- **Updates and patches:** Software Update in System Settings.
- **Rapid Security Response (RSR):** small security fixes Apple ships between regular updates so urgent holes close quickly, often needing only a restart.

### 1.9 Linux

Linux is case-sensitive: `Report.txt` and `report.txt` are different files.

**File management.**

| Command | Purpose | Examples |
|---|---|---|
| ls | List directory contents | `ls -l` long format with permissions, `ls -a` include hidden (dot) files, `ls -lh` human-readable sizes |
| pwd | Print working directory (where you are) | `pwd` |
| mv | Move or rename | `mv old.txt new.txt`, `mv file.txt /home/maria/` |
| cp | Copy | `cp a.txt b.txt`, `cp -r photos/ /backup/` to copy a folder |
| rm | Remove (there is no recycle bin) | `rm file.txt`, `rm -r folder/` to remove a folder, `-f` to skip prompts. `rm -rf` on the wrong path destroys data |
| chmod | Change permissions | `chmod 755 script.sh`, `chmod u+x script.sh` (add execute for the owner) |
| chown | Change owner and group | `chown maria:finance report.txt`, `-R` for a whole folder |
| grep | Search inside text | `grep "error" /var/log/syslog`, `-i` ignore case, `-r` search folders, `-v` show lines that do not match |
| find | Search for files by name, size, date | `find /home -name "*.pdf"`, `find / -size +1G`, `find . -mtime -7` (changed in the last 7 days) |

**Reading permissions.** `ls -l` shows something like `-rwxr-x---`. The first character is the type (`-` file, `d` directory). Then three sets of three: owner, group, others. r = 4, w = 2, x = 1. So `rwx` = 7, `r-x` = 5, `---` = 0, and `-rwxr-x---` is `750`. `chmod 644` gives `rw-r--r--`, the usual setting for a normal file.

**Filesystem management.** `fsck` checks and repairs a Linux file system; run it on an unmounted file system. `mount /dev/sdb1 /mnt/usb` attaches a partition to a folder; `umount /mnt/usb` detaches it.

**Administrative.** `su` switches to another user (root by default) and needs that user's password; `su -` also loads their environment. `sudo` runs one command as root using your own password, if you are allowed in the sudoers configuration, and logs it. Prefer `sudo` over signing in as root.

**Package management.**

| Tool | Distributions | Common commands |
|---|---|---|
| apt | Debian, Ubuntu and relatives | `sudo apt update` (refresh the package lists), `sudo apt upgrade` (install newer versions), `sudo apt install nano`, `sudo apt remove nano` |
| dnf | Fedora, Red Hat Enterprise Linux and relatives | `sudo dnf install nano`, `sudo dnf upgrade`, `sudo dnf remove nano` |

A common trap: `apt update` does not upgrade anything. It only refreshes the list of available versions.

**Network.**

| Command | Purpose | Examples |
|---|---|---|
| ip | Show and set addresses, links and routes (replaces ifconfig) | `ip addr` (or `ip a`), `ip link`, `ip route` |
| ping | Test reachability | Linux keeps pinging until Ctrl+C; `ping -c 4 8.8.8.8` sends four |
| curl | Transfer data to or from a URL | `curl https://example.com`, `curl -I` headers only, `curl -O` save the file |
| dig | Query DNS in detail | `dig example.com`, `dig example.com MX`, `dig @8.8.8.8 example.com`, `+short` for brief output |
| traceroute | Show each hop to a destination | `traceroute example.com` (Windows spells it tracert) |

**Informational.**

| Command | Purpose | Examples |
|---|---|---|
| man | Manual page for a command | `man chmod`, press q to quit |
| cat | Print a file's contents | `cat /etc/hosts` |
| top | Live view of processes by CPU and memory | Press q to quit |
| ps | Snapshot of running processes | `ps aux` or `ps -ef` for all processes |
| du | Disk usage of files and folders | `du -sh /var/log` total for one folder in readable units |
| df | Free and used space per mounted file system | `df -h` |

`df` answers "is the disk full?"; `du` answers "what is filling it?".

**Text editors.** `nano` is the simple editor: Ctrl+O saves, Ctrl+X exits, and the shortcuts are listed at the bottom of the screen.

**Common configuration files.**

| File | Contains |
|---|---|
| /etc/passwd | One line per account: username, user ID, group ID, home folder, default shell. Readable by everyone; the password field holds only an x |
| /etc/shadow | The hashed passwords and password aging rules. Readable only by root |
| /etc/hosts | Static hostname to IP mappings, normally checked before DNS |
| /etc/fstab | File systems to mount at boot and where |
| /etc/resolv.conf | DNS servers the system uses (`nameserver` lines) |

**OS components.** The **kernel** is the core that manages hardware, memory and processes. The **bootloader** (usually GRUB) loads the kernel at startup and offers a menu on multiboot systems. **systemd** is the first process started (process ID 1) and starts and manages services; control them with `systemctl status`, `start`, `stop`, `restart` and `enable` (start at boot).

**Root account.** The superuser, user ID 0, can do anything, including destroying the system. Day-to-day work uses a normal account plus `sudo`.

### 1.10 Installing applications

**System requirements for applications.**

| Requirement | What to check |
|---|---|
| 32-bit vs 64-bit | A 64-bit OS runs both 64-bit and 32-bit apps (32-bit apps install in C:\Program Files (x86)). A 32-bit OS cannot run 64-bit apps at all, and is limited to 4 GB of RAM |
| Dedicated vs integrated graphics | Integrated graphics share system RAM and suit office work. CAD, video editing and games often need a dedicated card |
| VRAM | Video memory on a dedicated card. Apps list a minimum, for example 4 GB |
| RAM | Minimum and recommended amounts. Below recommended, the app runs slowly and pages to disk |
| CPU | Speed, core count, sometimes a specific instruction set or generation |
| External hardware tokens | Some licensed software needs a USB license dongle; some sign-ins need a hardware security key |
| Storage | Free space for the install and its data, sometimes an SSD |
| Application to OS compatibility | Supported OS versions. Old apps may need compatibility mode or a virtual machine |

Check requirements before installing: msinfo32 or Settings, System, About shows the OS type, RAM and CPU.

**Distribution methods.**

| Method | Notes |
|---|---|
| Physical media | DVD or USB, rare now. Needs a drive the PC may not have |
| Mountable ISO file | A disk image file. In Windows, right-click and Mount to get a virtual drive letter, no burning needed |
| Downloadable package | .exe or .msi installers on Windows, .dmg or .pkg on macOS, .deb or .rpm on Linux. Download only from the vendor |
| Image deployment | The app is baked into the company's standard image, so every new PC has it |

**Impact considerations for new applications.**

- **Device:** performance, disk space, conflicts with existing software or drivers, security exposure.
- **Network:** bandwidth for downloads and use, firewall rules or ports the app needs, load on servers.
- **Operation:** user training, support load, changes to how daily work is done.
- **Business:** licensing, compliance, downtime during rollout, whether the app is approved.

In a company, a new app normally goes through change management (Core 2 Domain 4) rather than being installed on request.

### 1.11 Cloud productivity tools

Microsoft 365 and Google Workspace are the two big suites. The help desk sets them up, connects users, and fixes sync and license problems.

**Email systems.** Cloud-hosted mailboxes (Exchange Online in Microsoft 365, Gmail in Google Workspace). Desktop and mobile mail apps find the server automatically when the user enters their address (Autodiscover for Outlook). Webmail always works, which makes it a good first test: if webmail works and Outlook does not, the problem is on the PC.

**Storage and sync settings.** OneDrive, Google Drive, Dropbox and iCloud Drive keep files in the cloud and sync them to devices.

- **Files on demand:** files show in File Explorer but download only when opened, saving disk space. A file marked "online-only" will not open without internet.
- **Choose folders:** sync only selected folders to a device.
- **Folder backup:** redirect Desktop, Documents and Pictures into OneDrive so they are backed up (Known Folder Move).
- Sync conflicts appear as duplicate files with the device name added. Paused sync is often caused by a metered connection, a full cloud quota or the user being signed out.

**Collaboration tools.**

| Type | Microsoft 365 | Google Workspace |
|---|---|---|
| Spreadsheets | Excel | Sheets |
| Videoconferencing | Teams | Meet |
| Presentation tools | PowerPoint | Slides |
| Word processing | Word | Docs |
| Instant messaging | Teams chat | Chat |

Several people can edit the same file at once, and version history lets you restore an earlier copy.

**Identity synchronization.** Companies with on-premises Active Directory sync accounts to the cloud directory (Microsoft Entra Connect syncs to Microsoft Entra ID, formerly Azure AD), so users keep one username and password for both. Changes made on-premises, such as disabling a leaver, flow to the cloud on the next sync. Make account changes in the source directory, or the next sync can overwrite them.

**Licensing assignment.** Creating a user is not enough: each user needs a license assigned in the admin center to get a mailbox, desktop apps and storage. Licenses are often assigned by group membership. When someone leaves, remove the license so the seat can be reused. "The account exists but Outlook has no mailbox and Office says unlicensed" points straight at license assignment.

## How questions look

Most items are short scenarios with a user's complaint and four tools, commands or settings as options: "A user reports... Which tool should the technician use?" Expect a lot of "MOST likely" and "BEST" wording where two options would technically work but one fits better. Exhibits include ipconfig, netstat or tracert output, an `ls -l` permission string, Task Manager or Event Viewer summaries, and command lines where you pick the correct switch. "Choose two" items are common for command pairs (apply and verify Group Policy) and edition features. Performance-based items may ask you to type or select commands to fix a problem, configure IP settings, match tools to tasks, or pick the right file system and partition style for a set of drives. Upgrade items use "FIRST" wording.

## A method for these questions

1. Name the OS and edition in the stem before anything else. Linux commands in a Windows question, or a Pro feature on a Home PC, are the most common distractors.
2. Decide what the user actually needs: information (view, check, show) or a change (fix, apply, configure). Many tool pairs split that way: gpresult vs gpupdate, Event Viewer vs Task Scheduler.
3. For tool items, ask "now or over time?" and "summary or detail?" to choose between Task Manager, Resource Monitor, Performance Monitor and Event Viewer.
4. For command items, check the exact switch. Read every option to the end: `/mir` vs `/e`, `-t` vs `-n`, `/f` vs `/r`.
5. For file system and partition items, run the numbers: files over 4 GB rule out FAT32, disks over 2 TB rule out MBR, Windows 11 needs UEFI and GPT.
6. For networking items, read the IP address first. 169.254.x.x points to DHCP; a good IP with failing names points to DNS; local works and internet fails points to the gateway.
7. For "FIRST" items in installs and upgrades, back up before you change anything, and check compatibility before you buy or install.

## Traps that cost points

- **Home edition features.** Home cannot join a domain, cannot host Remote Desktop, has no BitLocker and no gpedit.msc. The fix is an edition upgrade to Pro, not a reinstall.
- **FAT32 for big files.** FAT32 caps each file at 4 GB. For a drive shared between Windows and macOS with large files, the answer is exFAT, not NTFS (macOS cannot write it natively).
- **MBR on a big disk.** MBR addresses only 2 TB. Extra partitions do not help; the disk must be GPT.
- **robocopy /mir as a backup.** Mirroring deletes destination files that are gone from the source, so an accidental deletion spreads to the "backup". Use `/e` when you want to keep old copies.
- **net use vs net user.** One maps drives, the other manages accounts. Read the letters.
- **apt update vs apt upgrade.** `update` refreshes the package list; `upgrade` installs newer versions.
- **su vs sudo.** `su` asks for the target account's password and gives a whole shell; `sudo` asks for your own password and runs one command, logged.
- **Turning off the firewall.** When an app is blocked, the correct answer is an exception or rule for that app or port, not disabling the firewall.
- **Fast startup and "I restarted".** Shut down with fast startup on is not a clean boot. Use Restart, or disable fast startup, when a fix needs a full restart.

## Timing

Core 2 is one 90-minute block with up to 90 questions, so the average is about a minute per item, with PBQs taking longer. Most items in this domain are recall wrapped in a short scenario: once you spot the tool or switch, answer and move on, and aim for well under a minute. Spend the saved time on command-output exhibits and command PBQs, and flag any switch question you are unsure of rather than staring at it. If a PBQ looks long, do the multiple-choice items first and come back.

## Practice items

These 2 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

An administrator changed a Group Policy object that maps a printer for the Sales team. A sales user's PC still does not have the printer. The technician wants to apply policy on that PC immediately and then confirm which policy objects were applied. Which TWO commands should the technician run? (Choose two.)

A. gpedit.msc

B. gpupdate /force

C. sfc /scannow

D. netstat -b

E. gpresult /r

<details>
<summary>Answer and explanation</summary>

**Answer: B and E.** `gpupdate /force` reapplies all policy settings now. `gpresult /r` shows the summary of which Group Policy objects applied to the user and computer. (Objective 1.5)

- **A** is wrong because gpedit.msc edits local policy on this one PC; it does not pull the domain policy or report what applied.
- **C** is wrong because sfc repairs system files and has nothing to do with Group Policy.
- **D** is wrong because netstat -b shows network connections by program.

</details>

### Item 2

A technician runs `ls -l` on a Linux server and sees this line:

```
-rwxr-x--- 1 maria finance 2048 Nov 20 09:14 payroll.sh
```

Which numeric permission does this file have?

A. 755

B. 740

C. 750

D. 570

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Owner `rwx` = 4+2+1 = 7, group `r-x` = 4+1 = 5, others `---` = 0, so 750. Maria can read, change and run the script, the finance group can read and run it, and nobody else has access. (Objective 1.9)

- **A** is wrong because 755 would give others `r-x`, but others have no permissions here.
- **B** is wrong because 740 would give the group only `r--`, without execute.
- **D** is wrong because 570 swaps the owner and group values.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 | 2 |
|---|---|---|
| Answer | B, E | C |
| Objective | 1.5 | 1.9 |

- **2 of 2:** strong. Keep the command tables fresh with short daily drills, since exact switches fade quickly.
- **1 of 2:** list the objectives you missed. Switches, edition features and file system limits are the usual weak spots; reread [1.5 Command-line tools](#15-command-line-tools), [1.3 Windows editions](#13-windows-editions) and [1.1 OS types and file systems](#11-os-types-and-file-systems).
- **0 of 2:** spend two or three study sessions here. Write the edition table and the command tables from memory, then reread [1.4 Windows tools](#14-windows-tools), [1.7 Windows networking](#17-windows-networking) and [1.9 Linux](#19-linux) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. On a Windows PC, press Win+R and open each console from 1.4 by its file name (eventvwr.msc, diskmgmt.msc, devmgmt.msc and the rest), saying out loud what each one is for. Then run `ipconfig /all`, `netstat -ano` and `whoami /groups` and explain every line. If you can, do the same on a free Linux virtual machine with `ip a`, `ls -l /etc`, `df -h` and `sudo apt update`.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Core 2 (220-1202) overview](README.md) | Next: [Core 2, Domain 2: Security](2-security.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
