# Hyunuk Yang · 양현욱

**Applied AI · Document Retrieval, Agents & Robotics**

Computer Science and Engineering, Sogang University · Expected Feb 2027

[hyunuk200202@gmail.com](mailto:hyunuk200202@gmail.com) · [English résumé](README.en.md)

예금보험 신청자에게 필요한 서식을 찾는 챗봇과 자동차 부품사가 견적을 검토하는 도구를 만들었습니다. 두 프로젝트에서 가장 많이 고민한 질문은 “지금 이 사람이 판단하려면 어떤 정보가 필요한가?”였습니다. 로봇 프로젝트에서는 A* 경로계획을 맡았고, 캡스톤이 끝난 뒤 팀에 후속 실험을 제안해 학습한 주행 정책을 창고 시뮬레이터에서 시험하고 있습니다.

## Selected Project Experience

### 4MATION / 예봄24 · 예금보험 업무 안내 챗봇

**Project Lead & RAG Developer** · 개발 4인 · 멋쟁이사자처럼 × ClaBi · Jul–Sep 2026, 이후 자율 개선

예금보험공사의 공개 자료를 바탕으로 6개 업무를 안내합니다. 같은 착오송금 반환 신청이라도 개인이 직접 신청할 때와 법인의 대리인이 신청할 때 필요한 서식이 다릅니다.

- 신청 주체와 자격이 빠지면 되묻는 대화 양식(Q-Form)을 설계했습니다. 사용자가 “준비물도 알려줘”라고 이어 물으면 앞서 확인한 조건을 검색어와 첨부 서식 선택에 반영합니다.
- 웹페이지와 첨부파일의 출처를 보존하고, 키워드 검색(BM25)과 벡터 검색(FAISS)의 순위를 결합했습니다. 문서 분할 방식을 바꿔도 결과를 비교할 수 있도록 정답 근거를 원문의 구절로 표시하는 방식을 제안했습니다.
- 같은 정답 문서를 가진 질문 150쌍을 비교했습니다. 원래 질문을 일상적인 표현으로 바꾸자 하이브리드 검색의 상위 3개 결과에 정답 문서가 든 비율이 85.3%에서 75.3%로 낮아졌습니다. [프로젝트 코드](https://github.com/likelion-4MATION/4MATION) · [질문 쌍별 검색 결과](https://github.com/likelion-4MATION/4MATION_archive/blob/dev/crawler/data/pair_report.md)

### OptiDocu · 자동차 부품 견적 검토 지원

**Technical Lead** · 5인 · 서강대 캡스톤디자인 II × 겁쟁이사자 · Sep 2026–Present · 비공개

부품사가 견적요청서(RFQ)를 받으면 도면과 납기 조건을 읽고 여러 부서의 회신을 모아야 합니다. 협력 기업과 이 과정을 구체화하고, 담당자가 응답 초안의 각 항목에서 근거가 된 PDF 페이지나 엑셀 셀로 돌아갈 수 있도록 시스템을 설계했습니다.

- 문서 처리 단계의 입출력을 정하고 FastAPI 작업 큐·워커와 저장 구조를 구현했습니다. 개발용 사례에서 원문 근거를 추적하고, 담당자가 답을 고친 뒤에도 AI 초안과 수정 이력을 보존하는 흐름을 검증했습니다.
- 접수 시점의 모델이 며칠 뒤 도착한 회신을 미리 읽으면 평가가 쉬워집니다. 가상 견적 24건을 각각 **접수·회신 취합·제출 전**으로 나눠 시점별 입력 72개를 만들고, 허용 문서와 근거 답안을 분리했습니다. 개발용 8건과 최종 평가용 16건을 구분해 데이터를 동결하고 협력 기업의 확인을 받았습니다.

### Opticore · 다중 로봇 관제에서 학습형 주행까지

**Project Lead & Systems Integration** · 5인 · 서강대 캡스톤디자인 I 및 팀 후속 프로젝트

- **Warehouse AMR · Mar–Jun 2026.** ROS 2·Gazebo 창고에서 A* 전역 경로계획과 다중 로봇 관제를 개발했습니다. 한 로봇의 센서값이 다른 로봇에 섞이는 문제를 추적해 로봇별 토픽과 좌표계를 분리했고, 한 차례 시연에서 4대가 각자 지정된 목표에 도착했습니다. [4대 주행 기록](https://github.com/sogang-opticore/opticore-amr/blob/c4598710d9c2d0287feb6fce7ee7fa41114d8d81/docs/fleet_f1/report.md)
- **AMR Autonomy · Sep 2026–Present.** 팀원이 주도한 장애물 회피 규칙의 튜닝을 돕다가, 같은 시뮬레이터에서 주행 경험을 모아 회피 행동을 학습시키자고 제안했습니다. 경량 학습 환경과 ROS 2에서 최근 네 번의 LiDAR 스캔을 같은 순서로 읽도록 맞추고, 학습 정책이 로봇에 속도 명령을 보내는 경로를 통합했습니다.
- 정적 4m 시험에서 로봇 한 대가 정책의 명령으로 주행하다가 강제 정지 후 재출발해 충돌 없이 도착했습니다. 더 긴 경량 환경 임무 4종은 모두 시간 초과였습니다. 경로 진척도와 실제 목표 거리를 대조해 목표 옆을 지나친 경우와 차단 구간에서 거의 전진하지 못한 경우를 구분했습니다. [창고 주행 및 실패 분석](https://github.com/sogang-opticore/opticore-amr-autonomy/blob/2116816b26dda37a5403e119053b38b8c75e1343/docs/m3/README.md)

## Additional Projects

- **ContextWeld · 멀티모달 작업 검토.** 2인 해커톤에서 시작해 대회 뒤 개인 개발로 이어갔습니다. 저장 이미지에서 읽은 선박 부재 표기를 작업지시·도면·용접절차서와 연결했습니다. 대상이 모호하면 사람이 확인하도록 했고, 확인된 명세를 현대·두산 두 형식으로 변환해 모의 수신기까지 전달했습니다. [판독부터 모의 전달까지](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md)
- **Agent Workspace · 개인 개발.** Mac mini에서 코딩 에이전트의 작업마다 Git worktree를 분리하고, 웹에서 추가 지시와 명령 승인을 처리하게 만들었습니다. 실제 DeepSeek 작업의 파일 변경과 서버 재시작 후 완료 기록 보존을 확인했습니다. [구현 및 실행 기록](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md)
- **VeriFlow · PM & Backend · May 2026.** Upstage 해커톤 3인 팀에서 고객상담 챗봇 답변을 발송 전에 검증하는 n8n 워크플로를 개발했습니다. Upstage API로 정책 PDF에서 규칙을 추출하고, 답변을 원문과 대조해 그대로 보내거나 수정하거나 상담원에게 넘기도록 구성했습니다. [워크플로 코드](https://github.com/ukkhnn/upstage_hackathon_team19)

## Leadership & Teaching

- **공창진 AI Hands-on Lab · Co-organizer · Sep 2026–Present.** 자율 개발 모임을 공동 운영하며 에이전트 구조를 직접 구현하고 비교했습니다. 도구를 쓰는 고정 과제 20개에서 단일 에이전트와 전문 에이전트에 위임하는 구조가 모두 만점을 기록했습니다. 위임 구조의 중앙 응답 시간이 1.28초에서 2.08초로 늘고 비용도 약 32% 올라, 이 과제에는 단일 에이전트를 선택했습니다. [실험 결과](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)
- **서강대학교 · Undergraduate Teaching Assistant · Fall 2026.** 알고리즘설계와분석 수업의 수업 환경 준비, 시험 감독과 채점을 담당했습니다.

## Education & Training

- **서강대학교 · 컴퓨터공학과 심화단일전공** · 2027년 2월 졸업 예정
- **멋쟁이사자처럼 · 기업 연계 AI·자연어처리 심화과정** · Jun–Sep 2026 · 343시간 수료. ClaBi 연계 4MATION 프로젝트에서 팀을 이끌었습니다.

## Technical Skills

| 분야 | 프로젝트에서 사용한 기술 |
| --- | --- |
| Languages & backend | Python, C/C++, JavaScript, SQL, FastAPI, SQLite, pytest |
| Retrieval & agents | BM25, FAISS, BGE-M3, OpenAI Agents SDK, n8n |
| Robotics & learning | ROS 2, Gazebo, A*, LiDAR, PyTorch, Stable-Baselines3 |

<details>
<summary>전공 과제 · 학습 저장소 · 프로젝트 아카이브</summary>

- **Systems coursework (비공개).** Pintos에서 스케줄링·시스템 호출·가상 메모리를 구현했습니다. 후속 정리본은 QEMU 테스트 226개를 통과했습니다. 그 밖에 캐시 시뮬레이터, OpenSSD의 호스트 I/O와 FTL, C++·OpenGL 그래픽스 과제를 수행했습니다.
- **AI study.** [AI/NLP 부트캠프 실습](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) · [CS231n PyTorch 구현](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) · [딥러닝 자율 학습](https://github.com/ukkhnn/Self_Study_Deep_Learning)
- **Project repositories.** [4MATION 초기 구현](https://github.com/likelion-4MATION/4MATION_archive) · [Opticore AMR](https://github.com/sogang-opticore/opticore-amr) · [AMR Autonomy](https://github.com/sogang-opticore/opticore-amr-autonomy) · [공창진 Hands-on](https://github.com/GongChangJin/hands-on) · [GCJ projects](https://github.com/GongChangJin/projects) · [GCJ project template](https://github.com/GongChangJin/project-template)
- **개인 계정의 프로젝트 사본.** [4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [4MATION archive](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo) · [Opticore AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) · [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)
- **Learning forks.** [Let's Build GPT](https://github.com/ukkhnn/practice-let-s-build-gpt) · [Build with AI](https://github.com/ukkhnn/build-with-ai-handson-campus-hands-on) · [oh-my-claudecode](https://github.com/ukkhnn/oh-my-claudecode)

</details>
