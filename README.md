# BrandLab 치과 브랜드 전략 벤치마킹 스킬

> "환자가 선택하는 병원을 만듭니다 — 브랜드 전략부터 수익 구조까지"

Claude Cowork 전용 스킬. 지정 지역 치과들의 온라인 홍보 채널을 자동 수집·분석하고,  
BrandLab 브랜드 전략 제안서를 5-Color Harness 기준으로 자동 생성·품질 검증합니다.

---

## 산출물 (3종)

| 파일명 | 설명 |
|--------|------|
| `치과_홍보채널_조사표.docx` | 병원별 홈페이지·블로그·플레이스·SNS 링크 표 |
| `치과_홍보대행_벤치마킹_분석보고서.docx` | 원장 브랜딩·AEO·수익 구조 진단 포함 내부 전략 보고서 |
| `BrandLab_브랜드전략_제안서.docx` | 클라이언트 전달용 제안서 (5color 합격본) |

---

## 스크립트 구성

```
scripts/
  make_link_table.js   # 홍보 채널 링크 조사표 생성
  make_analysis.js     # 벤치마킹 분석 보고서 생성
  make_proposal.js     # BrandLab 브랜드 전략 제안서 생성
```

### 실행 방법

```bash
npm install docx
node scripts/make_link_table.js
node scripts/make_analysis.js
node scripts/make_proposal.js
```

---

## 설치 방법 (Cowork 스킬)

1. 이 저장소를 클론합니다
2. `SKILL.md`와 `scripts/` 폴더를 Cowork 스킬 디렉토리에 복사합니다
3. Claude Cowork에서 "치과 마케팅 분석해줘" 또는 "BrandLab 제안서 만들어줘"로 실행

---

## 커스터마이징

- **지역 변경**: 세 스크립트의 병원 데이터 배열 교체
- **가격 변경**: `make_proposal.js`의 `priceTable` 배열 수정
- **연락처 변경**: `make_proposal.js` 하단 CTA 섹션 이메일 수정 (`paulyoo95@gmail.com`)
- **의료 과목 변경**: `SKILL.md` 키워드 교체 (피부과, 한의원, 성형외과 등)

---

## 기술 스택

- Node.js + [`docx`](https://www.npmjs.com/package/docx) 라이브러리
- Claude Cowork (WebSearch + Claude in Chrome)
- 5-Color Harness 품질 루프 (최대 10회 자동 개선)
