<!-- nav:top -->
[Contents](../../README.md#contents) · Previous: [Core 1, Domain 1: Mobile Devices](1-mobile-devices.md) · Next: [Core 1, Domain 3: Hardware](3-hardware.md)
<!-- /nav:top -->

# Core 1, Domain 2: Networking

**Weight:** 23% of the Core 1 exam (220-1201), CompTIA's figure. By our estimate that is roughly 20 of up to 90 questions. **Objectives:** 2.1 to 2.8.

This domain is everything a help desk technician needs to get people online: port numbers, Wi-Fi bands and standards, the servers and appliances on a network, DNS and DHCP, the boxes in the network closet, IP addressing on a small office router, internet connection types and the tools in a cabling kit. It is a memorization-heavy domain, and that is exactly where marks go: one wrong port number or a mixed-up DNS record turns an easy question into a miss. Learn the tables until you can write them from memory.

## What this domain measures

Objectives 2.1 to 2.5 are mostly "know the facts": ports, wireless, services, DNS and DHCP, hardware. Objective 2.6 is hands-on and scenario-based: given a symptom on a small network, find the addressing mistake. Objectives 2.7 and 2.8 are about choosing the right connection type and the right tool.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 2.1 | Compare TCP and UDP ports, protocols and their purposes | FTP, SSH, Telnet, SMTP, DNS, DHCP, HTTP, POP3, NetBIOS, IMAP, LDAP, HTTPS, SMB, RDP, TCP vs UDP |
| 2.2 | Explain wireless networking technologies | 2.4, 5 and 6 GHz, channels, widths, regulations, 802.11 standards, Bluetooth, NFC, RFID |
| 2.3 | Summarize services provided by networked hosts | DNS, DHCP, file, print, mail, syslog, web, AAA, database and NTP servers; spam gateways, UTM, load balancers, proxies; SCADA; IoT |
| 2.4 | Explain common network configuration concepts | DNS records (A, AAAA, CNAME, MX, TXT), SPF, DKIM, DMARC, DHCP leases, reservations, scope, exclusions, VLAN, VPN |
| 2.5 | Compare networking hardware devices | Routers, managed and unmanaged switches, access points, patch panels, firewalls, PoE, cable modem, DSL, ONT, NIC and MAC address |
| 2.6 | Configure basic wired and wireless SOHO networks | IPv4 private and public, IPv6, APIPA, static and dynamic addressing, subnet mask, gateway |
| 2.7 | Compare internet connection types and network types | Satellite, fiber, cable, DSL, cellular, WISP; LAN, WAN, PAN, MAN, SAN, WLAN |
| 2.8 | Explain networking tools and their purposes | Crimper, cable stripper, Wi-Fi analyzer, toner probe, punchdown tool, cable tester, loopback plug, network tap |

## Key concepts explained

### 2.1 Ports and protocols

**TCP vs UDP.** Both carry data between applications, identified by port numbers.

| | TCP | UDP |
|---|---|---|
| Connection | Connection-oriented: a three-way handshake (SYN, SYN-ACK, ACK) before data flows | Connectionless: just sends |
| Reliability | Acknowledges data, resends lost segments, keeps order | No acknowledgment, no resend |
| Speed and overhead | More overhead | Less overhead, faster |
| Good for | Web pages, email, file transfer, remote logins | Quick lookups (DNS, DHCP), streaming, voice, games |

A simple way to remember: if losing a piece would break the result (a file, an email), use TCP. If speed matters more than a missing piece, or the exchange is one small question and answer, use UDP.

**The port table.** These are the ports listed in the objectives. Know the number, the transport and what it is for.

| Port | Protocol | Transport | Purpose |
|---|---|---|---|
| 20, 21 | FTP (File Transfer Protocol) | TCP | File transfer. 21 is control (commands), 20 is data in active mode. Unencrypted |
| 22 | SSH (Secure Shell) | TCP | Encrypted remote command line. SFTP and SCP also run over SSH on 22 |
| 23 | Telnet | TCP | Unencrypted remote command line. Replaced by SSH |
| 25 | SMTP (Simple Mail Transfer Protocol) | TCP | Sending mail and server-to-server mail relay |
| 53 | DNS (Domain Name System) | UDP and TCP | Name resolution. Normal queries use UDP; zone transfers and large responses use TCP |
| 67, 68 | DHCP (Dynamic Host Configuration Protocol) | UDP | Automatic IP addressing. Server listens on 67, client on 68 |
| 80 | HTTP (Hypertext Transfer Protocol) | TCP | Unencrypted web traffic |
| 110 | POP3 (Post Office Protocol 3) | TCP | Downloading mail to one device |
| 137 to 139 | NetBIOS and NetBIOS over TCP/IP (NetBT) | UDP 137 and 138, TCP 139 | Legacy Windows name service (137), datagram service (138) and session service (139) |
| 143 | IMAP (Internet Message Access Protocol) | TCP | Reading mail that stays on the server, synced across devices |
| 389 | LDAP (Lightweight Directory Access Protocol) | TCP (UDP also possible) | Querying and authenticating against a directory such as Active Directory |
| 443 | HTTPS (HTTP Secure) | TCP | Encrypted web traffic using TLS |
| 445 | SMB (Server Message Block) and CIFS | TCP | Windows file and printer sharing |
| 3389 | RDP (Remote Desktop Protocol) | TCP (UDP also used) | Remote graphical desktop of a Windows computer |

Memory hooks that help: 20 to 23 are the "remote access and files" block (FTP, SSH, Telnet) in alphabetical order. 25 is "sending mail", 110 and 143 are "receiving mail". 67 and 68 are DHCP's pair, server first. 443 is "80 with a lock". 445 is file sharing, two digits away from 443. 3389 is the only four-digit port on the list.

**Secure versions you will meet in support work** (not separate objectives here, but useful when setting up mail on a phone): IMAP over TLS uses 993, POP3 over TLS uses 995, and mail clients usually submit outgoing mail on 587.

### 2.2 Wireless networking technologies

**Frequency bands.**

| Band | Range and penetration | Channels | Notes |
|---|---|---|---|
| 2.4 GHz | Longest range, best through walls | Only three non-overlapping 20 MHz channels: 1, 6 and 11 (in North America) | Crowded: neighbors, Bluetooth and microwave ovens all use it |
| 5 GHz | Shorter range than 2.4 GHz | Many more channels, so less overlap | Faster, less interference. Some channels need DFS (dynamic frequency selection) to avoid radar |
| 6 GHz | Shortest range of the three | Lots of clean spectrum, wide channels | Needs Wi-Fi 6E or Wi-Fi 7 devices |

**Channels, widths and regulations.** A channel is a slice of a band. **Channel width** is how wide that slice is: 20, 40, 80, 160 MHz, and 320 MHz with Wi-Fi 7 in the 6 GHz band. Wider channels carry more data but there are fewer of them, so they overlap with neighbors more easily. In a crowded 2.4 GHz area, use 20 MHz width on channel 1, 6 or 11. **Regulations** differ by country: each country decides which channels and transmit power are allowed, which is why access points ask for a country or region setting. **Channel selection** is the task of picking the least crowded channel, usually with a Wi-Fi analyzer.

**802.11 standards.**

| Standard | Wi-Fi name | Bands | Theoretical maximum |
|---|---|---|---|
| 802.11a | (none) | 5 GHz | 54 Mbps |
| 802.11b | (none) | 2.4 GHz | 11 Mbps |
| 802.11g | (none) | 2.4 GHz | 54 Mbps |
| 802.11n | Wi-Fi 4 | 2.4 and 5 GHz | 600 Mbps |
| 802.11ac | Wi-Fi 5 | 5 GHz | About 6.9 Gbps |
| 802.11ax | Wi-Fi 6 | 2.4 and 5 GHz | About 9.6 Gbps |
| 802.11ax | Wi-Fi 6E | Adds 6 GHz | About 9.6 Gbps |
| 802.11be | Wi-Fi 7 | 2.4, 5 and 6 GHz | About 46 Gbps |

Real speeds are far lower than these figures, which assume ideal conditions. For the exam, the band column matters most: 802.11b and g are 2.4 GHz only, 802.11a and ac are 5 GHz only, and 6 GHz arrives with Wi-Fi 6E.

**Other wireless technologies.**

| Technology | Frequency and range | Use |
|---|---|---|
| Bluetooth | 2.4 GHz, about 10 meters for most devices | Headsets, keyboards, mice, speakers; forms a personal area network (PAN) |
| NFC | 13.56 MHz, a few centimeters | Tap-to-pay, badge access, tap-to-pair |
| RFID (radio-frequency identification) | Varies, from centimeters to many meters | Tags on stock, pallets, badges and toll passes. Passive tags have no battery and are powered by the reader; active tags have their own battery and longer range |

### 2.3 Services provided by networked hosts

**Server roles.**

| Server | What it does |
|---|---|
| DNS server | Turns names (www.example.com) into IP addresses |
| DHCP server | Hands out IP addresses, subnet masks, gateways and DNS servers automatically |
| File share | Central storage for shared folders, usually over SMB |
| Print server | Holds print queues and drivers, shares printers with many users |
| Mail server | Sends, receives and stores email (SMTP, IMAP, POP3) |
| Syslog server | Collects log messages from routers, switches, firewalls and servers in one place |
| Web server | Hosts websites and web apps over HTTP and HTTPS |
| AAA server | Authentication (who you are), authorization (what you can do) and accounting (what you did). RADIUS and TACACS+ are AAA protocols |
| Database server | Stores structured data for applications |
| NTP server | Keeps clocks in sync. Accurate time matters for logins (Kerberos), logs and certificates |

**Internet appliances.**

| Appliance | What it does |
|---|---|
| Spam gateway | Filters incoming email for spam, phishing and malware before it reaches the mail server |
| UTM (unified threat management) | One box combining firewall, intrusion prevention, antivirus, content filtering and often VPN |
| Load balancer | Spreads incoming requests across several servers so no single one is overloaded, and routes around a failed server |
| Proxy server | Makes web requests on behalf of clients; can cache pages, filter content and log browsing |

**Legacy and embedded systems.** **SCADA** (supervisory control and data acquisition) systems run industrial equipment such as power, water and manufacturing plants. They often run old software that cannot be patched easily, so they are kept on isolated, segmented networks.

**IoT devices.** Smart thermostats, cameras, speakers, lights and sensors. They often ship with weak default passwords and get few updates. Change default credentials, update firmware, and put them on a separate network or VLAN (a guest or IoT network on a SOHO router).

### 2.4 DNS, DHCP, VLAN and VPN

**DNS record types.**

| Record | What it holds | Example use |
|---|---|---|
| A | A name to an IPv4 address | www.example.com to 203.0.113.20 |
| AAAA | A name to an IPv6 address | www.example.com to 2001:db8::20 |
| CNAME (canonical name) | An alias pointing to another name | shop.example.com is an alias of example.com |
| MX (mail exchanger) | Which server receives email for the domain, with a priority number (lower is preferred) | Mail for example.com goes to mail.example.com |
| TXT (text) | Free text, used for verification and email security | SPF, DKIM and DMARC records |

**Spam management with TXT records.**

| Record | What it does |
|---|---|
| SPF (Sender Policy Framework) | Lists which servers are allowed to send mail for the domain |
| DKIM (DomainKeys Identified Mail) | Publishes a public key so receivers can check the digital signature on the domain's outgoing mail |
| DMARC (Domain-based Message Authentication, Reporting, and Conformance) | Tells receivers what to do when SPF or DKIM checks fail (none, quarantine or reject) and where to send reports |

A short memory hook: SPF says **who** may send, DKIM proves the message was **signed and not changed**, DMARC says **what to do** when the checks fail.

**DHCP.** A client gets its address through four messages, remembered as **DORA**: Discover (client broadcasts), Offer (server offers an address), Request (client asks for it), Acknowledge (server confirms).

| DHCP term | Meaning |
|---|---|
| Scope | The range of addresses the server can hand out on a subnet, plus options such as gateway and DNS servers |
| Lease | How long a client may keep its address. Clients try to renew partway through the lease |
| Reservation | A specific address always given to one device, matched by its MAC address. Good for printers |
| Exclusion | Addresses inside the scope that the server must never hand out, for example ones used by static devices |

A reservation and a static address both give a device a fixed IP. The difference: a reservation is still handed out by DHCP and managed centrally; a static address is typed into the device itself.

**VLAN (virtual LAN).** A managed switch can split its ports into separate logical networks. Devices in different VLANs cannot talk directly; traffic between them must go through a router or firewall. Uses: separating guest Wi-Fi, IoT devices, VoIP phones or departments without buying separate switches.

**VPN (virtual private network).** An encrypted tunnel across an untrusted network, usually the internet. A remote-access VPN connects one user's device to the office network. A site-to-site VPN joins two office networks.

### 2.5 Networking hardware

| Device | What it does | How to tell it apart |
|---|---|---|
| Router | Connects different networks and forwards traffic between them using IP addresses | Your default gateway is a router |
| Unmanaged switch | Connects devices on the same network; forwards frames by MAC address | Plug and play, no configuration |
| Managed switch | A switch you can configure | Supports VLANs, port settings, monitoring, port mirroring |
| Access point | Connects wireless devices to the wired network | Bridges Wi-Fi to Ethernet |
| Patch panel | A panel of ports where building cabling ends in the network closet | Passive: no power, no forwarding. Cables are punched down on the back, patch cables plug in the front |
| Firewall | Allows or blocks traffic based on rules | Hardware appliance or software on a host |
| Cable modem | Connects to the cable provider's coaxial network | Uses coax with an F-type connector; DOCSIS standard |
| DSL modem | Connects to the phone company over telephone lines | Uses an RJ11 phone line |
| ONT (optical network terminal) | Converts the provider's fiber signal to Ethernet | The box at the end of a fiber-to-the-home line |
| NIC (network interface card) | Connects a computer to the network | Each has a **MAC address**: 48 bits written as 12 hexadecimal digits, such as 3C:52:82:1A:9F:04. The first half identifies the manufacturer |

A SOHO "router" is usually a router, switch, access point and firewall in one box.

**Power over Ethernet (PoE).** Carries power and data over one Ethernet cable to devices such as access points, IP cameras and VoIP phones.

| Standard | Common name | Power at the source port |
|---|---|---|
| 802.3af | PoE | Up to 15.4 W |
| 802.3at | PoE+ | Up to 30 W |
| 802.3bt | PoE++ (Type 3 and Type 4) | Up to 60 W (Type 3) and up to 90 W (Type 4) |

A **PoE switch** powers devices directly from its ports. A **PoE injector** sits between a normal switch and the device, adding power to one cable. Use an injector when you need power for one or two devices and the switch does not support PoE. The device and the source must support the same or a compatible standard, and the switch has a total power budget across all ports.

### 2.6 SOHO network configuration and IP addressing

**IPv4 basics.** An IPv4 address is 32 bits, written as four numbers from 0 to 255, such as 192.168.1.50. The **subnet mask** says which part is the network and which part is the host. The **default gateway** is the router address a device uses to reach any other network, including the internet.

**Private and public addresses.**

| Range | CIDR | Notes |
|---|---|---|
| 10.0.0.0 to 10.255.255.255 | 10.0.0.0/8 | Private |
| 172.16.0.0 to 172.31.255.255 | 172.16.0.0/12 | Private |
| 192.168.0.0 to 192.168.255.255 | 192.168.0.0/16 | Private, the usual SOHO range |
| 169.254.0.0 to 169.254.255.255 | 169.254.0.0/16 | APIPA (link-local) |
| 127.0.0.1 | 127.0.0.0/8 | Loopback (this computer) |

Private addresses are used inside homes and offices and are not routed on the internet. The SOHO router uses NAT (network address translation) to share its single **public** address, given by the ISP, with all the private devices inside.

**APIPA (Automatic Private IP Addressing).** When a Windows computer is set to get an address automatically and no DHCP server answers, it gives itself an address from 169.254.0.0/16 with mask 255.255.0.0 and no gateway. It can only talk to other APIPA devices on the same local link. If you see a 169.254 address, the client could not reach DHCP: check the cable and link light, the Wi-Fi connection, the switch port, and whether the DHCP server or router is working.

**Static vs dynamic.** Dynamic (DHCP) addressing suits most clients. Static addresses suit devices others must always find: routers, servers, printers and network storage. If you set a static address, use one outside the DHCP scope (or excluded from it) to avoid a duplicate address conflict.

**Worked example: reading a /24.** A PC has 192.168.1.50 with mask 255.255.255.0 (also written /24).

| Item | Value | How you get it |
|---|---|---|
| Network address | 192.168.1.0 | The first three numbers are the network, the last is 0 |
| Usable hosts | 192.168.1.1 to 192.168.1.254 | 254 addresses (2 to the power of 8, minus 2) |
| Broadcast | 192.168.1.255 | The last address in the network |
| Valid gateway | Any usable address in 192.168.1.x, often 192.168.1.1 | The gateway must be on the same subnet as the host |

So if this PC had a gateway of 192.168.0.1, it could talk to local devices but not to the internet, because the gateway is on a different network. With mask 255.255.0.0 (/16), the network would be 192.168.0.0 and hosts from 192.168.0.1 to 192.168.255.254 would all be local.

**IPv6 basics.** IPv6 addresses are 128 bits, written as eight groups of four hexadecimal digits separated by colons, such as 2001:0db8:0000:0000:0000:0000:0000:0020. You can drop leading zeros in each group and replace one run of all-zero groups with `::`, giving 2001:db8::20. Addresses starting with fe80 are **link-local** (every IPv6 interface has one, similar in spirit to APIPA). `::1` is the IPv6 loopback. IPv6 hosts can configure their own addresses (SLAAC) or use DHCPv6.

**Configuring a SOHO router: a practical checklist.**

1. Change the default admin password and, if possible, the admin username.
2. Update the router's firmware.
3. Set the Wi-Fi network name (SSID) and use WPA3, or WPA2 with AES if older devices need it. Use a long passphrase.
4. Disable WPS (Wi-Fi Protected Setup), which is easy to attack.
5. Check the DHCP scope, and reserve addresses for printers and network storage.
6. Pick the best channels using a Wi-Fi analyzer; use 20 MHz on 2.4 GHz.
7. Create a separate guest network for visitors, and consider one for IoT devices.
8. Set port forwarding only for services that must be reached from outside, and disable UPnP if not needed.
9. Test: confirm clients get the right addresses and can reach the internet.

### 2.7 Internet connection types and network types

**Internet connection types.**

| Type | Medium | Characteristics |
|---|---|---|
| Fiber | Glass fiber to the premises, ending at an ONT | Fastest and most reliable, often symmetrical (same upload and download), low latency. Not available everywhere |
| Cable | The cable TV coaxial network, cable modem | Fast downloads, slower uploads, bandwidth shared with neighbors |
| DSL | Telephone copper lines, DSL modem | Slower; speed drops the farther you are from the provider's equipment. Asymmetric (ADSL) is common |
| Cellular | 4G and 5G mobile networks | Available almost anywhere with signal; may have data caps; speed varies with signal |
| Satellite | Dish to a satellite | Works in remote areas. Traditional geostationary satellite has high latency because of the distance; low earth orbit services cut latency. Weather can affect it |
| WISP (wireless internet service provider) | A fixed antenna on the building aimed at the provider's tower | Common in rural areas; usually needs line of sight |

**Network types.**

| Type | Scale | Example |
|---|---|---|
| PAN (personal area network) | Around one person | Phone, watch and earbuds over Bluetooth |
| LAN (local area network) | One building or floor | An office network |
| WLAN (wireless LAN) | A LAN over Wi-Fi | The office Wi-Fi |
| MAN (metropolitan area network) | A city or campus | A city council linking its buildings across town |
| WAN (wide area network) | Across cities and countries | Branch offices linked together; the internet is the largest WAN |
| SAN (storage area network) | A dedicated network for storage | Servers reaching shared block storage over Fibre Channel or iSCSI |

### 2.8 Networking tools

| Tool | What it does | When you reach for it |
|---|---|---|
| Cable stripper | Removes the outer jacket without nicking the wires | First step of making a cable or a punchdown termination |
| Crimper | Presses an RJ45 (or RJ11) connector onto the end of a cable | Making patch cables |
| Punchdown tool | Pushes wires into the contacts of a patch panel, keystone jack or punchdown block (66 or 110) and trims them | Terminating building cabling |
| Cable tester | Checks each wire for continuity, opens, shorts and wrong pin order | After making or punching down a cable |
| Toner probe | A tone generator on one end and a probe that "hears" it on the other | Finding which unlabeled cable or port in a bundle or patch panel goes where |
| Loopback plug | Sends a port's output straight back into its input | Testing whether a NIC or switch port works |
| Wi-Fi analyzer | Shows nearby networks, channels and signal strength | Picking a channel, finding dead spots and interference |
| Network tap | Copies traffic passing through a link to a monitoring device | Capturing traffic for analysis without disturbing it |

The usual order for making a cable: strip, untwist and arrange the wires in T568B (or T568A) order, trim, insert into the connector, crimp, then test.

## How questions look

Expect a lot of direct "which port" and "which record" items, often wrapped in a short scenario: "A firewall must allow encrypted remote command-line access. Which port?" Scenario items describe a user who cannot browse, a printer that keeps changing address, a camera with no power outlet, or a crowded Wi-Fi channel. Exhibits are common: `ipconfig` output with a 169.254 address or a wrong gateway, a list of DNS records, or a Wi-Fi analyzer screen. "Choose two" items often ask for two protocols that share a trait, such as two that use UDP. Performance-based questions may ask you to configure a SOHO router (SSID, security, DHCP, port forwarding), match ports to protocols, or match tools to tasks.

## A method for these questions

1. Find the objective: a port, a wireless setting, a server role, a DNS or DHCP setting, a device, an addressing problem, a connection type or a tool.
2. For port items, name the protocol first, then recall its number and whether it uses TCP or UDP. Watch for "secure" or "encrypted" in the stem.
3. For addressing items, write down the host IP, mask and gateway, and check three things: is the address in a valid range (not 169.254), is the gateway on the same subnet, and is anything duplicated.
4. For wireless items, check the band first (2.4, 5 or 6 GHz), then the standard, then channel overlap.
5. For hardware items, ask what the device actually does: forward between networks (router), connect devices on one network (switch), add power to a cable (PoE), or terminate the provider's line (modem or ONT).
6. For tool items, picture the physical task: finding a cable, attaching a connector, terminating a panel, testing a port.
7. Eliminate options that would work only in theory or would break something else, such as giving a printer a static address inside the DHCP scope.

## Traps that cost points

- **SMTP vs POP3 vs IMAP.** SMTP (25) sends. POP3 (110) downloads mail to one device. IMAP (143) keeps mail on the server so it matches across devices. A user who reads mail on phone and laptop needs IMAP.
- **Mixing 443 and 445.** 443 is HTTPS, 445 is SMB file sharing.
- **DHCP on TCP.** DHCP uses UDP 67 and 68. DNS uses UDP for normal queries and TCP for zone transfers.
- **Telnet for "secure" access.** Telnet (23) sends everything in clear text. SSH (22) is the secure choice.
- **APIPA treated as a working address.** A 169.254 address means DHCP failed. Fix the path to the DHCP server, not the DNS settings.
- **Gateway on a different subnet.** Local traffic works but nothing leaves the network. The gateway must share the host's network.
- **Overlapping 2.4 GHz channels.** Only 1, 6 and 11 do not overlap. Channel 3 overlaps both 1 and 6.
- **A record vs MX record.** Mail delivery follows the MX record. An A record only maps a name to an IPv4 address.
- **Patch panel as an active device.** A patch panel just terminates cables. It does not switch, route or power anything.

## Timing

The exam is one 90-minute block with up to 90 questions, so plan for about a minute per multiple-choice item and extra time for performance-based questions. Pure recall items in this domain (ports, records, bands) should take well under a minute if you know your tables, which buys time for the `ipconfig` exhibits and router configuration PBQs. For addressing questions, jot the IP, mask and gateway on your scratch material rather than holding them in your head.

## Practice items

These 2 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A technician needs to manage a Linux server's command line remotely. Company policy says all remote administration traffic must be encrypted. Which port should the firewall allow?

A. TCP 23

B. TCP 3389

C. TCP 22

D. UDP 69

<details>
<summary>Answer and explanation</summary>

**Answer: C.** SSH gives an encrypted remote command line on TCP 22. (Objective 2.1)

- **A** is wrong because TCP 23 is Telnet, which sends everything, including passwords, in clear text.
- **B** is wrong because 3389 is RDP, a graphical Windows remote desktop, not a Linux command line.
- **D** is wrong because UDP 69 is TFTP, a simple unauthenticated file transfer protocol, not remote administration.

</details>

### Item 2

A desktop is configured with the settings below. It can print to the printer at 192.168.10.20 but cannot reach the internet. Other desktops on the same switch work fine.

```
IPv4 Address    192.168.10.75
Subnet Mask     255.255.255.0
Default Gateway 192.168.1.1
DNS Server      192.168.10.1
```

What is the MOST likely cause?

A. The subnet mask should be 255.255.255.255

B. The IP address is in the APIPA range

C. The default gateway is on a different subnet from the desktop

D. The printer is using the same IP address

<details>
<summary>Answer and explanation</summary>

**Answer: C.** With a /24 mask, the desktop's network is 192.168.10.0. Its gateway, 192.168.1.1, is on another network, so the desktop cannot send traffic off the local subnet. The gateway is probably 192.168.10.1. (Objective 2.6)

- **A** is wrong because 255.255.255.255 would leave no room for other hosts on the network.
- **B** is wrong because APIPA addresses start with 169.254.
- **D** is wrong because the printer is at .20 and the desktop is at .75, and printing works.

</details>

Want more? The [free timed CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=vv7axy&utm_content=a-plus) has 25 questions across both cores, with your score split by domain.

## Score yourself

| Item | 1 | 2 |
|---|---|---|
| Answer | C | C |
| Objective | 2.1 | 2.6 |

- **2 of 2:** strong. Keep the port table fresh by writing it from memory once a week, because this domain carries close to a quarter of Core 1.
- **1 of 2:** list the objectives you missed. Port mix-ups mean reread [2.1 Ports and protocols](#21-ports-and-protocols); addressing misses mean work through [2.6 SOHO network configuration and IP addressing](#26-soho-network-configuration-and-ip-addressing) again.
- **0 of 2:** spend two study sessions here. Write the port table, the 802.11 table and the private address ranges from memory until they are perfect, then reread [2.4 DNS, DHCP, VLAN and VPN](#24-dns-dhcp-vlan-and-vpn) before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. On your own computer, run `ipconfig /all` (Windows) or `ip addr` and `ip route` (Linux), and explain each line: address, mask, gateway, DNS servers, DHCP server and lease times. Then log in to your home router and find the DHCP scope, any reservations and the Wi-Fi channel it uses.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=vv7axy&utm_content=a-plus) to practice pacing across the whole exam.

---

<!-- nav:bottom -->
← Previous: [Core 1, Domain 1: Mobile Devices](1-mobile-devices.md) | Next: [Core 1, Domain 3: Hardware](3-hardware.md) → | [Back to contents](../../README.md#contents)
<!-- /nav:bottom -->
