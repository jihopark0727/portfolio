# 박지호 · Product Manager Portfolio

기술을 깊이 이해하되, 그것으로 사람의 문제를 푸는 PM을 지향합니다. 개발자의 언어를 이해하는 기획자로서 문제 정의부터 지표 설계, 검증까지 제품의 전 과정을 책임집니다.

학교와 부트캠프에서 진행한 3개의 프로젝트로 "개발자 → 개발자의 언어를 이해하는 기획자 → PM"으로 이어진 성장 과정을, 재직 중인 회사에서 직접 기획하고 만들어 운영하는 2개의 사내 도구로 그 역량을 실무에서 어떻게 쓰고 있는지 담았습니다.

🔗 **Portfolio** — [jihopark0727.github.io/portfolio](https://jihopark0727.github.io/portfolio/)

---

## 💼 Work — 재직 중인 회사 기획팀

### 🟣 메일 트리아지봇 — 요청 메일을 Slack 안에서 끝내는 업무 자동화 봇

**Role:** 기획 · 개발 전 과정 · 사내 프로젝트 2026

외부 요청 메일을 LLM으로 분석해 Slack 카드로 올리고, 담당자 지정부터 완료 처리, Jira 티켓 생성, 기존 이슈 연결까지 Slack 안에서 끝내는 사내 업무 자동화 봇. 요구사항 정의부터 설계, 구현, 테스트, 배포, 운영 이슈 대응까지 전 과정을 맡았습니다.

- "누락 0"을 목표로 한 설계: 어떤 실패도 조용히 버리지 않고 사람에게 확인요망 알림 · AI는 분석하고 결정은 사람이 하는 4갈래 처리 경로(완료 · 티켓 · 연결 · 무시)
- 팀 피드백 반영: 카드별 리마인더를 하루 세 번 목록 알림으로 전환 · 개인 PC에서 AWS EC2 + systemd 상시 운영으로 이전 · 테스트 512개와 typecheck 통과 상태로 운영 반영

### 🟠 OPS-BOARD — 정기 업무를 오늘 할 일로 띄워 주는 사내 운영 보드

**Role:** 기획 · 구현 · 운영 (직접 제작) · 사내 프로젝트 2026

인수인계로 넘어온 정기 업무를 놓치지 않도록, 주기(일간 · 주간 · 월 첫 평일 · 월 마지막 평일)마다 할 일을 카드로 띄워 주는 칸반 보드. 2주 POC로 리포팅 보드부터 열고 범위를 넓히며, 운영 중 생긴 장애를 직접 진단하고 고쳤습니다.

- 정기 업무 30 → 34종 · 리포팅 노출 9 → 13종으로 확장 · 자동 테스트 73 → 98개
- 멱등 설계(UNIQUE 인덱스 + INSERT OR IGNORE)로 절전 누락을 매시 재확인 방식으로 해결 · 파일 복사 백업의 WAL 누락(296건 중 229건)을 db.backup()으로 교체해 296 = 296 검증

---

## 📂 Projects

### 🟢 Plan B — AI 실시간 여정 복구 에이전트

**Role:** PM · Backend 겸임 · goorm Builders League 2026

현지의 폭우·임시 휴업·인파로 여정이 무너진 순간, 최적의 대안 경로를 되살리는 여행 서비스. 문제 정의부터 지표 설계, 핵심 기능 구현, 2사이클 베타 검증까지 총괄했습니다.

- 대안 교체 전환율 42% → 61% (+19%p) · 추천 API 응답 400s → 20s (−95%)
- PMF 45%(Sean Ellis 기준 돌파) · NPS +33 · 부트캠프 중간 발표 1위

### 🟤 Seatify — AI 기반 실시간 좌석 인식

**Role:** Backend · 기획 참여 · 2025 캡스톤 디자인 (팀 3인)

CCTV 영상을 YOLO로 분석해 카페의 좌석별 점유 상태를 실시간으로 시각화하는 서비스. 백엔드 서버·DB 설계와 실시간 처리 최적화를 맡고, 아이디어 발굴·사용자 인터뷰 등 기획 전반에 참여했습니다.

- 평균 응답 속도 15s → 7s (−53%) · DB 복합 인덱스로 쿼리 효율 약 4.6배 향상
- 사용자 인터뷰 → 실시간(3초) 좌석 상태·리뷰/커뮤니티 기능 결정으로 연결

### 🔵 마음읽기 — AI 감정 분석 상담 지원 시스템

**Role:** Backend · 문제 정의·리서치 · 2024 캡스톤 디자인 (팀 3인)

녹음 한 번으로 축어록·감정 분석·시각화까지 자동화한 심리 상담사 지원 웹서비스. 현직 상담사 심층 인터뷰로 문제를 정의하고, 그 요구사항을 백엔드로 직접 설계·구현했습니다.

- 현장 인터뷰 → 요구사항 → DB 설계 → API로 이어지는 문제 중심 설계
- KoBERT → OpenAI API 전환 주도: "모델이 좋은가"가 아니라 "우리 데이터에서 되는가" 기준의 기술 의사결정

---

## 🛠 Tech Stack

| 구분 | 기술 |
|---|---|
| Backend | Node.js · TypeScript · Express · Spring Boot · Flask |
| Frontend | React (Vite) |
| Database | MySQL · SQLite |
| AI · Data | Claude API · OpenAI API · YOLO · OpenCV · Naver Clova STT |
| Integration | Slack Bolt · Jira REST API · Gmail API |
| Infra · Etc | AWS EC2 · systemd · pm2 · node-cron · Vitest · JWT · Amplitude |

---

## 📬 Contact

- Email — jiho200727@naver.com
- GitHub — [github.com/jihopark0727](https://github.com/jihopark0727)
