# vn-marketers

LUXBANO(리모라사이언스) 베트남 시장진출 마케팅 프로젝트 작업 저장소입니다.

> ⚠️ 2027년 1~2월 출시 예정 제품의 디자인·정보가 포함되어 있습니다. 경진대회 목적 외 사용·재배포를 금지합니다.

**Live demo:** https://combile.github.io/vn-marketers/ (GitHub Pages, `main` 브랜치 루트에서 배포)

## skin-lab/ — LUXBANO AI Skin Lab (목업)

피부 진단 + 맞춤 스킨케어 추천 웹 목업입니다. Engagement 단계 캠페인(TikTok·KOL/KOC → Zalo OA → Skin Lab → 바우처)과 몰 체험 부스용으로 기획했습니다.

- 흐름: 얼굴 스캔(AI) → 라이프스타일 설문 5문항 → AI 분석 → Skin Report(7개 지표·종합 점수) → 제품 매칭·루틴 → 바우처(QR)
- 언어: 베트남어 / 영어 / 한국어
- 테마: 브랜드 라이트(기본) / 다크
- 얼굴 인식: MediaPipe Face Landmarker(468 포인트, 기기 내 처리 — 사진은 서버로 전송되지 않음)

### 로컬 실행

카메라는 `localhost` 또는 https에서만 동작합니다.

```bash
cd skin-lab
python3 -m http.server 8000
# http://localhost:8000
```

### URL 파라미터

| 파라미터 | 예시 | 설명 |
|---|---|---|
| `lang` | `vi` / `en` / `ko` | 언어 |
| `theme` | `light` / `dark` | 테마 |
| `src` | `tiktok`, `kol01`, `booth` | 유입 채널 추적(KPI) |
| `mode` | `booth` | 부스 모드: "다음 고객" 버튼, 2분 무입력 시 초기화 |
| `demo` | `cam` / `quiz` / `analyze` / `result` / `voucher` | 기획 캡처용 화면 바로가기 |

### 목업의 한계 (실서비스 전 필요 작업)

- 피부 점수는 시연용 휴리스틱입니다. 실서비스는 피부 분석 API/모델로 교체해야 합니다.
- 바우처는 브라우저에서만 생성됩니다. 발급·검증·Zalo ZNS 발송용 백엔드가 필요합니다.
- `index.html` 상단 `CONFIG`의 Zalo OA / Shopee / TikTok Shop 링크는 임시값입니다.
