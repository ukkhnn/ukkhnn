# Hi, I'm Hyunuk Yang

**I build AI applications that connect documents, visual observations, and sensor data to the work people need to do.**

My projects range from document-grounded chatbots to visual recognition of industrial parts and multi-robot simulations. I enjoy connecting model outputs to useful workflows, reproducing failures, and tracing them back to their causes.

**Computer Science and Engineering, Sogang University** · Expected graduation: February 2027<br>
[Email](mailto:hyunuk200202@gmail.com) · [한국어](README.md)

[Selected projects](#selected-projects) · [Agents and workflow automation](#agents-and-workflow-automation) · [Learning and CS foundations](#learning-and-cs-foundations) · [More repositories](#more-repositories)

## Selected projects

### 4MATION — RAG that keeps track of the conversation

An **industry-linked team PoC** answering questions across six service areas using public information from the Korea Deposit Insurance Corporation. I led architecture and project management and implemented the Q-Form clarification flow, routing, retrieval tuning, and web integration.

- **Preserved context across short follow-ups.** I distinguished follow-up questions from topic changes, carried confirmed conditions into retrieval and attachment selection, and separated retrieval queries from users' original messages.
- **Connected configuration to actual answers.** I integrated the user and admin web applications with retrieval, generation, and validation. The current user interface uses FastAPI and a static web UI.
- **Revisited the evaluation questions.** In a historical comparison of 150 question pairs sharing the same gold answers, natural wording lowered hit@3 from 0.853 to 0.753. This prompted a closer look at wording-related evaluation bias. Deployment and operational validation are the next steps for version 2.0.

[Code](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [Context handling](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/f9671aae7fa826104ebd7e77598aa5ad0deac745) · [Retrieval integration](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/d1cd6f55210042ee8c5d7ba9889e8c44f1dc9890) · [Paired evaluation](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b)

### ContextWeld · PAC2026 — From visual markings to work instructions

A project connecting markings and visual relationships on shipbuilding parts with work orders, drawings, and welding procedure specifications (WPS). **I handled planning and development in a two-person hackathon team and have continued developing it independently.**

- **Separated observations from work requirements.** VLM observations of parts and joints are checked against work orders; ambiguous targets go to review. Visual observations and conditions retrieved from documents retain separate provenance.
- **Connected recognition to downstream work.** A real-model run on stored RGB images connected recognition, document evidence retrieval, registered welding conditions, a common work specification, Hyundai/Doosan format conversion, and a mock HTTP receiver.
- **Made corrections traceable.** Original recognition results remain intact, selected user corrections feed a new review, and duplicate transmission of the same request is blocked. Verification currently covers stored images and simulated reception; physical welding and autonomous robot recapture remain outside the completed scope.

[Code](https://github.com/ukkhnn/PAC2026) · [Recognition-to-delivery run](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md) · [Target binding checks](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7) · [Correction and review](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

### Opticore AMR + Autonomy — Perception, planning, and learning

A **team capstone on multi-robot warehouse simulation** using ROS 2 and Gazebo, followed by learning-based navigation experiments. My AMR work covered multi-robot configuration, fleet coordination, sensor fusion, and connecting CCTV obstacles to path planning.

- **Traced localization errors to sensor sources.** I isolated Gazebo topics and frames that were mixing data across robots, starting at generation. A bounded simulation run confirmed all four robots reaching their respective goals.
- **Connected camera detections to map coordinates.** For a fixed CCTV scene where a small person was missed, I used background subtraction, projected detections to the floor, and connected an obstacle layer to A*. Map integration was verified; the effect on rerouting remained a separate validation task.
- **Reworked the navigation evaluation protocol.** [Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) compares rule-based control, behavior cloning, and PPO. In a lightweight environment, the evaluation covered five training seeds and 4,160 total test episodes: PPO best achieved 85.4% success, versus 86.2% for the rule baseline. Checkpoint selection and test data were separated instead of generalizing from the initial small sample.

[AMR code](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [Four-robot run](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md) · [CCTV experiment](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/cctv/PROGRESS.md) · [Autonomy evaluation](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo/blob/dev/experiments/m1_reproducibility/RESULTS.md)

## Agents and workflow automation

I carry decisions from small experiments into application execution and state management.

| Project | Problem and my contribution | What is available today |
| --- | --- | --- |
| [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo) | Two-person study with independent implementations and shared findings. Agent implementations, evaluation tooling, and routing | Single-agent and handoff designs both passed 20/20 fixed tasks. Handoff increased p50 latency by about 63% and cost by about 32%, informing a single-agent choice for these small tool-based tasks. [Comparison](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md) |
| [personal-ai / Agent Workspace](https://github.com/ukkhnn/personal-ai) | Personal project. Per-task worktrees, queued instructions, approvals, execution state, and web UI | Verified a real DeepSeek task, HTTPS access, and completed-task persistence after a server-process restart on a Mac mini. [App implementation is on a working branch](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md); physical cross-device use and real concurrent tasks await validation |
| [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19) | Upstage team hackathon. n8n verification workflow design and Upstage API integration | Compares responses with policy documents and routes them to pass, correction, or blocking. Repository: `upstage_hackathon_team19`; the live demo has ended |
| **OptiDocu** · Private | Team capstone supporting automotive RFQ review. Workflow definition, synthetic business data, and evaluation design | Prepared separate stage-specific inputs and evaluation answers for intake, consolidation, and pre-submission review. Currently at the data/evaluation preparation stage; product and model-performance evaluation are subsequent work |

## Learning and CS foundations

I return to small implementations and experiments when a project exposes a gap in my understanding. Alongside machine learning, I have worked on operating systems, memory, I/O, and spatial representation.

| Public learning repository | Focus |
| --- | --- |
| [LikeLion_26S_BootCamp_AI_NLP](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) | AI/NLP bootcamp and self-study. A small translation exercise with attention, encoder, and decoder implemented through PyTorch tensor operations; experiments on RAG metrics, label quality, and evaluation bias |
| [CS231n-Pytorch-Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) | CS231n-based PyTorch tensor exercises and KNN implementation |
| [Self_Study_Deep_Learning](https://github.com/ukkhnn/Self_Study_Deep_Learning) | Personal notes and implementations for deep learning study |

The following **coursework repositories are private**. Their learning and implementation scope is summarized here.

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

I also keep earlier versions and learning forks. Together with the projects and learning repositories above, this lists all 15 currently public repositories.

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

If you would like to discuss a design choice or a failure case from these projects, feel free to [email me](mailto:hyunuk200202@gmail.com).
