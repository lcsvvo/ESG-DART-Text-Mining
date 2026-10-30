# Data

**공개 기업 식별정보와 분석 사전** 안내.

## Source

- 사업보고서: [OpenDART](https://opendart.fss.or.kr)
- 외부 평가: 한국ESG기준원, KCGS
- 분석 표본: **127개 상장기업, 2022–2024년의 381개 기업-연도**

## Files

| Folder | Content |
|---|---|
| [Sample](sample/README.md) | 기업 식별정보, 대상 연도, 공시 특성 측정값 |
| [Dictionary](dictionary/README.md) | E, S, G seed 사전과 불용어 |

## Inputs

- `stock_code`, `corp_code`, `rcept_no`, `fiscal_year`를 기준으로 보고서 연결
- 분석용 **KCGS 등급은 별도 확보 후 결합** 필요
- 재무 통제 모형은 결측을 제외한 **344개 기업-연도** 기준
- 사업연도와 등급 기준연도의 대응은 분석 설정에 맞춰 구분 필요

## Access

- 원문 ZIP/XML, 개별 ESG 등급, API 키와 중간 가공자료는 공개 제외
- 실제 키는 `OPENDART_API_KEY` 환경변수에 설정. `config.py`와 `.env`는 커밋 금지
- 공개 기업 목록에는 개별 등급과 내부 역할, 교체 메모 미포함
