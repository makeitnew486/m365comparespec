# Changelog

## 2026-06-07 (오후) — M365 E7 + Agent 365 신규 SKU 반영

직전 검증(2026-05-11) 이후 Microsoft 공식 페이지 확인 결과 **2026-05-01 자로 신규 SKU 2개 출시**됨을 발견. 즉시 반영.

### 신규 SKU 소개 — 영업용 쉬운 설명

**Microsoft 365 E7 (Frontier Suite)**
- "AI 비서(Copilot)와 AI 직원(Agent)이 사람과 함께 일하는 시대용 최상위 라이선스"
- 구성: **E5 + M365 Copilot + Entra Suite + Agent 365** 4개 SKU 통합
- 2015년 E5 출시 이후 **10년 만의 신규 엔터프라이즈 티어**
- 한국 가격은 공시되어 있으나 본 문서에는 표기하지 않음 (FBKR 영업 견적 별도)

**Agent 365**
- "회사 안 모든 AI 에이전트를 IT 팀이 한 콘솔에서 보고·관리·통제하는 **에이전트 관제 센터**"
- Copilot Studio 등으로 만든 커스텀 에이전트를 안전하게 운영하기 위한 거버넌스 도구
- E7에 기본 포함 + 별도 add-on으로도 구매 가능
- 컨셉: "AI는 도구 → AI는 워크포스" 전환점

### 반영된 변경

- **플랜 섹션** — Teams 포함 카테고리에 E7 카드 추가 (다크 인버전 + "신규" 배지), Copilot 옵션 카테고리에 Agent 365 카드 추가
- **플랜 섹션 상단** — 신규 출시 안내 박스 (notice) 추가
- **홈 공지 배너** — E7 출시 공지 + 기존 7월 가격 공지 2개 병렬
- **비교 매트릭스** — E7 컬럼 추가 (E5 옆), 신규 카테고리 "🚀 E7 신규 (Entra Suite · Agent 365)" + 2 신규 행, `min-width 900 → 1080px`, `e7tag` CSS 추가
- **page-head subtitle** — "4 SKU + Copilot 옵션 4종" → "E3·E5·E7·Teams 제외 변형 + Copilot·Agent 365 옵션"

### 출처
- [Microsoft 365 plans and pricing (한국)](https://www.microsoft.com/ko-kr/microsoft-365/enterprise/microsoft-365-plans-and-pricing)
- [Directions on Microsoft — E7 Agent-Centered Subscription Plan](https://www.directionsonmicrosoft.com/microsoft-365-e7-a-new-subscription-plan-with-agents-at-the-center/)
- [Trustmarque — M365 E7 & Agent 365 Launching 1 May](https://trustmarque.com/microsoft-365-e7-agent-365-whats-launching-1-may-and-what-it-means)
- [Redmond Channel Partner — Agent 365 + E7 launch](https://rcpmag.com/articles/2026/05/06/microsoft-pushes-ai-governance.aspx)

---

## 2026-06-07 (오전) — "왜 FBKR" 섹션 + 콘텐츠 정책 강화

### "왜 FBKR과 함께해야 하는가" 섹션 신설
홈 페이지 영업 narrative 완성. **프로페셔널 서비스 로드맵 → 둘러보기 사이**에 신규 섹션 삽입.

홈 narrative 흐름:
- 왜 구독형 (3 pillars) → 고객 제안 5단계 → 프로페셔널 서비스 로드맵 → **왜 FBKR (NEW)** → 둘러보기

최종 5 카드 (`.reason-grid` 패턴 재사용):
1. 종합 IT 파트너 (라이선스 + 사무환경 + 보안 한 창구)
2. 고객 환경 깊이 이해 (기존 FBKR 사무기기·문서 솔루션과 매끄러운 통합)
3. 프로페셔널 서비스 turn-key (도입~운영 책임)
4. DX·AI 트랜스포메이션 동반자 (FBKR OCR·문서AI + Copilot 시너지)
5. 장기 라이프사이클 관리 (갱신·업셀·최적화 매년 동행)

### 콘텐츠 정책 (사용자 명시)
- **DocuShare 언급 제거** — FBKR 현재 미운영(2026-06-07 사용자 확인). 카드 01·CHANGELOG·HANDOVER에서 모두 제거. `ApeosWare 등` 일반 표기로 대체.
- **카드 03 "글로벌 그룹 + 현지 인프라" 삭제** — Fujifilm 그룹·전국망 언급 제외. 6 카드 → 5 카드. 섹션 부제 "6가지 → 5가지" 변경.

### 문서 동기화
- `README.md` 5 카드 + 콘텐츠 정책 섹션 + 2026-06-07 날짜
- `docs/HANDOVER.md` DD-010 갱신 + 섹션 4.1 홈 구조 갱신 + 콘텐츠 금지 항목 명시
- 메모리 `project_m365_tool.md` — DocuShare/Fujifilm 금지 룰 영구 기록

---

## 2026-05-11 — MAXHUB-inspired redesign + content overhaul

### 디자인
- **Airbnb/MAXHUB-inspired 디자인 시스템** 전면 채택
  - 마이크로소프트 블루 → 흰 캔버스 + rausch 핑크 (#ff385c) 액센트
  - 잉크 #222 텍스트 + 헤어라인 #ddd 보더 + 풀-라운드 칩
- **나눔스퀘어 네오 Bold** 전 영역 통일 (`* { font-weight: 700 !important }`)
- 80px sticky nav + underline 액티브 인디케이터
- 그림자 거의 제거, 컬러 블로킹 위주 시각 위계

### 구조 단순화
- nav 탭 **7개 → 5개** (홈/플랜/기능/라이선스/영업 자료)
- Apps → 기능 탭 안 sub-section으로 흡수
- Terms → 영업 자료 탭 안 sub-section으로 흡수
- 거대 오렌지 hero 제거 → page-head 컴팩트 헤더로 교체

### 컨텐츠
- **모든 ₩ 가격 제거** (24곳) — "FBKR 영업 견적 별도"로 통일
- **라이선스 모델 섹션** 신규: 영구형 카탈로그 8종 + 비교표 + 9가지 전환 이유 + 6가지 반박 처리
- **홈 전략 대시보드** 신규:
  - 왜 구독형 (3 pillar: AI / 보안 / 협업)
  - 고객 제안 5단계 (진단→페인→가치제안→PoC→전환)
  - FBKR 프로페셔널 서비스 로드맵 (STAGE 1~4, GOAL은 다크 인버전)
- **2026-07-01 가격 인상 advisory** 공지 (Microsoft 공식 공지 링크 포함)
- **앱 33개 상세 모달** — 아이콘·카테고리·설명·핵심 기능·영업 활용·포함 플랜
- **사용 안내 disclaimer** — nav 우측 ⓘ 버튼 + 풀-라운드 툴팁

### 인터랙션
- FBKR 로고 클릭 → 홈 이동 (키보드 접근성 포함)
- 앱 카드 클릭 → 상세 모달 팝업
- ⓘ 사용 안내 → 부드러운 disclaimer 툴팁
- ESC / 배경 클릭 → 모달·툴팁 닫기

### 테이블
- 27행 큰 기능 매트릭스 (sticky thead `top: 80px`, sticky 첫 컬럼 `left: 0`)
- `.table-wrap` visual 제거 (background/border/radius 모두 0) — sticky thead가 떠오를 때 wrap 안 흰 공백 보였던 문제 해결
- 모바일(≤1023px)에서만 `overflow-x: auto` 활성화 → 데스크탑 sticky context 보존
- 셀 패딩 컴팩트하게 (thead 12px, tbody 11px)

### 줄바꿈/타이포
- `word-break: keep-all` + `overflow-wrap: anywhere` — 한글 단어 보존 + ASCII 점(·)으로 이어진 긴 토큰 안전 줄바꿈
- 좁은 카드용 괄호 내부 공백 22개 패턴 `&nbsp;` 치환 (Teams 포함, E3/E5 모두 가능, ID·액세스 관리 등)

### 폰트 로딩
- jsDelivr/moonspam NSN CDN을 1순위로 추가 (Naver pstatic CDN은 fallback) — GitHub Pages에서 안정 로드

---

## 2026-05-07 — Initial commit

- 단일 HTML M365 영업 가이드 도구
- 7탭 구조 (홈/플랜/라이선스 모델/기능 비교/앱/영업 팁/영업 용어)
- Microsoft 블루 디자인
- ₩ 가격 표기 포함
- GitHub Pages 첫 배포

---

## 운영 노트

- **Repo:** https://github.com/makeitnew486/m365comparespec
- **Live URL:** https://makeitnew486.github.io/m365comparespec/
- **작업 흐름:** `Output/index.html` 편집 → `cp Output/index.html index.html` → commit → 사용자가 push
- 자세한 인수인계는 [`docs/HANDOVER.md`](docs/HANDOVER.md) 참고
