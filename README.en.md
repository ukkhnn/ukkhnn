# Hi, I'm Hyunuk Yang 👋

**RAG · Vision · Robotics · Agents**

I study computer science and engineering at Sogang University. I build document-grounded chatbots, tools that read visual information, and multi-robot simulations. I like running things, seeing what happens, and figuring out why the results differ from what I expected.

[Email](mailto:hyunuk200202@gmail.com) · [한국어](README.md)

## Projects

- **[4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)**<br>
  A RAG chatbot covering six service areas using public Korea Deposit Insurance Corporation information.<br>
  Industry-linked team project · Architecture, project coordination, Q-Form, routing, retrieval tuning, web integration

  - Carries follow-up conditions into retrieval and attachment selection. FastAPI and static UI, with deployment and operational validation next for 2.0.

- **[ContextWeld · PAC2026](https://github.com/ukkhnn/PAC2026)**<br>
  Reads markings on ship parts and connects them to work orders, drawings, and welding procedures.<br>
  Two-person hackathon, planning and development → continued independently

  - Tested real-model inference on stored RGB images through document retrieval, Hyundai/Doosan format conversion, and mock HTTP reception.

- **[Opticore AMR + Autonomy](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)**<br>
  ROS 2 and Gazebo warehouse simulation, followed by learning-based navigation experiments.<br>
  Team capstone · Multi-robot configuration, fleet coordination, sensor fusion, CCTV integration with planning

  - All four robots reached their goals in a bounded simulation run. Follow-up Autonomy experiments compare rule-based control, BC, and PPO.

- **[GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)**<br>
  A study of agent architectures and evaluation tools through small implementations.<br>
  Two-person study · Independent implementations, shared findings, evaluation tooling and routing

  - Single-agent and handoff designs both passed 20/20 fixed tasks. Also compared latency and cost.

- **[personal-ai · Agent Workspace](https://github.com/ukkhnn/personal-ai)**<br>
  A personal tool for running AI tasks on a Mac mini and checking their status on the web.<br>
  Personal project · Per-task worktrees, queued instructions, approvals, execution state and web UI

  - Verified a real DeepSeek task, HTTPS, and completed-task persistence after a server restart. Cross-device use and real concurrent tasks await validation.

<details>
<summary>Other team projects</summary>

| Project | What I worked on | Results and current status |
| --- | --- | --- |
| [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19) | Upstage team hackathon. n8n verification workflow design and Upstage API integration | Compares responses with policy documents and routes them to pass, correction, or blocking. Repository: `upstage_hackathon_team19`; the live demo has ended |
| **OptiDocu** · Private | Team capstone supporting automotive RFQ review. Workflow definition, synthetic business data, and evaluation design | Prepared separate stage-specific inputs and evaluation answers for intake, consolidation, and pre-submission review. Currently at the data/evaluation preparation stage; product and model-performance evaluation are subsequent work |

</details>

## Notes from building

### Checking the evaluation

- **4MATION** — In an earlier test of 150 question pairs with the same reference answers, natural wording brought hit@3 from 0.853 to 0.753. This led me to look more closely at wording bias in evaluation. [Paired evaluation](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b)
- **Autonomy** — After an initial small sample, I separated checkpoint-selection data from test data. Across five training seeds and 4,160 total evaluation episodes in a lightweight environment, PPO best reached 85.4% success and the rule baseline reached 86.2%. [Evaluation](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo/blob/dev/experiments/m1_reproducibility/RESULTS.md)
- **GCJ Hands-on** — Both designs passed the same 20 tasks, while handoff increased p50 latency by about 63% and cost by about 32%. I chose a single agent for these small tool-based tasks. [Comparison](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)

### Connecting perception to the next step

- Tracing robot position errors led to sensor data mixing across robots. I separated Gazebo topics and frames at generation. [Four-robot run](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md)
- For a fixed CCTV scene that missed a small person, I used background subtraction and connected floor projections and an obstacle map layer to A*. Map integration was checked. The effect on rerouting needs further testing. [CCTV experiment](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/cctv/PROGRESS.md)
- ContextWeld keeps visual observations and document conditions separate and sends ambiguous targets to review. Original readings are preserved, selected corrections feed a new review, and duplicate transmissions are blocked. Testing covers stored images and a mock receiver. [Code](https://github.com/ukkhnn/PAC2026) · [Recognition-to-delivery run](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md) · [Target binding checks](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7) · [Correction and review](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

## Stack

**AI and retrieval** — PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK<br>
**Applications and evaluation** — Python, FastAPI, JavaScript, SQLite, pytest, n8n<br>
**Systems and robotics** — C/C++, ROS 2, Gazebo, Linux, Git

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

## Education

Computer Science and Engineering, Sogang University · Expected graduation February 2027
