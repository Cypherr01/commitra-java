# **Phase 0 – Foundations of Computing**  
**Project‑Anchored Java Learning Roadmap**  

---

## 1. Project Overview  

| Item | Details |
|------|---------|
| **Project** | **Personal Computer Museum** – an interactive website that tells the story of computing, from early binary machines to modern operating systems. |
| **Tagline** | *Explore the History of Computing* |
| **Description** | The site offers a virtual tour of historic computer systems, interactive visualisations, and short coding challenges. It is aimed at students, educators, and tech‑enthusiasts who want to understand how computers work and why they matter. |
| **Current Tech Stack** | **HTML + CSS + JavaScript** (front‑end).  In later phases Java will be introduced for back‑end simulations, data‑processing services, and algorithmic challenges. |
| **Why Java?** | Java’s platform‑independent nature, strong typing, and rich standard library make it ideal for modelling operating‑system concepts, file‑system logic, and algorithmic puzzles that will later be integrated into the museum’s interactive modules. |

---

## 2. Phase 0 – Purpose  

Phase 0 is the **foundation layer**. Before learners write any Java code, they must understand the *hardware* and *conceptual* building blocks that Java will later model. Each topic is directly tied to a concrete artefact that will become part of the museum website (e.g., a binary calculator, a virtual file‑system UI, a simple OS simulator).  

**Goal:**  
*Equip learners with a mental model of computers, number systems, data representation, and basic OS ideas, while simultaneously producing small, reusable web components that will be integrated into the museum.*  

---

## 3. Learning Objectives  

By the end of Phase 0 learners will be able to:

1. **Describe** the core components of a computer (CPU, memory, I/O, storage).  
2. **Explain** binary, octal, decimal, and hexadecimal number systems and **implement** a binary calculator in JavaScript.  
3. **Illustrate** how bits, bytes, and data types represent information.  
4. **Model** fundamental OS concepts (processes, scheduling, memory management) with a simple Java‑based simulator.  
5. **Design** a virtual file‑system hierarchy and **manipulate** it via a web‑based UI.  
6. **Create** a command‑line interface (CLI) that interacts with the virtual file system.  
7. **Outline** the basic layers of the Internet (physical, transport, application) and **draw** a network diagram.  
8. **Set up** a local development environment (VS Code, Node, Git) ready for Java development later.  
9. **Articulate** what programming is and **author** a set of interactive coding challenges (HTML/JS) that will later be re‑implemented in Java.  
10. **Reflect** on personal growth, adopt a growth‑mindset statement, and **plan** next steps toward Java mastery.  

---

## 4. Topic‑to‑Project Connection Map  

| Phase 0 Sub‑topic | Museum‑Component (HTML/JS) | Java‑Learning Bridge |
|-------------------|----------------------------|----------------------|
| **0.1 What is a Computer?** | Introductory page with labelled diagram of CPU, RAM, storage, I/O. | Later Java classes `Computer`, `CPU`, `Memory` will mirror these components. |
| **0.2 Binary & Number Systems** | Interactive binary calculator (input → binary/decimal/hex output). | Java `NumberSystem` utility class; practice with `Integer.toBinaryString()`. |
| **0.3 Bits, Bytes & Data Representation** | Visual “bit‑grid” that shows how a character, integer, and image pixel are stored. | Java `ByteBuffer` demos; discussion of primitive types (`byte`, `int`, `char`). |
| **0.4 Operating System Basics** | Mini‑OS simulator (process queue, simple scheduler visual). | Java `Process` and `Scheduler` classes; introduction to multithreading concepts. |
| **0.5 File Systems & Directories** | Virtual file‑system UI (folders, files, drag‑and‑drop). | Java `File` API; building a mock file‑system in memory. |
| **0.6 Command Line & Terminal** | Web‑based CLI that accepts `ls`, `cd`, `cat` commands against the virtual FS. | Java `Scanner`‑based console app; parsing commands, handling I/O. |
| **0.7 How the Internet Works** | Clickable network diagram (client ↔ router ↔ server). | Java networking basics (`Socket`, `ServerSocket`). |
| **0.8 Dev Environment Setup** | Guide to installing VS Code, Node, Git, and a local web server. | Additional guide to installing JDK, Maven/Gradle, and IntelliJ/Eclipse. |
| **0.9 What is Programming?** | Set of HTML/JS puzzles (e.g., “write a loop that counts to 10”). | Same puzzles re‑implemented in Java; introduction to `for`, `while`, methods. |
| **0.10 Growth Mindset for Engineering** | Reflection blog post on the museum site. | Personal learning journal; plan for tackling Java challenges. |

---

## 5. Deliverables & Assessment  

| Deliverable | Description | Success Criteria |
|-------------|-------------|------------------|
| **Intro Page** | One‑page HTML with a concise definition of a computer and labelled diagram. | Clear, accurate description; diagram correctly identifies at least 4 components. |
| **Binary Calculator** | Interactive widget (HTML + JS) that converts between bases. | Works for numbers up to 32‑bit; handles invalid input gracefully. |
| **Bit‑Grid Visualiser** | Grid that lights up bits for a given character/number. | Correct representation for at least three data types. |
| **Mini‑OS Simulator** | Visual queue of “processes” with start/stop controls. | Demonstrates round‑robin scheduling; UI updates in real time. |
| **Virtual File System** | Tree view with create/delete/rename actions. | Persists state in `localStorage`; reflects changes instantly. |
| **Web CLI** | Text input that parses `ls`, `cd`, `cat` against the virtual FS. | Correct command output; error messages for unknown commands. |
| **Network Diagram** | SVG or Canvas diagram with hover‑over explanations. | All major layers (physical, IP, TCP/UDP, HTTP) labelled. |
| **Dev‑Env Guide** | Markdown/HTML guide with screenshots. | New learner can clone repo, run `npm start`, and view site locally. |
| **Coding Challenges** | 3‑5 simple puzzles with auto‑check in JS. | Each puzzle has a passing test case and a clear solution description. |
| **Growth‑Mindset Statement** | 200‑word reflective blog post. | Shows self‑awareness, identifies a challenge, and outlines a concrete improvement plan. |

*Assessment will be formative – peers review each artefact, and the instructor provides a rubric‑based feedback sheet.*

---

## 6. Suggested Timeline (2‑Week Sprint)

| Day | Activity |
|-----|----------|
| **Day 1** | Kick‑off meeting – review project vision, set up GitHub repo. |
| **Day 2‑3** | Topic 0.1 – write intro page; discuss Java class mapping. |
| **Day 4‑5** | Topic 0.2 – build binary calculator; draft Java `NumberSystem` stub. |
| **Day 6** | Topic 0.3 – create bit‑grid visualiser; explore Java `Byte` handling. |
| **Day 7** | **Sprint Review** – demo first three components, collect feedback. |
| **Day 8‑9** | Topic 0.4 – OS simulator; prototype Java `Process` class. |
| **Day 10‑11** | Topic 0.5 & 0.6 – virtual FS + CLI; sketch Java file‑system API. |
| **Day 12** | Topic 0.7 – network diagram; write simple Java socket demo. |
| **Day 13** | Topic 0.8 – dev‑environment guide (HTML + Java setup). |
| **Day 14** | Topic 0.9 & 0.10 – coding challenges & growth‑mindset blog; sprint retrospective. |

---

## 7. Resources  

| Category | Resource |
|----------|----------|
| **HTML/CSS/JS** | MDN Web Docs – <https://developer.mozilla.org> |
| **Java Basics** | *Head First Java* (2nd ed.) – Chapters 1‑4 |
| **Version Control** | GitHub Learning Lab – “Introduction to GitHub” |
| **IDE** | VS Code (with Live Server) – <https://code.visualstudio.com> |
| **Java Setup** | AdoptOpenJDK 17 LTS, Maven, IntelliJ Community Edition |
| **Binary & Number Systems** | Khan Academy – “Number Systems” video series |
| **Operating‑System Concepts** | *Operating Systems: Three Easy Pieces* – Chapter 1 |
| **File‑System Theory** | Wikipedia – “File system” (overview) |
| **Networking** | Cisco “Introduction to Networks” – Module 1 |
| **Growth Mindset** | Carol Dweck – *Mindset: The New Psychology of Success* (selected chapters) |

---

## 8. How This Phase Leads to Java Mastery  

1. **Conceptual Grounding** – Understanding hardware and low‑level data prepares learners for Java’s strict type system and memory model.  
2. **Reusable Artefacts** – The web components built now will later be *re‑implemented* in Java, giving learners a concrete “before‑and‑after” comparison.  
3. **Incremental Coding** – Learners start with JavaScript (no compilation barrier) and then transition to Java, reinforcing algorithmic thinking while learning new syntax.  
4. **Project Motivation** – Every Java class they write will have a visible purpose inside the museum (e.g., `BinaryCalculator`, `VirtualFileSystem`). This keeps motivation high and contextualises abstract concepts.  

---

## 9. Next Steps (Into Phase 1 – Java Core)

* Review the Phase 0 artefacts and the Java stubs you drafted.  
* Install the JDK, Maven, and your chosen IDE.  
* Clone the repository’s **java‑starter** branch – it contains skeleton classes for `Computer`, `Process`, `FileSystem`, etc.  
* Begin Phase 1 by tackling **0.9 What is Programming?** in Java: rewrite the first three JS puzzles as console applications.  

---

### **Ready to start?**  
Open the **Phase 0** folder in the repo, read the `README.md`, and start building the first museum component. Remember: every line of Java you write later will be a *direct evolution* of the interactive piece you create today. Happy coding!