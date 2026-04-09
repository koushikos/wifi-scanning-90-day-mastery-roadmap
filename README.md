# wifi-scanning-90-day-mastery-roadmap
A complete beginner-to-advanced 90-day structured roadmap for mastering Wi-Fi scanning in networking and cyber security. Covers concepts, wireless protocols, scanning methods, tools, commands, labs, security use-cases, packet analysis, and practical exercises with daily learning tasks and milestones.

    
# Wi-Fi Scanning — Complete 90-Day Mastery Roadmap
   
> A Comprehensive Learning Guide for Cyber Security Students
 
![Wi-Fi Scanning](https://img.shields.io/badge/Wi--Fi-Scanning-90--Day%20Roadmap-blue?style=for-the-badge&logo=wifi)
![Cyber Security](https://img.shields.io/badge/Cyber-Security-Student-green?style=for-the-badge&logo=shield)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-red?style=for-the-badge&logo=graph)

---

## Table of Contents

1. [Introduction](#introduction)
2. [How to Use This Roadmap](#how-to-use-this-roadmap)
3. [Prerequisites](#prerequisites)
4. [Week-by-Week Overview](#week-by-week-overview)
5. [Daily Curriculum (Day 1-90)](#daily-curriculum-day-1-90)
6. [Capstone Project](#capstone-project)
7. [Tools & Resources](#tools--resources)
8. [Certification Path](#certification-path)
9. [Career Guidance](#career-guidance)

---

## Introduction

Wi-Fi scanning is a fundamental skill for any cyber security professional. Whether you're performing reconnaissance for a penetration test, conducting a wireless security audit, or implementing defensive monitoring capabilities, understanding how to discover, analyze, and assess wireless networks is essential.

This 90-day roadmap takes you from absolute beginner to advanced practitioner in wireless security. You'll learn the theoretical foundations, master industry-standard tools, complete hands-on labs, and develop the skills needed for real-world wireless security assessments.

### What You'll Achieve

By completing this roadmap, you will:

- ✅ Understand Wi-Fi fundamentals and how wireless networks operate
- ✅ Master both passive and active scanning techniques
- ✅ Proficiently use tools like airodump-ng, Kismet, and Wireshark
- ✅ Perform comprehensive wireless reconnaissance
- ✅ Detect rogue access points and evil twin attacks
- ✅ Conduct professional wireless security assessments
- ✅ Build automated scanning and monitoring solutions

---

## How to Use This Roadmap

### Structure

Each day follows a consistent format:

```
Day X: [Topic Name]

📚 Concepts to Learn:
- [Concept 1]
- [Concept 2]

💡 Detailed Explanation:
[Comprehensive content covering the topic]

🔧 Commands/Tools to Practice:
```
bash
# Command examples
```

🧪 Mini Lab/Exercise:
[Step-by-step exercise instructions]

🎯 Expected Outcome:
[What you should be able to do after completing]
```

### Learning Tips

1. **Hands-On First**: Always practice the commands before reading deeper theory
2. **Take Notes**: Document your findings in a lab journal
3. **Build Labs**: Create your own test environment using old hardware
4. **Repeat Exercises**: Do each lab multiple times until muscle memory forms
5. **Teach Others**: Explain concepts to reinforce your understanding

---

## Prerequisites

### Hardware Requirements

| Item | Minimum | Recommended |
|------|---------|-------------|
| Laptop/PC | 4GB RAM, 50GB HDD | 8GB+ RAM, SSD |
| Wi-Fi Adapter | External USB required | Alfa AWUS036ACH or similar |
| Access Point | 1 for basics | 2-3 for advanced labs |
| Mobile Device | Android phone | Dedicated scanning device |

### Software Requirements

- **Primary OS**: Kali Linux (recommended) or Ubuntu
- **Virtual Machine**: VirtualBox or VMware
- **Tools**: Pre-installed in Kali Linux
- **Additional**: Wireshark, Python 3, Git

### Knowledge Prerequisites

- Basic understanding of networking (TCP/IP)
- Familiarity with Linux command line
- Fundamental security concepts

---

## Week-by-Week Overview

| Week | Theme | Key Topics |
|------|-------|------------|
| Week 1-2 | Foundations | Wi-Fi basics, standards, terminology |
| Week 3-4 | Technical Deep Dive | 802.11 frames, packet structures |
| Week 5-6 | Tools - Linux | airodump-ng, iw, Kismet |
| Week 7-8 | Tools - Windows & Apps | netsh, NetSpot, WiFi Analyzer |
| Week 9-10 | Practical Labs | Capture, analysis, mapping |
| Week 11-12 | Security Applications | Auditing, detection, reporting |
| Week 13 | Capstone Project | Comprehensive assessment |

---

## Daily Curriculum (Day 1-90)

---

# PHASE 1: FOUNDATIONS (Days 1-14)

---

## Day 1: Introduction to Wi-Fi Scanning

### Concepts to Learn

- What is Wi-Fi scanning
- Why it matters in cyber security
- The role of wireless reconnaissance
- Legal and ethical boundaries

### Detailed Explanation

Wi-Fi scanning is the process of discovering and gathering information about wireless networks in range. This includes identifying network names (SSIDs), detecting access points (APs), measuring signal strength, and analyzing network configurations.

**Why Wi-Fi Scanning Matters in Cyber Security:**

1. **Reconnaissance Phase**: Wireless scanning is often the first step in penetration testing, providing critical information about the target environment
2. **Vulnerability Assessment**: Identifying misconfigured or insecure wireless networks
3. **Compliance Auditing**: Ensuring wireless networks meet security standards (PCI-DSS, HIPAA, etc.)
4. **Incident Response**: Detecting unauthorized access points
5. **Defensive Monitoring**: Continuous monitoring for threats

**Legal Considerations:**

⚠️ **IMPORTANT**: Wireless scanning raises significant legal issues:

- **Unauthorized Access**: Scanning networks without permission may violate computer crime laws
- **Interception**: Capturing wireless traffic may violate wiretap regulations
- **Local Laws**: Regulations vary by jurisdiction (e.g., FCC in US, Ofcom in UK)
- **Scope of Testing**: Always have written authorization

**Rule of Thumb**: Only scan networks you own or have explicit written permission to test.

### Commands/Tools to Practice

```
bash
# First, check your wireless interface
ip link show
iw dev
ip addr show wlan0

# Check if wireless is enabled
rfkill list all
rfkill unblock wifi
```

### Mini Lab/Exercise

1. Boot into Kali Linux or your preferred security distribution
2. Identify your wireless interface name (usually wlan0, wlp2s0, or similar)
3. Verify the interface is detected by the system
4. Document your interface name and capabilities

### Expected Outcome

- Understanding of what Wi-Fi scanning is and its importance
- Knowledge of legal/ethical boundaries
- Ability to identify wireless interfaces in Linux

---

## Day 2: How Wi-Fi Works - The Basics

### Concepts to Learn

- Radio frequency (RF) fundamentals
- Wi-Fi frequency bands (2.4 GHz vs 5 GHz)
- Basic transmission principles
- Infrastructure vs ad-hoc modes

### Detailed Explanation

Wi-Fi uses radio waves to transmit data between devices. Understanding the physical layer is crucial for effective scanning and analysis.

**Radio Frequency Fundamentals:**

Radio waves are electromagnetic waves that oscillate at specific frequencies. Wi-Fi operates in two main frequency bands:

```
┌─────────────────────────────────────────────────────────────┐
│                    Wi-Fi FREQUENCY BANDS                    │
├─────────────────┬───────────────────┬───────────────────────┤
│     Band       │    Frequency      │    Characteristics    │
├─────────────────┼───────────────────┼───────────────────────┤
│     2.4 GHz    │  2.4 - 2.4835 GHz │  Longer range, more  │
│                │                   │  interference, older │
│                │                   │  devices              │
├─────────────────┼───────────────────┼───────────────────────┤
│     5 GHz      │  5.15 - 5.875 GHz │  Shorter range, less │
│                │                   │  interference, faster│
│                │                   │  speeds               │
├─────────────────┼───────────────────┼───────────────────────┤
│    6 GHz       │  5.925 - 7.125 GHz│  Newest band, least  │
│    (Wi-Fi 6E)  │                   │  congestion           │
└─────────────────┴───────────────────┴───────────────────────┘
```

**Transmission Principles:**

1. **Modulation**: Data is encoded onto radio waves using various modulation schemes (BPSK, QPSK, OFDM, etc.)
2. **Channels**: The frequency band is divided into channels to allow multiple networks
3. **CSMA/CA**: Carrier Sense Multiple Access with Collision Avoidance - how devices share the medium

**Network Modes:**

- **Infrastructure Mode**: Networks use an Access Point (AP) as a central hub
- **Ad-hoc Mode**: Devices communicate directly without an AP
- **Mesh Mode**: Devices form a peer-to-peer network

### Commands/Tools to Practice

```
bash
# List wireless capabilities
iw list | grep -A 10 "Supported interface modes"

# Check supported bands
iw list | grep -A 5 "Frequencies"

# View current interface info
iw dev wlan0 info
```

### Mini Lab/Exercise

1. Use `iw list` to see your adapter's capabilities
2. Identify which bands (2.4 GHz, 5 GHz, 6 GHz) your adapter supports
3. Note the supported channel widths (20 MHz, 40 MHz, 80 MHz, 160 MHz)

### Expected Outcome

- Understanding of RF fundamentals
- Knowledge of Wi-Fi frequency bands
- Awareness of infrastructure vs ad-hoc modes

---

## Day 3: Wireless Standards (802.11 Family)

### Concepts to Learn

- Evolution of Wi-Fi standards
- 802.11a, b, g, n, ac, ax differences
- Wi-Fi generations (Wi-Fi 4, 5, 6)
- Throughput and range characteristics

### Detailed Explanation

The IEEE 802.11 standard defines Wi-Fi protocols. Understanding these standards helps you know what to expect from different networks.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                     802.11 STANDARDS COMPARISON                         │
├──────────┬─────────┬────────────┬────────────┬──────────────────────────┤
│ Standard │ Year    │ Band       │ Max Speed  │ Key Features             │
├──────────┼─────────┼────────────┼────────────┼──────────────────────────┤
│ 802.11a  │ 1999    │ 5 GHz      │ 54 Mbps    │ First 5 GHz standard      │
│ 802.11b  │ 1999    │ 2.4 GHz    │ 11 Mbps    │ Long range, DSSS          │
│ 802.11g  │ 2003    │ 2.4 GHz    │ 54 Mbps    │ Backward compatible       │
│ 802.11n  │ 2009    │ 2.4/5 GHz  │ 600 Mbps   │ MIMO, 40 MHz channels     │
│ 802.11ac │ 2013    │ 5 GHz      │ 3.4 Gbps   │ MU-MIMO, 160 MHz         │
│ 802.11ax │ 2021    │ 2.4/5/6GHz │ 9.6 Gbps   │ OFDMA, BSS Coloring      │
└──────────┴─────────┴────────────┴────────────┴──────────────────────────┘
```

**Wi-Fi Generation Naming:**

| Generation | IEEE Standard | Common Name |
|------------|---------------|-------------|
| Wi-Fi 4   | 802.11n       | -            |
| Wi-Fi 5   | 802.11ac      | -            |
| Wi-Fi 6   | 802.11ax      | -            |
| Wi-Fi 6E  | 802.11ax      | Extended 6 GHz |

**Key Technologies:**

- **MIMO**: Multiple Input Multiple Output - uses multiple antennas
- **MU-MIMO**: Multi-User MIMO - serves multiple clients simultaneously
- **OFDMA**: Orthogonal Frequency Division Multiple Access - divides channels
- **BSS Coloring**: Reduces interference in dense environments

### Commands/Tools to Practice

```
bash
# Check interface capabilities for each standard
iw list | grep -E "(HT|VHT|HE)"

# HT = 802.11n (High Throughput)
# VHT = 802.11ac (Very High Throughput)
# HE = 802.11ax (High Efficiency)
```

### Mini Lab/Exercise

1. Review your wireless adapter's supported standards
2. Create a table of what standards your adapter can connect to
3. Research what standards are common in your environment

### Expected Outcome

- Knowledge of Wi-Fi standard evolution
- Understanding of throughput capabilities
- Awareness of which standards your hardware supports

---

## Day 4: Core Terminology - SSID, BSSID, RSSI

### Concepts to Learn

- SSID (Service Set Identifier)
- BSSID (Basic Service Set Identifier)
- RSSI (Received Signal Strength Indicator)
- MAC addresses in wireless

### Detailed Explanation

These are the fundamental identifiers you'll encounter when scanning wireless networks.

**SSID (Service Set Identifier):**

The SSID is the network name that users see when connecting to Wi-Fi. It can be 1-32 characters long and is broadcast by access points in beacon frames.

```
┌────────────────────────────────────────┐
│         SSID Examples                  │
├────────────────────────────────────────┤
│ HomeNetwork                            │
│ Starbucks_WiFi                        │
│ Corporate_Secure                      │
│ MyWiFi                                │
└────────────────────────────────────────┘
```

**BSSID (Basic Service Set Identifier):**

The BSSID is the unique identifier of an access point - essentially its MAC address. Every AP has a BSSID, and in enterprise environments, multiple APs may share an SSID.

```
BSSID Format: XX:XX:XX:XX:XX:XX

Example:    00:11:22:33:44:55
            │││││││││││││
            └┴┴┴┴┴┴┴┴┴┴┴┴─ Vendor OUI (first 3 octets)
```

**RSSI (Received Signal Strength Indicator):**

RSSI measures the signal power received by your adapter. Higher values (closer to 0) mean stronger signals.

```
RSSI Scale:
┌─────────────────────────────────────────────────────────────┐
│  -30 dBm  │ Excellent │ Full signal, very close to AP      │
├───────────┼───────────┼────────────────────────────────────┤
│  -50 dBm  │ Very Good │ Strong signal, good connection     │
├───────────┼───────────┼────────────────────────────────────┤
│  -60 dBm  │ Good      │ Reliable connection                 │
├───────────┼───────────┼────────────────────────────────────┤
│  -70 dBm  │ Fair      │ Intermittent issues possible        │
├───────────┼───────────┼────────────────────────────────────┤
│  -80 dBm  │ Poor      │ Frequent disconnections            │
├───────────┼───────────┼────────────────────────────────────┤
│  -90 dBm  │ Very Poor │ Barely usable                       │
└─────────────────────────────────────────────────────────────┘
```

**Signal to Noise Ratio (SNR):**

SNR = Signal Strength - Noise Floor

| SNR Value | Quality |
|-----------|---------|
| > 40 dB   | Excellent |
| 25-40 dB  | Good |
| 15-25 dB  | Fair |
| < 15 dB   | Poor |

### Commands/Tools to Practice

```
bash
# Check current connection status (Linux)
iw dev wlan0 link

# Check signal quality (Windows)
netsh wlan show interfaces

# Use iwconfig (older but useful)
iwconfig wlan0
```

### Mini Lab/Exercise

1. Connect to a Wi-Fi network
2. Use `iw dev wlan0 link` to see your current connection details
3. Note the SSID, BSSID, and signal strength
4. Move around and observe how RSSI changes

### Expected Outcome

- Understanding of SSID, BSSID, and RSSI
- Ability to interpret signal strength values
- Knowledge of MAC address structure in wireless

---

## Day 5: Channels and Frequency Bands

### Concepts to Learn

- Wi-Fi channel numbering
- Channel overlap and congestion
- 2.4 GHz channel layout
- 5 GHz channel layout
- DFS channels
- Channel selection strategies

### Detailed Explanation

Wi-Fi channels divide the frequency spectrum into manageable segments. Understanding channel layout is crucial for both scanning and troubleshooting.

**2.4 GHz Channel Layout:**

The 2.4 GHz band has 14 channels (varies by region), but only 3 are non-overlapping:

```
Channel:  1     2     3     4     5     6     7     8     9    10    11    12    13    14
          │     │     │     │     │     │     │     │     │     │     │     │     │     │
          ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼
       ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐
       │ 1   │ │ 2   │ │ 3   │ │ 4   │ │ 5   │ │ 6   │ │ 7   │ │ 8   │ │ 9   │ │ 10  │ │ 11  │
       └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘ └─────┘
       └─────────┘         └─────────┘         └─────────┘         └─────────┘
          22 MHz             22 MHz             22 MHz             22 MHz

Non-overlapping channels: 1, 6, 11 (in US/Canada)
```

**5 GHz Channel Layout:**

The 5 GHz band has many more non-overlapping channels:

```
┌────────────────────────────────────────────────────────────────────────────────┐
│                           5 GHz CHANNEL LAYOUT                                 │
├──────────────────┬───────────────────────┬─────────────────────────────────────┤
│ UNII Band        │ Channels             │ Characteristics                     │
├──────────────────┼───────────────────────┼─────────────────────────────────────┤
│ UNII-1 (Low)     │ 36, 40, 44, 48        │ Indoor only, no DFS required        │
│ UNII-2 (Middle)  │ 52, 56, 60, 64        │ DFS required, weather radar         │
│ UNII-2 Extended  │ 100, 104, 108...144   │ DFS required, more channels         │
│ UNII-3 (High)    │ 149, 153, 157, 161   │ Higher power, indoor/outdoor        │
│ UNII-4 (New)     │ 165, 169, 173        │ 6 GHz compatible                    │
└──────────────────┴───────────────────────┴─────────────────────────────────────┘
```

**Channel Width Impact:**

| Channel Width | Spectrum Used | Throughput | Interference Risk |
|---------------|---------------|------------|-------------------|
| 20 MHz        | 20 MHz        | Baseline   | Low               |
| 40 MHz        | 40 MHz        | ~2x        | Medium            |
| 80 MHz        | 80 MHz        | ~4x        | High              |
| 160 MHz       | 160 MHz       | ~8x        | Very High         |

### Commands/Tools to Practice

```
bash
# List available frequencies (Linux)
iw list | grep -E "(frequencies|MHz)"

# Scan for networks and see channel usage
sudo iw dev wlan0 scan | grep -E "(SSID|channel|signal|freq)"

# Use iwlist to get detailed channel info
sudo iwlist wlan0 scanning

# Check current channel (Linux)
iw dev wlan0 info | grep channel
```

### Mini Lab/Exercise

1. Perform a Wi-Fi scan using `sudo iw dev wlan0 scan`
2. Create a chart showing all networks found, their channels, and signal strength
3. Identify channel congestion in your area
4. Determine if there are overlapping channels causing interference

### Expected Outcome

- Understanding of channel numbering
- Knowledge of non-overlapping channels
- Ability to identify channel congestion

---

## Day 6: Beacon Frames and Probe Frames

### Concepts to Learn

- Beacon frames
- Probe request frames
- Probe response frames
- How networks advertise themselves
- Hidden SSIDs

### Detailed Explanation

Wireless networks communicate their existence through management frames, primarily beacon frames and probe frames.

**Beacon Frames:**

Beacon frames are broadcast by access points periodically (typically every 100ms). They contain critical information about the network.

```
┌─────────────────────────────────────────────────────────────────┐
│                    BEACON FRAME CONTENTS                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────┐                                           │
│  │ Timestamp       │ Current AP time (for sync)              │
│  ├─────────────────┤                                           │
│  │ Beacon Interval │ Time between beacons (default: 100ms)    │
│  ├─────────────────┤                                           │
│  │ Capability Info │ ESS/IBSS, Privacy, Spectrum Mgmt, etc.   │
│  ├─────────────────┤                                           │
│  │ SSID            │ Network name (can be hidden)             │
│  ├─────────────────┤                                           │
│  │ Supported Rates │ Data rates the AP supports               │
│  ├─────────────────┤                                           │
│  │ DS Parameter    │ Channel number                           │
│  ├─────────────────┤                                           │
│  │ Traffic Ind Map │ Information for power saving clients     │
│  ├─────────────────┤                                           │
│  │ Vendor Specific │ Manufacturer information                 │
│  └─────────────────┘                                           │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Probe Frames:**

Probe frames are used by clients and APs to discover each other:

- **Probe Request**: Sent by client seeking networks
- **Probe Response**: Sent by AP in response to probe requests

```
┌─────────────────────────────────────────┐
│      PROBE REQUEST (Client → Network)   │
├─────────────────────────────────────────┤
│ SSID: "MyNetwork" (or broadcast for all)│
│ Supported Rates                         │
│ Requested Capabilities                  │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│      PROBE RESPONSE (AP → Client)        │
├─────────────────────────────────────────┤
│ SSID: "MyNetwork"                       │
│ BSSID: [AP MAC Address]                  │
│ Capability Information                   │
│ Supported Rates                          │
│ Channel                                  │
│ RSN Information (security)              │
└─────────────────────────────────────────┘
```

**Hidden SSID Discovery:**

When SSID broadcast is disabled, the network doesn't appear in beacon frames. However, it can still be discovered through:

1. **Probe Response capture**: When a client connects, it sends probe requests with the SSID
2. **Association requests**: During connection, the SSID is transmitted
3. **Deauthentication capture**: Forcing clients to reconnect reveals SSIDs

### Commands/Tools to Practice

```
bash
# Capture beacon frames with airodump-ng
sudo airodump-ng wlan0mon --manufacturer

# Capture specific probe requests
sudo airodump-ng wlan0mon --uptime

# Use Wireshark to filter beacons
# Display filter: wlan.fc.type == 0 && wlan.fc.subtype == 8

# Filter probe requests
# Display filter: wlan.fc.type == 0 && wlan.fc.subtype == 4
```

### Mini Lab/Exercise

1. Start airodump-ng in monitor mode
2. Observe beacon frames being received
3. Identify the SSID, BSSID, and channel from beacon information
4. Look for probe requests from clients
5. Try to identify any hidden networks

### Expected Outcome

- Understanding of beacon frame structure
- Knowledge of probe request/response mechanics
- Ability to discover hidden SSIDs through frame analysis

---

## Day 7: Skill Checkpoint - Week 1 Review

### Concepts to Learn

- Review all Week 1 concepts
- Practical assessment
- Gap identification

### Weekly Milestones

✅ **Week 1 Completed:**

- [ ] Understanding of Wi-Fi fundamentals
- [ ] Knowledge of 802.11 standards
- [ ] Familiarity with SSID, BSSID, RSSI
- [ ] Understanding of channels and frequencies
- [ ] Knowledge of beacon and probe frames

### Practical Exercise

**Comprehensive Review Exercise:**

1. List all wireless networks in your area
2. For each network, document:
   - SSID (or indicate if hidden)
   - BSSID
   - Channel
   - Frequency band
   - Signal strength (RSSI)
   - Security type
   - Vendor (from MAC OUI)
3. Identify the 2.4 GHz vs 5 GHz distribution
4. Note any channel congestion issues

### Commands Review

```
bash
# Complete wireless scan checklist
ip link show                              # Check interfaces
iw dev                                    # List interface details
sudo iw dev wlan0 scan                    # Scan networks
sudo iwlist wlan0 scanning                # Alternative scan
sudo airodump-ng wlan0mon                  # Monitor mode scan
```

### Expected Outcome

- Confirmation of Week 1 learning
- Identification of any knowledge gaps
- Ready to proceed to Week 2

---

## Day 8: Active vs Passive Scanning

### Concepts to Learn

- Active scanning process
- Passive scanning process
- When to use each method
- Pros and cons of each approach

### Detailed Explanation

Wi-Fi scanning can be performed in two fundamentally different ways: active and passive scanning.

**Passive Scanning:**

Passive scanning listens for beacon frames broadcast by access points. The scanner doesn't transmit anything, making it stealthier.

```
┌────────────────────────────────────────────────────────────────┐
│                    PASSIVE SCANNING                            │
│                                                                │
│   ┌──────────┐         BEACON         ┌──────────┐          │
│   │   AP 1   │ ──────────────────────▶│  Scanner │          │
│   └──────────┘         (every 100ms)   └──────────┘          │
│                                                │              │
│   ┌──────────┐         BEACON                  │              │
│   │   AP 2   │ ────────────────────────────────┘              │
│   └──────────┘                                                │
│                                                                │
│   ┌──────────┐         BEACON                                 │
│   │   AP 3   │ ───────────────────────────────────────────    │
│   └──────────┘                                                │
│                                                                │
│   SCANNER ONLY LISTENS - DOES NOT TRANSMIT                    │
└────────────────────────────────────────────────────────────────┘
```

**Advantages of Passive Scanning:**
- More stealthy (doesn't reveal scanner)
- Can capture all beacon frames
- Better for capturing handshakes
- Less likely to be detected by IDS

**Disadvantages of Passive Scanning:**
- Won't discover hidden SSIDs
- Depends on AP beacon interval
- May miss networks with long beacon intervals

**Active Scanning:**

Active scanning sends probe requests and listens for probe responses. The scanner actively queries the environment.

```
┌────────────────────────────────────────────────────────────────┐
│                    ACTIVE SCANNING                             │
│                                                                │
│   ┌──────────┐  PROBE REQUEST   ┌──────────┐                  │
│   │  Scanner │ ─────────────────│   AP 1   │                  │
│   └──────────┘  (broadcast)     └──────────┘                  │
│         │                              │                       │
│         │    PROBE RESPONSE            │                       │
│         └──────────────────────────────┘                       │
│         │                                                      │
│         │  PROBE REQUEST                                       │
│         ├──────────────────────────────────┐                   │
│         │                                  │                   │
│         │    PROBE RESPONSE               │                   │
│         └──────────────────────────────────┘                   │
│                                                                │
│   SCANNER TRANSMITS AND LISTENS FOR RESPONSES                  │
└────────────────────────────────────────────────────────────────┘
```

**Advantages of Active Scanning:**
- Can discover hidden SSIDs
- Faster discovery of specific networks
- Can target specific channels
- Can identify non-beaconing APs

**Disadvantages of Active Scanning:**
- More detectable
- May miss some APs (if they don't respond)
- Can cause interference

### Commands/Tools to Practice

```
bash
# Passive scanning - just listen
sudo airodump-ng wlan0mon

# Active scanning - send probe requests
sudo iw dev wlan0 scan active

# Scan specific channel passively
sudo iw dev wlan0 scan freq=2437

# Use mdk3 for active scanning
sudo mdk3 wlan0mon p -m
```

### Mini Lab/Exercise

1. Perform passive scanning with airodump-ng for 2 minutes
2. Note all networks discovered
3. Perform active scanning with iw
4. Compare the results
5. Identify any networks found in one but not the other

### Expected Outcome

- Understanding of active vs passive scanning
- Knowledge of when to use each method
- Ability to choose appropriate scanning strategy

---

## Day 9: Monitor Mode Deep Dive

### Concepts to Learn

- What is monitor mode
- How it differs from managed mode
- Enabling monitor mode
- Monitor vs promiscuous mode
- Radiotap headers

### Detailed Explanation

Monitor mode is a special operation mode that allows a wireless adapter to capture all wireless traffic, regardless of which network the adapter is connected to.

**Wireless Interface Modes:**

```
┌─────────────────────────────────────────────────────────────────┐
│               WIRELESS INTERFACE MODES                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────────┐                                               │
│  │ Managed Mode │  Normal client mode                          │
│  │              │  - Connected to an AP                        │
│  │              │  - Only sees traffic to/from this client     │
│  │              │  - Filters out other traffic                 │
│  └──────────────┘                                               │
│                                                                 │
│  ┌──────────────┐                                               │
│  │ Monitor Mode│  Capture mode                                 │
│  │              │  - Not associated with any AP               │
│  │              │  - Sees ALL frames in range                  │
│  │              │  - Includes 802.11 headers                   │
│  │              │  - Perfect for packet capture                │
│  └──────────────┘                                               │
│                                                                 │
│  ┌──────────────┐                                               │
│  │ Ad-hoc Mode │  Peer-to-peer mode                            │
│  │              │  - Direct client-to-client                   │
│  └──────────────┘                                               │
│                                                                 │
│  ┌──────────────┐                                               │
│  │ Master Mode │  Act as access point                          │
│  │  (AP Mode)  │  - Creates an access point                    │
│  └──────────────┘                                               │
│                                                                 │
│  ┌──────────────┐                                               │
│  │  Mesh Mode  │  Mesh networking                              │
│  └──────────────┘                                               │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Radiotap Headers:**

When in monitor mode, frames include additional metadata called radiotap headers. These contain valuable information about the captured frame:

```
┌─────────────────────────────────────────────────────────────────┐
│                     RADIOTAP HEADER                             │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │ Version     │ Padding  │  Length                        │   │
│  ├─────────────────────────────────────────────────────────┤   │
│  │ Present Flags                                               │   │
│  ├─────────────────────────────────────────────────────────┤   │
│  │ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐        │   │
│  │ │Timestamp │ │RSSI    │ │Antenna │ │Rate     │  ...   │   │
│  │ └─────────┘ └─────────┘ └─────────┘ └─────────┘        │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │              802.11 Frame Data                           │   │
│  │  ┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐   │   │
│  │  │FC        │ │Duration  │ │Address 1 │ │Address 2 │   │   │
│  │  └──────────┘ └──────────┘ └──────────┘ └──────────┘   │   │
│  │  ┌──────────┐ ┌──────────┐ ┌────────────────────────┐  │   │
│  │  │Address 3 │ │Seq Control│ │   Data / Management    │  │   │
│  │  └──────────┘ └──────────┘ └────────────────────────┘  │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Commands/Tools to Practice

```
bash
# Method 1: Using iw
sudo ip link set wlan0 down
sudo iw wlan0 set monitor control
sudo ip link set wlan0 up

# Method 2: Using airmon-ng (creates new interface)
sudo airmon-ng start wlan0

# Check if monitor mode is active
iw dev | grep -A 5 "monitor"

# Verify with ip link
ip link show wlan0mon

# Return to managed mode
sudo airmon-ng stop wlan0mon
sudo ip link set wlan0 up

# Check supported monitor modes
iw list | grep -A 10 "monitor"
```

### Mini Lab/Exercise

1. Put your wireless adapter into monitor mode using airmon-ng
2. Verify monitor mode is active
3. Use airodump-ng to scan for networks
4. Capture a few packets and examine the radiotap header in Wireshark
5. Return to managed mode

### Expected Outcome

- Understanding of monitor mode
- Ability to enable/disable monitor mode
- Knowledge of radiotap headers

---

## Day 10: Setting Up Your Lab Environment

### Concepts to Learn

- Lab architecture
- Virtual machine setup
- Hardware requirements
- Network isolation

### Detailed Explanation

Building a proper lab environment is essential for safe, legal practice of Wi-Fi scanning skills.

**Recommended Lab Architecture:**

```
┌─────────────────────────────────────────────────────────────────┐
│                      LAB ENVIRONMENT                            │
│                                                                 │
│  ┌─────────────────┐                                           │
│  │   Host System   │  Your main computer                        │
│  │   (Windows/Mac) │                                           │
│  └────────┬────────┘                                           │
│           │                                                     │
│           │ Virtual Machine Network (Host-Only or NAT)          │
│           │                                                     │
│  ┌────────▼────────┐                                           │
│  │   Kali Linux   │  Primary security testing platform         │
│  │  VM (4GB RAM)  │  - airodump-ng, Kismet, Wireshark          │
│  └────────┬────────┘                                           │
│           │                                                     │
│           │ USB Passthrough                                     │
│           │                                                     │
│  ┌────────▼────────┐                                           │
│  │ External Wi-Fi  │  Alfa AWUS036ACH (recommended)            │
│  │    Adapter      │  - 2.4/5 GHz support                      │
│  │                 │  - Monitor mode capable                   │
│  └────────┬────────┘                                           │
│           │                                                     │
│           │ Wireless Signal                                     │
│           │                                                     │
│  ┌────────▼────────┐                                           │
│  │  Test Access    │  Your own access point for practice       │
│  │    Point(s)     │  - Configure different security types     │
│  └─────────────────┘  - Change channels and bands              │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Hardware Setup Checklist:**

| Item | Purpose | Notes |
|------|---------|-------|
| Laptop/Desktop | Primary system | Minimum 8GB RAM recommended |
| VM Software | Run Kali Linux | VirtualBox is free |
| Wi-Fi Adapter | Wireless capture | Must support monitor mode |
| Access Point | Test target | Own AP only |
| Ethernet Cable | Initial setup | For Kali installation |
| Phone/Tablet | Client testing | For association tests |

**VM Configuration:**

```
VirtualBox Settings:
- RAM: 4096 MB minimum
- CPU: 2 cores
- Storage: 50 GB
- Network: NAT (for updates), Host-Only (for USB)
- USB: Enable USB 2.0/3.0 controller
```

### Commands/Tools to Practice

```
bash
# Verify USB passthrough in VirtualBox
# Settings > USB > Enable USB Controller > Add Filter

# Check adapter in Kali Linux
lsusb
lsusb | grep -i wireless

# Verify adapter is detected
ip link show

# Test basic connectivity
ping -c 4 8.8.8.8
```

### Mini Lab/Exercise

1. Install VirtualBox on your host system
2. Download and set up Kali Linux VM
3. Configure USB passthrough for your Wi-Fi adapter
4. Verify the adapter is detected in Kali Linux
5. Test basic network connectivity

### Expected Outcome

- Functional lab environment
- Wi-Fi adapter working in Kali Linux
- Ready for hands-on practice

---

## Day 11: Introduction to 802.11 Frame Types

### Concepts to Learn

- 802.11 frame format
- Frame types (Management, Control, Data)
- Frame subtypes
- MAC addresses in 802.11

### Detailed Explanation

Understanding 802.11 frame types is crucial for advanced wireless analysis and security testing.

**802.11 Frame Structure:**

```
┌─────────────────────────────────────────────────────────────────┐
│                  802.11 MAC FRAME FORMAT                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┐     │
│  │ Frame    │ Duration │  Address │  Address │  Address │     │
│  │ Control  │   ID     │    1     │    2     │    3     │     │
│  │  (2 B)   │  (2 B)   │  (6 B)   │  (6 B)   │  (6 B)   │     │
│  ├──────────┼──────────┼──────────┼──────────┼──────────┤     │
│  │ Sequence │  Address │   QoS    │   HT     │  Frame   │     │
│  │ Control  │    4     │ Control  │ Control  │  Body    │     │
│  │  (2 B)   │  (6 B)   │  (2 B)   │  (4 B)   │ (0-2312) │     │
│  └──────────┴──────────┴──────────┴──────────┴──────────┘     │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Frame Control Field:**

```
┌─────────────────────────────────────────────────────────────────┐
│                  FRAME CONTROL FIELD                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌────────┬────────┬────────┬────────┬────────┬────────┐      │
│  │Protocol│ Type   │ Subtype│  To    │ From   │  More  │      │
│  │Version │        │        │   DS   │   DS   │Fragments│     │
│  │(2 bits)│(2 bits)│(4 bits)│(1 bit) │(1 bit) │(1 bit) │      │
│  ├────────┴────────┴────────┴────────┴────────┴────────┤      │
│  │             Retry (1 bit)                           │      │
│  ├─────────────────────────────────────────────────────┤      │
│  │           Power Management (1 bit)                  │      │
│  ├─────────────────────────────────────────────────────┤      │
│  │           More Data (1 bit)                         │      │
│  ├─────────────────────────────────────────────────────┤      │
│  │           WEP (1 bit)                               │      │
│  ├─────────────────────────────────────────────────────┤      │
│  │           Order (1 bit)                             │      │
│  └─────────────────────────────────────────────────────┘      │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Three Main Frame Types:**

| Type Value | Type Name   | Description |
|------------|-------------|-------------|
| 0          | Management  | Network discovery, association, authentication |
| 1          | Control     | Handshake, ACK, RTS/CTS |
| 2          | Data        | Actual data transmission |

**Management Frames (Type 0):**

| Subtype | Name | Purpose |
|---------|------|---------|
| 0 | Association Request | Client requests to join AP |
| 1 | Association Response | AP accepts/rejects client |
| 2 | Reassociation Request | Client roams to new AP |
| 3 | Reassociation Response | Response to roaming |
| 4 | Probe Request | Client searches for networks |
| 5 | Probe Response | AP responds to probe |
| 8 | Beacon | AP announces network |
| 9 | ATIM | Announcement traffic |
| 10 | Disassociation | End association |
| 11 | Authentication | Security handshake |
| 12 | Deauthentication | Leave network |

**Control Frames (Type 1):**

| Subtype | Name | Purpose |
|---------|------|---------|
| 7 | CF-End | Contention-free period end |
| 8 | CF-End + CF-ACK | End + acknowledgment |
| 9 | ACK | Frame acknowledgment |
| 10 | CTS | Clear to send |
| 11 | RTS | Request to send |

**Data Frames (Type 2):**

| Subtype | Name | Purpose |
|---------|------|---------|
| 0 | Data | Standard data frame |
| 1 | Data + CF-ACK | Data with acknowledgment |
| 2 | Data + CF-Poll | Data with poll |
| 3 | Data + CF-ACK + CF-Poll | Combined frame |
| 4 | Null (no data) | Power save poll |
| 5 | CF-ACK (no data) | Control frame |
| 6 | CF-Poll (no data) | Control frame |
| 7 | CF-ACK + CF-Poll | Control frame |

### Commands/Tools to Practice

```
bash
# Filter for management frames in airodump-ng
sudo airodump-ng wlan0mon

# In Wireshark, filter by frame type:
# Management frames: wlan.fc.type == 0
# Control frames: wlan.fc.type == 1
# Data frames: wlan.fc.type == 2

# Filter specific management frames:
# Beacons: wlan.fc.type == 0 && wlan.fc.subtype == 8
# Probe requests: wlan.fc.type == 0 && wlan.fc.subtype == 4
# Probe responses: wlan.fc.type == 0 && wlan.fc.subtype == 5
# Authentication: wlan.fc.type == 0 && wlan.fc.subtype == 11
# Association: wlan.fc.type == 0 && wlan.fc.subtype == 0
```

### Mini Lab/Exercise

1. Start a Wireshark capture in monitor mode
2. Filter for different frame types using the filters above
3. Identify each frame type you see in the capture
4. Create a capture of association process and label each frame type

### Expected Outcome

- Understanding of 802.11 frame structure
- Knowledge of frame type and subtype values
- Ability to filter specific frame types in Wireshark

---

## Day 12: Management Frames Deep Dive

### Concepts to Learn

- Authentication frames
- Association frames
- Reassociation frames
- Disassociation frames
- Deauthentication frames
- The complete connection process

### Detailed Explanation

Management frames control the association process between clients and access points. Understanding these frames is essential for wireless security assessments.

**The Complete Wi-Fi Connection Process:**

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    WIFI CONNECTION PROCESS                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│   CLIENT                              ACCESS POINT                          │
│     │                                     │                                 │
│     │───── Probe Request (broadcast) ────▶│                                 │
│     │◀──── Probe Response ───────────────│                                 │
│     │                                     │                                 │
│     │───── Authentication Request ───────▶│                                 │
│     │◀──── Authentication Response ──────│                                 │
│     │                                     │                                 │
│     │───── Association Request ─────────▶│                                 │
│     │◀──── Association Response ─────────│                                 │
│     │                                     │                                 │
│     │        DATA COMMUNICATION           │                                 │
│     │◀──────────────────────────────────▶│                                 │
│     │                                     │                                 │
│     │───── Deauthentication ─────────────▶│ (When disconnecting)            │
│     │                                     │                                 │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Authentication Frame:**

The authentication frame is the first step in the security handshake. There are multiple authentication algorithms:

| Algorithm | Description | Security Level |
|-----------|-------------|----------------|
| 0 | Open System | None (open network) |
| 1 | Shared Key | Basic (uses WEP) |
| 802.1X | Port-based | Enterprise grade |

**Association Frame:**

After authentication, the client sends an association request containing:
- SSID name
- Supported data rates
- Capability information (ESS, short preamble, etc.)
- RSN (Robust Security Network) information for WPA/WPA2/WPA3

**Deauthentication vs Disassociation:**

- **Deauthentication**: Complete logout from the AP, terminates the security association
- **Disassociation**: Temporarily disconnects without removing security credentials

Both can be sent by either the client or the AP, and both can be used in wireless attacks.

### Commands/Tools to Practice

```
bash
# Filter authentication frames in Wireshark
wlan.fc.type == 0 && wlan.fc.subtype == 11

# Filter association frames
wlan.fc.type == 0 && wlan.fc.subtype == 0

# Filter deauthentication frames
wlan.fc.type == 0 && wlan.fc.subtype == 12

# Capture association process
sudo tcpdump -i wlan0mon -w association_capture.pcap &
# Then connect to a network

# Analyze with airodump-ng
sudo airodump-ng wlan0mon -w output
```

### Mini Lab/Exercise

1. Start Wireshark in monitor mode
2. Connect to a Wi-Fi network with a client device
3. Capture the entire connection process
4. Label each frame type in the capture
5. Identify the authentication algorithm used

### Expected Outcome

- Understanding of management frame flow
- Knowledge of connection process steps
- Ability to analyze authentication types

---

## Day 13: Control Frames and Data Frames

### Concepts to Learn

- ACK frames
- RTS/CTS frames
- CF-Poll frames
- Data frame structure
- QoS control
- Fragmentation

### Detailed Explanation

Control frames assist in delivering data frames, while data frames carry the actual payload.

**Control Frames Explained:**

**ACK (Acknowledgment) Frame:**
- Sent to confirm successful frame reception
- Required for reliable transmission
- If ACK not received, frame is retransmitted

```
┌─────────────────────────────────────────────┐
│        ACK FRAME FLOW                        │
├─────────────────────────────────────────────┤
│                                             │
│  Sender          Receiver                    │
│    │                │                        │
│    │───── Data ────▶│                        │
│    │                │                        │
│    │◀───── ACK ────│                        │
│    │                │                        │
└─────────────────────────────────────────────┘
```

**RTS/CTS (Request/Clear to Send):**

Used for collision avoidance in congested environments or when hiding stations:

- **RTS**: Sender requests to transmit
- **CTS**: AP grants permission
- Prevents hidden node problem

**Data Frames:**

Data frames carry the actual network traffic. They can be encrypted and can include QoS information.

| QoS Priority | Traffic Type |
|--------------|--------------|
| 0 | Best Effort |
| 1 | Background |
| 2 | Reserved |
| 3 | Excellent Effort |
| 4 | Voice |
| 5 | Video |
| 6 | Network Control |
| 7 | Highest |

### Commands/Tools to Practice

```
bash
# Filter ACK frames
wlan.fc.type == 1 && wlan.fc.subtype == 13

# Filter RTS frames
wlan.fc.type == 1 && wlan.fc.subtype == 11

# Filter CTS frames  
wlan.fc.type == 1 && wlan.fc.subtype == 12

# Filter data frames
wlan.fc.type == 2

# Filter QoS data frames
wlan.fc.type == 2 && wlan.qos
```

### Mini Lab/Exercise

1. Capture wireless traffic during normal browsing
2. Identify ACK frames and their timing
3. Look for any RTS/CTS exchanges
4. Analyze QoS fields in data frames

### Expected Outcome

- Understanding of control frame purpose
- Knowledge of data frame structure
- Ability to identify QoS mechanisms

---

## Day 14: Skill Checkpoint - Week 2 Review

### Weekly Milestones

✅ **Week 2 Completed:**

- [ ] Understanding of 802.11 frame types
- [ ] Knowledge of management frames
- [ ] Familiarity with control frames
- [ ] Understanding of data frames
- [ ] Ability to analyze frame exchanges

### Practical Exercise

**Frame Analysis Exercise:**

1. Capture a complete client association
2. Document each frame in order
3. Identify the frame type and subtype
4. Explain what each frame accomplishes
5. Note any anomalies or unexpected frames

### Commands Review

```
bash
# Monitor mode scanning
sudo airodump-ng wlan0mon

# Wireshark frame filters
wlan.fc.type == 0  # Management
wlan.fc.type == 1  # Control  
wlan.fc.type == 2  # Data

# Save captures
sudo tcpdump -i wlan0mon -w capture.pcap
```

### Expected Outcome

- Confirmation of Week 2 learning
- Ready for Phase 2: Technical Deep Dive

---

# PHASE 2: TECHNICAL DEEP DIVE (Days 15-28)

---

## Day 15: Signal Measurement and Analysis

### Concepts to Learn

- RSSI deep dive
- Noise floor measurement
- Signal to Noise Ratio (SNR)
- Packet loss indicators
- Link quality metrics

### Detailed Explanation

Understanding signal measurement is crucial for both offensive and defensive wireless security.

**Signal Strength Metrics:**

**RSSI (Received Signal Strength Indicator):**
- Vendor-specific scale (usually -100 to 0 dBm)
- Higher (closer to 0) = stronger signal
- Not standardized across vendors

**dBm (Decibels relative to milliwatt):**
- Absolute power measurement
- -30 dBm = excellent
- -90 dBm = very poor
- Formula: dBm = 10 × log₁₀(mW)

**Noise Floor:**
- Background interference level
- Typically -90 to -100 dBm in clean environments
- Higher (less negative) = more interference

**SNR (Signal to Noise Ratio):**
- Signal Strength - Noise Floor
- Higher = better signal quality
- >40 dB = excellent
- <10 dB = unusable

```
┌─────────────────────────────────────────────────────────────────┐
│                    SIGNAL QUALITY SCALE                          │
├──────────────────┬─────────────┬─────────────────────────────────┤
│ SNR (dB)         │ Quality     │ User Experience                │
├──────────────────┼─────────────┼─────────────────────────────────┤
│ 40+              │ Excellent   │ Full speed, perfect connectivity│
│ 25-40            │ Good        │ Fast, reliable                  │
│ 15-25            │ Fair        │ Usable, occasional issues      │
│ 10-15            │ Poor        │ Slow, frequent disconnects     │
│ <10              │ Unusable   │ Barely connects                 │
└──────────────────┴─────────────┴─────────────────────────────────┘
```

**Measuring Signal:**

You can measure signal in various ways:

1. **From client perspective**: `iw dev wlan0 link`
2. **From scanner perspective**: airodump-ng RSSI column
3. **Via Wireshark**: Radiotap header RSSI field

### Commands/Tools to Practice

```
bash
# Check signal in Linux
iw dev wlan0 link
# Output shows: signal: -XX dBm

# Check with iwconfig
iwconfig wlan0

# Detailed signal info
iw dev wlan0 survey dump

# With airodump-ng (shows RSSI)
sudo airodump-ng wlan0mon

# In Wireshark, check radiotap
# The radiotap header contains signal strength
```

### Mini Lab/Exercise

1. Connect to a Wi-Fi network
2. Measure signal strength at different locations
3. Calculate SNR using noise floor measurements
4. Create a signal map of your environment

### Expected Outcome

- Understanding of signal metrics
- Ability to measure and interpret signal strength
- Knowledge of SNR calculations

---

## Day 16: Channel Overlap Theory

### Concepts to Learn

- Channel bandwidth
- Spectral mask
- Adjacent channel interference
- Co-channel interference
- Channel planning

### Detailed Explanation

Understanding channel overlap is essential for both optimizing networks and conducting interference analysis.

**Channel Bandwidth:**

Each Wi-Fi channel has a defined bandwidth (usually 20 or 22 MHz for 2.4 GHz). However, due to spectral mask leakage, signals actually occupy more space than the channel number suggests.

**2.4 GHz Channel Overlap:**

```
Channel:     1     2     3     4     5     6     7     8     9    10    11
             │     │     │     │     │     │     │     │     │     │     │
             ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼     ▼
          ┌─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┬─────┐
          │     │     │     │     │     │     │     │     │     │     │     │
          │ 1   │ 2   │ 3   │ 4   │ 5   │ 6   │ 7   │ 8   │ 9   │ 10  │ 11  │
          │     │     │     │     │     │     │     │     │     │     │     │
          └─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┴─────┘
          
Overlap:     ├───┤           ├───┤
             Channel 1's energy bleeds into Ch 2, 3

Non-Overlapping: 1, 6, 11 (US standard)
```

**Impact of Channel Selection:**

Using overlapping channels causes interference:

| Scenario | Impact |
|----------|--------|
| Adjacent channels | Moderate interference |
| Same channel | Severe interference |
| 5 GHz channels | Usually non-overlapping |

**40 MHz Channels in 2.4 GHz:**

Using 40 MHz in 2.4 GHz is generally discouraged because it causes significant interference with many channels.

### Commands/Tools to Practice

```
bash
# View channel configuration
iw dev wlan0 info

# Scan and analyze channel usage
sudo iw dev wlan0 scan | grep -E "(CHANNEL|signal|freq)"

# Use airodump-ng to see channel congestion
sudo airodump-ng wlan0mon

# Check for interference with spectral analysis
sudo iw dev wlan0 survey dump
```

### Mini Lab/Exercise

1. Scan your environment for all networks
2. Identify which channels are most congested
3. Determine which networks are causing interference
4. Suggest optimal channel recommendations

### Expected Outcome

- Understanding of channel overlap
- Ability to identify interference sources
- Knowledge of optimal channel selection

---

## Day 17: Hidden SSID Discovery Methods

### Concepts to Learn

- What are hidden SSIDs
- How they work
- Discovery techniques
- Active vs passive discovery
- Limitations of hidden SSIDs

### Detailed Explanation

Hidden SSIDs (also called non-broadcast SSIDs) don't appear in beacon frames, but they're not truly hidden.

**How Hidden SSIDs Work:**

When SSID broadcast is disabled:
1. AP stops sending beacon frames with the SSID
2. Clients must actively probe for the network
3. SSID is still transmitted during association

**Discovery Methods:**

**Method 1: Probe Request/Response Capture**

When clients search for the network, they send probe requests containing the SSID:

```
┌──────────────────────────────────────────────┐
│     DISCOVERY VIA PROBE REQUESTS            │
├──────────────────────────────────────────────┤
│                                              │
│  Client sends: Probe Request (SSID="Hidden")│
│          │                                   │
│          ▼                                   │
│  AP responds: Probe Response (SSID="Hidden")│
│          │                                   │
│          ▼                                   │
│  Scanner captures SSID!                     │
│                                              │
└──────────────────────────────────────────────┘
```

**Method 2: Association Request Capture**

When clients connect, the SSID is included in association requests.

**Method 3: Deauthentication Forcing**

Send deauth to force clients to reconnect:

```
bash
# Force client to reconnect (reveals SSID)
sudo aireplay-ng --deauth 10 -a BSSID -c CLIENT wlan0mon
```

**Method 4: Bruteforce/Guessing**

If you know the network is there but not the name:
- Use wordlists to send probe requests
- Look for responses

### Commands/Tools to Practice

```
bash
# Capture probe requests with hidden SSIDs
sudo airodump-ng wlan0mon

# Look for SSID in probe requests
# Filter: wlan.fc.type == 0 && wlan.fc.subtype == 4
# Look for SSID field

# Force deauth to trigger reconnection
sudo aireplay-ng --deauth 100 -a [AP_BSSID] wlan0mon

# Use mdk3 for bruteforce
sudo mdk3 wlan0mon p -f /wordlist.txt -t [BSSID]
```

### Mini Lab/Exercise

1. Configure an AP with hidden SSID
2. Attempt to discover it passively
3. Use probe request capture method
4. Use deauth forcing method
5. Compare results

### Expected Outcome

- Understanding of hidden SSID mechanics
- Knowledge of multiple discovery methods
- Ability to find hidden networks

---

## Day 18: Client Detection Techniques

### Concepts to Learn

- Detecting wireless clients
- Probe request analysis
- Client fingerprinting
- Tracking client movement
- Privacy implications

### Detailed Explanation

Wireless clients can be detected and tracked, which has significant privacy and security implications.

**How Clients Are Detected:**

**1. Probe Requests:**

Clients constantly send probe requests looking for networks they've previously connected to:

```
┌─────────────────────────────────────────────────────┐
│          PROBE REQUEST CAPTURE                     │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Frame: Probe Request                              │
│  SSID: "HomeNetwork"  ← Previous network          │
│  Client MAC: AA:BB:CC:DD:EE:FF  ← Our target!     │
│                                                     │
│  This reveals:                                     │
│  - Client MAC address                             │
│  - Networks client has connected to               │
│  - Client vendor (from OUI)                       │
│                                                     │
└─────────────────────────────────────────────────────┘
```

**2. Association Requests:**

When connecting, clients send association requests revealing:
- The target SSID
- Client capabilities
- Supported rates

**3. MAC Address Tracking:**

Client MAC addresses can be tracked across locations:
- Unique identifiers
- Persistent even when not connected
- Can be used for movement tracking

**Client Information from Probe Requests:**

| Field | Information |
|-------|-------------|
| Source MAC | Client identifier |
| SSID | Networks client knows |
| Supported rates | Client capabilities |
| Vendor | Manufacturer from OUI |

### Commands/Tools to Practice

```
bash
# Detect clients with airodump-ng
sudo airodump-ng wlan0mon --Manufacturer

# Filter probe requests in Wireshark
wlan.fc.type == 0 && wlan.fc.subtype == 4

# Use tcpdump
sudo tcpdump -i wlan0mon -e -n | grep -i probe

# Kismet for tracking
sudo kismet
```

### Mini Lab/Exercise

1. Capture wireless traffic in a public area
2. Identify all client probe requests
3. Extract SSIDs from probe requests
4. Track unique clients by MAC address

### Expected Outcome

- Understanding client detection methods
- Knowledge of probe request analysis
- Ability to track wireless clients

---

## Day 19: Packet Structure Deep Dive

### Concepts to Learn

- Full 802.11 packet structure
- Header fields explained
- Frame body contents
- Trailer/CRC
- Encapsulation

### Detailed Explanation

Let's examine the complete structure of 802.11 packets.

**Complete 802.11 Frame Structure:**

```
┌─────────────────────────────────────────────────────────────────────────┐
│                  COMPLETE 802.11 FRAME STRUCTURE                       │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  ┌──────────┬──────────┬──────────┬──────────┬──────────┬──────────┐ │
│  │  Frame   │ Duration │ Address 1│ Address 2│ Address 3│ Sequence │ │
│  │ Control  │    ID    │   (RA)   │   (TA)   │   (DA)   │ Control  │ │
│  │  2 bytes │  2 bytes │  6 bytes │  6 bytes │  6 bytes │  2 bytes │ │
│  ├──────────┴──────────┴──────────┴──────────┴──────────┴──────────┤ │
│  │                                                                      │ │
│  │  ┌──────────────────────────────────────────────────────────────┐  │ │
│  │  │                    FRAME BODY                                │  │ │
│  │  │  (0-2312 bytes) - Contains management/control/data payload   │  │ │
│  │  │                                                               │  │ │
│  │  │  Management: Beacon, Probe, Auth, Assoc, etc.               │  │ │
│  │  │  Control: RTS, CTS, ACK, etc.                               │  │ │
│  │  │  Data: LLC header + payload                                  │  │ │
│  │  └──────────────────────────────────────────────────────────────┘  │ │
│  │                                                                      │ │
│  ├──────────────────────────────────────────────────────────────────────┤ │
│  │  Frame Check Sequence (FCS) - 4 bytes                            │ │
│  │  CRC-32 error detection                                           │ │
│  │                                                                      │ │
│  └──────────────────────────────────────────────────────────────────────┘ │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

**Address Fields in Different Scenarios:**

| To DS | From DS | Address 1 | Address 2 | Address 3 | Address 4 |
|-------|---------|------------|------------|------------|------------|
| 0     | 0       | Destination| Source    | BSSID     | - |
| 0     | 1       | Destination| BSSID     | Source    | - |
| 1     | 0       | BSSID     | Source    | Destination| - |
| 1     | 1       | Receiver  | Transmitter| Destination| AP |

**Frame Body Examples:**

**Beacon Frame Body:**
- Timestamp (8 bytes)
- Beacon Interval (2 bytes)
- Capability Information (2 bytes)
- SSID Element
- Supported Rates
- DS Parameter Set
- And more...

**Data Frame Body:**
- LLC Header (8 bytes): DSAP, SSAP, Control, OUI
- Payload: IP packet (when not encrypted)
- Encrypted payload (when using WEP/WPA/WPA2/WPA3)

### Commands/Tools to Practice

```
bash
# Analyze frame structure in Wireshark
# Enable 802.11 dissection
# View > Internal > Wireshark > Protocol Enabled

# Filter and examine specific frames
# Look at frame details pane for structure

# Export frame for analysis
# File > Export Specified Packets
```

### Mini Lab/Exercise

1. Capture some frames in Wireshark
2. Expand each layer in the details pane
3. Map each field to the 802.11 structure
4. Identify addresses in different frame types

### Expected Outcome

- Understanding of complete packet structure
- Knowledge of all header fields
- Ability to analyze frame contents

---

## Day 20: Wireless Security Types

### Concepts to Learn

- Open networks
- WEP encryption
- WPA/WPA2 Personal
- WPA/WPA2 Enterprise
- WPA3
- Transition modes

### Detailed Explanation

Understanding wireless security types is essential for both assessment and hardening.

**Security Type Comparison:**

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                    WIRELESS SECURITY TYPES                                     │
├──────────────────┬──────────────┬──────────────┬──────────────────────────────┤
│ Security Type    │ Encryption   │ Key Exchange │ Security Level             │
├──────────────────┼──────────────┼──────────────┼──────────────────────────────┤
│ Open             │ None         │ None         │ None - No security          │
│ WEP              │ RC4          │ Static       │ Weak - Easily cracked       │
│ WPA              │ TKIP         │ 4-way HS     │ Moderate                    │
│ WPA2-Personal   │ AES-CCMP     │ 4-way HS     │ Strong - PSK vulnerability  │
│ WPA2-Enterprise │ AES-CCMP     │ 802.1X/EAP   │ Strongest - Recommended    │
│ WPA3-Personal   │ SAE           │ Dragonfly    │ Strongest - Modern         │
│ WPA3-Enterprise │ 192-bit      │ 802.1X/EAP   │ Enterprise grade           │
└──────────────────┴──────────────┴──────────────┴──────────────────────────────┘
```

**WEP (Wired Equivalent Privacy):**

- Uses RC4 stream cipher
- Static encryption key
- 24-bit IV (initialization vector)
- Weak IV attacks
- Easily cracked in minutes

**WPA (Wi-Fi Protected Access):**

- Uses TKIP (Temporal Key Integrity Protocol)
- 4-way handshake for key exchange
- Michael MIC for integrity
- Temporary key per packet
- Interim solution

**WPA2:**

- Uses AES-CCMP encryption
- Two modes: Personal (PSK) and Enterprise (802.1X)
- 4-way handshake
- Considered secure until KRACK attack

**WPA3:**

- Uses SAE (Simultaneous Authentication of Equals)
- Dragonfly handshake
- Protected Management Frames (PMF required)
- Forward secrecy
- Easier secure setup (Wi-Fi Easy Connect)

### Commands/Tools to Practice

```
bash
# Identify security type with airodump-ng
sudo airodump-ng wlan0mon
# Look at ENC column or AUTH column

# In Wireshark, filter authentication
# Look for RSN information element for WPA2
# wlan.rsn.akm

# Check for WPA3
wlan.tag.number == 48  # Vendor-specific
```

### Mini Lab/Exercise

1. Scan for networks with different security types
2. Document the security type of each network
3. Note which are most common in your area

### Expected Outcome

- Understanding of all security types
- Knowledge of encryption differences
- Ability to identify security types

---

## Day 21-28: Additional Technical Topics

*Continue with advanced topics:*

## Day 21: Handshake Capture Concepts

**4-Way Handshake:**

```
┌────────────────────────────────────────────────────────────────┐
│                 WPA/WPA2 4-WAY HANDSHAKE                      │
├────────────────────────────────────────────────────────────────┤
│                                                                 │
│  AP                        Client                              │
│   │                           │                                │
│   │─────── ANonce ───────────▶│  (1st message)               │
│   │                           │                                │
│   │◀───── SNonce + MIC ──────│  (2nd message)               │
│   │                           │                                │
│   │───── MIC + Install PTK ──▶│  (3rd message)               │
│   │                           │                                │
│   │◀─────── ACK ──────────────│  (4th message)               │
│   │                           │                                │
│   │     ENCRYPTED DATA        │                                │
│   │◀─────────────────────────▶│                                │
│                                                                 │
└────────────────────────────────────────────────────────────────┘
```

The 4-way handshake proves both parties possess the correct PMK (Pairwise Master Key) without transmitting it.

---

## Day 22: Wireshark Wireless Capture Setup

### Commands:

```
bash
# Start capture in monitor mode
sudo wireshark -i wlan0mon &

# Capture filters
# Just management frames: type mgt
# Just control frames: type control  
# Just data frames: type data

# Display filters to learn:
wlan.bssid == AA:BB:CC:DD:EE:FF
wlan.ssid == "NetworkName"
wlan.addr == AA:BB:CC:DD:EE:FF
```

---

## Day 23-28: Continue with Tools

# PHASE 3: TOOLS - LINUX (Days 29-42)

## Day 29: Introduction to Airodump-ng

### Concepts:
- What is airodump-ng
- Basic usage
- Output options
- Channel hopping

### Detailed Explanation

airodump-ng is part of the Aircrack-ng suite and is the primary tool for Wi-Fi discovery and monitoring.

**Basic Usage:**

```
bash
# Basic scan
sudo airodump-ng wlan0mon

# Scan specific channel
sudo airodump-ng wlan0mon --channel 6

# Scan 5GHz band only
sudo airodump-ng wlan0mon --band a

# Scan both bands
sudo airodump-ng wlan0mon --band abg

# Save to file
sudo airodump-ng wlan0mon -w capture

# With manufacturer info
sudo airodump-ng wlan0mon --manufacturer
```

**Output Fields:**

| Field | Description |
|-------|-------------|
| BSSID | AP MAC address |
| PWR | Signal level |
| Beacons | Beacons received |
| #Data | Data packets |
| #/s | Packets per second |
| CH | Channel |
| MB | Max speed |
| ENC | Encryption |
| CIPHER | Encryption cipher |
| AUTH | Authentication |
| ESSID | Network name |

---

## Day 30-42: Continue with Tools

*Continue detailed tool coverage including:*

- Airolib-ng (database management)
- Aireplay-ng (packet injection)
- Aircrack-ng (WEP/WPA cracking)
- Kismet
- Wireshark filters
- iw/iwconfig/iwlist
- Command Reference

---

# PHASE 4: TOOLS - WINDOWS & APPS (Days 43-56)

## Day 43: Netsh WLAN Commands

### Commands:

```
bash
# Windows - List networks
netsh wlan show networks mode=bssid

# Show interfaces
netsh wlan show interfaces

# Connect to network
netsh wlan connect name="NetworkName"

# Show profiles
netsh wlan show profiles

# Export profiles
netsh wlan export profile folder=C:\wifi
```

---

## Day 44-56: Windows Tools & Mobile Apps

*Continue with:*
- NetSpot
- inSSIDer
- WiFi Analyzer (Android)
- Airport Utility (iOS)
- CommView for WiFi

---

# PHASE 5: PRACTICAL LABS (Days 57-70)

## Day 57: Lab 1 - Basic Network Discovery

### Step-by-Step:

1. Start Kali Linux
2. Enable monitor mode: `airmon-ng start wlan0`
3. Run airodump-ng: `airodump-ng wlan0mon`
4. Document all found networks
5. Create network inventory

---

## Day 58-70: Additional Labs

*Continue with:*
- Packet capture lab
- Channel survey lab
- Signal mapping lab
- Client detection lab
- Hidden SSID lab
- Security assessment lab

---

# PHASE 6: SECURITY APPLICATIONS (Days 71-84)

## Day 71: Reconnaissance Workflow

### Complete Workflow:

```
┌─────────────────────────────────────────────────────────────────┐
│              WIRELESS RECON WORKFLOW                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  1. PASSIVE DISCOVERY                                           │
│     └─ airodump-ng (monitor mode)                               │
│        └─ Document all APs                                      │
│                                                                 │
│  2. ACTIVE PROBING                                              │
│     └─ Probe specific targets                                   │
│        └─ Discover hidden SSIDs                                 │
│                                                                 │
│  3. CLIENT ENUMERATION                                          │
│     └─ Identify clients                                         │
│        └─ Track probe requests                                  │
│                                                                 │
│  4. SECURITY ANALYSIS                                           │
│     └─ Identify encryption                                      │
│        └─ Check for vulnerabilities                            │
│                                                                 │
│  5. TARGET SELECTION                                             │
│     └─ Choose targets for further testing                       │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## Day 72-84: Security Topics

*Continue with:*
- Rogue AP detection
- Evil twin detection
- Wardriving
- Wireless auditing
- Defensive monitoring
- Reporting

---

# PHASE 7: ADVANCED TOPICS (Days 85-90)

## Day 85-90: Capstone Project

### Final Project: Comprehensive Wireless Security Assessment

**Requirements:**

1. Perform complete wireless reconnaissance
2. Document all networks in target area
3. Identify security issues
4. Create professional report
5. Provide recommendations

**Deliverables:**

- Network inventory spreadsheet
- Signal coverage map
- Security assessment report
- Remediation recommendations

---

## Tools & Resources

### Essential Tools:

| Tool | Purpose | Platform |
|------|---------|----------|
| airodump-ng | Network discovery | Linux |
| Kismet | Wardriving/scanning | Linux |
| Wireshark | Packet analysis | Cross-platform |
| Aircrack-ng | Security testing | Linux |
| NetSpot | Site survey | Windows/Mac |
| inSSIDer | Wi-Fi analysis | Windows |
| WiFi Analyzer | Mobile scanning | Android |

### Learning Resources:

- Aircrack-ng documentation
- Wireshark wiki
- IEEE 802.11 standards
- OWASP Wireless testing guide

---

## Certification Path

### Recommended Certifications:

1. **CompTIA Security+** - Foundation
2. **CWNA (Certified Wireless Network Administrator)** - Wireless fundamentals
3. **OSCP** - Penetration testing (includes wireless)
4. **GPEN** - Penetration testing
5. **CISSP** - Security management

---

## Career Guidance

### Job Roles:

- Penetration Tester
- Security Analyst
- Wireless Network Administrator
- Security Consultant
- Red Team Member

### Skills to Develop:

- Programming (Python, Bash)
- Network architecture
- Security frameworks
- Report writing
- Communication

---

## Conclusion

This 90-day roadmap provides a comprehensive path from beginner to advanced wireless security practitioner. Remember to always practice ethically and legally - only scan networks you own or have explicit permission to test.

**Happy Learning!**

---

*Last Updated: 2024*
