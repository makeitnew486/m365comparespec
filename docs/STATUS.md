# STATUS — 라이브 상태 한눈에

> 다음 세션 시작 시 이 파일 먼저 확인. 변경 직후 갱신.

**🌐 Live:** https://makeitnew486.github.io/m365comparespec/
**📦 Repo:** https://github.com/makeitnew486/m365comparespec
**📅 최종 Microsoft 공식 페이지 검증:** 2026-06-07 (오후 — E7·Agent 365 신규 SKU 발견)

---

## 현재 commit 헤드

```
aff0a16 (main, origin/main)  Remove '글로벌 그룹 + 현지 인프라' card — 5 cards total
5e129e8                       Remove DocuShare references — FBKR no longer operates it
57d351b                       docs: reflect '왜 FBKR' section in CHANGELOG + HANDOVER + DD-010
e6748a1                       Add '왜 FBKR과 함께해야 하는가' section to homepage
8b27897                       docs: README overhaul + HANDOVER + CHANGELOG
```

---

## 5탭 구조 (현재 라이브 · 2026-06-07 다이어트 후)

```
홈 (overview)  ← 압축됨, 17 카드 → 7 카드
 ├─ Hero page-head
 ├─ Advisory bar (E7 출시 + 7월 가격 공지 — 2행 1박스)
 ├─ 왜 구독형 M365인가 (3 pillars: AI · 보안 · 협업)
 ├─ 둘러보기 (4 quick links)
 └─ Footer source

플랜 (plans)
 ├─ Teams 포함 (E3·E5·E7 🆕 신규 — list 압축됨 4줄/카드)
 ├─ Teams 미포함 (E3·E5·Teams Enterprise 단독)
 ├─ Copilot · Agent 옵션 (Chat·Copilot·Agent 365 🆕·Studio Pack·SMB)
 └─ 고객 유형별 추천 (4 카드)
 ※ 모든 가격은 "FBKR 영업 견적 별도"

기능 (compare)
 ├─ 압축 기능 매트릭스 (11행, 7 컬럼 — 그룹화)
 │   ├─ 생산성·협업 4행
 │   ├─ 보안·ID 관리 2행 (기본 / 고급 E5+)
 │   ├─ 🚀 E7 신규 2행 (Entra Suite · Agent 365)
 │   └─ AI / Copilot 2행 (무료 / 유료)
 └─ 포함된 앱 (5 카테고리, 33개 카드, 클릭→상세 모달)

라이선스 (license)
 ├─ 영구형 카탈로그 (8 SKU)
 ├─ 영구형 vs 구독형 비교표 (12행)
 ├─ 구독형 전환 9가지 이유 (.reason-grid)
 └─ 자주 듣는 반박 처리 (6 카드)

영업 자료 (tips)
 ├─ 영업 팁 (15개 아코디언 + 4 카테고리 필터)
 └─ 영업 용어집 (27개 카드 + 검색 + 5 카테고리 필터)
```

---

## 정상 동작 확인 (works as expected)

- ✅ 5탭 전환 (FBKR 로고 클릭 시 홈 이동 포함)
- ✅ Nav 우측 ⓘ 사용 안내 툴팁 (outside click + ESC로 닫힘)
- ✅ 비교표 sticky thead (≥1024px viewport)
- ✅ 첫 컬럼 sticky left
- ✅ 앱 카드 33개 모두 클릭 → 상세 모달 (33개 데이터 모두 매핑됨)
- ✅ 영업 팁 카테고리 필터 + 아코디언
- ✅ 영업 용어 검색 + 카테고리 필터
- ✅ 나눔스퀘어 네오 Bold 전영역 적용 (jsDelivr CDN 1순위 로드)
- ✅ 모바일 (≤768px) 컴팩트 레이아웃
- ✅ 괄호 안 공백 줄바꿈 처리 (22개 패턴 `&nbsp;`)

---

## 콘텐츠 정책 준수 상태

| 룰 | 상태 |
|---|---|
| ₩ 가격 표기 0개 | ✅ (24곳 모두 제거) |
| DocuShare 언급 0개 | ✅ |
| Fujifilm 그룹/글로벌 R&D 언급 0개 | ✅ |
| 검증 안 된 자격·등급 언급 0개 | ✅ |

---

## 알려진 이슈 (상세는 HANDOVER §7)

- [ ] 모바일 sticky thead 비활성화 — overflow-x:auto 트랩 (정상 동작이나 UX 개선 여지)
- [ ] term-card / tip 본문 일부 괄호 `&nbsp;` 미적용 (320px+ 폭이라 거의 무관)
- [ ] Pages 빌드 상태 자동 알림 없음
- [ ] 2026-07-01 Microsoft 가격 변경 시행 → advisory 배너 업데이트 필요

---

## 다음 액션 후보

1. 2026-07-01 이후 — 새 가격 advisory 업데이트, 출처 페이지 재검증
2. 모바일 sticky thead UX 개선 (선택)
3. STATUS.md / CHANGELOG.md 자동 갱신 워크플로우 검토 (선택)

---

📖 **상세 인수인계:** [`HANDOVER.md`](HANDOVER.md)
📖 **변경 연대기:** [`../CHANGELOG.md`](../CHANGELOG.md)
