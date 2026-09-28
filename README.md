# Hi, I'm Hyunuk Yang 👋

### AI Engineer · AI Systems · Robotics · LLM

> **I build AI systems through experimentation, evaluation, and reliable integration.**

AI를 단순히 적용하는 것보다
**문제를 정의하고 → 실험하고 → 평가하고 → 실패 조건을 분석하고 → 실제 시스템에 통합하는 과정**에 관심이 있습니다.

---

## 🚀 What I Do

| Area                          | Experience                                                           |
| ----------------------------- | -------------------------------------------------------------------- |
| 🤖 **Robotics / Physical AI** | Multi-AMR navigation, SLAM, A*, Fleet Management, Gazebo             |
| 🧠 **Reinforcement Learning** | PPO, Stable PPO, behavior cloning, safety shield                     |
| 🔎 **RAG / LLM**              | Hybrid Retrieval, BM25, RRF, Reranking, Query Routing                |
| 🧩 **AI Agents**              | Agent evaluation, routing, tool integration, multi-agent experiments |
| 🛡️ **AI Reliability**        | Guardrails, validation gates, OOS handling, fail-closed design       |
| ⚙️ **AI Systems**             | FastAPI, evaluation pipelines, reproducibility, regression testing   |

---

# ⭐ Featured Projects

## 01. Opticore-AMR

### Multi-AMR Warehouse Navigation System

**Problem**
Multiple autonomous mobile robots must navigate a warehouse while avoiding collisions and resolving conflicts.

**Architecture**

```text
LiDAR / Camera
      ↓
 SLAM / AMCL
      ↓
 A* Global Planner
      ↓
 DWA Local Planner
      ↓
 YOLOv8
      ↓
 Fleet Management
      ↓
   Multi-AMR
```

**My Contribution**

* Designed overall system architecture
* Built Gazebo warehouse environment
* Implemented A* global planning
* Designed Fleet Management logic
* Integrated navigation components for multi-robot operation

**Validation**

* Independent goal tests: **4 / 4 successful**
* Pose error: **0.18–0.49 m**
* Collision overlap samples: **0 / 1,216**
* Deadlock tests: **23 / 23**
* Proactive priority tests: **13 / 13**

**Focus:** `Robotics` `Navigation` `Multi-Agent` `Gazebo`

---

## 02. Opticore-AMR-Lite

### Learning-Based Navigation Feasibility Study

> **Technical spike:** Can learning-based navigation improve or complement a rule-based navigation system?

Started from the limitations observed in **A* + DWA** navigation and built a lightweight 2D LiDAR simulation environment.

**Experiments**

```text
Rule-based
    ├── Behavior Cloning
    ├── DAgger-lite
    ├── PPO
    ├── Stable PPO
    └── Safety Shield
```

**Experiment Setup**

* 270° LiDAR
* 72 rays / frame
* 4-frame observation stack
* **296-dimensional observation**
* Custom reward design
* PPO / Stable PPO comparison
* Safety shield experiment

**Phase 0 Result**

| Method                  | Success | Collision | Timeout |
| ----------------------- | ------: | --------: | ------: |
| Rule baseline           |   87.5% |     12.5% |      0% |
| Stable PPO · Shield OFF |   87.5% |     12.5% |      0% |
| Stable PPO · Shield ON  |     75% |     12.5% |   12.5% |

> The experiment is intentionally treated as a **feasibility study**, not as evidence that RL outperforms the rule-based baseline.

**Focus:** `Reinforcement Learning` `PPO` `Simulation` `Safety`

---

## 03. 4MATION

### Evaluation-Driven RAG Application

Built an end-to-end RAG system with retrieval, evaluation, routing, grounding and operational controls.

```text
Web Collection
      ↓
Parsing / Metadata
      ↓
Chunking
      ↓
Dense Retrieval ──┐
                  ├─→ RRF / Boost
BM25 ─────────────┘
      ↓
Query Routing
      ↓
Answer Generation
      ↓
Validation Gate
      ↓
Citation / OOS
```

**My Contribution**

* Designed retrieval and evaluation architecture
* Implemented crawler / parser / chunking pipeline
* Implemented Dense + BM25 + RRF retrieval
* Designed **Q-Form metadata boosting**
* Built evaluation harness and GT pipeline
* Investigated leakage and label quality
* Implemented query routing and OOS handling
* Built FastAPI / Web UI integration
* Added reproducibility and freshness controls

**Current Scale**

* **38 documents**
* **181 chunks**
* **450 natural-language questions**
* **450 retrieval ground-truth records**
* **47 Python tests**

**Focus:** `RAG` `Information Retrieval` `Evaluation` `LLM` `FastAPI`

---

## 04. GCJ Hands-on Lab

### AI Agent Capability Evaluation & Integration

A continuous hands-on lab for evaluating new AI technologies before integrating them into a common system.

```text
Discover
   ↓
Hands-on Experiment
   ↓
Metrics / Failure Analysis
   ↓
Decision
   ↓
Mini Project
   ↓
System Integration
```

**Implemented Capabilities**

* Agent Evaluation
* Local LLM
* Agentic RAG
* Multimodal
* Research
* LLM Router
* Computer Use
* Coding
* Cybersecurity

**System Design**

```text
TaskRequest
     ↓
   Router
     ↓
Agent Adapter
     ↓
 Tool Execution
     ↓
EvaluationRecord
```

**Reliability**

* **213 local regression tests**
* **1,421 result records**
* **10 / 10 integration replay**
* **10 / 10 route / agent / status match**
* **4 / 4 live smoke tests**
* Fail-closed behavior for invalid formats, unsafe conditions and local-only violations

**Focus:** `AI Agents` `Evaluation` `LLM Router` `Reliability`

---

## 05. VeriFlow

### LLM Output Validation & Guardrail

Built a separate validation layer for an LLM-based CS chatbot.

```text
Customer Question
       ↓
   LLM Draft
       ↓
  Policy Lookup
       ↓
 Cross Validation
       ↓
 ┌─────┼─────┐
GREEN YELLOW RED
  ↓      ↓      ↓
Send   Correct  Block
```

**My Contribution**

* Backend implementation
* n8n validation workflow
* Upstage API integration
* Policy extraction pipeline
* Structured rule validation

**Key Idea**

> **Don't trust the LLM output directly.
> Validate it before it reaches the user.**

**Focus:** `LLM` `Guardrails` `Validation` `n8n`

---

# 🧠 How I Build AI Systems

```text
Problem Definition
        ↓
Technical Spike
        ↓
Small Experiment
        ↓
Comparison / Evaluation
        ↓
Failure Analysis
        ↓
Safety / Reliability
        ↓
System Integration
        ↓
Theory / Learning Feedback
```

I especially care about:

* What happens when the model fails?
* Can the result be reproduced?
* What assumptions does the experiment make?
* Where does uncertainty enter the system?
* How should the system fail safely?
* Can an experiment become a maintainable system?

---

# 📚 Foundations

### Machine Learning / Deep Learning

* Transformer implemented with PyTorch
* KNN
* Linear Classifier
* CS231n
* NLP / IR metrics
* Evaluation methodology
* Data leakage / labeling analysis

### Systems / CS

* Operating Systems
* PintOS
* System-level programming
* Software architecture

---

# 🛠️ Tech Stack

**AI / ML**

`PyTorch` `Transformers` `PPO` `RAG` `LLM` `BM25` `FAISS`

**Robotics**

`ROS` `Gazebo` `SLAM` `AMCL` `A*` `DWA` `YOLOv8`

**Backend / Systems**

`Python` `FastAPI` `n8n` `Git` `Linux`

**Evaluation / Reliability**

`Regression Testing` `Ground Truth` `Guardrails` `OOS` `Fail-Closed` `Reproducibility`

---

# 🔗 Selected Projects

* [Opticore-AMR](https://github.com/ukkhnn/Opticore-AMR)
* [Opticore-AMR-Lite](https://github.com/ukkhnn/Opticore-AMR-Lite)
* [4MATION](https://github.com/ukkhnn/4MATION)
* [GCJ Hands-on Lab](https://github.com/ukkhnn/GCJ)
* [VeriFlow](https://github.com/ukkhnn/VeriFlow)

---

## 👋 About Me

**AI Engineer focused on turning AI technologies into measurable, reliable systems.**

My interests sit at the intersection of:

**Robotics × Reinforcement Learning × RAG × AI Agents × Reliability**

I enjoy finding the boundary between
**“it works in a demo”** and **“it works as a system.”**

[GitHub](https://github.com/ukkhnn)
