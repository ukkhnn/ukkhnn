# 안녕하세요, 양현욱입니다

서강대에서 컴퓨터공학을 공부하고 있어요. 문서를 찾아 답하는 챗봇, 선박 부재의 표기를 읽는 도구, 여러 로봇이 움직이는 시뮬레이션 같은 걸 만들어 봤습니다. 모델이 읽어 낸 정보가 다음 작업에 어떻게 쓰이는지 궁금하고, 예상대로 안 움직일 때 어디서부터 어긋났는지 찾아보는 것도 좋아해요.

[Email](mailto:hyunuk200202@gmail.com) · [English](README.en.md)

[만든 것들](#만든-것들) · [에이전트와 업무 자동화](#에이전트와-업무-자동화) · [공부 기록](#공부-기록) · [다른 저장소](#다른-저장소)

## 만든 것들

### 4MATION — 질문의 맥락을 이어 가는 RAG

예금보험공사 공개 정보를 바탕으로 6개 업무 분야의 질문에 답하는 기업과 함께 만든 팀 프로토타입입니다. 전체 구조와 프로젝트 관리를 맡았고, Q-Form으로 추가 질문을 받는 흐름과 질문 라우팅, 검색 튜닝, 웹 연동을 작업했습니다.

- 짧은 후속 질문에도 앞에서 확인한 조건을 이어서 쓰도록 했습니다. 주제가 바뀌었는지 구분하고, 조건을 검색과 첨부 문서 선택까지 넘겼습니다. 사용자 원문과 검색용 질의도 분리했습니다.
- 웹에서 바꾼 설정이 답변에도 반영되도록 사용자·관리자 화면을 검색, 답변 생성, 검증에 연결했습니다. 현재 사용자 화면은 FastAPI와 정적 웹 UI로 구성되어 있습니다.
- 질문 표현만 바꾸면 검색 결과가 얼마나 달라질지 궁금해서, 같은 정답을 가진 150쌍의 질문을 비교했습니다. 자연스러운 표현으로 바꾸면 hit@3가 0.853 → 0.753으로 낮아졌습니다. 이 결과를 보고 평가 질문의 말투가 검색 점수에 얼마나 영향을 주는지 살펴봤습니다. 현재는 2.0의 배포·운영 검증을 준비하고 있습니다.

[코드](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [맥락 처리](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/f9671aae7fa826104ebd7e77598aa5ad0deac745) · [검색 연동](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/d1cd6f55210042ee8c5d7ba9889e8c44f1dc9890) · [질문 비교 실험](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b)

### ContextWeld · PAC2026 — 보이는 표기를 작업 정보로

선박 부재의 표기와 시각적 관계를 읽고, 작업지시·도면·용접절차서(WPS)와 연결하는 프로젝트입니다. 둘이서 참가한 해커톤에서 기획과 개발을 맡았고, 지금은 개인 작업으로 이어 가고 있습니다.

- VLM의 부재·이음 관측을 작업지시와 대조하고, 대상이 모호하면 검토 단계로 보냅니다. 이미지에서 관측한 내용과 문서에서 얻은 조건을 따로 남깁니다.
- 저장된 RGB 이미지의 실제 모델 추론에서 문서 근거 조회, 등록 작업조건 선택, 공통 작업명세, 현대·두산 형식 변환, 모의 HTTP 수신까지 이어지는 실행을 확인했습니다.
- 최초 판독은 보존하고 선택한 수정만 새 검토에 반영하며, 같은 요청의 중복 전송을 막았습니다. 지금까지는 저장 이미지부터 모의 수신까지 확인했습니다. 실제 용접과 로봇의 자율 재촬영은 검증 범위 밖에 있습니다.

[코드](https://github.com/ukkhnn/PAC2026) · [인식부터 전달까지](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md) · [대상 연결 검사](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7) · [수정·검토 흐름](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

### Opticore AMR + Autonomy — 인지·경로계획·학습을 함께 보기

ROS 2·Gazebo 기반의 다중 물류 로봇 팀 캡스톤과 후속 학습 기반 주행 실험입니다. AMR의 다중 로봇 구성, fleet 조율, 센서 융합과 CCTV 장애물의 경로계획 연계를 맡았습니다.

- 로봇 위치가 어긋나는 원인을 따라가 보니 로봇 간 센서 데이터가 섞이고 있었습니다. Gazebo 토픽과 프레임을 생성 단계부터 분리했고, 제한된 시뮬레이션 실행에서 4대 모두 각 목표에 도달하는 것을 확인했습니다.
- 작은 사람을 놓치는 고정 CCTV 장면에서 배경 차분을 선택하고, 바닥 좌표 투영과 장애물 지도 레이어를 A*에 연결했습니다. 지도 반영까지 확인했으며, 경로 변경 효과 검증은 별도 과제로 남겼습니다.
- [Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo)에서는 규칙 기반·BC·PPO를 비교했습니다. 경량 환경의 5개 학습 seed·전체 4,160개 평가 episode에서 PPO best 성공률은 85.4%, 규칙 기반은 86.2%였습니다. 처음에는 표본이 적어서, 다시 비교할 때는 정책 선택용 데이터와 최종 평가용 데이터를 나눴습니다.

[AMR 코드](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [4대 주행 기록](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md) · [CCTV 실험](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/cctv/PROGRESS.md) · [Autonomy 평가](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo/blob/dev/experiments/m1_reproducibility/RESULTS.md)

## 에이전트와 업무 자동화

| 프로젝트 | 해본 것 | 진행 상황과 실험 결과 |
| --- | --- | --- |
| [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo) | 2인 스터디에서 독립 구현과 결과 공유. Agent 구현·평가 도구·라우팅 담당 | 고정 20개 과제에서 단일 Agent와 handoff 모두 20/20. handoff의 p50 지연 약 63%·비용 약 32% 증가를 보고 작은 도구 작업에는 단일 Agent 선택. [비교 기록](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md) |
| [personal-ai / Agent Workspace](https://github.com/ukkhnn/personal-ai) | 개인 프로젝트. 작업별 worktree, 지시 대기열, 승인, 실행 상태와 웹 UI 구현 | Mac mini에서 실제 DeepSeek 작업·HTTPS·서버 프로세스 재시작 후 완료 작업 보존 확인. [앱 구현은 작업 브랜치에 있으며](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md), 물리 기기 간 사용·실제 병행 작업 검증은 진행 예정 |
| [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19) | Upstage 해커톤 팀 프로젝트. n8n 검증 워크플로우 설계·Upstage API 연동 담당 | 정책 전문과 답변을 비교해 통과·보정·차단으로 분기하는 워크플로우. 저장소명 `upstage_hackathon_team19`; 현재 라이브 데모는 종료 |
| **OptiDocu** · 비공개 | 자동차 부품 RFQ 검토 지원 팀 캡스톤. 업무 흐름·가상 업무 데이터·평가 설계 담당 | 접수→취합→제출 전의 시점별 입력과 평가용 답안을 분리해 준비. 현재 데이터·평가 체계 준비 단계이며 제품·모델 성능평가는 후속 작업 |

## 공부 기록

프로젝트에서 막히면 작은 예제로 다시 만들어 봅니다. 딥러닝 실습과 운영체제, 메모리, I/O, 그래픽스 과제를 모아 뒀습니다.

| 공개 학습 저장소 | 학습 내용 |
| --- | --- |
| [LikeLion_26S_BootCamp_AI_NLP](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) | AI/NLP 부트캠프와 자율 학습. PyTorch 텐서 연산으로 attention·encoder·decoder를 구현한 작은 번역 실습, RAG 지표·라벨 품질·평가 편향 실험 |
| [CS231n-Pytorch-Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) | CS231n 기반 PyTorch 텐서 연산과 KNN 구현 실습 |
| [Self_Study_Deep_Learning](https://github.com/ukkhnn/Self_Study_Deep_Learning) | 딥러닝 개념과 구현을 정리하는 개인 학습 저장소 |

전공 과제는 비공개 저장소에 모아 뒀습니다.

| 과목 · 저장소 | 구현·학습한 내용 |
| --- | --- |
| 운영체제 · `cse4070-pintos` | 프로세스·시스템 호출, 우선순위 스케줄링, 가상 메모리. 후속 정리본은 QEMU 226/226 테스트 통과 |
| 컴퓨터시스템개론 · `computer-systems-labs` | C 비트 연산, x86-64 프로그램 분석, 캐시 시뮬레이터 |
| 임베디드시스템소프트웨어 · `cse4116-openssd`, `CSE4116_PRJ3` | OpenSSD 호스트 I/O, FTL, 펌웨어와 커널 패치. 제출 자료를 보존하고 실행·장치 의존성을 문서화 |
| 기초컴퓨터그래픽스 · `basic-computer-graphics` | C++·OpenGL 기반 그래픽스 과제. 제출 소스·셰이더·텍스처와 제공 코드를 구분해 정리 |

## 주로 사용하는 도구

**AI·검색** — PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK<br>
**애플리케이션·평가** — Python, FastAPI, JavaScript, SQLite, pytest, n8n<br>
**시스템·로보틱스** — C/C++, ROS 2, Gazebo, Linux, Git

## 다른 저장소

이전 버전과 따라 만들어 본 코드도 여기 모아 뒀습니다.

<details>
<summary><strong>아카이브·학습용 포크·프로필</strong></summary>

| 저장소 | 용도 |
| --- | --- |
| [4MATION_archive-on-ukkhnns-repo](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo) | 초기 RAG PoC의 구현·평가 기록. 현재 개발본과 구분해 보관 |
| [practice-let-s-build-gpt](https://github.com/ukkhnn/practice-let-s-build-gpt) | Andrej Karpathy의 GPT 구현 튜토리얼을 따라가기 위한 포크 |
| [build-with-ai-handson-campus-hands-on](https://github.com/ukkhnn/build-with-ai-handson-campus-hands-on) | Build with AI 캠퍼스 실습 자료 포크 |
| [oh-my-claudecode](https://github.com/ukkhnn/oh-my-claudecode) | Claude Code 오케스트레이션 도구를 살펴보기 위한 포크. 원 프로젝트는 Yeachan-Heo/oh-my-claudecode |
| [ukkhnn](https://github.com/ukkhnn/ukkhnn) | 이 프로필의 국문·영문 README |

</details>

<details>
<summary><strong>함께 작업한 조직의 저장소</strong></summary>

- **4MATION:** [현재 개발본](https://github.com/likelion-4MATION/4MATION) · [초기 아카이브](https://github.com/likelion-4MATION/4MATION_archive)
- **Opticore:** [AMR](https://github.com/sogang-opticore/opticore-amr) · [Autonomy](https://github.com/sogang-opticore/opticore-amr-autonomy) · `opticore-optidocu`는 비공개
- **공창진:** [hands-on](https://github.com/GongChangJin/hands-on) · `idea-lab` · [projects](https://github.com/GongChangJin/projects) · [project-template](https://github.com/GongChangJin/project-template)

</details>

프로젝트 얘기는 언제든 [메일](mailto:hyunuk200202@gmail.com)로 편하게 보내 주세요.
