# Hyunuk Yang · 양현욱

**Applied AI · Document Retrieval, Agents & Robotics**

Computer Science and Engineering, Sogang University · Expected Feb 2027

[hyunuk200202@gmail.com](mailto:hyunuk200202@gmail.com) · [한국어 이력서](README.md)

I build AI tools for people working through documents. A deposit insurance applicant needs the right form, while an automotive supplier needs to know which delivery terms it can promise. In both projects, I designed how the software finds the evidence for the next decision. I also develop robot navigation software. After leading route planning for a warehouse robotics capstone, I brought the team back together to test a learned driving policy in simulation.

## Selected Project Experience

### 4MATION / 예봄24 · Deposit insurance chatbot

**Project Lead & RAG Developer** · 4 developers · LIKELION × ClaBi · Jul–Sep 2026, with continued development

Built a chatbot for six service areas using public guidance from the Korea Deposit Insurance Corporation. Someone applying to recover a mistaken transfer needs different forms depending on whether they are acting for themselves or on behalf of a company.

- Designed a follow-up form that asks who is applying and in what capacity. When a user then asks “What should I bring?”, the chatbot carries those details into its document search and attachment selection.
- Preserved the source of each web page and attachment, and combined BM25 keyword search with FAISS vector search using reciprocal rank fusion. Proposed labeling the supporting passages in the original documents so retrieval could be evaluated across different chunk sizes.
- Compared 150 question pairs with the same reference documents. The hybrid retriever returned a correct document in its top three results for 85.3% of the original questions and 75.3% of their conversational variants. [Code](https://github.com/likelion-4MATION/4MATION) · [Paired retrieval results](https://github.com/likelion-4MATION/4MATION_archive/blob/dev/crawler/data/pair_report.md)

### OptiDocu · Automotive quote review

**Technical Lead** · 5-person industry capstone · Sogang University × 겁쟁이사자 · Sep 2026–Present · Private repository

Automotive suppliers review drawings, delivery requirements, and replies from several departments before they can quote a customer. Worked with the industry partner to define that process and designed a review tool that lets a reviewer trace a draft response to a PDF page or spreadsheet cell.

- Defined the inputs and outputs of each processing step and built the FastAPI job queue, worker, and storage layer. Verified on a development case that a reviewer could trace a claim to its source and edit a response while preserving the original AI draft and its revision history.
- Created 24 synthetic requests for quotation, each with three snapshots covering intake, departmental replies, and final review. Each of the **72 inputs** exposes only the documents available at that point, with reference answers stored separately. Froze the dataset with eight development cases and 16 held out for final evaluation, then secured the partner’s confirmation.

### Opticore · Warehouse robotics and learned navigation

**Project Lead & Systems Integration** · 5-person team · Sogang University capstone and independent follow-up

- **Warehouse AMR · Mar–Jun 2026.** Developed A* global path planning and fleet coordination in ROS 2 and Gazebo. Traced a localization error to sensor messages crossing between robots and isolated their topics and coordinate frames. All four robots reached their individual goals in one recorded simulation run. [Four-robot run](https://github.com/sogang-opticore/opticore-amr/blob/c4598710d9c2d0287feb6fce7ee7fa41114d8d81/docs/fleet_f1/report.md)
- **AMR Autonomy · Sep 2026–Present.** While helping a teammate tune the local obstacle-avoidance controller, I proposed training a policy on driving experience from the simulator. Aligned the four most recent LiDAR scans across the training environment and ROS 2, then integrated the learned policy’s velocity commands into the warehouse simulator.
- In a static four-metre trial, one robot drove under policy control, stopped on command, resumed, and reached the goal without a collision. Four longer tasks in the lightweight simulator all timed out. Comparing progress along the path with distance to the goal distinguished a robot that passed beside its goal from one that barely advanced in a blocked aisle. [Navigation trial and diagnostics](https://github.com/sogang-opticore/opticore-amr-autonomy/blob/2116816b26dda37a5403e119053b38b8c75e1343/docs/m3/README.md)

## Additional Projects

- **ContextWeld · Visual inspection and work instructions.** Started in a two-person hackathon and continued independently. Connected markings read from stored images of ship components to work orders, drawings, and welding procedures. Routed ambiguous matches to a reviewer and tested delivery of the approved specification to mock receivers in Hyundai and Doosan formats. [End-to-end demonstration](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md)
- **Agent Workspace · Independent project.** Built a web interface for running coding agents on a Mac mini, with a Git worktree per task, queued instructions, and command approvals. Verified that a live DeepSeek task could edit files and that completed task records survived a server process restart. [Implementation and verification](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md)
- **VeriFlow · Project Lead & Backend Developer · May 2026.** Built the pre-send review workflow for a customer support chatbot in a three-person Upstage hackathon team. Used n8n and Upstage APIs to extract rules from policy PDFs, check draft answers against the source text, and route them for delivery, correction, or human review. [Workflow](https://github.com/ukkhnn/upstage_hackathon_team19)

## Leadership & Teaching

- **GongChangJin AI Hands-on Lab · Co-organizer · Sep 2026–Present.** Co-run an independent developer group where we implement and compare agent designs. On 20 fixed tool-use tasks, both my single-agent and specialist-handoff implementations passed all 20. Handoffs raised median latency from 1.28 to 2.08 seconds and cost about 32% more, so I chose the single agent for this workload. [Experiment results](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)
- **Sogang University · Undergraduate Teaching Assistant · Fall 2026.** Set up the classroom and handled exam proctoring and grading for Design and Analysis of Algorithms.

## Education & Training

- **Sogang University · Computer Science and Engineering** · Expected graduation Feb 2027
- **LIKELION · Advanced AI and Natural Language Processing** · Jun–Sep 2026 · Completed 343 hours of training and led the 4MATION project with industry partner ClaBi.

## Technical Skills

| Area | Technologies used in projects |
| --- | --- |
| Languages & backend | Python, C/C++, JavaScript, SQL, FastAPI, SQLite, pytest |
| Retrieval & agents | BM25, FAISS, BGE-M3, OpenAI Agents SDK, n8n |
| Robotics & learning | ROS 2, Gazebo, A*, LiDAR, PyTorch, Stable-Baselines3 |

<details>
<summary>Coursework, learning repositories, and project archives</summary>

- **Systems coursework (private).** Implemented scheduling, system calls, and virtual memory in Pintos. The revised version passed 226 QEMU tests. Other coursework includes a cache simulator, OpenSSD host I/O and flash translation, and C++/OpenGL graphics.
- **AI study.** [AI/NLP bootcamp exercises](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) · [CS231n PyTorch implementations](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) · [Deep learning study notes](https://github.com/ukkhnn/Self_Study_Deep_Learning)
- **Project repositories.** [4MATION archive](https://github.com/likelion-4MATION/4MATION_archive) · [Opticore AMR](https://github.com/sogang-opticore/opticore-amr) · [AMR Autonomy](https://github.com/sogang-opticore/opticore-amr-autonomy) · [GongChangJin Hands-on](https://github.com/GongChangJin/hands-on) · [GCJ projects](https://github.com/GongChangJin/projects) · [GCJ project template](https://github.com/GongChangJin/project-template)
- **Project copies on my profile.** [4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [4MATION archive](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo) · [Opticore AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) · [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)
- **Learning forks.** [Let's Build GPT](https://github.com/ukkhnn/practice-let-s-build-gpt) · [Build with AI](https://github.com/ukkhnn/build-with-ai-handson-campus-hands-on) · [oh-my-claudecode](https://github.com/ukkhnn/oh-my-claudecode)

</details>
