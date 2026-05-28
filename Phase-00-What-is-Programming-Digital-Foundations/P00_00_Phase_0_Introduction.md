# Phase 0 – Foundations of Computing & Programming  
**Project:** Personal Computer Museum | **Tagline:** *Explore the History of Computing*  

---

## 1. Why Phase 0? – Rationale (the reasoning behind the phase)

Phase 0 is the launch‑pad for the entire Java‑centric learning roadmap.  
Before learners can write Java code that powers a sophisticated web‑based museum, they must first understand **what a computer is**, how it represents information, and how the software stack they will eventually use (HTML + CSS + JavaScript + Java back‑ends) fits into the broader computing ecosystem.  

The topics in this phase are deliberately chosen to:

| Goal | How it connects to the museum project |
|------|----------------------------------------|
| **Conceptual grounding** – “What is a computer?” | Learners write a short introductory page for the museum that explains the basic hardware components they will later showcase. |
| **Binary & number systems** | A binary calculator becomes an interactive exhibit that lets visitors convert numbers, reinforcing the museum’s “first binary systems” narrative. |
| **Bits, bytes & data representation** | A visual data‑representation widget demonstrates how text, images, and sound are stored—perfect for a “how data is stored” exhibit. |
| **OS basics** | A tiny OS simulator illustrates the role of an operating system, mirroring the museum’s “modern OS” section. |
| **File systems & directories** | A virtual file system models how the museum’s assets (photos, PDFs, code) are organized. |
| **Command‑line interface** | The CLI lets visitors “navigate” the virtual file system, giving a hands‑on feel for early computer interaction. |
| **Internet fundamentals** | A network diagram explains how the museum is delivered over the web, tying into the “online museum” experience. |
| **Dev‑environment setup** | Learners configure the exact tools they will use to build, test, and host the museum site. |
| **What is programming?** | Interactive coding challenges become museum mini‑games that teach programming concepts to visitors. |
| **Growth mindset** | Reflective writing helps learners adopt the resilient attitude needed for long‑term engineering projects. |

By completing these activities, students acquire the **mental models** and **practical scaffolding** required for the Java‑centric phases that follow (e.g., building server‑side services, data persistence, and API integration).

---

## 2. Phase 0 Overview

| **Component** | **Details** |
|---------------|-------------|
| **Duration** | 2 weeks (≈ 10 working days) |
| **Primary Language** | No Java code yet – focus is on concepts using HTML/CSS/JS for quick prototypes. |
| **Deliverables** | 1. Intro page “What is a Computer?”  <br>2. Binary calculator widget  <br>3. Data‑representation visualiser  <br>4. Simple OS simulator (web‑based)  <br>5. Virtual file‑system prototype  <br>6. CLI for the virtual FS  <br>7. Network‑diagram infographic  <br>8. Dev‑environment checklist  <br>9. Interactive coding‑challenge page  <br>10. Growth‑mindset reflection (≈ 300 words) |
| **Assessment** | • Completion of each deliverable (auto‑graded where possible). <br>• Short quiz covering core concepts. <br>• Peer‑review of the reflection statement. |
| **Key Tools** | VS Code, Git, Node.js (for local server), Chrome DevTools, Markdown, PlantUML (for network diagram). |

---

## 3. Detailed Topic‑to‑Project Connection Map  

| **Topic Code** | **Topic Title** | **Learning Activity (Project‑linked)** | **Outcome for the Museum** |
|----------------|----------------|----------------------------------------|----------------------------|
| **0.1** | What is a Computer? | Write a concise introductory article (≈ 200 words) + simple diagram of CPU, memory, I/O. | This becomes the “Welcome” section of the museum site. |
| **0.2** | Binary & Number Systems | Build a **binary calculator** (HTML/JS) that converts between decimal, binary, hex. | Interactive exhibit showing early computing foundations. |
| **0.3** | Bits, Bytes & Data Representation | Design a **data‑representation visualiser** (e.g., colour‑coded bits for characters). | Demonstrates how text/images are stored – used in “Data Storage” exhibit. |
| **0.4** | Operating System Basics | Create a **mini‑OS simulator** (process list, simple scheduler) using JS. | Shows OS evolution; can be embedded as a sandbox demo. |
| **0.5** | File Systems & Directories | Implement a **virtual file system** (JSON‑backed) with folders/files UI. | Powers the museum’s “Explore the Archive” navigation. |
| **0.6** | Command Line & Terminal | Add a **CLI** that accepts commands (`ls`, `cd`, `cat`) to interact with the virtual FS. | Gives visitors a retro‑terminal experience. |
| **0.7** | How the Internet Works | Draw a **network diagram** (client ↔ server ↔ DNS ↔ routers) using PlantUML or draw.io. | Serves as an infographic explaining the museum’s online delivery. |
| **0.8** | Dev Environment Setup | Produce a **setup guide** (install VS Code, Git, Node, Live Server) and a repo scaffold. | Provides a reproducible environment for all later phases. |
| **0.9** | What is Programming? | Write **interactive coding challenges** (e.g., “Write a function that flips a bit”). | Embedded mini‑lessons for museum visitors. |
| **0.10** | Growth Mindset for Engineering | Draft a **personal growth‑mindset statement** reflecting on challenges and learning strategies. | Shared on the “Team” page to model engineering attitudes. |

---

## 4. Learning Objectives (What the learner will be able to do)

1. **Explain** the core hardware components of a computer and their roles.  
2. **Convert** numbers between decimal, binary, and hexadecimal and **justify** why binary is foundational.  
3. **Illustrate** how bits and bytes encode different data types (text, images, audio).  
4. **Describe** basic operating‑system concepts (processes, scheduling, memory management).  
5. **Model** a file system hierarchy and **perform** basic file operations programmatically.  
6. **Use** a command‑line interface to navigate and manipulate a virtual file system.  
7. **Diagram** the key layers of the Internet (client‑server model, DNS, routing).  
8. **Set up** a local development environment suitable for web‑based projects.  
9. **Define** programming and **create** simple interactive challenges that teach core concepts.  
10. **Articulate** a growth‑mindset statement that connects personal learning to engineering practice.

---

## 5. Suggested Timeline (10‑day sprint)

| Day | Activity | Deliverable |
|-----|----------|-------------|
| 1 | Project kickoff – read project brief, create repo | Repo initialized |
| 2 | Topic 0.1 – write intro article + diagram | `intro.html` |
| 3 | Topic 0.2 – binary calculator prototype | `binary.html` |
| 4 | Topic 0.3 – data‑representation visualiser | `data.html` |
| 5 | Topic 0.4 – mini‑OS simulator | `os.html` |
| 6 | Topic 0.5 – virtual file system (JSON + UI) | `vfs.html` |
| 7 | Topic 0.6 – CLI overlay for VFS | `cli.js` |
| 8 | Topic 0.7 – network diagram (export PNG) | `network.png` |
| 9 | Topic 0.8 – dev‑environment guide (Markdown) | `SETUP.md` |
| 10| Topics 0.9 & 0.10 – coding challenges + growth‑mindset essay | `challenges.html`, `mindset.md` |

*Each day ends with a **commit** and a **quick peer review** (via the class Slack/Discord channel).*

---

## 6. Resources & References

| Resource Type | Link / Description |
|---------------|--------------------|
| **Project Documentation** | Detailed spec in the repo’s `README.md`. |
| **HTML/CSS/JS Basics** | MDN Web Docs – *Getting started with the web*. |
| **Binary Calculator Tutorial** | “Build a Binary Converter with JavaScript” – freeCodeCamp. |
| **Operating‑System Concepts** | *Operating Systems: Three Easy Pieces* (Ch. 1–2) – free PDF. |
| **Virtual File System Example** | “In‑Memory File System in JavaScript” – GitHub gist. |
| **PlantUML** | `https://plantuml.com/` – for network diagram. |
| **Growth Mindset** | Carol Dweck’s *Mindset* – Chapter 2 summary PDF. |
| **Collaboration** | GitHub Classroom, VS Code Live Share. |

---

## 7. Assessment Rubric (summary)

| Criterion | Excellent (A) | Satisfactory (B) | Needs Improvement (C) |
|-----------|---------------|------------------|------------------------|
| **Conceptual Accuracy** | All explanations are technically correct and clearly written. | Minor inaccuracies, but overall correct. | Major misconceptions. |
| **Functional Prototypes** | All interactive widgets work without bugs; UI is polished. | Most widgets work; minor bugs or UI roughness. | Many non‑functional or broken features. |
| **Documentation** | Clear README, setup guide, and inline comments. | Adequate documentation, some gaps. | Missing or unclear documentation. |
| **Reflection** | Insightful growth‑mindset statement, ties to engineering challenges. | Generic reflection, limited depth. | No reflection or off‑topic. |
| **Collaboration** | Frequent commits, peer feedback incorporated. | Regular commits, limited peer interaction. | Sparse commits, no peer feedback. |

---

## 8. Next Steps (Into Phase 1)

Once Phase 0 is complete, learners will transition to **Phase 1 – Java Fundamentals**, where they will:

* Write their first Java classes that model museum artifacts.  
* Connect the front‑end (HTML/JS) to a simple Java‑based REST API.  
* Begin persisting data (e.g., artifact metadata) using Java collections and files.

Phase 0 therefore serves as the **conceptual and infrastructural backbone** that makes those later Java implementations meaningful and context‑rich.

---

### Ready to start?

1. **Clone** the starter repository.  
2. **Read** the `README.md` for the sprint schedule.  
3. **Set up** your development environment (Day 9 activity).  
4. **Begin** with Topic 0.1 and move forward day‑by‑day.

Good luck, and enjoy building the foundations of the Personal Computer Museum!