# Phase 0 – Foundations of Computing  
**Project‑Anchored Java Learning Roadmap**  

---

## 1. Project Overview  

| Item | Details |
|------|---------|
| **Project** | **Personal Computer Museum** – an interactive web site that tells the story of computing, from early binary machines to modern operating systems. |
| **Tagline** | *Explore the History of Computing* |
| **Target Audience** | Students, educators, hobbyists, and anyone curious about how computers have shaped society. |
| **Technology Stack** | Front‑end: **HTML + CSS + JavaScript** (the museum UI).  <br>Back‑end / Simulation layer: **Java** (used to build the “engine” that powers the interactive demos, command‑line simulator, and data‑representation tools). |
| **Why Java?** | Java’s platform‑independent nature, strong typing, and rich standard library make it ideal for building the logical core of the museum (binary calculator, OS simulator, virtual file system, etc.) while the UI remains in the web stack. |

---

## 2. Phase 0 Purpose  

Phase 0 establishes the **conceptual and technical foundation** required for every later phase of the roadmap. Learners will:

1. **Grasp the fundamentals of what a computer is** and how its hardware and software interact.  
2. **Translate core computer‑science ideas into small, runnable Java programs** that will later be wired into the museum UI.  
3. **Set up a professional Java development environment** that can be used throughout the project.  
4. **Adopt a growth‑mindset** for engineering work—critical for tackling the larger, more complex phases ahead.

---

## 3. Learning Objectives  

By the end of Phase 0, learners will be able to:

| Objective | Evidence (Deliverable) |
|-----------|------------------------|
| **Define a computer and its basic components** (CPU, memory, I/O, storage). | A 300‑word written introduction added to the museum “What is a Computer?” page (HTML). |
| **Explain binary, octal, decimal, and hexadecimal systems** and convert between them. | A **Java‑based binary calculator** (CLI) that accepts two numbers and an operation, displays results in binary/decimal/hex. |
| **Describe bits, bytes, and data representation** (signed/unsigned, ASCII, Unicode). | A **Java data‑representation utility** that shows how a given integer or character is stored as bits/bytes. |
| **Outline the role of an operating system** (process management, memory management, I/O). | A **simple OS simulator** written in Java that can start/stop “process” objects and display a textual schedule. |
| **Model a file system hierarchy** and understand directories vs. files. | A **virtual file‑system class library** (Java) with `File`, `Directory`, `create()`, `delete()`, `list()` methods. |
| **Use a command‑line interface (CLI) to interact with the virtual file system**. | A **Java CLI** that parses commands (`ls`, `cd`, `mkdir`, `rm`) and manipulates the virtual file system. |
| **Illustrate basic networking concepts** (client‑server, packets, IP). | A **static network diagram** (drawn with a web‑based tool) that will later be animated by Java code. |
| **Set up a Java development environment** (IDE, JDK, build tool, version control). | A **README.md** with step‑by‑step setup instructions and a committed Git repository. |
| **Articulate a personal growth‑mindset statement** for engineering. | A 150‑word reflection posted to the project wiki. |

---

## 4. Topic‑to‑Project Connection Map  

| Phase 0 Sub‑topic | Java‑centric Mini‑Project | How it Feeds the Museum |
|-------------------|---------------------------|--------------------------|
| **0.1 What is a Computer?** | Write a `Computer` class with fields for CPU, RAM, Storage, and a `toString()` that produces the introductory paragraph. | The `toString()` output is embedded on the museum’s “What is a Computer?” page. |
| **0.2 Binary & Number Systems** | `BinaryCalculator` (CLI) – supports addition, subtraction, conversion. | Results are displayed in an interactive widget on the site (JS calls the Java service via a simple REST endpoint). |
| **0.3 Bits, Bytes & Data Representation** | `DataViewer` – prints binary/hex/ASCII view of any `int` or `char`. | Used in the “Bits & Bytes” exhibit to show live transformations. |
| **0.4 Operating System Basics** | `SimpleOS` – manages a list of `Process` objects, schedules them round‑robin, prints a timeline. | Powers the “Operating System Simulator” page, showing how the OS switches tasks. |
| **0.5 File Systems & Directories** | `VirtualFS` – tree‑structure of `Directory`/`File` objects with CRUD operations. | Drives the “Virtual File System” tour where users click folders to explore. |
| **0.6 Command Line & Terminal** | `Terminal` – parses user commands and invokes `VirtualFS` methods. | Embedded as a terminal‑like widget on the museum site. |
| **0.7 How the Internet Works** | Static diagram (draw.io) + future Java animation stub. | Provides the visual foundation for the later “Network Simulator” module. |
| **0.8 Dev Environment Setup** | `setup.sh` / `setup.bat` scripts that install JDK, Maven/Gradle, and clone the repo. | Guarantees every learner starts from the same baseline. |
| **0.9 What is Programming?** | A set of **interactive coding challenges** (Java methods with unit tests) hosted on the site via JS‑powered editor. | Introduces visitors to “Try it yourself” sections throughout the museum. |
| **0.10 Growth Mindset for Engineering** | Markdown file `GROWTH.md` with personal reflection. | Showcased on the “Learner Stories” page. |

---

## 5. Deliverables & Assessment  

| Deliverable | Format | Success Criteria |
|-------------|--------|------------------|
| **Intro paragraph** | HTML snippet (≈300 words) | Clear, accurate description; integrated into museum page. |
| **Binary Calculator** | Java CLI (`BinaryCalculator.jar`) | Handles +, –, ×, ÷; converts between bases; passes supplied test cases. |
| **Data Viewer** | Java CLI (`DataViewer.jar`) | Shows binary, hex, ASCII for any input; documented usage. |
| **OS Simulator** | Java console app (`SimpleOS.jar`) | Simulates at least 3 processes; displays schedule; no runtime errors. |
| **Virtual File System** | Java library (`vfs.jar`) + unit tests | Supports create, delete, list, navigate; passes all JUnit tests. |
| **Terminal Interface** | Java console app (`Terminal.jar`) | Correctly parses `ls`, `cd`, `mkdir`, `rm`; interacts with VFS. |
| **Network Diagram** | PNG/SVG file | Accurately labels client, server, router, packets. |
| **Setup Scripts & README** | Bash/Batch + Markdown | New machine can clone repo, run `setup` and compile all Java code. |
| **Coding Challenges** | JS‑embedded editor + Java backend | Each challenge compiles, runs, and passes hidden tests. |
| **Growth‑Mindset Statement** | Markdown (`GROWTH.md`) | Reflective, 150 ± 30 words, demonstrates self‑awareness. |

*Assessment* will be **formative** (peer code reviews, automated JUnit tests) and **summative** (a rubric covering correctness, documentation, and reflection).

---

## 6. Resources  

| Category | Resource | Link / Access |
|----------|----------|---------------|
| **Java Language** | *Head First Java* (2nd ed.) – Chapters 1‑4 | https://www.oreilly.com |
| **IDE** | IntelliJ IDEA Community Edition | https://www.jetbrains.com/idea |
| **Build Tool** | Maven (or Gradle) – quick‑start archetype | https://maven.apache.org |
| **Version Control** | Git & GitHub Classroom | https://github.com |
| **Testing** | JUnit 5 documentation | https://junit.org/junit5 |
| **CLI Parsing** | Apache Commons CLI | https://commons.apache.org/proper/commons-cli |
| **Project Repo Template** | `pc-museum-phase0-template` (includes skeleton classes) | (insert repo URL) |
| **Design Tools** | draw.io (for network diagram) | https://app.diagrams.net |
| **Growth‑Mindset Reading** | *Mindset* by Carol Dweck – Chapter 1 | https://www.goodreads.com |

---

## 7. Timeline (Suggested 4‑Week Sprint)

| Week | Focus | Milestones |
|------|-------|------------|
| **1** | Project context, Java setup, **0.1** & **0.2** | Development environment ready; binary calculator functional. |
| **2** | **0.3**, **0.4** | Data viewer and OS simulator completed; unit tests passing. |
| **3** | **0.5**, **0.6** | Virtual file system library and terminal interface integrated. |
| **4** | **0.7**, **0.8**, **0.9**, **0.10** | Network diagram, setup scripts, coding challenges, growth‑mindset statement submitted. |
| **End of Sprint** | **Demo Day** – each learner presents their Phase 0 artifacts and explains how they will be used in the museum. | Peer feedback, instructor rubric grading. |

---

## 8. How Phase 0 Connects to Later Phases  

| Future Phase | Dependency on Phase 0 |
|--------------|-----------------------|
| **Phase 1 – Front‑End Integration** | Java services (calculator, OS simulator, VFS) will be exposed via simple HTTP endpoints (e.g., SparkJava) and consumed by the HTML/JS UI. |
| **Phase 2 – Advanced Java Topics** (OOP, Collections, Streams) | Builds on the `Process`, `File`, and `Directory` classes created in Phase 0. |
| **Phase 3 – Persistence & Databases** | The virtual file system will evolve into a persisted model using SQLite/JPA. |
| **Phase 4 – Deployment & CI/CD** | The Maven/Gradle build created in Phase 0 will be extended with Docker and GitHub Actions for automated deployment of the museum site. |

---

## 9. Closing Note  

Phase 0 is **the launchpad**: you will translate the abstract ideas that underpin computing into concrete Java programs, and those programs will become the interactive heart of the Personal Computer Museum. Embrace the challenges, iterate quickly, and keep a growth‑mindset—every bug you fix is a step toward a richer learning experience for future museum visitors.  

**Happy coding!** 🚀