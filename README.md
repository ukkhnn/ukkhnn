# Hi, I'm ukkhnn 👋

**RAG · Vision · Robotics · Agents**

I'm a computer science student at Sogang University, building things with AI—from document-grounded chatbots to vision tools and multi-robot simulations. I enjoy trying ideas out and figuring out why things behave the way they do.

[Email](mailto:hyunuk200202@gmail.com) · [English](README.en.md)

## Projects

- **[4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)**<br>
  예금보험공사 공개 정보로 6개 업무 분야의 질문에 답하는 RAG 챗봇.<br>
  기업 연계 팀 프로젝트 · 전체 구조·프로젝트 관리, Q-Form, 라우팅·검색 튜닝·웹 연동

  - 후속 질문의 조건을 검색과 첨부 문서 선택까지 연결. FastAPI·정적 UI 기반으로 2.0 배포·운영 검증 준비 중.

- **[ContextWeld · PAC2026](https://github.com/ukkhnn/PAC2026)**<br>
  선박 부재의 표기를 읽고 작업지시·도면·용접절차서와 연결하는 도구.<br>
  2인 해커톤에서 기획·개발 → 개인 개발로 확장

  - 저장 RGB 이미지의 실제 모델 추론부터 문서 조회, 현대·두산 형식 변환, 모의 HTTP 수신까지 실행 확인.

- **[Opticore AMR + Autonomy](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)**<br>
  ROS 2·Gazebo 물류 로봇 시뮬레이션과 학습 기반 주행 실험.<br>
  팀 캡스톤 · 다중 로봇 구성, fleet 조율, 센서 융합, CCTV·경로계획 연계

  - 제한된 시뮬레이션에서 4대 모두 목표 도달. 후속 Autonomy 실험에서 규칙 기반·BC·PPO 비교.

- **[GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)**<br>
  Agent 구조와 평가 도구를 직접 만들어 비교하는 스터디.<br>
  2인 스터디 · 독립 구현과 결과 공유, 평가 도구·라우팅

  - 고정 20개 과제에서 단일 Agent와 handoff 모두 20/20. 지연·비용도 함께 비교.

- **[personal-ai · Agent Workspace](https://github.com/ukkhnn/personal-ai)**<br>
  Mac mini에서 AI 작업을 실행하고 웹으로 상태를 확인하는 개인 도구.<br>
  개인 프로젝트 · 작업별 worktree, 지시 대기열, 승인, 실행 상태·웹 UI

  - 실제 DeepSeek 작업, HTTPS, 서버 프로세스 재시작 후 완료 작업 보존 확인. 기기 간 사용과 실제 병행 작업 검증은 진행 예정.

<details>
<summary>함께 만든 다른 프로젝트</summary>

| 프로젝트 | 해본 것 | 진행 상황과 실험 결과 |
| --- | --- | --- |
| [VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19) | Upstage 해커톤 팀 프로젝트. n8n 검증 워크플로우 설계·Upstage API 연동 담당 | 정책 전문과 답변을 비교해 통과·보정·차단으로 분기하는 워크플로우. 저장소명 `upstage_hackathon_team19`; 현재 라이브 데모는 종료 |
| **OptiDocu** · 비공개 | 자동차 부품 RFQ 검토 지원 팀 캡스톤. 업무 흐름·가상 업무 데이터·평가 설계 담당 | 접수→취합→제출 전의 시점별 입력과 평가용 답안을 분리해 준비. 현재 데이터·평가 체계 준비 단계이며 제품·모델 성능평가는 후속 작업 |

</details>

## 만들면서 알게 된 것들

### 평가 조건을 바꿔 보기

- **4MATION** — 같은 정답을 가진 150쌍의 질문을 비교했더니, 자연스러운 표현에서 hit@3가 0.853 → 0.753으로 낮아졌습니다. 질문의 말투도 평가 결과에 영향을 준다는 걸 확인했습니다. [질문 비교 실험](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b)
- **Autonomy** — 초기 소표본 실험 이후 정책 선택용·평가용 데이터를 나눠 다시 비교했습니다. 경량 환경의 5개 학습 seed·전체 4,160개 평가 episode에서 PPO best 성공률은 85.4%, 규칙 기반은 86.2%였습니다. [평가 기록](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo/blob/dev/experiments/m1_reproducibility/RESULTS.md)
- **GCJ Hands-on** — 같은 20개 과제를 모두 통과해도 handoff의 p50 지연은 약 63%, 비용은 약 32% 늘었습니다. 이 작은 도구 작업에는 단일 Agent를 선택했습니다. [비교 기록](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)

### 인식 결과를 다음 작업으로 연결하기

- 로봇 위치 오류를 따라가 보니 센서 데이터가 로봇 사이에 섞이고 있었습니다. Gazebo 토픽과 프레임을 생성 단계부터 분리했습니다. [4대 주행 기록](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md)
- 고정 CCTV에서 작은 사람을 놓치는 장면에 배경 차분을 적용하고, 바닥 좌표 투영·장애물 지도 레이어를 A*에 연결했습니다. 지도 반영까지 확인했고 경로 변경 효과는 추가 검증이 필요합니다. [CCTV 실험](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/cctv/PROGRESS.md)
- ContextWeld에서는 이미지 관측과 문서 조건을 따로 남기고, 모호한 대상은 검토로 보냅니다. 최초 판독을 보존하면서 선택한 수정만 새 검토에 반영하고 중복 전송을 막았습니다. 검증 범위는 저장 이미지와 모의 수신까지입니다. [코드](https://github.com/ukkhnn/PAC2026) · [인식부터 전달까지](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md) · [대상 연결 검사](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7) · [수정·검토 흐름](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

## Stack

**AI·검색** — PyTorch, Transformers, BGE-M3, FAISS, BM25, OpenAI Agents SDK<br>
**애플리케이션·평가** — Python, FastAPI, JavaScript, SQLite, pytest, n8n<br>
**시스템·로보틱스** — C/C++, ROS 2, Gazebo, Linux, Git

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

## Education

서강대학교 컴퓨터공학과 · 2027년 2월 졸업 예정
