# Hi, I'm Hyunuk Yang 👋

### AI Engineer · AI Systems · Robotics · LLM

I build AI systems through **experimentation, evaluation, and reliable integration**.

My interests span from **Robotics and Learning-based Navigation** to **RAG, LLM Agents, and AI Reliability**.

```text
Problem
   ↓
Technical Spike
   ↓
Evaluation
   ↓
Failure Analysis
   ↓
Safety / Reliability
   ↓
System Integration
```

---

## 🚀 What I'm Working On

| Area                      | Focus                                            |
| ------------------------- | ------------------------------------------------ |
| 🤖 Robotics               | Multi-AMR navigation, planning, fleet management |
| 🧠 Reinforcement Learning | Learning-based local navigation                  |
| 🔎 RAG / LLM              | Retrieval, evaluation, routing, grounding        |
| 🧩 AI Agents              | Capability evaluation, routing, integration      |
| 🛡️ AI Reliability        | Guardrails, validation, fail-closed systems      |

---

## ⭐ Featured Projects

### 🤖 [Opticore-AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)

**Multi-AMR warehouse navigation system**

An intelligent warehouse simulation connecting perception, localization, planning, and multi-robot operation.

```text
LiDAR / Camera
      ↓
SLAM / AMCL
      ↓
A* Global Planning
      ↓
DWA Local Planning
      ↓
Fleet Management
      ↓
Multi-AMR Operation
```

**My focus**

* System architecture
* Gazebo warehouse environment
* A* Global Planner
* Fleet Management
* Multi-AMR integration

**Validation**

* 4/4 independent goals passed
* 0 collision overlap across 1,216 collision samples
* Fleet priority / deadlock management tests

`ROS` `Gazebo` `A*` `DWA` `YOLOv8` `SLAM` `AMCL`

---

### 🧠 [Opticore-AMR-Lite](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo)

**Learning-based Navigation Feasibility Study**

Can learning-based navigation address limitations observed in rule-based local planning?

I built a lightweight 2D LiDAR environment to compare:

```text
Rule-based
    │
    ├── Behavior Cloning
    ├── DAgger-lite
    ├── PPO
    └── Stable PPO
```

The environment uses a **296-dimensional observation** consisting of LiDAR history and navigation-related state variables.

Phase 0 evaluation showed **87.5% success for the selected Stable PPO checkpoint**, while the rule baseline also achieved 87.5% under the same limited evaluation setup.

Rather than treating this as a final performance result, the project is currently being used to investigate **convergence, safety, reproducibility, and generalization**.

`PyTorch` `PPO` `LiDAR` `Reinforcement Learning` `Simulation`

---

### 🔎 [4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)

**Evaluation-driven RAG Application**

A RAG application covering the full pipeline from document collection to retrieval, generation, validation, and user/admin interfaces.

```text
Web Collection
      ↓
Parsing / Chunking
      ↓
Dense Retrieval + BM25
      ↓
RRF / Metadata Boost
      ↓
Query Routing / Q-Form
      ↓
Answer Generation
      ↓
Validation / OOS
      ↓
API / UI / Admin
```

**Key work**

* Hybrid Retrieval
* RRF
* Q-Form design
* Retrieval evaluation framework
* OOS handling
* Validation and freshness guard
* Evaluation harness and regression testing

The project also led to deeper investigation of **ground truth quality, evaluation leakage, corpus drift, micro/macro evaluation, and reproducibility**.

`RAG` `FAISS` `BM25` `RRF` `FastAPI` `LLM` `Evaluation`

---

### 🧩 [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)

**AI Agent Capability Evaluation & Integration**

A hands-on lab for independently validating AI capabilities before integrating them into a larger agent system.

```text
Capability
    ↓
Common Contract
    ↓
Evaluation
    ↓
Router
    ↓
Agent Adapter
    ↓
Security Gate
    ↓
Integration
```

Hands-on 01–09 cover areas including:

* Agent Evaluation
* Local LLM
* Agentic RAG
* Multimodal
* Research
* LLM Router
* Computer Use
* Coding
* Cybersecurity

**Validation**

* 213 local regression tests passed
* 1,421 result records passed contract validation
* 10/10 integration replay
* 4/4 integration live smoke paths

A major focus is **safe failure**:

```text
Timeout
Format Error
Policy Violation
       ↓
   Fail Closed
```

`Agents` `LLM` `RAG` `Evaluation` `Security` `Integration`

---

### 🛡️ [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19)

**LLM Output Validation & Guardrail**

A guardrail system that validates LLM-generated customer-service responses against policy documents before they reach users.

```text
LLM Answer
    ↓
Policy Retrieval
    ↓
Cross Validation
    ↓
GREEN / YELLOW / RED
    ↓
Send / Correct / Block
```

**My focus**

* Backend
* n8n validation workflow
* Upstage API integration

The system uses policy extraction, structured rules, LLM cross-validation, and risk-based response handling.

`n8n` `Upstage` `LLM` `Guardrail` `Validation`

---

## 🧪 How I Build

Across different projects, I tend to follow the same loop:

```text
01. Define the failure
        ↓
02. Build a small experiment
        ↓
03. Establish a measurable evaluation
        ↓
04. Analyze failures
        ↓
05. Add safety / reliability mechanisms
        ↓
06. Integrate into the larger system
```

I don't want to stop at **"it works."**

I want to understand:

* When does it fail?
* Can the result be reproduced?
* What should happen when the system is uncertain?
* Can the failure be detected?
* Can the system fail safely?
* Does the experiment actually support the conclusion?

---

## 📚 Learning & Foundations

I also study the underlying principles behind the systems I build.

### Deep Learning / NLP

* Transformer components implemented with PyTorch
* Scaled dot-product attention
* Multi-head attention
* Encoder / Decoder
* KNN
* Linear Classifier
* CS231n implementations
* NLP / Information Retrieval evaluation

### Computer Science

* Operating Systems
* System Programming
* C / C++
* Data Structures & Algorithms
* Computer Architecture
* Python

---

## 🛠️ Technologies

```text
Languages
Python · C · C++

AI / ML
PyTorch · Reinforcement Learning · NLP · Computer Vision

LLM / RAG
RAG · FAISS · BM25 · RRF · LLM Agents · Guardrails

Robotics
ROS · Gazebo · SLAM · AMCL · Navigation

Backend
FastAPI · SQLite · REST API

Engineering
Testing · Evaluation · Reproducibility · System Integration
```

---

## 📌 Selected Repositories

* [Opticore-AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)
* [Opticore-AMR-Lite](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo)
* [4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)
* [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)
* [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19)
* [Self Study Deep Learning](https://github.com/ukkhnn/Self_Study_Deep_Learning)
* [CS231n PyTorch Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation)

---

## 📫 Contact

GitHub: [@ukkhnn](https://github.com/ukkhnn)
