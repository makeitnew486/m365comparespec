# TODO — 미해결 작업 · 개선 아이디어

> 작업 시 이 파일 먼저 확인. 처리 완료 시 STATUS.md로 옮기거나 항목 삭제 + CHANGELOG에 기록.

---

## 🚨 우선순위 높음

### 2026-07-01 Microsoft 가격 변경 시행 후 작업
시행일 이후 1주 내 처리:
- [ ] [microsoft.com/ko-kr 공식 페이지](https://www.microsoft.com/ko-kr/microsoft-365/enterprise/microsoft-365-plans-and-pricing) 재방문 → 한국 신가격 공개 여부 확인
- [ ] 홈·플랜 페이지의 "**2026-07-01 가격 인상 예정**" advisory 배너 갱신:
  - 신가격 공개됨 → "**2026-07-01부 가격 변경 시행됨** — 신가격은 FBKR 영업 담당자 문의"
  - 여전히 미공개 → 배너 유지
- [ ] CHANGELOG에 시행일 기록
- [ ] STATUS.md "최종 검증" 일자 갱신

### 출처 링크 정기 검증
Microsoft가 페이지 구조·URL 변경 시 링크 깨질 수 있음. 분기별 (3개월) 한 번 점검:
- [ ] [플랜 및 가격](https://www.microsoft.com/ko-kr/microsoft-365/enterprise/microsoft-365-plans-and-pricing)
- [ ] [엔터프라이즈 Copilot 가격](https://www.microsoft.com/ko-kr/microsoft-365-copilot/pricing/enterprise)
- [ ] [Copilot Studio 가격](https://www.microsoft.com/ko-kr/microsoft-365-copilot/pricing/copilot-studio)
- [ ] [Lifecycle Policy](https://learn.microsoft.com/ko-kr/lifecycle/products/)
- [ ] [2026-07-01 가격 공지](https://news.microsoft.com/source/asia/2025/12/05/m365-pricing-updates/?lang=ko)

---

## 🟡 중간 우선순위

### UX 개선
- [ ] 모바일 (≤1023px) 비교표에 sticky thead 활성화 검토 — 현재는 `.table-wrap`의 `overflow-x: auto`가 sticky context를 가로채서 thead가 viewport에 안 붙음. JS 기반 sticky 라이브러리 도입 또는 mobile-only 다른 레이아웃
- [ ] 영업 팁 검색 기능 — 현재는 카테고리 필터만 있음, 키워드 검색 추가 시 유용
- [ ] 앱 모달 keyboard navigation — 모달 열림 시 첫 focusable 요소로 포커스 이동, Tab 트랩
- [ ] 압축된 매트릭스 행을 클릭 시 펼치는 expandable 뷰 — sub 디테일이 항상 보이는데 옵션으로 줄였다 폈다 가능하면 더 깔끔

### 콘텐츠
- [ ] term-card / tip-box 본문의 괄호 일부도 `&nbsp;` 처리 (320px+ 폭이라 거의 무관하지만 모바일에서 어색할 수 있음 — 발견 시 즉시 처리)
- [ ] 영업 팁에 "Copilot 가치 입증 케이스 스터디" 추가 검토 (실제 도입 효과 수치)
- [ ] "F1/F3 Frontline" 플랜 카드를 플랜 섹션에 추가 검토 (현재는 영업 팁/용어에만 언급)
- [ ] E7 Copilot vs M365 Copilot 비교 — E7에 포함된 Copilot과 별도 라이선스의 동일성/차이 명확화

### 추적·관리
- [ ] STATUS.md 자동 갱신 워크플로우 — git hook 으로 commit 직후 STATUS의 "현재 commit 헤드" 섹션 자동 업데이트
- [ ] GitHub Actions 배포 상태 알림 — push 후 빌드 성공/실패를 Slack 또는 이메일로 통보

---

## 🟢 낮은 우선순위 / 백로그

### 기능 확장
- [ ] 다국어 (영어) 지원 — 외국계 고객 대응 시 필요
- [ ] 인쇄용 CSS — A4 PDF 출력 시 정렬·페이지 분할 최적화
- [ ] OG 메타태그 — Teams·카카오톡 공유 시 미리보기 카드
- [ ] favicon — FBKR 로고 기반 32x32 / 192x192 아이콘
- [ ] 다크 모드 검토 — 현재는 흰 배경만, 발표용 다크 모드 옵션

### 데이터 확장
- [ ] EA·NCE 계약 시뮬레이터 — 사용자 수 입력 시 약정 비용 추정 (단, 가격 미표기 정책과 충돌 — 검토 필요)
- [ ] 산업별 추천 매트릭스 강화 — 현재 4 시나리오 → 8~10개로 확장
- [ ] Microsoft Lifecycle 자동 임포트 — 영구판 SKU 종료일 자동 업데이트

### 인프라
- [ ] Custom 도메인 연결 (예: `m365.fbkr.co.kr`) — GitHub Pages 도메인 의존 탈피
- [ ] Pages → Cloudflare Pages 또는 Netlify 마이그레이션 검토 (성능·CDN)
- [ ] Privacy 정책·이용 약관 별도 페이지

---

## 처리 완료 (참고용 · 한 달 내)

→ 자세한 내역은 [`../CHANGELOG.md`](../CHANGELOG.md)
