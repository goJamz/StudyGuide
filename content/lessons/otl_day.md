---
title: OTL Day
description: Study guide for OPTASKLINK, voice nets, fine synchronization, and tactical data link unit definitions.
tags:
  - lessons
  - optasklink
  - tactical-data-links
---

## Duty Codes

| Code    | Duty or Role                                    |
| ------- | ----------------------------------------------- |
| **804** | ICO                                             |
| **805** | JICO                                            |
| **812** | NTR                                             |
| **815** | IEJU                                            |
| **822** | Link 16 Secondary Navigation Controller (SECNC) |
| **907** | JREJU                                           |
| **908** | JREU                                            |

## OPTASKLINK

### JICO and the OPTASKLINK

The **Area Air Defense Commander (AADC)** designates a **Joint Interface Control Officer (JICO)** who **builds the OPTASKLINK for the theater of operations**.

The ICO and interface units coordinate during OPTASKLINK **production, dissemination, and implementation**.

### Key Sets

| Set          | Information Provided                       |
| ------------ | ------------------------------------------ |
| **JUDATA**   | Link 16 data for the unit                  |
| **SATINFOJ** | Link 16 satellite information for the unit |
| **UNITINFO** | JRE information for the unit               |
| **LNKPROT**  | JRE protocol being used                    |

### Message Format

OPTASKLINK messages use the **United States Message Text Format (USMTF)**.

### Set, Segment, and Field

| Element     | Definition                                                               |
| ----------- | ------------------------------------------------------------------------ |
| **Set**     | Begins with an abbreviated word called the **set ID**.                   |
| **Segment** | A group of two or more consecutive sets that can be repeated as a group. |
| **Field**   | An individual data entry within a set.                                   |

### Special Characters

| Character | Meaning                        |
| --------- | ------------------------------ |
| `/`       | Marks the beginning of a field |
| `//`      | Marks the end of a set         |
| `-`       | Indicates no data              |

> **Memory aid:** One slash starts a field, two slashes stop a set, and a hyphen means no data.

### Common Message Sets

#### EXER

Provides the designated code name or nickname when the message supports an **exercise**.

#### OPER

Provides the designated code name or nickname when the message supports an **operation**.

#### JUDATA

The **JUDATA** set provides data about **Link 16 data-link system units**. Key information includes:

- **Unit designation**
- **Call sign**
- **Primary JU address**
- **Link 16 track block assignment**

> **Quick recall:** JUDATA tells you **who the Link 16 unit is, how it is identified, its JU address, and its track block**.

## Voice Nets

| Net                                             | Primary Use                                                                                                           | Key Detail                                                                                        |
| ----------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| **Voice Product Net (VPN)**                     | Provides amplifying signals intelligence (SIGINT) information to other interface units (IUs).                         | Employed by Special Information System (SIS) units for intelligence information and coordination. |
| **Track Supervision Net (TSN)**                 | Maintains a clear tactical picture and assists units entering or exiting the interface.                               | The Track Data Coordinator (TDC) is the net control station (NCS).                                |
| **Air Defense Command and Control Net (ADCCN)** | Disseminates changes to the area air defense plan, including TACOPDAT-defined positions, responsibilities, or status. | Used by the Area Air Defense Commander (AADC) for high-level air defense coordination.            |
| **Data Link Coordination Net (DCN)**            | Manages and coordinates the entire TADIL interface.                                                                   | Used by the Interface Control Officer (ICO); this wide-area net is usually SATCOM or HF/UHF.      |

### Voice Net Quick Match

- **VPN:** intelligence information and coordination
- **TSN:** tactical-picture management
- **ADCCN:** high-level air defense coordination
- **DCN:** overall TADIL interface management

## Link 16 Time Structure

The Link 16 network uses three time units of measurement:

1. **Epoch**
2. **Frame**
3. **Time Slot**

> **Quick recall:** **Epoch -> Frame -> Time Slot**.

## Fine Synchronization

### Round Trip Timing Interrogation (RTT-I)

- A terminal in **coarse sync** uses an RTT-I message to achieve **fine sync**.
- The terminal sends the RTT-I to another suitable terminal.

### Round Trip Timing Reply (RTT-R)

- The terminal receiving the RTT-I sends an RTT-R.
- The reply is transmitted in the **same time slot** in which the RTT-I was received.
- A successful RTT-I/RTT-R exchange brings the initiating terminal into fine sync.

### Maintaining Fine Sync

Once in fine sync, a terminal periodically sends RTT-I messages to suitable terminals to maintain synchronization.

### Fine-Sync Sequence

1. A terminal is in **coarse sync**.
2. It sends an **RTT-I** to a suitable terminal.
3. The receiving terminal sends an **RTT-R in the same time slot**.
4. A successful exchange places the initiating terminal in **fine sync**.
5. The terminal periodically repeats RTT-I messages to maintain fine sync.

> **Memory aid:** RTT-I **interrogates**; RTT-R **replies**.

## Unit Definitions

### Basic Units

| Unit   | Definition                                               |
| ------ | -------------------------------------------------------- |
| **IU** | Participating unit.                                      |
| **PU** | Participating unit communicating on TDL A (**Link 11**). |
| **RU** | Reporting unit communicating on TDL B (**Link 11B**).    |
| **JU** | JTIDS unit communicating on TDL J (**Link 16**).         |

### Forwarding Units

| Unit      | Definition                                                                          |
| --------- | ----------------------------------------------------------------------------------- |
| **FPU**   | Forwarding PU that forwards data between TDL A and TDL B.                           |
| **FRU**   | Forward reporting unit that forwards data between two or more TDL B RUs.            |
| **FJUA**  | Forward JTIDS unit that translates and forwards data between TDL J and TDL A.       |
| **FJUB**  | Forward JTIDS unit that translates and forwards data between TDL J and TDL B.       |
| **FJUAB** | Forward JTIDS unit that translates and forwards data among TDL J, TDL A, and TDL B. |

### Special Unit Types

| Unit     | Definition                                                                                                                     |
| -------- | ------------------------------------------------------------------------------------------------------------------------------ |
| **CIU**  | Concurrent interface unit communicating on TDL A, TDL B, and TDL J without forwarding data.                                    |
| **SFJU** | Standby JTIDS unit that is active on TDL J and monitors the status of an FJU on TDL A and/or TDL B, but does not forward data. |

### Data Link Quick Reference

| Designator | Data Link |
| ---------- | --------- |
| **TDL A**  | Link 11   |
| **TDL B**  | Link 11B  |
| **TDL J**  | Link 16   |

> **Pattern:** The leading **F** identifies a forwarding unit. The letters **A**, **B**, and **J** identify the data links involved.

## Quick Recall

1. Which duty code identifies the Link 16 SECNC?
2. Which OPTASKLINK set identifies the JRE protocol being used?
3. What message format does OPTASKLINK use?
4. What is the difference between a set, a segment, and a field?
5. What do `/`, `//`, and `-` mean?
6. Which voice net is used to maintain a clear tactical picture?
7. Who is the NCS for the TSN?
8. Which voice net is used by the ICO to manage the entire TADIL interface?
9. What exchange moves a terminal from coarse sync to fine sync?
10. In which time slot must an RTT-R be transmitted?
11. Which data links correspond to TDL A, TDL B, and TDL J?
12. What is the difference between a CIU and an FJUAB?
13. What does an SFJU monitor, and does it forward data?
14. Who builds the OPTASKLINK for the theater of operations?
15. What key information does the JUDATA set provide?
16. What are the three Link 16 time units of measurement?

## Answer Key

1. **822**
2. **LNKPROT**
3. **USMTF**
4. A set begins with a set ID; a segment is a repeatable group of consecutive sets; a field is an individual data entry within a set.
5. `/` begins a field, `//` ends a set, and `-` indicates no data.
6. **Track Supervision Net (TSN)**
7. The **Track Data Coordinator (TDC)**
8. **Data Link Coordination Net (DCN)**
9. A successful **RTT-I/RTT-R exchange**
10. The **same time slot** in which the RTT-I was received
11. TDL A is **Link 11**, TDL B is **Link 11B**, and TDL J is **Link 16**.
12. A CIU communicates on TDL A, B, and J without forwarding; an FJUAB translates and forwards data among all three.
13. It monitors the status of an FJU on TDL A and/or TDL B, and it **does not forward data**.
14. The **JICO**, designated by the AADC.
15. **Unit designation, call sign, JU address, and Link 16 track block assignment**.
16. **Epoch, Frame, and Time Slot**.
