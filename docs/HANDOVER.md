# HANDOVER — FBKR M365 영업 가이드

> 이 문서는 다음 작업자 (또는 미래의 Claude 세션) 가 이 프로젝트의 맥락·결정·구조·작업 방식을 빠르게 파악하기 위해 작성됨.

**📖 읽기 순서:** `HANDOVER.md` (현재 문서) → [`STATUS.md`](STATUS.md) (현재 라이브 상태) → [`TODO.md`](TODO.md) (미해결 작업) → [`../CHANGELOG.md`](../CHANGELOG.md) (변경 연대기)

---

## 1. 프로젝트 정체성

**무엇:** Microsoft 365 엔터프라이즈 영업 활동에 사용하는 FBKR 내부 영업 가이드 (단일 HTML, 단일 페이지).

**누가:** 후지필름비즈니스이노베이션 (FBKR) 영업팀.

**목적:**
1. M365 플랜·기능 빠른 확인 (고객 미팅 직전 1분 정리)
2. 영구형 Office 사용 고객을 M365 구독으로 전환 제안 시 talking point
3. 영업 신입에게 EA·NCE·SKU 등 용어 학습용
4. 최종적으로 FBKR 프로페셔널 서비스로 가는 영업 로드맵 제시

**Live:** https://makeitnew486.github.io/m365comparespec/
**Repo:** https://github.com/makeitnew486/m365comparespec

---

## 1.5. ⚠ 콘텐츠 절대 금지 항목

다음은 **사용자 명시 룰**이며, 추가하지 말 것 — 모든 새 콘텐츠·텍스트 변경 시 자가검열 필수.

| 항목 | 금지 사유 | 확인일 |
|---|---|---|
| **₩ 가격 표기** (E3·E5·Copilot 등) | FBKR 영업 견적이 공시가와 다를 수 있어 혼동 방지 | 2026-05-11 |
| **DocuShare 언급** (제품명·솔루션명) | FBKR 현재 미운영 | 2026-06-07 |
| **Fujifilm 그룹 / 글로벌 R&D / 일본 본사** 언급 | 사용자 명시 제외 ("왜 FBKR" 카드 03 삭제 시) | 2026-06-07 |
| **검증 안 된 자격·등급·실적** (Solutions Partner 등급, 도입사례 N개 등) | 임의 추가 금지 — FBKR이 명시 제공한 자산만 사용 | 2026-06-07 |
| **자동화 도구 직접 실행** (이메일 발송·PDF 변환·회사 PC 접근) | 워크플로우 정책 — News bot 메모리와 동일 | — |

**언급 가능 자산:** ApeosWare 등 문서 솔루션, OCR·문서 처리 AI 노하우, 전국 지점·기술 서비스 인프라, M365 도입·운영 컨설팅, Copilot 활성화 교육.

---

## 2. 파일 구조 & 워크플로우

```
m365_sales_tool/
├── index.html        ← GitHub Pages가 서빙하는 라이브 파일
├── Output/
│   └── index.html    ← 작업 사본 (.gitignore — git에 안 올라감)
├── README.md         ← 공개 readme
├── CHANGELOG.md      ← 주요 변경 연대기
├── docs/
│   └── HANDOVER.md   ← 이 문서
└── .gitignore
```

### 작업 흐름
1. **`Output/index.html` 편집** (Output이 작업 사본, root는 라이브)
2. 만족스러우면 `cp Output/index.html index.html`
3. `git add index.html` + `git commit -m "..."`
4. 사용자가 PowerShell에서 `git push` 직접 실행 (PAT 토큰 채팅 노출 방지)
5. GitHub Pages 자동 재배포 (~1분)
6. 브라우저 강제 새로고침 (Ctrl+Shift+R)로 확인

### Push 인증
- `gh` CLI 미설치
- Username: `makeitnew486`
- Email: `fxk20160015@gmail.com`
- PAT: 사용자가 자격증명 매니저에 입력 (채팅 X)

---

## 3. 디자인 시스템

### 영감
**Airbnb / MAXHUB compare tool** — 흰 캔버스 + 핑크 액센트 + ink 텍스트 + 헤어라인 + 풀-라운드 칩.

### 컬러 토큰
```css
--rausch: #ff385c;          /* Airbnb 핑크 — 브랜드 액센트 (FBKR 로고·rec-badge·featured tag·info icon) */
--rausch-deep: #e00b41;
--ink: #222222;             /* 주 텍스트 + featured 다크 인버전 카드 */
--body: #3f3f3f;            /* 본문 텍스트 */
--muted: #6a6a6a;           /* 보조 텍스트 (eyebrow·태그·메타) */
--muted-soft: #929292;
--hairline: #dddddd;        /* 1px 보더 */
--hairline-soft: #ebebeb;
--surface-soft: #f7f7f7;    /* 짝수 행 배경·태그 배경 */
--surface-strong: #f2f2f2;
--success: #2e7d32;         /* ✓ 체크 마크 */
```

### 타이포그래피
- **전 영역 통일**: `NanumSquareNeo-Variable` (Naver 나눔스퀘어 네오)
- **무게**: `700 !important` 강제 (Bold) — 사용자 요청
- **CDN 1순위**: `https://cdn.jsdelivr.net/gh/moonspam/NanumSquareNeo/nanumsquareneo.min.css`
- **CDN fallback**: `https://hangeul.pstatic.net/hangeul_static/css/nanum-square-neo.css` (Naver)
- 시스템 fallback: `Apple SD Gothic Neo`, `Malgun Gothic`, sans-serif
- 사이즈 토큰:
  - display-xl 32px (page-head h1)
  - display-md 22px (section-title h2)
  - title-md 18px (card h3)
  - body-md 16px / body-sm 14px / caption 13px / eyebrow 12px+letterspace

### 레이아웃 토큰
- 컨테이너 max-width 1280px
- 패딩 데스크탑 40px / 태블릿 24px / 모바일 16px
- 카드 라운드 16px (.card, .plan-card, .reason-card) / 14px (.app-item) / 12px (.tip-box)
- 칩/버튼 라운드 9999px (전부 풀-라운드)
- 1px hairline 보더로 컬러 블로킹 (그림자 거의 사용 안 함)

### 반응형 브레이크포인트
- `≤1280px`: 컨테이너 패딩 32px
- `≤1024px`: 패딩 24px · plan-card 2-up · pillar-grid 1-up · journey-flow 2-up · table overflow-x auto
- `≤768px`: 패딩 16px · nav 64px (logo 22px) · plan-card 1-up · sub 라벨 숨김 · nav-info 아이콘만
- `≤480px`: app-grid 3-up · journey-flow 1-up
- `≤425px`: app-grid 2-up

---

## 4. 섹션 아키텍처 (5탭)

각 섹션은 `<section class="section" id="...">`이고, JS의 `showTab(id)`가 클래스 `active` 토글.

```
overview → 홈
plans    → 플랜
compare  → 기능 (Compare + Apps 통합)
license  → 라이선스 모델
tips     → 영업 자료 (Tips + Glossary 통합)
```

### 4.1 홈 (#overview)
1. **page-head** (eyebrow + h1 + 한 줄 서브타이틀)
2. **notice 박스**: 2026-07-01 가격 인상 공지 (Microsoft 공식 공지 링크)
3. **왜 구독형 M365인가** (.section-title + 3 pillar 카드: AI·보안·협업)
4. **고객 제안 5단계** (.journey-flow 가로 5스텝: 진단→페인→가치 제안→PoC→전환)
5. **FBKR 프로페셔널 서비스 로드맵** (.roadmap-flow 4 stage: 라이선스→도입→운영→전략 파트너) — STAGE 4가 다크 인버전 + 핑크 태그로 destination 강조
6. **왜 FBKR과 함께해야 하는가** (.reason-grid 5 카드 — 종합 IT 파트너 / 고객 환경 이해 / 프로페셔널 서비스 turn-key / DX·AI 동반자 / 장기 라이프사이클)
7. **둘러보기** (.quick-grid 4링크: Plans / Features / License / Sales Kit)
8. **footer-source**: 출처 + 마지막 확인일

### 4.2 플랜 (#plans)
- **신규 출시 안내 박스** (notice with rausch 좌측 보더) — E7·Agent 365 영업용 쉬운 설명 (2026-05-01 출시)
- Teams 포함 (E3·E5·**E7** 🆕)
- Teams 미포함 (E3·E5·Teams Enterprise 단독)
- Copilot 옵션 (Copilot Chat 무료·M365 Copilot·**Agent 365** 🆕·Copilot Studio Pack·M365 Copilot Business SMB)
- 고객 유형별 추천 (.cards-grid 4장)

**가격 표기 정책:** 모든 .price/.pn 요소 제거. 각 카드 하단에 `📎 가격: **FBKR 영업 견적 별도** · 공식: microsoft.com` 형태.

### 4.3 기능 (#compare)
- **전체 기능 매트릭스** (.big-table): 29행 7열 (기능 항목·E3·E5·**E7 🆕**·E3 no-Teams·E5 no-Teams·+Copilot)
- 카테고리 행 (.cat-row): ink 배경 + 흰 텍스트, 6개 카테고리 (생산성·협업·보안·E5 이상·🚀 E7 신규·AI)
- E7 신규 카테고리에 2 행: Entra Suite (Zero Trust + 네트워크), Agent 365 (AI 에이전트 관리·거버넌스)
- `min-width: 1080px` (E7 컬럼 추가로 900 → 1080 확장)
- `e7tag` CSS — 다크(ink) 배경 + 흰 텍스트 9999 round chip
- **sticky thead** `top: 80px` (모바일 64px), z-index 3
- **sticky 첫 컬럼** `left: 0` (가로 스크롤 시 라벨 고정)
- `.table-wrap`는 visual 제거 (background/border/radius 없음) — sticky 떠오를 때 자리가 자연스러움
- 모바일 (≤1023px) 에서만 wrap이 `overflow-x: auto` 활성화
- **포함 앱 (sub-section)**: 검색 바 + 5개 카테고리 그리드 (AI·생산성·협업·보안·Viva)
- **앱 카드 33개 모두 클릭 가능** → 상세 모달 팝업

### 4.4 라이선스 (#license)
- **영구형 카탈로그**: 8 .card (Home & Business 2024, Home & Student 2024, Standard, Pro Plus, LTSC, Project, Visio, Exchange/SharePoint Server)
- **영구형 vs 구독형 비교표**: 12행 3열 (구분·영구형·구독형)
- **구독형 전환 9가지 이유**: .reason-grid (numbered 01–09)
- **자주 듣는 반박 처리**: 6 .card (비용/오프라인/보안/지원종료/호환성/교육)
- 출처 footer

### 4.5 영업 자료 (#tips)
- **영업 팁 (sub-section)**:
  - 카테고리 칩 필터 (전체·계약·반론·제품·프로세스)
  - 15개 .tip-box (data-cat별로 좌측 보더 색 차별: ink·rausch·success·orange)
  - 클릭 → `.tip-a` 펼침 (toggleTip)
- **영업 용어집 (sub-section)**:
  - 검색 바 + 5개 카테고리 칩 필터
  - 27개 .term-card (5 분류: 계약·구독·제품·기술·영업)

---

## 5. JavaScript 함수

```js
showTab(id)             // 탭 전환 (smooth scroll to top)
toggleTip(el)           // 영업 팁 아코디언
filterTips(cat, btn)    // 영업 팁 카테고리 필터
filterApps(q)           // 앱 검색 (텍스트)
filterTerms(q)          // 용어 검색
filterTermCat(cat, btn) // 용어 카테고리 필터
openAppModal(item)      // 앱 카드 클릭 → 상세 모달
closeAppModal()         // 모달 닫기
toggleInfoTooltip(e)    // nav 우측 ⓘ 사용 안내 토글
```

**Modal:** `#appModal` (fixed full-screen) + `appDetails` 객체 (33개 앱별 데이터). ESC·배경 클릭·닫기 버튼으로 닫힘. 모달 열림 동안 body 스크롤 잠금.

---

## 6. 주요 결정 기록 (Decision log)

### DD-001 — 디자인 시스템: Airbnb/MAXHUB 채택
**왜:** 사용자가 기존 MAXHUB 비교 도구의 깔끔한 UI를 좋아함. Microsoft 블루 디자인은 답답하다고 표현.
**적용:** 흰 캔버스 + rausch 핑크 액센트 (단, 액센트는 최소 사용) + ink 본문.

### DD-002 — 가격 전수 제거
**왜:** "회사 가격은 따로 있을 수 있기 때문" — FBKR 견적이 공시가와 다를 수 있어 혼동 방지.
**적용:** 24개 ₩ 위치 모두 삭제, "FBKR 영업 견적 별도"로 통일.

### DD-003 — 7탭 → 5탭 단순화
**왜:** 사용자가 "정신없다"고 표현. 카테고리화 단순화 요청.
**적용:** Apps → 기능 (Compare) 안 sub-section / Terms → 영업 자료 (Tips) 안 sub-section.

### DD-004 — 폰트 통일: 나눔스퀘어 네오 Bold
**왜:** 사용자 명시 요청 "글씨체는 나눔스퀘어네오 BOLD로 다 반영".
**적용:** `* { font-family: NanumSquareNeo-Variable; font-weight: 700 !important; }` 전역 강제.

### DD-005 — 홈을 전략 대시보드로
**왜:** 단순 네비 페이지가 아니라 영업 narrative를 전달하라는 사용자 요청.
**적용:** 왜 구독형 (3 pillar) → 5단계 제안 → 프로페셔널 서비스 로드맵 (STAGE 4=GOAL).

### DD-006 — 사용 안내 disclaimer
**왜:** "참고용일뿐 정확한 것은 내부 자료 및 담당자 확인하라고 부드럽게 표현해줘".
**적용:** Nav 우측 ⓘ 풀-라운드 버튼 → 클릭 시 툴팁 ("본 자료만으로 견적 발행 X" 등).

### DD-007 — 앱 카드 클릭 모달
**왜:** "무슨 기능인지 팝업으로" 사용자 요청.
**적용:** 33개 앱 모두 `appDetails` JS 객체에 풍부한 데이터 (설명·기능·영업 활용·포함 플랜) + 모달 컴포넌트.

### DD-008 — Sticky thead in compare table
**왜:** 사용자가 "스크롤 내릴 때 E3 E5 계속 틀고정"을 명시.
**구현:** thead th + 첫 컬럼 td를 position:sticky로. **wrap에 overflow-x:auto가 있으면 sticky context를 가로채므로 데스크탑에서는 overflow 제거, 모바일에서만 활성화**.

### DD-009 — 한글 줄바꿈 정밀 조정
**왜:** 카드 좁은 폭에서 "(E3/E5 모두 가능)" 같은 괄호 내용이 어색하게 분리됨.
**적용:** `word-break: keep-all` + `overflow-wrap: anywhere` + 괄호 내부 공백을 `&nbsp;`로 22개 패턴 일괄 치환.

### DD-010 — 홈에 "왜 FBKR" 섹션 추가
**왜:** 사용자가 "고객이 왜 FBKR이랑 해야 하는지" 영업 narrative 보강 요청.
**적용:** 홈 페이지의 프로페셔널 서비스 로드맵 다음, 둘러보기 앞에 5 reason 카드 추가 (2026-06-07 기준 — 원래 6 카드였으나 사용자 요청으로 "글로벌 그룹 + 현지 인프라" 카드 삭제). 기존 `.reason-grid` 패턴 재사용 (License 섹션의 9 전환 이유와 같은 컴포넌트). FBKR 자산만 언급 (ApeosWare·OCR·전국 지점) — 검증 안 된 자격/실적은 의도적으로 제외. **주의: DocuShare는 현재 미운영(2026-06-07 확인) — 언급 금지. Fujifilm 그룹/글로벌 R&D 언급도 제외.**

### DD-011 — Microsoft 365 E7 + Agent 365 신규 SKU 반영 (2026-06-07)
**왜:** 사용자가 "공식 페이지 갱신 확인" 요청. WebFetch 결과 **2026-05-01 자로 E7 + Agent 365 신규 출시** 확인 — 직전 검증(2026-05-11)에서 놓친 상태. E5 출시(2015) 이후 10년 만의 신규 엔터프라이즈 티어이므로 즉시 반영.
**E7 구성:** E5 + M365 Copilot + Entra Suite + Agent 365 4 SKU 통합.
**Agent 365:** 조직 내 모든 AI 에이전트를 IT/보안 팀이 한 콘솔에서 관리·통제하는 거버넌스 제어 플레인. E7에 기본 포함 + 별도 add-on 가능.
**적용:** ① 플랜 섹션 Teams 포함에 E7 카드 + Copilot 옵션에 Agent 365 카드 (모두 다크 인버전 + 핑크 "신규" 배지) · ② 플랜 섹션 상단에 영업용 쉬운 설명 안내 박스 (notice with rausch border) · ③ 홈 상단에 출시 공지 배너 추가 (기존 7월 가격 공지 위) · ④ 매트릭스에 E7 컬럼 추가 + Entra Suite/Agent 365 행 + `e7tag` CSS · ⑤ `min-width 900 → 1080px` · ⑥ 영업용 쉬운 설명 ("AI 비서 + AI 직원이 사람과 함께 일하는 시대", "에이전트 관제 센터") 카드·notice 모두에 일관 적용.
**가격 표기 정책 유지:** 한국 가격(₩133,800 E7 / ₩20,300 Agent 365)이 공식 페이지에 명시되어 있으나 **본 문서에는 표기 X** — 모든 신규 카드에도 "FBKR 영업 견적 별도".

---

## 7. 알려진 이슈 / TODO

- [ ] 모바일에서 sticky thead 비활성화 (현재 ≤1023px에서 overflow-x:auto로 sticky 무력화) — 정상 동작이지만 UX 개선 여지
- [ ] term-card / tip 본문의 괄호 일부는 `&nbsp;` 처리 안 됨 (320px+ 폭이라 거의 문제 없지만 가끔 모바일에서 어색할 수 있음)
- [ ] Pages 빌드 상태 자동 알림 없음 (push 후 직접 새로고침해서 확인)
- [ ] 출처 페이지 정기 검증 프로세스 없음 — Microsoft가 페이지 구조 바꾸면 링크 깨질 수 있음
- [ ] 2026-07-01 가격 변경 후 공식 공지 페이지에서 한국 신가격 확인 시 advisory 배너 업데이트 필요
- [ ] 다국어 (영어) 미지원

---

## 8. 자주 쓰는 명령어

```bash
# 작업 시작
cd "C:\Start coding\m365_sales_tool"

# Output 편집 후 root 반영
cp Output/index.html index.html

# Commit + push
git add index.html
git commit -m "..."
# (PowerShell에서 사용자 직접) git push

# 로컬 미리보기
# Output\index.html 더블클릭 → 브라우저
```

---

## 9. 외부 출처

- [Microsoft 365 플랜 및 가격 (KR)](https://www.microsoft.com/ko-kr/microsoft-365/enterprise/microsoft-365-plans-and-pricing)
- [엔터프라이즈 Copilot 가격](https://www.microsoft.com/ko-kr/microsoft-365-copilot/pricing/enterprise)
- [Copilot Studio 가격](https://www.microsoft.com/ko-kr/microsoft-365-copilot/pricing/copilot-studio)
- [2026-07-01 가격 변경 공지](https://news.microsoft.com/source/asia/2025/12/05/m365-pricing-updates/?lang=ko)
- [Microsoft Lifecycle Policy](https://learn.microsoft.com/ko-kr/lifecycle/products/)
- [Office Updates](https://learn.microsoft.com/ko-kr/officeupdates/)

---

**최종 검증일 2026-06-07** (오후 — E7·Agent 365 신규 SKU 발견 후 반영 완료) · 다음 검증 권장 시점: **2026-07-01 이후** (Microsoft 가격 변경 시행 직후 단가·SKU 변동 확인)
