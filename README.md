# Hyunuk Yang

**AI Application Engineering · RAG · Agents · Multimodal**

I build RAG and agent applications, and improve them through experiments and failure analysis. My work connects retrieval, dialogue state, and tool execution with the interfaces people use to review and correct results.

Computer Science and Engineering undergraduate, **Sogang University**  
Mar 2021 – Expected graduation: Feb 2027 · [hyunuk200202@gmail.com](mailto:hyunuk200202@gmail.com)

## Projects

### [4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)
*Jul–Sep 2026 · Team project*

An industry-linked RAG chatbot PoC answering questions across six service areas using public information from the Korea Deposit Insurance Corporation.

**My role:** Overall architecture and project management; Q-Form clarification flow, routing, retrieval and tuning, and web integration.

- **Kept user context connected to retrieval.** Short follow-up questions could be classified into a different service area and lose previously collected conditions. I distinguished follow-ups from topic changes, carried confirmed conditions into retrieval and attachment selection, and separated the retrieval query from the user's original message. [Context handling](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/f9671aae7fa826104ebd7e77598aa5ad0deac745) · [Retrieval integration](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/d1cd6f55210042ee8c5d7ba9889e8c44f1dc9890)
- **Connected administrative controls to answers.** Integrated the user and admin web applications so settings reached retrieval, answer generation, and validation. [Implementation](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/e9a97816c312471bc9a6b0e5d26c37e2879710bc)
- **Revisited the evaluation baseline.** To examine possible inflation from wording close to the source documents, I compared **150 question pairs** with the same gold answers. More natural wording lowered hit@3 from **0.853 to 0.753**; I used that gap to reassess the baseline for subsequent improvements. [Paired evaluation](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b) · [Baseline correction](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/355d08827273067273134e0fd13898e3f17b64a5)

### [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)
*Sep 2026–present · Two-person study project, with independent implementations and shared findings*

Experiments with RAG, routing, and tool-using agents, using a shared format to record and compare quality, cost, latency, and failures.

**My role:** Agent implementations, evaluation tooling, routing, and integration checks.

- **Chose an architecture from measured trade-offs.** A single agent and a handoff architecture both passed **20/20 fixed tasks**, while handoff increased p50 latency by **about 63%** and cost by **about 32%**. I chose the single-agent design for these small tool-based tasks, with a plan to reassess as task complexity grows. [Comparison](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)
- **Checked the inputs to tools.** An agent invented numbers for a calculation that required looking up a policy first. I added a check for whether the numbers were grounded in the question and redirected unsupported calculations through retrieval before execution. [Fix and regression test](https://github.com/GongChangJin/hands-on/commit/8000b1f45652e88d040a3a40a785db6d1d959716)
- **Corrected the measurement code.** API request counts from one experimental condition were leaking into the next. I switched to per-condition counter deltas and documented historical latency values that could not be reconstructed without the raw samples. [Correction and audit](https://github.com/GongChangJin/hands-on/commit/d2c6b2ca6672ff719cd62b18bebb09e86008d472)

### [ContextWeld](https://github.com/ukkhnn/PAC2026)
*Oct 2026–present · Started as a two-person hackathon project; continuing independently*

A system under development that connects markings on shipbuilding parts with work orders, drawings, and welding references to suggest candidate welding conditions and flag items for review.

**My role:** Planning and development during the hackathon, followed by continued individual development.

- **Validated what a marking refers to.** Added checks that connect recognized markings to the selected part and joint, rejecting unrelated text and ambiguous relationships. [Binding checks](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7)
- **Made corrections reviewable.** Preserved original recognition results, stored user corrections separately, and applied only selected corrections to a new review. The demo connects review to a simulated receiver and prevents duplicate transmission for the same request. [Correction and review workflow](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

### [Opticore-AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)
*Mar–Jul 2026 · Team capstone project*

A multi-robot warehouse simulation combining path planning, localization, and fleet coordination in ROS 2 and Gazebo.

**My role:** System architecture, Gazebo environment, A* planning, fleet logic, and multi-robot integration.

- **Traced localization errors to the data source.** Gazebo sensor and motion topics were shared across robots, so ROS bridges were republishing mixed data. I separated topics and frames from URDF generation through Gazebo and the bridges. A recorded simulation run confirmed **all four robots reaching their respective goals**. [Topic isolation](https://github.com/sogang-opticore/opticore-amr/commit/58a9feb088d3d1361a2d616e53fb7b3eb88a2bd6) · [Run report](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md)
- **Isolated a map-boundary error.** A wall was being tracked as a moving obstacle when a cluster center fell outside the map grid. After fixing the boundary condition, phantom wall tracks fell from **10 to 0** in a same-route simulation comparison. Remaining object-detection misses were tracked as a separate issue. [Fix and comparison](https://github.com/sogang-opticore/opticore-amr/commit/5b76ac066719f1a49a14b835648e5288672fd1aa)

## In Progress

**OptiDocu** · Oct 2026–present · Industry–university capstone project · Private repository

Preparing a PoC to help automotive suppliers review RFQs, gather evidence across departments, draft responses, and check omissions or conflicts. My work focuses on workflow definition, synthetic business data, and evaluation design. The project is currently in **data preparation and review**: documenting a fictional company's operating criteria and separating task inputs from evaluation answers.

**[personal-ai / Agent Workspace](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)** · Personal project

Building a web workspace for development agents running on a Mac mini, covering task state, queued instructions, approvals, and code changes. I implement the execution lifecycle and web/runtime integration. Current verification covers a real model task, HTTPS access, and preservation of completed tasks across a server-process restart. [Implementation and verification scope](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)

## Learning in Practice

**[LikeLion AI/NLP Study](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP)** brings together study sessions and exercises from the fifth LikeLion AI/NLP bootcamp, along with self-directed study during 4MATION.

I implemented attention, an encoder, and a decoder with PyTorch tensor operations, then trained and ran a small translation example. Questions from the RAG project led to further notebooks on retrieval metrics, label quality, evaluation bias, and confidence intervals, using minimal implementations and simulations. [Transformer exercise](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/blob/main/StudySession_FUNDAMENTAL/Fundatmental_ipynb/FUNDAMENTAL_day10~14_TransformerWithoutMagic.ipynb) · [RAG evaluation notebooks](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/tree/main/selfstudy_rag_for4MATION/C_evaluation)

- **[Opticore AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo)** — Comparisons of rule-based navigation, behavior cloning, and PPO, including checks on safety constraints and evaluation conditions.
- **[CS231n PyTorch Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation)** — PyTorch fundamentals and KNN implementation experiments.

## Tools

**Models & retrieval:** PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK  
**Applications & evaluation:** Python, FastAPI, JavaScript, SQLite, pytest, Arize Phoenix  
**Systems & robotics:** ROS 2, Gazebo, Linux, Git
