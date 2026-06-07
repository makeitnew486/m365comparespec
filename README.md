# FBKR · Microsoft 365 영업 가이드

후지필름비즈니스이노베이션(FBKR) 영업 현장에서 사용하는 **Microsoft 365 통합 영업 자료**.
가격 비교, 기능 매트릭스, 영구형→구독형 전환 가이드, 영업 팁·용어집까지 한 페이지에 정리.

🌐 **라이브 URL**: https://makeitnew486.github.io/m365comparespec/

---

## 핵심 특징

- 📱 **단일 HTML, 빌드 시스템 X** — 브라우저에서 바로 열림
- 🎨 **Airbnb/MAXHUB-inspired 디자인** — 흰 캔버스 + 핑크 액센트 + ink 텍스트
- 🅰 **나눔스퀘어 네오 Bold** — 전 영역 통일
- 💰 **가격 표기 제거** — FBKR 영업 견적은 공시가와 다를 수 있어 모든 ₩ 표기 삭제, "FBKR 영업 견적 별도"로 통일

## 5개 섹션

| 탭 | 내용 |
|---|---|
| **홈** | 왜 구독형 (3 pillar) · 고객 제안 5단계 · FBKR 프로페셔널 서비스 로드맵 · **왜 FBKR (5 카드)** · 가격 공지 · 둘러보기 4링크 |
| **플랜** | E3·E5·**E7 🆕**·Teams 제외·Teams 단독·Copilot·**Agent 365 🆕** 옵션 카드 + 고객 유형별 추천 |
| **기능** | 29행 전체 기능 매트릭스 (E7 컬럼 포함, sticky thead) + 33개 앱 카탈로그 (클릭→상세 모달) |
| **라이선스** | 영구형 카탈로그 8종 + 영구형 vs 구독형 비교 + 9가지 전환 이유 + 6가지 반박 처리 |
| **영업 자료** | 15개 영업 팁 (계약·반론·제품·프로세스 필터) + 27개 용어 사전 (검색·카테고리 필터) |

## 인터랙션

- **FBKR 로고 클릭** → 홈 이동
- **앱 카드 클릭** → 상세 모달 (설명·핵심 기능·영업 활용·포함 플랜)
- **사용 안내 (ⓘ)** → 참고용 안내 툴팁
- **영업 팁 카드 클릭** → 아코디언 펼침
- **용어/앱 검색** → 실시간 필터
- **카테고리 칩** → 분류 필터링

## 파일 구조

```
m365_sales_tool/
├── index.html           # 라이브 (GitHub Pages가 서빙)
├── Output/
│   └── index.html       # 작업 사본 (.gitignore — 푸시되지 않음)
├── README.md
├── CHANGELOG.md
├── docs/
│   └── HANDOVER.md      # 인수인계 문서
└── .gitignore
```

**작업 흐름:** `Output/index.html` 편집 → `cp Output/index.html index.html` → commit → push → GitHub Pages 자동 배포 (~1분)

## 가격 정책

본 자료에 ₩ 단가는 표기하지 않습니다. 모든 플랜 카드에 "**FBKR 영업 견적 별도**"로 안내. 영업 담당자의 실제 견적이 공시가와 다를 수 있기 때문.

공식 단가는 출처 링크로만 접근:
- [Microsoft 365 플랜 및 가격 (microsoft.com/ko-kr)](https://www.microsoft.com/ko-kr/microsoft-365/enterprise/microsoft-365-plans-and-pricing)
- [엔터프라이즈 Copilot 가격](https://www.microsoft.com/ko-kr/microsoft-365-copilot/pricing/enterprise)
- [2026-07-01 가격 인상 공지](https://news.microsoft.com/source/asia/2025/12/05/m365-pricing-updates/?lang=ko)

## 디스클레이머

> 본 가이드는 영업 활동의 **참고용**입니다. 정확한 사양·가격·계약 조건은 FBKR 내부 자료 및 영업 담당자 확인이 우선이며, 본 자료만으로 고객 제안서 작성이나 견적 발행을 진행하지 않도록 유의해 주세요.

## 콘텐츠 정책 (영업이 절대 위반하면 안 되는 것)

- ₩ 단가 표기 절대 금지 — "FBKR 영업 견적 별도"로 통일
- **DocuShare 언급 금지** (2026-05-19 기준 FBKR 미운영)
- "왜 FBKR" 섹션에 검증 안 된 자격·실적·파트너 등급 임의 추가 금지
- 2026-07-01 Microsoft 가격 변경 공지 advisory 배너 유지

---

**최근 업데이트 2026-05-19** (오후 — Microsoft E7 + Agent 365 신규 SKU 반영) · 자세한 인수인계는 [`docs/HANDOVER.md`](docs/HANDOVER.md), 변경 연대기는 [`CHANGELOG.md`](CHANGELOG.md) 참고
