# Hi, I'm Hyunuk Yang

I study computer science and engineering at Sogang University. I've built chatbots that look things up in documents, a tool that reads markings on ship parts, and a simulator with several robots. I'm curious about what happens after a model produces an answer or a detection. I also like figuring out where things went wrong when a run surprises me.

[Email](mailto:hyunuk200202@gmail.com) · [한국어](README.md)

[Things I've built](#things-ive-built) · [Agents and workflow automation](#agents-and-workflow-automation) · [Study notes](#study-notes) · [More repositories](#more-repositories)

## Things I've built

### 4MATION — RAG that keeps track of the conversation

A team prototype built with an industry partner. It uses public information from the Korea Deposit Insurance Corporation to answer questions across six service areas. I led the architecture and coordinated the project. I built the Q-Form clarification flow, worked on routing and retrieval tuning, and connected the web interface.

- A short follow-up can reuse the conditions already established in the conversation. I added a check for topic changes, passed those conditions to retrieval and attachment selection, and kept the search query separate from the original message.
- To make web settings take effect in the answers, I connected the user and admin web applications with retrieval, generation, and validation. The current user interface uses FastAPI and a static web UI.
- I wanted to see how much question wording mattered. In an earlier test with 150 pairs that shared the same reference answers, more natural wording brought hit@3 down from 0.853 to 0.753. This prompted a closer look at wording-related evaluation bias. Deployment and operational validation are the next steps for version 2.0.

[Code](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [Context handling](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/f9671aae7fa826104ebd7e77598aa5ad0deac745) · [Retrieval integration](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/d1cd6f55210042ee8c5d7ba9889e8c44f1dc9890) · [Paired evaluation](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b)

### ContextWeld · PAC2026 — From visual markings to work instructions

A project connecting markings and visual relationships on shipbuilding parts with work orders, drawings, and welding procedure specifications (WPS). I worked on planning and development in a two-person hackathon team, and I’ve kept working on it on my own.

- VLM observations of parts and joints are checked against work orders. Ambiguous targets go to review. Visual observations and conditions retrieved from documents retain separate provenance.
- A real-model run on stored RGB images connected recognition, document evidence retrieval, registered welding conditions, a common work specification, Hyundai/Doosan format conversion, and a mock HTTP receiver.
- Original recognition results remain intact, selected user corrections feed a new review, and duplicate transmission of the same request is blocked. So far I’ve tested the flow from stored images through to a mock receiver. Physical welding and autonomous robot recapture are outside that test scope.

[Code](https://github.com/ukkhnn/PAC2026) · [Recognition-to-delivery run](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md) · [Target binding checks](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7) · [Correction and review](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

### Opticore AMR + Autonomy — Perception, planning, and learning

A team capstone on multi-robot warehouse simulation using ROS 2 and Gazebo, followed by learning-based navigation experiments. My AMR work covered multi-robot configuration, fleet coordination, sensor fusion, and connecting CCTV obstacles to path planning.

- When robot positions looked wrong, I traced the issue to sensor data mixing across robots. I separated the Gazebo topics and frames at the source. A bounded simulation run confirmed all four robots reaching their respective goals.
- For a fixed CCTV scene where a small person was missed, I used background subtraction, projected detections to the floor, and connected an obstacle layer to A*. I checked that detections appeared on the map. The effect on rerouting still needs testing.
- [Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) compares rule-based control, behavior cloning, and PPO. In a lightweight environment, the evaluation covered five training seeds and 4,160 total test episodes: PPO best achieved 85.4% success, versus 86.2% for the rule baseline. The first sample was small, so I ran another comparison with separate data for checkpoint selection and testing.

[AMR code](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [Four-robot run](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md) · [CCTV experiment](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/cctv/PROGRESS.md) · [Autonomy evaluation](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo/blob/dev/experiments/m1_reproducibility/RESULTS.md)

## Agents and workflow automation

| Project | What I worked on | Results and current status |
| --- | --- | --- |
| [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo) | Two-person study with independent implementations and shared findings. Agent implementations, evaluation tooling, and routing | Single-agent and handoff designs both passed 20/20 fixed tasks. Handoff increased p50 latency by about 63% and cost by about 32%, informing a single-agent choice for these small tool-based tasks. [Comparison](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md) |
| [personal-ai / Agent Workspace](https://github.com/ukkhnn/personal-ai) | Personal project. Per-task worktrees, queued instructions, approvals, execution state, and web UI | Verified a real DeepSeek task, HTTPS access, and completed-task persistence after a server-process restart on a Mac mini. [App implementation is on a working branch](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md); physical cross-device use and real concurrent tasks await validation |
| [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19) | Upstage team hackathon. n8n verification workflow design and Upstage API integration | Compares responses with policy documents and routes them to pass, correction, or blocking. Repository: `upstage_hackathon_team19`; the live demo has ended |
| **OptiDocu** · Private | Team capstone supporting automotive RFQ review. Workflow definition, synthetic business data, and evaluation design | Prepared separate stage-specific inputs and evaluation answers for intake, consolidation, and pre-submission review. Currently at the data/evaluation preparation stage; product and model-performance evaluation are subsequent work |

## Study notes

When I get stuck on something in a project, I like to build a small version and see how it works. Here are some of my deep learning exercises and coursework on operating systems, memory, I/O, and graphics.

| Public learning repository | Focus |
| --- | --- |
| [LikeLion_26S_BootCamp_AI_NLP](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) | AI/NLP bootcamp and self-study. A small translation exercise with attention, encoder, and decoder implemented through PyTorch tensor operations; experiments on RAG metrics, label quality, and evaluation bias |
| [CS231n-Pytorch-Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) | CS231n-based PyTorch tensor exercises and KNN implementation |
| [Self_Study_Deep_Learning](https://github.com/ukkhnn/Self_Study_Deep_Learning) | Personal notes and implementations for deep learning study |

I keep my coursework in private repositories.

| Course · Repository | Implementation and study |
| --- | --- |
| Operating Systems · `cse4070-pintos` | Processes and system calls, priority scheduling, and virtual memory. The later cleanup version passed 226/226 QEMU tests |
| Introduction to Computer Systems · `computer-systems-labs` | C bit operations, x86-64 program analysis, and cache simulation |
| Embedded System Software · `cse4116-openssd`, `CSE4116_PRJ3` | OpenSSD host I/O, FTL, firmware, and a kernel patch. Preserved submissions and documented runtime/hardware dependencies |
| Basic Computer Graphics · `basic-computer-graphics` | C++/OpenGL coursework, with submitted source, shaders, and textures distinguished from provided code |

## Tools I use

**AI and retrieval** — PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK<br>
**Applications and evaluation** — Python, FastAPI, JavaScript, SQLite, pytest, n8n<br>
**Systems and robotics** — C/C++, ROS 2, Gazebo, Linux, Git

## More repositories

Here are a few earlier versions and forks I use to follow along with tutorials.

<details>
<summary><strong>Archives, learning forks, and this profile</strong></summary>

| Repository | Purpose |
| --- | --- |
| [4MATION_archive-on-ukkhnns-repo](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo) | Implementation and evaluation records from the initial RAG PoC, separate from current development |
| [practice-let-s-build-gpt](https://github.com/ukkhnn/practice-let-s-build-gpt) | Fork for following Andrej Karpathy's GPT implementation tutorial |
| [build-with-ai-handson-campus-hands-on](https://github.com/ukkhnn/build-with-ai-handson-campus-hands-on) | Fork of Build with AI campus hands-on materials |
| [oh-my-claudecode](https://github.com/ukkhnn/oh-my-claudecode) | Fork for exploring Claude Code orchestration. Upstream: Yeachan-Heo/oh-my-claudecode |
| [ukkhnn](https://github.com/ukkhnn/ukkhnn) | Korean and English versions of this profile |

</details>

<details>
<summary><strong>Repositories in organizations I work with</strong></summary>

- **4MATION:** [Current development](https://github.com/likelion-4MATION/4MATION) · [Early archive](https://github.com/likelion-4MATION/4MATION_archive)
- **Opticore:** [AMR](https://github.com/sogang-opticore/opticore-amr) · [Autonomy](https://github.com/sogang-opticore/opticore-amr-autonomy) · `opticore-optidocu` is private
- **GongChangJin:** [hands-on](https://github.com/GongChangJin/hands-on) · `idea-lab` · [projects](https://github.com/GongChangJin/projects) · [project-template](https://github.com/GongChangJin/project-template)

</details>

Feel free to [email me](mailto:hyunuk200202@gmail.com) if you’d like to chat about any of these projects.
