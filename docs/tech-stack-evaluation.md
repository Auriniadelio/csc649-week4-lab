# Tech Stack Evaluation

## Project

A Narrative-Driven Technical Support Simulation Game Using Finite State Machine for Cybersecurity Literacy

## Requirements that drive the decision

* **FR1**: The system shall execute a Finite State Machine (FSM) to manage state transitions across distinct gameplay phases (Main Menu, Workstation Shift, Personal Phone Break, Ticket Diagnostic Mode, and Shift Summary).
* **FR3**: The system shall provide diagnostic inspection tools (including a domain lookup tool, email header inspector, and internal threat knowledge wiki) to evaluate evidence artifacts.
* **NFR1**: The system shall complete state transitions (such as switching between the Workstation desktop and the Personal Phone interface) within 0.5 seconds of user input.
* **NFR2**: The system shall maintain a rendering performance of at least 60 frames per second (FPS) on baseline target desktop hardware during active gameplay.
* **NFR3**: The system shall parse and load external scenario JSON data files into the FSM game logic within 2 seconds during initial application boot.

## Options

* **Option A:** Godot Engine 2D (GDScript)
* **Option B:** Unity Engine 2D (C#)
* **Option C:** Web Application (React + HTML5 Canvas / Phaser.js)

## Decision matrix

Weight: how important the criterion is for YOUR project (1 = low, 5 = high).
Score: how well each option does (1 = poor, 5 = excellent).
Weighted score = weight x score. Add them up for each option.

| Criterion                        | Weight | A score | B score | C score |
| ---------------------------------|--------|---------|---------|---------|
| Fits my requirements             | 5      | 5       | 5       | 3       |
| Skills I already have            | 4      | 4       | 3       | 4       |
| Time to build before my deadline | 5      | 5       | 3       | 3       |
| Free hosting and tools           | 4      | 5       | 4       | 5       |
| Performance and security needs   | 3      | 5       | 4       | 4       |
| Room to grow later               | 3      | 4       | 5       | 3       |
| **Total (weighted)** | **24** | **113** | **95** | **87** |

*Calculations:*

* **Option A (Godot):** $(5\times5) + (4\times4) + (5\times5) + (4\times5) + (3\times5) + (3\times4) = 25 + 16 + 25 + 20 + 15 + 12 = 113$
* **Option B (Unity):** $(5\times5) + (4\times3) + (5\times3) + (4\times4) + (3\times4) + (3\times5) = 25 + 12 + 15 + 16 + 12 + 15 = 95$
* **Option C (React/Phaser):** $(5\times3) + (4\times4) + (5\times3) + (4\times5) + (3\times4) + (3\times3) = 15 + 16 + 15 + 20 + 12 + 9 = 87$

## Decision record

* **Context:** Developing a 2D UI-driven tech support simulator within strict FYP submission deadlines. The software requires custom Finite State Machine (FSM) state management, dynamic external JSON scenario loading, fast UI responsiveness (<0.5s transitions), and zero licensing costs.

* **Decision:** **Option A: Godot Engine 2D (GDScript)**
* **Reasons:**
1. **Native 2D & FSM Optimization:** Godot's node-and-signal architecture makes building Finite State Machines and 2D UI canvas interfaces straightforward without engine bloat, easily meeting NFR1 (<0.5s transitions) and NFR2 (60 FPS).
2. **Fast Development Iteration:** GDScript’s Python-like syntax and Godot's built-in JSON parsing allow rapid prototyping of diagnostic tools and external content pipelines, saving time before the project deadline.
3. **Cost & Portability:** Godot is 100% free and open-source (MIT License) with lightweight build binaries that can be hosted on itch.io or exported as standalone desktop executables without royalty or subscription concerns.


* **Consequences:**
* *What becomes easy:* Implementing UI layouts, writing clean node-based FSM logic, parsing external JSON scenarios, and rapid testing due to instant project launch times.
* *What becomes hard:* Sourcing pre-made specialized UI assets, as Godot's third-party asset marketplace is smaller than Unity's, requiring custom UI styling and assets.


* **Risks and next review:**
* *Risk:* Potential learning curve adapting to Godot's node/signal pattern if unfamiliar with game engine signals.
* *Next review:* Milestone 2 (Core Prototype Phase), where state transition latency and JSON parsing speed will be formally benchmarked against NFR1 and NFR3.