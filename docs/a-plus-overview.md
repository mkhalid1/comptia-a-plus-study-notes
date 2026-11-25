<!-- nav:top -->
[Contents](../README.md#contents) · Next: [Diagnostic: Core 1 and Core 2](diagnostic.md)
<!-- /nav:top -->

# How CompTIA A+ works

CompTIA A+ is a vendor-neutral certification for entry-level IT support: hardware, networking, operating systems, security and the everyday work of a help desk. Unlike most CompTIA certifications, A+ is **two exams**. These notes cover the current version, **A+ V15**: Core 1 (**220-1201**) and Core 2 (**220-1202**).

## Two exams, one certification

- **You must pass both.** Passing Core 1 alone, or Core 2 alone, does not earn A+. You become certified when you have passed both.
- **Any order.** CompTIA lets you take Core 1 and Core 2 in either order.
- **Same version only.** CompTIA's wording is: "Core 1 and Core 2 exams must be taken from the same version, no mixing allowed." With V15, that means 220-1201 plus 220-1202. If you studied an older version's Core 1, you cannot pair it with a V15 Core 2.

Each exam has its own objectives, passing score and score report. Treat them as two separate projects that share a little vocabulary.

## Quick facts, side by side

| | Core 1 (220-1201) | Core 2 (220-1202) |
|---|---|---|
| Version | A+ V15 | A+ V15 |
| Launched | March 25, 2025 | March 25, 2025 |
| Retires | Usually three years after launch (CompTIA estimates 2028) | Usually three years after launch (CompTIA estimates 2028) |
| Questions | A maximum of 90 | A maximum of 90 |
| Question types | Multiple-choice (single and multiple response), drag-and-drop, performance-based | Multiple-choice (single and multiple response), drag-and-drop, performance-based |
| Time | 90 minutes | 90 minutes |
| Passing score | **675** on a scale of 100 to 900 | **700** on a scale of 100 to 900 |
| Focus | Mobile devices, networking, hardware, virtualization and cloud, hardware and network troubleshooting | Operating systems, security, software troubleshooting, operational procedures |
| Recommended experience | 12 months of hands-on experience in an IT support specialist job role | Same |
| Languages | English, German, Japanese | English, German, Japanese |
| Delivery | Pearson VUE test center, or online with OnVUE | Same |

Both exams together count toward one certification, renewed on a three-year cycle with 20 continuing education units (CEUs).

Sources: CompTIA's [A+ page](https://www.comptia.org/en-us/certifications/a/), [Core 1 V15 page](https://www.comptia.org/en-us/certifications/a/core-1-v15/), [Core 2 V15 page](https://www.comptia.org/en-us/certifications/a/core-2-v15/), [Core 1 and 2 V15 page](https://www.comptia.org/en-us/certifications/a/core-1-and-2-v15/), the two official objectives documents and the CompTIA policy pages listed in [Sources](sources.md), checked 24 November 2026. CompTIA's pages write the scale as "on a scale of 900"; the objectives documents give it as 100 to 900.

## Domains and weights at a glance

| Exam | Domain | Weight | Roughly how many questions (our estimate) | Guide |
|---|---|---|---|---|
| Core 1 | 1.0 Mobile Devices | 13% | about 11 of up to 90 | [Core 1, Domain 1](core-1/1-mobile-devices.md) |
| Core 1 | 2.0 Networking | 23% | about 20 | [Core 1, Domain 2](core-1/2-networking.md) |
| Core 1 | 3.0 Hardware | 25% | about 22 | [Core 1, Domain 3](core-1/3-hardware.md) |
| Core 1 | 4.0 Virtualization and Cloud Computing | 11% | about 9 | [Core 1, Domain 4](core-1/4-virtualization-and-cloud-computing.md) |
| Core 1 | 5.0 Hardware and Network Troubleshooting | 28% | about 25 | [Core 1, Domain 5](core-1/5-hardware-and-network-troubleshooting.md) |
| Core 2 | 1.0 Operating Systems | 28% | about 25 of up to 90 | [Core 2, Domain 1](core-2/1-operating-systems.md) |
| Core 2 | 2.0 Security | 28% | about 25 | [Core 2, Domain 2](core-2/2-security.md) |
| Core 2 | 3.0 Software Troubleshooting | 23% | about 20 | [Core 2, Domain 3](core-2/3-software-troubleshooting.md) |
| Core 2 | 4.0 Operational Procedures | 21% | about 18 | [Core 2, Domain 4](core-2/4-operational-procedures.md) |

The weights are CompTIA's. The question counts are our arithmetic (weight times 90, rounded down), because CompTIA publishes only the maximum number of questions per exam, not how many come from each domain. Each core has its own overview: [Core 1 (220-1201)](core-1/README.md) and [Core 2 (220-1202)](core-2/README.md).

## Which core to take first

CompTIA has no required order. Our guidance:

- **Most people should take Core 1 first.** It builds the physical and networking picture (ports, cables, IP addressing, RAM, storage) that Core 2 assumes when it asks you to fix a Windows network setting or secure a SOHO router.
- **Take Core 2 first if you already live in software.** If you use Windows tools, the command line and account settings every day but have never opened a PC case, Core 2 may be the faster win.
- **Book them close together.** The two exams share topics such as wireless security, SOHO networks and mobile devices. A gap of a few weeks keeps that overlap fresh.

## Who A+ is for

CompTIA names roles such as IT support specialist and help desk technician, and lists DoD 8140 work roles including technical support specialist, system administrator and cyber defense infrastructure support specialist. The recommended 12 months of hands-on experience is a recommendation, not an entry requirement. Many people take A+ as their first IT certification, before Network+ or Security+.

## How the questions work

- **Multiple-choice, single response.** One correct answer.
- **Multiple-choice, multiple response.** Choose two or more. The stem tells you how many; read it every time.
- **Drag-and-drop.** Match or order items: ports to protocols, connectors to cables, steps into sequence.
- **Performance-based questions (PBQs).** Short hands-on tasks in a simulated environment, such as configuring a SOHO router, choosing a command-line tool, or placing components. They usually take longer. See [Performance-based questions and pacing](performance-based-questions.md).
- **Scenario wording.** Many stems include BEST, MOST likely, FIRST or NEXT. More than one option may be partly right; pick the one that fits the stated symptom, goal or constraint.

## How the objectives documents work

Each exam has its own objectives document. It lists every objective (for example "2.1 Compare and contrast Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) ports, protocols, and their purposes") with bulleted examples underneath. CompTIA notes that these bulleted lists **are not exhaustive**: other examples of technologies, processes or tasks for an objective may appear on the exam. Treat the bullets as the minimum.

Watch the verbs. "Compare and contrast" means telling similar things apart. "Explain" and "Summarize" mean knowing what something is and why it matters. "Given a scenario" means applying it to a situation, often in a PBQ.

One detail worth knowing: the Core 1 objectives document prints CompTIA's six-step troubleshooting methodology, but states that the methodology itself "will not be tested" and is not a formal objective. Learn it anyway as a working habit, because both exams are full of troubleshooting scenarios.

## Booking and taking the exams

You can sit each exam at a Pearson VUE test center or online through OnVUE. Online exams are recorded through your webcam, have no scheduled breaks, and can be rescheduled or cancelled only until the appointment start time. You book and pay for Core 1 and Core 2 separately. CompTIA lists the current exam price on its site and in its store. The full checklist is on the [exam-day page](exam-day-checklist.md).

## Retakes and renewal

- **Retakes.** The rules apply to each exam on its own. No waiting period between your first and second attempt. Before a third or later attempt you must wait at least 14 calendar days from your last attempt. Every attempt is paid in full, with no free retests. You cannot retake an exam you have passed under the same exam code without CompTIA's consent.
- **Renewal.** A+ is renewed on a three-year cycle through CompTIA's continuing education program, which requires 20 CEUs for A+.

## Practice the real format

Reading teaches the content; timed practice teaches the pace. When you have worked through a few domains of one core, take the [free CompTIA A+ practice test on PrepClubs](https://prepclubs.com/free-practice-tests/a-plus?utm_source=github&utm_medium=referral&utm_campaign=study-notes&utm_content=a-plus) to see how you do against the clock, then use the [diagnostic](diagnostic.md) and the score tables on each domain page to decide what to study next.

---

<!-- nav:bottom -->
Next: [Diagnostic: Core 1 and Core 2](diagnostic.md) → | [Back to contents](../README.md#contents)
<!-- /nav:bottom -->
