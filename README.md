# Hyunuk Yang

[English](#hyunuk-yang) · [한국어](#국문-소개)

**AI Application Engineering · RAG · Agents · Multimodal**

I build RAG and agent applications, and improve them through experiments and failure analysis. My work connects retrieval, dialogue state, and tool execution with the interfaces people use to review and correct results.

Computer Science and Engineering undergraduate, **Sogang University**  
Mar 2021 – Expected graduation: Feb 2027 · [hyunuk200202@gmail.com](mailto:hyunuk200202@gmail.com)

## 🧩 Projects

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

## 🚧 In Progress

**OptiDocu** · Oct 2026–present · Industry–university capstone project · Private repository

Preparing a PoC to help automotive suppliers review RFQs, gather evidence across departments, draft responses, and check omissions or conflicts. My work focuses on workflow definition, synthetic business data, and evaluation design. The project is currently in **data preparation and review**: documenting a fictional company's operating criteria and separating task inputs from evaluation answers.

**[personal-ai / Agent Workspace](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)** · Personal project

Building a web workspace for development agents running on a Mac mini, covering task state, queued instructions, approvals, and code changes. I implement the execution lifecycle and web/runtime integration. Current verification covers a real model task, HTTPS access, and preservation of completed tasks across a server-process restart. [Implementation and verification scope](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)

## 📚 Learning in Practice

**[LikeLion AI/NLP Study](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP)** brings together study sessions and exercises from the fifth LikeLion AI/NLP bootcamp, along with self-directed study during 4MATION.

I implemented attention, an encoder, and a decoder with PyTorch tensor operations, then trained and ran a small translation example. Questions from the RAG project led to further notebooks on retrieval metrics, label quality, evaluation bias, and confidence intervals, using minimal implementations and simulations. [Transformer exercise](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/blob/main/StudySession_FUNDAMENTAL/Fundatmental_ipynb/FUNDAMENTAL_day10~14_TransformerWithoutMagic.ipynb) · [RAG evaluation notebooks](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/tree/main/selfstudy_rag_for4MATION/C_evaluation)

- **[Opticore AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo)** — Comparisons of rule-based navigation, behavior cloning, and PPO, including checks on safety constraints and evaluation conditions.
- **[CS231n PyTorch Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation)** — PyTorch fundamentals and KNN implementation experiments.

## 🛠️ Tools

**Models & retrieval:** PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK  
**Applications & evaluation:** Python, FastAPI, JavaScript, SQLite, pytest, Arize Phoenix  
**Systems & robotics:** ROS 2, Gazebo, Linux, Git

---

# 국문 소개

[English](#hyunuk-yang) · [한국어](#국문-소개)

**AI 애플리케이션 개발 · 검색 증강 생성(RAG) · 에이전트 · 멀티모달**

RAG와 에이전트를 활용한 애플리케이션을 만들고, 실험과 실패 분석을 통해 개선합니다. 검색·대화 상태·도구 실행을 연결하고, 사용자가 결과를 확인하고 수정하는 흐름까지 함께 구현합니다.

**서강대학교 컴퓨터공학과** 재학  
2021년 3월 입학 · 2027년 2월 졸업 예정 · [hyunuk200202@gmail.com](mailto:hyunuk200202@gmail.com)

## 🧩 프로젝트

### [4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)
*2026년 7–9월 · 팀 프로젝트*

예금보험공사 공개 정보를 바탕으로 6개 업무 분야의 질문에 답하는 기업 연계 RAG 챗봇 PoC입니다.

**담당 역할:** 전체 아키텍처와 프로젝트 관리, Q-Form 되묻기 흐름, 라우팅, 검색·튜닝, 웹 통합.

- **대화에서 확인한 조건을 검색까지 연결했습니다.** 짧은 후속 질문이 다른 업무로 분류되면서 이전에 수집한 조건을 잃는 문제가 있었습니다. 후속 질문과 업무 전환을 구분하고, 확인된 조건을 검색·첨부 선택에 반영했으며, 검색용 질의와 사용자 원문을 분리했습니다. [문맥 처리](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/f9671aae7fa826104ebd7e77598aa5ad0deac745) · [검색 연결](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/d1cd6f55210042ee8c5d7ba9889e8c44f1dc9890)
- **관리자 설정이 실제 답변에 반영되도록 연결했습니다.** 사용자·관리자 웹을 통합하고, 설정 변경이 검색·답변 생성·검증 단계까지 적용되도록 구성했습니다. [구현 내용](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/e9a97816c312471bc9a6b0e5d26c37e2879710bc)
- **평가 기준선을 다시 점검했습니다.** 질문이 원문 표현과 가까워 점수가 높게 나올 가능성을 살펴보기 위해, 동일한 평가 정답을 유지한 **150쌍의 질문**을 비교했습니다. 자연스러운 표현으로 바꾸자 hit@3가 **0.853에서 0.753으로** 낮아졌고, 이 차이를 이후 개선 판단의 기준을 재검토하는 데 활용했습니다. [페어 평가](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b) · [기준값 정정](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/355d08827273067273134e0fd13898e3f17b64a5)

### [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)
*2026년 9월–현재 · 각자 독립적으로 구현하고 결과를 공유하는 2인 스터디 프로젝트*

RAG·라우팅·도구형 에이전트를 실험하고, 공통 형식으로 품질·비용·지연시간·실패를 기록하고 비교합니다.

**담당 역할:** 에이전트 구현, 평가 도구, 라우팅, 통합 검증.

- **실측 결과를 바탕으로 구조를 선택했습니다.** 단일 에이전트와 에이전트 간 작업을 넘기는 handoff 구조 모두 **고정 과제 20/20개를 통과**했지만, handoff는 p50 지연시간이 **약 63%**, 비용이 **약 32%** 높았습니다. 작은 도구형 과제에서는 단일 구조를 선택하고, 과제 복잡도가 커지면 다시 비교하도록 했습니다. [비교 결과](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)
- **도구에 넘기는 입력의 근거를 확인했습니다.** 문서에서 정책을 찾아야 하는 계산에 에이전트가 임의의 숫자를 사용하는 사례를 발견했습니다. 계산식의 숫자가 질문에 명시된 수치인지 검사하고, 근거가 없으면 검색을 거친 뒤 계산하도록 실행 경로를 바꿨습니다. [수정·회귀 테스트](https://github.com/GongChangJin/hands-on/commit/8000b1f45652e88d040a3a40a785db6d1d959716)
- **측정 코드의 오류를 수정했습니다.** 앞 실험 조건의 API 요청 수가 다음 조건에 누적되는 문제를 발견했습니다. 각 조건의 시작 시점과 비교한 요청 수 차이로 집계하도록 바꾸고, 원시 자료가 없어 복원할 수 없는 과거 지연시간 값은 한계로 기록했습니다. [집계 수정·기록 보정](https://github.com/GongChangJin/hands-on/commit/d2c6b2ca6672ff719cd62b18bebb09e86008d472)

### [ContextWeld](https://github.com/ukkhnn/PAC2026)
*2026년 10월–현재 · 2인 해커톤 프로젝트로 시작해 개인 개발 지속*

선박 부재의 표기를 작업지시·도면·용접 기준과 연결해 해석하고, 용접 조건 후보와 검토가 필요한 항목을 제시하는 시스템을 개발하고 있습니다.

**담당 역할:** 해커톤에서 기획·개발을 맡았으며, 이후 개인적으로 개발을 이어가고 있습니다.

- **표기가 가리키는 대상을 검증했습니다.** 인식한 표기가 선택한 부재·이음과 연결되는지 검사하고, 무관한 문자나 모호한 관계를 걸러내도록 했습니다. [대상 관계 검증](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7)
- **수정 내용을 다시 검토할 수 있도록 구성했습니다.** 원본 인식 결과를 보존하고 사용자 수정 기록을 별도로 저장하며, 선택한 수정만 새 검토에 적용했습니다. 데모에서는 재검토 결과를 모의 수신기로 전달하고, 같은 요청의 중복 전송을 막습니다. [수정·재검토 흐름](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

### [Opticore-AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)
*2026년 3–7월 · 팀 캡스톤 프로젝트*

ROS 2·Gazebo 기반 가상 물류창고에서 여러 로봇의 경로계획·위치추정·플릿 조율을 연결한 프로젝트입니다.

**담당 역할:** 시스템 아키텍처, Gazebo 환경, A* 경로계획, 플릿 로직, 다중 로봇 통합.

- **위치추정 오류를 데이터 발생 지점까지 추적했습니다.** 로봇들이 Gazebo의 센서·이동 토픽을 공유하면서 ROS 브리지가 이미 섞인 데이터를 재발행하고 있었습니다. URDF 생성부터 Gazebo와 브리지까지 로봇별 토픽·좌표계를 분리했습니다. 기록된 시뮬레이션 실행에서는 **4대 모두 각자의 목표에 도달**했습니다. [토픽 분리](https://github.com/sogang-opticore/opticore-amr/commit/58a9feb088d3d1361a2d616e53fb7b3eb88a2bd6) · [실행 기록](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md)
- **지도 경계 조건의 오류를 찾아 수정했습니다.** 클러스터 중심이 지도 격자 밖으로 나가면 벽을 이동 장애물로 추적하는 문제가 있었습니다. 수정 후 같은 경로의 시뮬레이션 비교에서 벽의 오탐 트랙이 **10개에서 0개로** 줄었습니다. 별도로 남은 객체 미탐 문제는 구분해 기록했습니다. [수정·비교 기록](https://github.com/sogang-opticore/opticore-amr/commit/5b76ac066719f1a49a14b835648e5288672fd1aa)

## 🚧 진행 중인 작업

**OptiDocu** · 2026년 10월–현재 · 산학 캡스톤 프로젝트 · 비공개 저장소

자동차 부품 공급사의 RFQ(견적요청서) 검토, 부서별 근거 수집, 응답 초안 작성, 누락·상충 점검을 돕는 PoC를 준비하고 있습니다. 업무 흐름 구체화, 가상 업무 데이터, 평가 설계를 맡고 있습니다. 현재는 **데이터 제작·검수 단계**로, 가상 회사의 업무 기준을 문서화하고 업무 입력과 평가 정답을 분리하는 기준을 마련하고 있습니다.

**[personal-ai / 에이전트 작업 환경](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)** · 개인 프로젝트

Mac mini에서 실행되는 개발 에이전트의 작업 상태·추가 지시 대기열·승인·코드 변경을 관리하는 웹 작업 환경을 만들고 있습니다. 작업의 실행·상태 관리와 웹·런타임 통합을 구현합니다. 현재 실제 모델 작업, HTTPS 접속, 서버 프로세스 재시작 후 완료 작업 보존까지 확인했습니다. [구현·검증 범위](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)

## 📚 프로젝트로 이어진 학습

**[멋쟁이사자처럼 AI/NLP 학습 기록](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP)**에는 멋쟁이사자처럼 AI/NLP 부트캠프 5기의 스터디·실습과 4MATION 진행 중의 자발적 학습을 함께 정리했습니다.

PyTorch 텐서 연산으로 어텐션·인코더·디코더를 구현하고 작은 번역 예제를 학습·실행했습니다. RAG 프로젝트에서 생긴 의문을 바탕으로 검색 지표·라벨 품질·평가 편향·신뢰구간도 최소 구현과 시뮬레이션으로 정리했습니다. [트랜스포머 실습](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/blob/main/StudySession_FUNDAMENTAL/Fundatmental_ipynb/FUNDAMENTAL_day10~14_TransformerWithoutMagic.ipynb) · [RAG 평가 학습 노트북](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/tree/main/selfstudy_rag_for4MATION/C_evaluation)

- **[Opticore AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo)** — 규칙 기반 주행·행동 모방 학습·PPO를 비교하고, 안전 제약과 평가 조건을 점검한 실험입니다.
- **[CS231n PyTorch 구현](https://github.com/ukkhnn/CS231n-Pytorch-Implementation)** — PyTorch 기초와 KNN 구현·실험을 정리했습니다.

## 🛠️ 사용 기술

**모델·검색:** PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK  
**애플리케이션·평가:** Python, FastAPI, JavaScript, SQLite, pytest, Arize Phoenix  
**시스템·로보틱스:** ROS 2, Gazebo, Linux, Git
