<!-- nav:top -->[Contents](../../README.md#contents) · Previous: [Core 1, Domain 3: Hardware](3-hardware.md) · Next: [Core 1, Domain 5: Hardware and Network Troubleshooting](5-hardware-and-network-troubleshooting.md)<!-- /nav:top -->

# Core 1, Domain 4: Virtualization and Cloud Computing

**Weight:** 11% of the Core 1 exam (220-1201), CompTIA's figure, the lightest Core 1 domain. By our estimate that is roughly 9 of up to 90 questions. **Objectives:** 4.1 to 4.2.

This domain is about running computers inside computers, and renting computing from someone else. On a help desk you will meet both every week: a developer who needs a test VM, a call center on virtual desktops, a user whose files "disappeared" from a sync folder. Marks are lost here because the terms sound alike (Type 1 and Type 2, PaaS and SaaS, elasticity and availability), so the exam tests whether you can tell them apart in a short scenario.

## What this domain measures

There are only two objectives, but each one packs a lot of vocabulary. Expect "which model fits this business" and "which hypervisor or setting fits this need" more than deep technical configuration.

| Objective | What it asks you to do | Topics you must know |
|---|---|---|
| 4.1 | Explain virtualization concepts | Why we use VMs (sandbox, test and development, application virtualization for legacy software and cross-platform use), requirements (security, network, storage), desktop virtualization and VDI, containers, Type 1 and Type 2 hypervisors |
| 4.2 | Summarize cloud computing concepts | Private, public, hybrid and community clouds; IaaS, PaaS and SaaS; shared vs dedicated resources, metered utilization, ingress and egress, elasticity, availability, file synchronization, multitenancy |

## Key concepts explained

### 4.1 Virtualization concepts

**The basic idea.** A **virtual machine (VM)** is a complete computer made of software: virtual CPU, memory, disk and network card. The physical computer is the **host**. Each VM is a **guest**, with its own operating system. The software that creates and runs VMs is the **hypervisor**.

**Hypervisors.** This is the most tested distinction in the domain.

| | Type 1 (bare metal) | Type 2 (hosted) |
|---|---|---|
| Where it runs | Directly on the hardware, no general-purpose OS underneath | As an application on top of a normal OS (Windows, macOS, Linux) |
| Typical use | Servers and data centers | Desktops and laptops: testing, training, running a second OS |
| Performance | Better, less overhead | Lower, because the host OS takes its share |
| Examples | VMware ESXi, Microsoft Hyper-V, Xen, KVM | Oracle VirtualBox, VMware Workstation, Parallels Desktop |

How to tell them apart in a question: if the stem mentions a server, a data center or "directly on the hardware", think Type 1. If it mentions a user's laptop, "installed on Windows" or "a tech wants to try Linux on their PC", think Type 2. Hyper-V is a Type 1 hypervisor even when you enable it on Windows 11 Pro, because once it is on, it sits under Windows.

**Purpose of virtual machines.**

| Purpose | What it means | Help desk example |
|---|---|---|
| Sandbox | An isolated place to run something risky. If it breaks or is infected, you throw the VM away or roll back a snapshot | Opening a suspicious attachment in a VM with no network access |
| Test development | Developers and IT test software, patches and settings on VMs before they touch real users | Testing a new Windows update on a VM copy of the standard image |
| Application virtualization | The application runs isolated from, or streamed to, the local OS instead of being installed normally | A web-delivered app that runs on any staff PC without a local install |
| Legacy software or OS | Keep an old app alive by running its old OS in a VM on modern hardware | An accounting program that only runs on an old, unsupported Windows version |
| Cross-platform virtualization | Run an OS or app made for a different platform | A Mac user running Windows in a VM to use a Windows-only tool |

A tip on legacy systems: an unsupported OS gets no security updates. Running it in a VM saves the old hardware but not the risk, so limit or remove its network access and give it only the data it needs.

**Requirements.** The objective lists three areas. A good mental checklist before building any VM:

| Area | What to check |
|---|---|
| CPU and firmware | Hardware virtualization support in the CPU (Intel VT-x or AMD-V) and turned on in UEFI or BIOS settings. If a hypervisor says virtualization is unavailable, this is the first place to look |
| Memory | Enough RAM for the host plus every guest running at the same time. A host with 16 GB cannot comfortably run three guests at 8 GB each |
| Storage | Each VM's disk is a file (or set of files) on the host. Fixed-size disks reserve all the space up front; dynamically expanding disks grow as data is written. Snapshots also use space and grow over time |
| Network | Choose how the guest connects (table below) |
| Security | Treat each guest like a real computer (details below) |

Common virtual network modes. Names vary by product, but the ideas are the same.

| Mode | What the guest can reach | When to use it |
|---|---|---|
| NAT | Shares the host's connection. The guest gets a private address from the hypervisor and can reach the internet, but other computers on the LAN cannot easily reach the guest | Default for casual use: browsing, updates |
| Bridged (Hyper-V calls the switch "external") | The guest appears on the physical LAN as its own device, with its own address from the office DHCP server | The guest must be reachable by other PCs, such as a test web server |
| Host-only or internal | Only the host and other guests on that virtual network | Lab work that must not touch the real network |
| Private | Only other guests on that virtual switch, not even the host | Fully isolated test networks, malware analysis |

**Security requirements.**

- Every guest OS needs its own patches, endpoint protection and strong passwords. Patching the host does not patch the guests.
- Patch the hypervisor too. A flaw that lets code break out of a guest into the host (often called VM escape) is the worst case, because one guest could then reach all the others.
- Watch for **VM sprawl**: forgotten VMs that nobody patches. Keep an inventory.
- A **snapshot** saves a VM's state so you can roll back. It is not a backup: it usually depends on the original disk files, so if those are lost, the snapshot is lost too.
- Isolate risky guests (sandbox, legacy OS) on host-only or private networks.

**Desktop virtualization and VDI.** With **Virtual Desktop Infrastructure (VDI)**, users' Windows desktops run as VMs on servers in a data center or the cloud. The user connects from a thin client, an old PC, a laptop or a tablet. The device is just a window into the desktop.

- Benefits: central management and patching, data stays in the data center, a broken device can be swapped in minutes, staff can work from anywhere.
- Costs: everything depends on the network and the servers. If the link is slow or down, nobody can work.
- **Persistent** desktops keep the user's changes between sessions. **Non-persistent** desktops reset to a clean image at logoff, which is common in call centers and labs.

**Containers.** A container packages an application with its libraries and settings, and runs it as an isolated process on the host's OS kernel. There is no separate guest OS in each container.

| | Virtual machine | Container |
|---|---|---|
| Includes | A full guest OS plus the app | The app and its dependencies only |
| Shares | Only the hardware, through the hypervisor | The host's OS kernel |
| Size and startup | Gigabytes, starts in tens of seconds or more | Often megabytes, starts in seconds |
| Isolation | Strong, each VM has its own kernel | Lighter, all containers share one kernel |
| Typical use | Running different operating systems, full servers | Shipping the same app identically to laptops, test and production |

Docker is the best-known container platform. The key exam phrase: containers **share the host kernel**, so a container built for Linux needs a Linux kernel to run on.

### 4.2 Cloud computing concepts

**Cloud models: who uses the infrastructure.**

| Model | Who uses it | Typical reason | Example |
|---|---|---|---|
| Private cloud | One organization only, run on its own hardware or hosted for it alone | Control, compliance, sensitive data | A bank runs its own virtualized data center with self-service VMs for its teams |
| Public cloud | Many unrelated customers on a provider's shared infrastructure | No hardware to buy, pay for what you use, global scale | A startup runs its website on a large public cloud provider |
| Hybrid cloud | A mix of private (or on-premises) and public, connected and used together | Keep sensitive systems in-house, burst or extend into the public cloud | Customer records stay on-premises; the public website and email run in the public cloud |
| Community cloud | Several organizations with shared needs (regulation, mission) share one cloud | Share the cost of meeting the same rules | Several hospitals or government agencies share a cloud built for their compliance rules |

How to tell hybrid from community: hybrid is **one organization using two kinds** of cloud. Community is **several organizations sharing one** cloud.

**Service models: who manages what.** Think of the stack from the bottom (hardware) to the top (your data). The further you move from IaaS to SaaS, the more the provider manages.

| Layer | On-premises | IaaS | PaaS | SaaS |
|---|---|---|---|---|
| Data and user accounts | You | You | You | You |
| Application | You | You | You (your code) | Provider |
| Runtime, middleware, database engine | You | You | Provider | Provider |
| Operating system and its patches | You | You | Provider | Provider |
| Virtualization, servers, storage, network | You | Provider | Provider | Provider |
| Building, power, physical security | You | Provider | Provider | Provider |

| Model | What you get | Help desk example |
|---|---|---|
| Infrastructure as a service (IaaS) | Virtual servers, storage and networks. You install and patch the OS and everything above it | Spinning up a cloud VM to host an internal ticketing server |
| Platform as a service (PaaS) | A ready platform to run your code: runtime, database, scaling. You bring the code and data | Developers push web app code and the platform runs it, with no OS to patch |
| Software as a service (SaaS) | A finished application used through a browser or app. You manage users, settings and data | Web-based email, office suites, CRM, video meetings |

Quick rule: if the customer **patches the OS**, it is IaaS. If the customer **writes the code but never sees the OS**, it is PaaS. If the customer **just logs in and uses it**, it is SaaS. In every model you are still responsible for your data and who has access to it.

**Cloud characteristics.**

| Characteristic | Plain meaning | What it looks like in a question |
|---|---|---|
| Shared resources | Your workloads run on hardware shared with other customers | Normal public cloud; cheapest option |
| Dedicated resources | Hardware reserved for you alone (for example a dedicated host) | A license or regulation requires that no other customer shares the physical server |
| Metered utilization | You pay for what you consume: compute time, storage per month, data transferred | "Pay only for what we use", a bill that changes with usage |
| Ingress | Data moving into the cloud | Uploading backups or migrating files to the cloud. Providers commonly charge little or nothing for this |
| Egress | Data moving out of the cloud to the internet or another provider | Serving large downloads or videos to customers, or moving out of a provider. Commonly the transfer line that grows the bill |
| Elasticity | Resources grow and shrink automatically with demand | Extra web servers appear for a holiday sale and disappear after it |
| Availability | The service stays up, usually through redundancy across locations, backed by an uptime commitment in the service agreement | "Must keep running if one data center fails" |
| File synchronization | Files are kept the same across devices and the cloud | A user edits a file on a laptop and sees the change on a phone |
| Multitenancy | Many customers (tenants) share the same infrastructure or application, kept logically separate | One SaaS application serves thousands of companies, each seeing only its own data |

Two distinctions that come up often:

- **Elasticity vs scalability.** Scalability is the ability to grow. Elasticity adds the automatic part: it grows **and shrinks** with demand, which matters because you are metered.
- **Synchronization is not backup.** If a user deletes or a ransomware infection encrypts a file in a sync folder, the change syncs everywhere. Recovery depends on the service's version history or recycle bin, or a separate backup. This is a common help desk call: "I deleted a file on my laptop and now it is gone from my phone too."

**Putting it together: a worked example.** A small accounting firm asks for advice.

- They want email and calendars with no servers to run: **SaaS**, a **public cloud** service.
- Their client tax database must stay on hardware they control for regulatory reasons, but they want to back it up to the cloud: **hybrid cloud**. The backups are **ingress**; a full restore from the cloud later is **egress** and may show up on the bill under **metered utilization**.
- In tax season they need extra capacity for a few weeks: **elasticity** in the public portion.
- Staff want the same files on office PCs and laptops: **file synchronization**, plus a real backup alongside it.

## How questions look

Most items here are short scenarios that ask you to pick a model, hypervisor type or characteristic. Common stems: "A company wants to... Which cloud model BEST fits?", "Which hypervisor type should the technician install?", "Which characteristic describes...?" and "What should the technician check FIRST?" when a VM will not start. Expect "Choose two" items that pair characteristics, such as elasticity with metered utilization. Exhibits can be VM settings (memory, network adapter, IP address) or a simple cloud bill. Drag-and-drop tasks may ask you to match examples to IaaS, PaaS and SaaS, or to match the four cloud deployment models to organizations.

## A method for these questions

1. Underline who owns or shares the resource. One organization, many unrelated customers, both, or a group with the same needs points to private, public, hybrid or community.
2. Find the highest layer the customer manages. OS means IaaS, code means PaaS, only users and settings means SaaS.
3. For hypervisor items, ask what is underneath: bare hardware (Type 1) or an existing desktop OS (Type 2).
4. For "run an app" items, decide whether a full separate OS is needed (VM) or only the app and its libraries on a shared kernel (container).
5. For characteristic items, match the business words: "automatically" and "shrink" (elasticity), "pay for use" (metered), "keeps running" (availability), "data leaving" (egress), "many customers on one platform" (multitenancy).
6. For VM troubleshooting, check in order: CPU virtualization enabled in firmware, enough RAM and disk on the host, then the virtual network mode.

## Traps that cost points

- **Hyper-V as Type 2.** It is enabled from inside Windows, so it feels hosted, but it is a Type 1 hypervisor. VirtualBox and VMware Workstation are the classic Type 2 examples.
- **Hybrid vs community.** Hybrid is one organization mixing private and public. Community is several organizations sharing one cloud.
- **PaaS vs SaaS.** If the customer deploys its own code, it is PaaS. SaaS is a finished application someone else wrote.
- **"The host is patched, so the guests are safe."** Each guest OS needs its own updates and endpoint protection.
- **Snapshots as backups.** A snapshot is a rollback point that depends on the original disk files. Keep real backups.
- **Elasticity mistaken for availability.** Adding capacity for demand is elasticity. Staying up when something fails is availability.
- **Sync treated as backup.** Deletions and encryption sync too. Recovery needs version history or a separate backup.
- **Containers carrying their own OS.** Containers share the host kernel. If the question needs a different operating system, the answer is a VM.
- **NAT expected to make a guest reachable.** With NAT, the guest can reach out, but LAN devices cannot easily reach in. Use bridged mode for that.

## Timing

Across the whole exam, plan on about a minute per multiple-choice item, and longer for performance-based questions. Items in this domain are usually quick vocabulary-in-context questions, so aim to finish them in well under a minute and bank the time for the hardware and troubleshooting PBQs. If two cloud answers both look right, reread who owns the resource and who manages which layer: that usually settles it in seconds.

## Practice items

These 10 items are original, written for these notes. They are not taken from CompTIA's exam or any prep provider.

### Item 1

A user forwards an email with an unexpected attachment to the help desk. The technician wants to open the file and watch what it does without putting the corporate network or their own workstation at risk. What is the BEST approach?

A. Open it on the user's PC, since that PC has already received the file

B. Forward it to the user's manager for approval before opening

C. Open it in a VM with networking disabled, then roll back to a clean snapshot

D. Open it on the file server, because servers have stronger antivirus

<details>
<summary>Answer and explanation</summary>

**Answer: C.** A VM used as a sandbox isolates the file. With no network access it cannot spread, and rolling back the snapshot removes any changes. (Objective 4.1)

- **A** is wrong because opening it on a production PC risks infecting that PC and the network.
- **B** is wrong because approval does not make the file safe to open.
- **D** is wrong because a file server holds shared data and is the worst place to run unknown code.

</details>

### Item 2

A small business buys a new server to run four virtual machines: a domain controller, a file server, a database and a print server. It wants the best performance, with no general-purpose operating system installed underneath the VMs. What should the technician install on the server?

A. A Type 1 hypervisor

B. A Type 2 hypervisor

C. A container engine

D. A VDI client

<details>
<summary>Answer and explanation</summary>

**Answer: A.** A Type 1 (bare-metal) hypervisor runs directly on the hardware, with less overhead than a hosted hypervisor, which suits servers. (Objective 4.1)

- **B** is wrong because a Type 2 hypervisor runs on top of a host operating system, which the business wants to avoid.
- **C** is wrong because containers share one host kernel and do not provide four separate full operating systems.
- **D** is wrong because a VDI client connects to remote desktops; it does not host VMs.

</details>

### Item 3

A firm's billing program runs only on an old Windows version that no longer receives security updates. The PC it runs on is failing. The firm needs the program for two more years. What is the BEST solution?

A. Move the old PC onto the main office network so more staff can reach it

B. Install the program on a new Windows 11 PC and disable updates to keep it compatible

C. Replace the program with a public cloud file sync service

D. Run the old OS in a VM on a modern host and restrict the VM's network access

<details>
<summary>Answer and explanation</summary>

**Answer: D.** Virtualizing the legacy OS keeps the program running on supported hardware. Because the old OS gets no patches, its network access should be limited. (Objective 4.1)

- **A** is wrong because exposing an unpatched OS to more of the network increases risk and does nothing about the failing hardware.
- **B** is wrong because the program does not run on the new OS, and disabling updates weakens the new PC.
- **C** is wrong because file synchronization stores files; it does not run a billing application.

</details>

### Item 4

A development team wants to package a web application with its exact libraries so it runs the same way on developer laptops, test servers and production. Each copy should start in seconds and must not carry a full operating system. Which technology fits BEST?

A. A separate Type 1 VM for each copy

B. Containers

C. Virtual desktop infrastructure

D. Dual-booting each laptop

<details>
<summary>Answer and explanation</summary>

**Answer: B.** Containers bundle the app and its dependencies and share the host's kernel, so they are small, start quickly and behave the same everywhere. (Objective 4.1)

- **A** is wrong because each VM includes a full guest OS, which the team wants to avoid.
- **C** is wrong because VDI delivers whole user desktops, not packaged applications.
- **D** is wrong because dual-booting switches between installed operating systems and does nothing to package the app.

</details>

### Item 5

A call center has 200 agents using thin clients. Each agent signs in to a Windows desktop that runs on servers in the company's data center. When a thin client breaks, the agent moves to a spare and carries on with the same desktop. What is this?

A. Virtual Desktop Infrastructure

B. Containers

C. A Type 2 hypervisor on each thin client

D. Application sandboxing

<details>
<summary>Answer and explanation</summary>

**Answer: A.** In VDI, desktops run as VMs on central servers and users connect from any device, so the device itself is replaceable. (Objective 4.1)

- **B** is wrong because containers package applications, not full user desktops.
- **C** is wrong because the desktops run in the data center, not on the thin clients.
- **D** is wrong because a sandbox isolates risky code; it is not a way to deliver desktops to users.

</details>

### Item 6

A technician builds a test VM to host a small web app. Coworkers on the office network cannot reach the app, although the technician can browse to it from inside the VM. The VM settings are shown.

```
VM name ............ HELPDESK-TEST
Guest OS ........... Windows 11
Memory ............. 4096 MB
Network adapter .... NAT
Host IP address .... 192.168.1.40
Guest IP address ... 10.0.2.15
Office LAN ......... 192.168.1.0/24
```

What change will let coworkers reach the web app?

A. Increase the VM's memory to 8192 MB

B. Change the network adapter to host-only

C. Change the network adapter to bridged

D. Add a second virtual hard disk

<details>
<summary>Answer and explanation</summary>

**Answer: C.** In NAT mode the guest sits behind the host on a private network (10.0.2.15), so LAN devices cannot easily reach it. Bridged mode puts the guest on the office LAN with its own 192.168.1.x address. (Objective 4.1)

- **A** is wrong because the app works inside the VM, so memory is not the problem.
- **B** is wrong because host-only limits the guest to the host and other guests, which blocks coworkers even more.
- **D** is wrong because storage has nothing to do with network reachability.

</details>

### Item 7

An online store's traffic triples every December. The owner wants extra servers to be added automatically during busy periods and removed afterwards, and wants to pay only for the capacity actually used. Which two cloud characteristics is the owner describing? Choose two.

A. Multitenancy

B. Elasticity

C. File synchronization

D. Metered utilization

E. Community cloud

<details>
<summary>Answer and explanation</summary>

**Answer: B and D.** Elasticity adds and removes resources automatically with demand. Metered utilization bills for what is consumed. Together they mean the store pays for the extra servers only while they run. (Objective 4.2)

- **A** is wrong because multitenancy is about many customers sharing infrastructure, not automatic scaling or billing.
- **C** is wrong because file synchronization keeps files the same across devices.
- **E** is wrong because a community cloud is a deployment model shared by organizations with common needs, not a characteristic of scaling.

</details>

### Item 8

A company's developers want to deploy their web application code to the cloud. They do not want to install, patch or manage the operating system or the runtime. They will manage their own code and data. Which service model fits?

A. IaaS

B. SaaS

C. Private cloud

D. PaaS

<details>
<summary>Answer and explanation</summary>

**Answer: D.** In platform as a service, the provider manages the OS and runtime and the customer brings the code and data. (Objective 4.2)

- **A** is wrong because with IaaS the customer manages the OS and everything above it.
- **B** is wrong because SaaS is a finished application; the customer does not deploy its own code.
- **C** is wrong because private cloud is a deployment model (who uses the infrastructure), not a service model.

</details>

### Item 9

Four regional hospitals agree to share one cloud environment built to meet the same health-data regulations. They split the cost, and no other organizations use it. Which cloud model is this?

A. Public cloud

B. Community cloud

C. Hybrid cloud

D. Private cloud

<details>
<summary>Answer and explanation</summary>

**Answer: B.** A community cloud is shared by several organizations with common requirements, such as the same regulations. (Objective 4.2)

- **A** is wrong because a public cloud is open to many unrelated customers.
- **C** is wrong because hybrid describes one organization combining private and public cloud.
- **D** is wrong because a private cloud serves a single organization, and four hospitals share this one.

</details>

### Item 10

A technician installs VirtualBox on a user's desktop. When creating a 64-bit VM, the software reports that hardware virtualization is not available. The PC has 32 GB of RAM and a recent CPU. What should the technician check FIRST?

A. Whether the host has enough free disk space for the virtual disk

B. Whether the VM's network adapter is set to bridged

C. Whether Intel VT-x or AMD-V is enabled in the UEFI settings

D. Whether the guest OS installer image is corrupted

<details>
<summary>Answer and explanation</summary>

**Answer: C.** Hypervisors need CPU virtualization extensions, and these are often turned off in firmware by default. The error message points directly at this requirement. (Objective 4.1)

- **A** is wrong because low disk space produces a storage error, not a hardware virtualization error.
- **B** is wrong because the network mode does not affect whether a VM can start.
- **D** is wrong because a bad installer would fail during installation, after the VM itself starts.

</details>

## Score yourself

| Item | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Answer | C | A | D | B | A | C | B, D | D | B | C |
| Objective | 4.1 | 4.1 | 4.1 | 4.1 | 4.1 | 4.1 | 4.2 | 4.2 | 4.2 | 4.1 |

- **9 to 10:** strong. This domain is small, so keep it warm with a quick review of the tables and spend your time on Domains 3 and 5.
- **7 to 8:** note which terms you confused. The usual pairs are Type 1 and Type 2, PaaS and SaaS, and hybrid and community. Reread those rows in [Key concepts](#key-concepts-explained).
- **6 or fewer:** reread [4.1 Virtualization concepts](#41-virtualization-concepts) and [4.2 Cloud computing concepts](#42-cloud-computing-concepts), then write the service model responsibility table and the four cloud models from memory before redoing the items.

## Next step

1. Redo any item you missed without opening the explanation, and write the trap you fell for in one line.
2. Install a free Type 2 hypervisor such as VirtualBox, build one Linux VM, and switch its network adapter between NAT, bridged and host-only. Each time, run `ip addr` in the guest and try to ping the guest from another PC, and explain what changed.
3. Take a timed run with the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to practise pacing across the whole exam.

---

<!-- nav:bottom -->← Previous: [Core 1, Domain 3: Hardware](3-hardware.md) | Next: [Core 1, Domain 5: Hardware and Network Troubleshooting](5-hardware-and-network-troubleshooting.md) → | [Back to contents](../../README.md#contents)<!-- /nav:bottom -->
