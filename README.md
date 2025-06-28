# Wazuh Implementation — Internship Cybersecurity Project

Implementation of a SIEM (Wazuh) to simulate a real-world cybersecurity monitoring environment.

---

## 👤 About Me

Hello, I’m **Rayane**, and this project was developed during a **1-month internship** at **CMPE Maroc**. The main objective was to deepen my knowledge of cybersecurity by simulating a centralized SIEM solution while respecting all internal security policies and using only **isolated infrastructure** on my personal machine.

---

## 💡 Project Motivation

This project came from my deep interest in cybersecurity and my desire to gain **hands-on experience** with real-world tools and challenges. Although my formal background is in **networking, Linux system administration, and coding**, I was determined to take a leap into cybersecurity, despite not having direct experience in the field.

After brainstorming different project ideas, I decided to simulate the implementation of a **SIEM system** using **Wazuh**, an open-source security platform. This was discussed with and approved by my internship manager, to whom I extend my sincere thanks for the support and trust.

---

## 🧩 Project Overview

I deployed a Wazuh SIEM stack on **Ubuntu 24.04.2 LTS**, including:
- `wazuh-manager`
- `wazuh-indexer`
- `wazuh-dashboard`

I then configured my machine to act as a **syslog server**, receiving logs from a **WatchGuard firewall** via **UDP port 514**, storing them in `/var/log/watchguard.log`.

⚠️ **Note:** All testing and configurations were performed on a separate machine under controlled and isolated conditions. No production environments were impacted.

---

## 🛠️ Tools & Technologies Used

- **Wazuh** — Open-source SIEM & XDR
- **Syslog (UDP/TCP 514)** — Log transport protocol
- **WatchGuard Firewall** — Log source (simulated input)
- **Ubuntu Server 24.04.2 LTS** — Host system
- **Wazuh Decoders & Rules** (XML) — Custom written for log parsing and alerting
- **Regex** — Used for pattern matching in custom decoders
- **Bash / Shell** — Debugging, file manipulation
- **Linux tools** (`journalctl`, `tail`, `netstat`, etc.) — Troubleshooting and monitoring

---

## 🔄 Project Workflow

1. **Tool Research & Selection**
   - Identified and chose **Wazuh** as a free, open-source, and powerful SIEM solution.

2. **Wazuh Installation**
   - Installed the full Wazuh stack by following the [official documentation](https://documentation.wazuh.com/current/installation-guide/index.html).
   - Faced multiple errors, system crashes, and repeated re-installations during this phase (see "Challenges" below).

3. **Syslog Configuration**
   - Requested manager permission to forward logs from a WatchGuard firewall to my machine using **Syslog over port 514**.
   - Configured the syslog service to save logs to `/var/log/watchguard.log`.

4. **Decoder & Rule Creation**
   - Developed **custom Wazuh decoders** to extract structured data from WatchGuard logs.
   - Wrote **rules** to generate alerts based on the decoded logs.
   - Spent significant time debugging Wazuh’s strict regex and decoder syntax.

---

## ⚠️ Challenges Faced

### 🧩 Installation & Environment
- Had to reinstall Wazuh over **7 times** due to broken packages, misconfigurations, and missing dependencies.
- Problems included:
  - Unstable internet during installation
  - Incomplete cleanup between reinstallation attempts
  - Changing IP addresses (not ideal for SIEM setup)

### 🔍 Regex & Decoder Development
- Creating regex for log parsing was not difficult in general — but Wazuh has **strict limitations** on supported regex patterns in XML decoders.
- Most online regex testers (and AI tools) validated patterns as correct, but they failed within Wazuh.
- Official documentation was insufficient for decoder syntax, leading to weeks of trial-and-error.
- Even multiple AI tools (ChatGPT, Gemini Pro, Copilot) couldn’t fully resolve these issues.
- Eventually, I succeeded by **manually analyzing patterns** and identifying unsupported syntax through experimentation.

### 🖥️ Hardware Limitations
- Used a low-end laptop that frequently crashed during installation and testing.

### ⏳ Time Constraints
- The internship was limited to one month, which restricted the project scope and prevented full completion of initial goals.

---

## ✅ Skills & Knowledge Gained

- Installation, configuration, and debugging of Wazuh SIEM
- Writing custom **regex patterns**, **decoders**, and **rules**
- Troubleshooting complex Linux and networking issues
- Working with **real-world, unstructured log data**
- Improved problem-solving and **technical perseverance**
- Learned to validate AI-generated solutions and rely on internal understanding when tools fail
- Managed and executed a self-initiated project from planning to deployment

---

## ⛔ What I Didn’t Complete

Although I reached my main goal, some planned tasks weren’t completed due to time and technical limitations:

- ❌ **Windows Server Log Integration** — Initially planned but not implemented.
- ❌ **Router Log Parsing** — Also planned, but not completed within the timeframe.
- ❌ **Automation** — Tasks like decoder testing and deployment weren’t automated, but could be future improvements.

---

## 📈 Future Improvements

If I had more time or resources, I would:
- Add full log integration from Windows servers and routers
- Build automation scripts for regex testing and decoder deployment
- Use tools like **Logstash** or **Filebeat** to enrich log collection
- Add dashboards and alert reports for clearer visualization

---

## 🙏 Final Words

This was my **first real-world cybersecurity project**, and even though it was extremely challenging, I learned more in one month than in many months of traditional study. I now understand not just how to install a tool, but how to fight through broken installations, incorrect documentation, confusing errors, and regex nightmares — and still deliver results.

I’d like to thank **CMPE Maroc** for their support and trust during this project.  
I now look forward to building more advanced security projects and sharing them on this journey.

> **_ Rayane **
