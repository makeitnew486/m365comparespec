# Changelog

## 2026-05-19 — "왜 FBKR" 섹션 추가

홈 페이지 영업 narrative 완성. **프로페셔널 서비스 로드맵 → 둘러보기 사이**에 "왜 FBKR과 함께해야 하는가" 신규 섹션 삽입.

흐름:
- 왜 구독형 (3 pillars) → 고객 제안 5단계 → 프로페셔널 서비스 로드맵 → **왜 FBKR (NEW)** → 둘러보기

6 카드 (`.reason-grid` 패턴 재사용):
1. 종합 IT 파트너 (라이선스 + 사무환경 + 보안 한 창구)
2. 고객 환경 깊이 이해 (기존 DocuShare/ApeosWare와 매끄러운 통합)
3. 글로벌 그룹 + 현지 인프라 (Fujifilm 그룹 + 한국 전국망)
4. 프로페셔널 서비스 turn-key (도입~운영 책임)
5. DX·AI 트랜스포메이션 동반자 (FBKR OCR·문서AI + Copilot 시너지)
6. 장기 라이프사이클 관리 (갱신·업셀·최적화 매년 동행)

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
