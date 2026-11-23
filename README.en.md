# ukkhnn · 양현욱

Computer Science @ Sogang University · [English résumé](https://github.com/ukkhnn/ukkhnn/blob/main/README.en.md) · [Email](mailto:hyunuk200202@gmail.com)

주로 문서 검색과 AI 에이전트를 만들고, 로봇 주행도 실험합니다. 지난 학기에 팀원들과 만든 가상 창고를 이번 학기에도 쓰고 있습니다. 그때는 A*로 로봇이 갈 길을 짰고, 지금은 그 길에서 장애물을 만났을 때 어떻게 움직일지를 학습시키고 있습니다.

## 🔧 On my desk

### OptiDocu · 자동차 부품사의 견적 검토

**개발 리드** · 서강대 캡스톤디자인 II × 겁쟁이사자 · 5인 · 2026.09–현재

자동차 부품사가 고객에게 견적을 보내려면 도면과 납기 조건을 읽고 여러 부서의 회신을 모아야 합니다. 협력 기업과 이 과정을 살펴보고, 담당자가 응답 초안의 각 항목에서 근거가 된 PDF 페이지나 엑셀 셀로 돌아갈 수 있는 검토 도구를 설계했습니다.

- 전체 아키텍처와 모듈별 입출력을 정하고, 문서를 처리하는 작업 큐·워커와 수정 이력을 저장하는 백엔드를 구현했습니다.
- 평가 데이터를 만들 때 가장 신경 쓴 건 **그때 알 수 있었던 정보**입니다. 견적을 처음 받은 날에는 사흘 뒤에 올 부서 회신을 볼 수 없기 때문입니다. 가상 견적 24건을 접수·회신 취합·제출 전으로 나눠 입력 72개를 만들고, 개발용 8건과 최종 평가용 16건을 분리해 협력 기업의 확인을 받았습니다.

*산학협력 비공개 저장소*

### Opticore AMR Autonomy · 학습한 주행 정책을 창고로

**후속 프로젝트 제안 · PM · 시스템 통합** · Opticore 5인 · 2026.09–현재

이전 캡스톤에서 팀원이 맡은 장애물 회피 규칙의 튜닝을 도왔습니다. 규칙 하나를 바꿀 때마다 같은 상황을 다시 주행하다 보니, 이 시뮬레이터에서 모은 경험으로 회피 행동을 학습시켜 보고 싶었습니다. 종강 후 팀에 제안해 시작한 프로젝트입니다.

- 경량 학습 환경과 ROS 2가 최근 네 번의 LiDAR 스캔을 같은 순서로 읽도록 맞추고, 학습 정책이 Gazebo 속 로봇에 직접 속도 명령을 보내도록 연결했습니다.
- 정적 4m 시험에서는 로봇이 주행 중 강제로 멈춘 뒤 다시 출발해 충돌 없이 도착했습니다. 더 긴 경량 환경 임무 4종은 모두 시간 초과였습니다. 주행 기록을 열어 보니, 한 임무에서는 **경로 끝까지 가고도 목표 옆에 멈췄고**, 다른 임무에서는 막힌 통로 앞에서 거의 움직이지 못했습니다.

[창고 주행 기록](https://github.com/sogang-opticore/opticore-amr-autonomy/blob/2116816b26dda37a5403e119053b38b8c75e1343/docs/m3/README.md) · [임무별 진단 데이터](https://github.com/sogang-opticore/opticore-amr-autonomy/blob/2116816b26dda37a5403e119053b38b8c75e1343/experiments/m3/training-diagnostic.json)

## 📌 Selected work

### 4MATION / 예봄24 · 예금보험 업무 안내 챗봇

**PM · RAG 및 대화 설계** · 멋쟁이사자처럼 × ClaBi · 개발 4인 · 2026.07–09, 이후 자율 개선

“준비물도 알려줘.” 착오송금 반환을 신청하는 대화에서 이 한마디에 답하려면, 앞서 사용자가 **법인의 대리인**이라고 말한 사실을 기억해야 합니다. 예봄24는 예금보험공사의 공개 자료를 바탕으로 6개 업무의 절차와 서식을 안내합니다.

- 신청 주체와 자격이 빠지면 되묻는 대화 양식(Q-Form)을 설계했습니다. 확인한 조건은 다음 질문의 검색어와 첨부 서식 선택에도 이어집니다.
- 웹페이지와 첨부파일의 연결을 보존하고 BM25 키워드 검색과 FAISS 벡터 검색을 결합했습니다. 문서 분할 방식을 바꿔 가며 검색을 비교할 수 있도록, 정답 근거를 원문 구절로 표시하는 방식을 제안했습니다.
- 같은 정답 문서를 가진 질문 150쌍을 비교했습니다. 상위 3개 검색 결과에 정답 문서가 포함된 비율은 원래 질문에서 **85.3%**, 일상적인 표현으로 바꾼 질문에서 **75.3%**였습니다.

[프로젝트 코드](https://github.com/likelion-4MATION/4MATION) · [질문 표현별 검색 결과](https://github.com/likelion-4MATION/4MATION_archive/blob/dev/crawler/data/pair_report.md)

### Opticore AMR · 네 대의 로봇이 함께 쓰는 창고

**PM · A\* 전역 경로계획 · 다중 로봇 관제** · 서강대 캡스톤디자인 I · 5인 · 2026.03–06

ROS 2와 Gazebo로 만든 물류 창고에서 로봇마다 목적지를 배정하고 A\*로 경로를 계산했습니다. 한 대씩 띄울 때는 괜찮았는데, 여러 대를 함께 띄우자 로봇의 추정 위치가 어긋났습니다. 원인을 따라가 보니 센서 메시지와 좌표계가 로봇 사이에 섞이고 있었습니다. 로봇별 토픽과 좌표계를 분리하고, 한 차례 창고 시연에서 **네 대가 각자의 목적지에 도착**하는 것을 확인했습니다.

[프로젝트 코드](https://github.com/sogang-opticore/opticore-amr) · [4대 주행 기록](https://github.com/sogang-opticore/opticore-amr/blob/c4598710d9c2d0287feb6fce7ee7fa41114d8d81/docs/fleet_f1/report.md)

### Side projects & hackathons

- **[ContextWeld](https://github.com/ukkhnn/PAC2026/blob/dev/docs/runs/WELD_PIPELINE.md)** · 선박 부재 사진에서 읽은 표기를 작업지시·도면·용접절차서와 연결하는 도구입니다. 2인 해커톤 이후 혼자 개발을 이어가며 모호한 판독을 사람이 수정하는 흐름을 추가했고, 확인된 작업 명세를 현대·두산 형식으로 변환해 모의 수신기까지 전달했습니다.
- **[Agent Workspace](https://github.com/ukkhnn/personal-ai/blob/main/agent-workspace/README.md)** · Mac mini에 코딩 작업을 맡기고 웹에서 추가 지시와 명령 승인을 처리하려고 만든 개인 도구입니다. 작업마다 Git worktree를 분리하고, 실제 DeepSeek 작업의 파일 변경과 서버 재시작 후 완료 기록 보존을 확인했습니다.
- **[VeriFlow](https://github.com/ukkhnn/upstage_hackathon_team19)** · Upstage 해커톤 3인 팀에서 PM·백엔드를 맡았습니다. 고객상담 챗봇이 답을 보내기 전에 정책 원문과 대조해 발송·수정·상담원 연결로 나누는 흐름을 n8n과 Upstage API로 구현했습니다.

## 🎓 Background

**서강대학교** · 컴퓨터공학과 심화단일전공 · 2027.02 졸업 예정  
**멋쟁이사자처럼** · 기업 연계 AI·자연어처리 심화과정 343시간 수료 · 2026.06–09  
**학부 조교** · 서강대 알고리즘설계와분석 수업 운영 및 시험 감독·채점 · 2026년 2학기

**공창진** · 2026년 9월부터 공동 운영하는 자율 개발 모임입니다. 관심 있는 기술을 각자 작게 구현해 보고 결과를 비교합니다. 단일 에이전트와 전문 에이전트에 일을 넘기는 구조를 같은 도구 사용 과제 20개에서 비교했을 때는 둘 다 20개를 통과했습니다. 위임 구조에서 응답 시간 중앙값이 1.28초에서 2.08초로 늘고 비용도 약 32% 높아, 이 과제에는 단일 에이전트를 선택했습니다. [실험 기록](https://github.com/GongChangJin/hands-on/blob/dev/experiments/01-agent-evaluation/README.md)

### Toolbox

| 분야 | 프로젝트에서 사용한 기술 |
| --- | --- |
| Retrieval & Agents | Python, BM25, FAISS, BGE-M3, OpenAI Agents SDK, n8n |
| Backend & Evaluation | FastAPI, JavaScript, SQL, SQLite, pytest |
| Robotics & Learning | ROS 2, Gazebo, C/C++, PyTorch, Stable-Baselines3 |

<details>
<summary><strong>전공 과제 · 학습 기록 · 다른 저장소</strong></summary>

**Systems coursework**  
Pintos에서 우선순위 스케줄링, 시스템 호출, 가상 메모리를 구현했습니다. 후속 정리본은 QEMU 테스트 226개를 통과했습니다. 캐시 시뮬레이터, OpenSSD의 호스트 I/O·FTL, C++·OpenGL 그래픽스 과제는 비공개 학업 저장소에 정리했습니다.

**AI study**  
[AI/NLP 부트캠프 실습](https://github.com/ukkhnn/LikeLion_26S_BootCamp_AI_NLP) · [CS231n PyTorch 구현](https://github.com/ukkhnn/CS231n-Pytorch-Implementation) · [딥러닝 자율 학습](https://github.com/ukkhnn/Self_Study_Deep_Learning)

**Team archives**  
[4MATION 초기 구현](https://github.com/likelion-4MATION/4MATION_archive) · [공창진 Hands-on](https://github.com/GongChangJin/hands-on) · [공창진 프로젝트](https://github.com/GongChangJin/projects) · [프로젝트 템플릿](https://github.com/GongChangJin/project-template)

**개인 계정의 프로젝트 사본**  
[4MATION](https://github.com/ukkhnn/4MATION-on-ukkhnns-repo) · [4MATION archive](https://github.com/ukkhnn/4MATION_archive-on-ukkhnns-repo) · [Opticore AMR](https://github.com/ukkhnn/opticore-amr-on-ukkhnns-repo) · [AMR Autonomy](https://github.com/ukkhnn/opticore-amr-autonomy-on-ukkhnns-repo) · [GCJ Hands-on](https://github.com/ukkhnn/GCJs-hands-on-on-ukkhnns-repo)

**Learning forks**  
[Let's Build GPT](https://github.com/ukkhnn/practice-let-s-build-gpt) · [Build with AI](https://github.com/ukkhnn/build-with-ai-handson-campus-hands-on) · [oh-my-claudecode](https://github.com/ukkhnn/oh-my-claudecode)

</details>
