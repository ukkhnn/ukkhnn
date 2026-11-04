# Hi, I'm Hyunuk Yang 👋

### AI Engineer · RAG · Agents · Multimodal

> **RAG와 Agent를 사용자 기능으로 만들고, 실험과 실패 분석으로 개선합니다.**

검색·대화·도구 실행을 애플리케이션으로 연결하는 일에 관심이 있습니다.  
모델이 답을 만드는 과정부터 사용자가 결과를 확인하고 수정하는 흐름까지 함께 설계합니다.

[![Email](https://img.shields.io/badge/hyunuk200202%40gmail.com-333333?style=flat-square&logo=gmail&logoColor=white)](mailto:hyunuk200202@gmail.com)

---

## Selected Work

- 🏦 **[4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo)** `2026.07 – 09`<br/>
  예금보험공사 공개 정보를 바탕으로 6개 업무 분야의 질문에 답하는 기업 연계 RAG 챗봇 PoC.<br/>
  팀 프로젝트 · **전체 아키텍처·PM, Q-Form·라우팅, 검색·튜닝, 웹 통합**
  - 되묻기로 확인한 사용자 조건을 멀티턴 대화·검색·첨부 반환에 연결했습니다.
  - 사용자·관리자 웹을 통합하고, 관리자 설정이 검색·답변 생성·검증에 반영되도록 구성했습니다.

- 🧩 **[GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)** `2026.09 – `<br/>
  RAG·Router·도구형 Agent를 구현하고, 공통 평가 형식으로 품질·비용·지연시간을 비교하는 실험 프로젝트.<br/>
  2인 공동 실험 · **개인 Agent 구현·평가, 라우팅·통합 검증**
  - 단일 Agent와 handoff 구조 모두 **20/20 과제 통과**. 작은 도구형 과제에서 비용과 지연시간을 비교해 단일 구조를 선택했습니다. · [비교 결과](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)

- 🔎 **[ContextWeld](https://github.com/ukkhnn/PAC2026)** `2026.10 – ` · in progress<br/>
  선박 부재의 표기를 작업지시·도면·용접 기준과 연결해 해석하고, 조건 후보와 확인할 항목을 제시하는 시스템.<br/>
  2인 해커톤 프로젝트 · **기획·개발 담당, 이후 개인 개발 지속**
  - 판독 결과의 대상·문서 관계를 검증하고, 사용자 수정 기록 저장 → 재검토 → 모의 수신까지 연결했습니다. · [현재 구현 범위](https://github.com/ukkhnn/PAC2026#현재-구현-상태)

- 🤖 **[Opticore-AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo)** `2026.03 – 07`<br/>
  ROS 2·Gazebo 가상 물류창고에서 다중 AMR의 경로계획·위치추정·플릿 조율을 연결한 캡스톤 프로젝트.<br/>
  팀 프로젝트 · **시스템 아키텍처, Gazebo 환경, A* 경로계획·플릿 로직, 다중 로봇 통합**
  - 로봇별 센서·좌표계·주행 경로를 분리하고, 시뮬레이션에서 **4대 각각의 목표 도달**을 확인했습니다. · [실행 기록](https://github.com/sogang-opticore/opticore-amr/blob/dev/docs/fleet_f1/report.md)

- 📄 **OptiDocu** 🔒 `2026.10 – ` · in progress<br/>
  자동차 부품 공급사의 RFQ 검토와 부서별 근거 수집, 응답 초안·누락·상충 점검을 지원하는 산학 캡스톤 PoC.<br/>
  팀 프로젝트 · **업무 흐름 구체화, 가상 업무 데이터·평가 기준 설계**
  - 현재 데이터 제작·검수 단계. 가상 회사의 공통 기준을 작성하고, 업무 입력과 평가 정답을 분리하는 기준을 마련하고 있습니다.

- 🛠️ **[personal-ai / Agent Workspace](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)** · in progress<br/>
  Mac mini에서 개발 Agent를 실행하고, 웹에서 작업·추가 지시·승인·변경 내용을 관리하는 개인 작업 환경.<br/>
  개인 프로젝트 · **실행 상태·대기열, 승인 흐름, 웹·런타임 통합**
  - 실제 모델 작업과 HTTPS 접속, 서버 프로세스 재시작 후 완료 작업 보존을 확인했습니다. · [구현·검증 범위](https://github.com/ukkhnn/personal-ai/tree/main/agent-workspace)

---

## Highlights

**Connecting conversation, retrieval, and execution**

- 4MATION에서 짧은 후속 질문이 다른 업무로 분류되며 기존 조건을 잃는 문제를 보완했습니다. 업무 전환과 후속 질문을 구분하고, 확인된 조건을 검색·첨부 반환에 연결했습니다. 검색용 질의와 사용자 원문도 분리해 생성 모델에 불필요한 검색 문구가 들어가지 않도록 했습니다. · [문맥 보정](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/f9671aae7fa826104ebd7e77598aa5ad0deac745) · [검색 연결](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo/commit/d1cd6f55210042ee8c5d7ba9889e8c44f1dc9890)
- ContextWeld에서 화면에 있는 표기가 선택한 부재·이음과 무관한 경우를 걸러내도록 대상 관계를 검사했습니다. 사용자 수정 기록은 원본과 분리해 보존하고, 선택한 수정만 새 검토에 적용하며 같은 요청의 중복 전송을 막았습니다. · [대상 관계 검증](https://github.com/ukkhnn/PAC2026/commit/c48c555acab09eefde16473b1e6dd744daf51cf7) · [수정·재검토](https://github.com/ukkhnn/PAC2026/commit/ce0d47f1650233159f2044a80e4bc85093b04ea1)

**Finding and fixing evaluation errors**

- 4MATION의 평가 질문이 원문 표현과 가까워 검색 점수가 높게 보일 가능성을 확인했습니다. 동일 정답을 유지한 **150쌍**의 질문을 자연스럽게 바꿔 비교하자 hit@3가 **0.853 → 0.753**으로 낮아졌고, 이 차이를 이후 개선 판단의 기준으로 삼았습니다. · [페어 평가](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/9345bb02b98921aa518fa989790a1d22809cb07b) · [기준값 정정](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo/commit/355d08827273067273134e0fd13898e3f17b64a5)
- GCJ에서 앞 실험의 API 요청 수가 다음 조건에 누적되는 집계 오류를 수정했습니다. 조건별 시작값과의 차이로 집계하고, 원시 지연시간 자료가 없어 복원하지 못한 과거 값은 한계로 남겼습니다. · [측정 코드·기록 보정](https://github.com/GongChangJin/hands-on/commit/d2c6b2ca6672ff719cd62b18bebb09e86008d472)

**Choosing and improving agent workflows**

- GCJ의 단일 Agent와 handoff 구조는 같은 20개 과제를 모두 통과했지만, handoff는 p50 지연시간이 **약 63%**, 비용이 **약 32%** 높았습니다. 이 범위에서는 단일 구조를 선택하고, 과제 복잡도가 커질 때 다시 비교하도록 했습니다. · [구조 비교](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)
- 문서의 정책을 찾아 계산해야 하는 Agent가 임의의 숫자를 계산기에 넘기는 사례를 발견했습니다. 계산식의 숫자가 질문에 근거하는지 검사하고, 근거가 없으면 검색 후 계산하도록 실행 경로를 바꿨습니다. · [계산 입력 검사·회귀 테스트](https://github.com/GongChangJin/hands-on/commit/8000b1f45652e88d040a3a40a785db6d1d959716)

**Debugging across system boundaries**

- Opticore의 다중 로봇 위치추정 오류를 추적해 Gazebo의 센서·주행 토픽이 공유되고 있음을 확인했습니다. URDF 생성 → 시뮬레이터 토픽 → ROS 브리지를 로봇별로 분리해 데이터가 섞이는 원인을 수정했습니다. · [토픽 분리](https://github.com/sogang-opticore/opticore-amr/commit/58a9feb088d3d1361a2d616e53fb7b3eb88a2bd6)
- 지도 경계 밖에 걸친 벽이 이동 장애물로 잡히는 문제를 경계 조건 오류로 좁혀 수정했습니다. 같은 경로의 시뮬레이션 비교에서 벽의 오탐 트랙은 **10 → 0개**로 줄었으며, 별도로 남은 객체 미탐 문제와 구분해 기록했습니다. · [경계 조건 수정·비교 기록](https://github.com/sogang-opticore/opticore-amr/commit/5b76ac066719f1a49a14b835648e5288672fd1aa)

**Learning from project problems**

- 부트캠프 스터디에서 PyTorch 텐서 연산으로 attention·encoder·decoder를 구현하고 작은 번역 예제로 학습·추론을 실습했습니다. 4MATION을 진행하며 자발적으로 공부한 검색 지표·라벨 품질·평가 편향·신뢰구간도 최소 구현과 시뮬레이션으로 정리했습니다. · [Transformer 실습](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/blob/main/StudySession_FUNDAMENTAL/Fundatmental_ipynb/FUNDAMENTAL_day10~14_TransformerWithoutMagic.ipynb) · [프로젝트 연계 학습](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP/tree/main/selfstudy_rag_for4MATION/C_evaluation)

---

## Stack

**AI · Retrieval**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Transformers](https://img.shields.io/badge/Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![BGE-M3](https://img.shields.io/badge/BGE--M3-555555?style=flat-square)
![FAISS](https://img.shields.io/badge/FAISS-555555?style=flat-square)
![BM25](https://img.shields.io/badge/BM25-555555?style=flat-square)
![Agents SDK](https://img.shields.io/badge/OpenAI_Agents_SDK-412991?style=flat-square)

**Application · Evaluation**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Phoenix](https://img.shields.io/badge/Arize_Phoenix-6F42C1?style=flat-square)

**Systems · Robotics**

![ROS 2](https://img.shields.io/badge/ROS_2-22314E?style=flat-square&logo=ros&logoColor=white)
![Gazebo](https://img.shields.io/badge/Gazebo-F58113?style=flat-square)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

---

## Other Repositories

| Repository | Description |
| --- | --- |
| [LikeLion AI/NLP Study](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) | 멋쟁이사자처럼 AI/NLP 5기 스터디·실습과 4MATION 진행 중의 자발적 학습 기록. PyTorch·Transformer 구현, RAG 평가 개념의 실험·시각화 |
| [Opticore AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) | 규칙 기반 주행과 BC·PPO 비교, 안전 제약과 평가 조건 점검 |
| [CS231n PyTorch Implementation](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) | PyTorch 기초와 KNN 구현·실험 |

---

## Education

- **서강대학교 컴퓨터공학과** 재학 · `2021.03 – 2027.02 졸업 예정`
