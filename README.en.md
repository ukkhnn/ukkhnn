# ukkhnn · Hyunuk Yang

Computer Science @ Sogang University · [한국어](https://github.com/ukkhnn/ukkhnn) · [Email](mailto:hyunuk200202@gmail.com)

Most of my projects involve document retrieval, AI agents, or robot navigation. I’m still working in the virtual warehouse my capstone team built last semester. Back then, I used A* to plan routes for four robots. These days, I’m teaching a robot what to do when something gets in its way.

## 🔧 On my desk

### OptiDocu · Reviewing automotive quote requests

**Technical lead** · 5-person industry capstone · Sogang University × 겁쟁이사자 · Sep 2026–present

Before an automotive supplier can send a quote, someone has to read the drawings, check delivery requirements, and reconcile replies from several departments. I worked with our industry partner to map out that process and designed a review tool that lets someone trace a claim in a draft response back to the PDF page or spreadsheet cell that supports it.

- I designed the architecture and the interfaces between processing stages, then built the job queue, document worker, and storage layer. Reviewers can edit a response and still see the original AI draft and its revision history.
- The tricky part of building the evaluation set was deciding **what the reviewer could have known at the time**. A reply that arrives on Thursday shouldn’t help the model review Monday’s request. I created 24 synthetic requests for quotation (RFQs), each with three snapshots covering intake, departmental replies, and final review. That gave us 72 inputs across eight development cases and 16 held-out cases. Our partner reviewed the frozen dataset.

*Private repository.*

### Opticore AMR Autonomy · Bringing a learned driving policy into the warehouse

**Project lead · Systems integration** · 5-person Opticore team · Sep 2026–present

During our first robotics capstone, I helped a teammate tune the local obstacle-avoidance controller. Each change meant running the same obstacle encounter again. I wanted to see whether a policy could learn from those runs, so I proposed a follow-up project and the five of us got back together after the course ended.

- I made the training simulator and ROS 2 assemble the four most recent LiDAR scans in the same order, then connected the policy’s velocity commands to a robot in Gazebo.
- In a static four-metre trial, the robot drove under policy control, stopped on command, resumed, and reached its goal without a collision. Four longer tasks in the lightweight simulator all timed out. The logs told two different stories: one robot made it to the end of its planned path but stopped just outside the goal radius. Another barely moved once the aisle was blocked.

[Warehouse trial](https://github.com/sogang-opticore/opticore-amr-autonomy/blob/2116816b26dda37a5403e119053b38b8c75e1343/docs/m3/README.md) · [Per-task diagnostics](https://github.com/sogang-opticore/opticore-amr-autonomy/blob/2116816b26dda37a5403e119053b38b8c75e1343/experiments/m3/training-diagnostic.json)

## 📌 Selected work

### 4MATION / 예봄24 · A chatbot for deposit insurance services

**Project lead · Retrieval and conversation design** · 4 developers · LIKELION × ClaBi · Jul–Sep 2026, with continued development

“What documents do I need?” The answer changes if the person asking is acting on behalf of a company. Our chatbot helps people find procedures and forms across six service areas using public guidance from the Korea Deposit Insurance Corporation.

- I designed a follow-up question flow we called Q-Form. It asks for missing details, such as who is applying and in what capacity, then carries those details into the next search. Someone who has already said they represent a company can simply ask “What should I bring?”
- I kept each source page linked to its attachments and combined BM25 keyword search with FAISS vector search. To compare different ways of splitting documents, I proposed labeling the supporting passage in the original text. The reference then stays useful when the chunk boundaries move.
- I tested 150 pairs of questions where both versions had the same reference documents. The hybrid retriever found a correct document in its top three results for **85.3% of the original questions** and **75.3% of their conversational variants**.

[Project repository](https://github.com/likelion-4MATION/4MATION) · [Paired retrieval results](https://github.com/likelion-4MATION/4MATION_archive/blob/dev/crawler/data/pair_report.md)

### Opticore AMR · Four robots in one warehouse

**Project lead · A\* path planning · Fleet coordination** · 5-person capstone · Sogang University · Mar–Jun 2026

I built the global route planner and fleet coordination software for a warehouse simulation in ROS 2 and Gazebo. Localization worked when we launched one robot at a time. With several robots running, their estimated positions started to drift. I traced the problem to sensor messages and coordinate frames getting mixed across robots and isolated them at launch. In one recorded warehouse run, **all four robots reached their assigned goals**.

[Project repository](https://github.com/sogang-opticore/opticore-amr) · [Four-robot run](https://github.com/sogang-opticore/opticore-amr/blob/c4598710d9c2d0287feb6fce7ee7fa41114d8d81/docs/fleet_f1/report.md)

### Side projects & hackathons

- **ContextWeld** · A tool that reads markings on ship components and matches them to work orders, drawings, and welding procedures. It started as a two-person hackathon project. I continued independently, adding a review step for ambiguous readings and testing the handoff to mock receivers in Hyundai and Doosan formats. [End-to-end demo](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md)
- **Agent Workspace** · I wanted to leave a coding agent running on my Mac mini and use a browser to send instructions, approve commands, and inspect changes. I built a workspace with a separate Git worktree for each task, tested file edits with a live DeepSeek run, and verified that completed task records survived a server restart. [Implementation notes](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md)
- **VeriFlow** · I led a three-person team and built the backend for an Upstage hackathon project. The n8n workflow checks a customer-support chatbot’s draft against the original policy document before deciding whether to send it, revise it, or hand it to a support agent. [Workflow](https://github.com/ukkhnn/upstage_hackathon_team19)

## 🎓 Background

**Sogang University** · Computer Science and Engineering · Expected graduation Feb 2027  
**LIKELION** · Advanced AI and Natural Language Processing · 343 hours completed · Jun–Sep 2026  
**Undergraduate Teaching Assistant** · Design and Analysis of Algorithms, Sogang University · Course operations, exam proctoring, and grading · Fall 2026

**GongChangJin** · I co-organize a small developer group where we try out ideas and compare what happens. In one experiment, I built a single agent and a version that handed tasks off to specialists. Both passed all 20 tool-use tasks. Handoffs pushed median latency from 1.28 to 2.08 seconds and cost about 32% more, so I kept the single agent for that workload. [Experiment and results](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)

### Toolbox

| Area | Tools I’ve used in projects |
| --- | --- |
| Retrieval & agents | Python, BM25, FAISS, BGE-M3, OpenAI Agents SDK, n8n |
| Backend & evaluation | FastAPI, JavaScript, SQL, SQLite, pytest |
| Robotics & learning | ROS 2, Gazebo, C/C++, PyTorch, Stable-Baselines3 |

<details>
<summary><strong>Coursework, study notes, and more repositories</strong></summary>

**Systems coursework**  
I implemented priority scheduling, system calls, and virtual memory in Pintos. The revised version passed 226 tests under QEMU. My private coursework repositories also cover a cache simulator, OpenSSD host I/O and its flash translation layer, and C++/OpenGL graphics.

**AI study**  
[AI/NLP bootcamp exercises](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) · [CS231n PyTorch implementations](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) · [Deep learning study notes](https://github.com/ukkhnn/Self_Study_Deep_Learning)

**Team repositories**  
[Early 4MATION implementation](https://github.com/likelion-4MATION/4MATION_archive) · [GongChangJin Hands-on](https://github.com/GongChangJin/hands-on) · [Group projects](https://github.com/GongChangJin/projects) · [Project template](https://github.com/GongChangJin/project-template)

**Project copies on my profile**  
[4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [4MATION archive](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo) · [Opticore AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) · [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)

**Learning forks**  
[Let’s Build GPT](https://github.com/ukkhnn/practice-let-s-build-gpt) · [Build with AI](https://github.com/ukkhnn/build-with-ai-handson-campus-hands-on) · [oh-my-claudecode](https://github.com/ukkhnn/oh-my-claudecode)

</details>
