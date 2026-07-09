# notebook — 최종 통합 분석 노트북

수집 → 전처리 → feature → 검증 → 회귀 → 격차 분석을 한 노트북(`3조_분석노트북.ipynb`)으로 재현하는 정본. 단계별 모듈 실행은 [`scripts/`](../scripts/README.md), 함수는 [`src/`](../src/README.md).

분석 단위: 127개 상장기업 × 2022–2024 = 381 firm-year. 연구 질문: 한국 상장기업 사업보고서의 ESG 관련 표현이 KCGS ESG 등급과 어떤 연관성을 보이는가.

| 단계 | 내용 | 방법·산출 |
|---|---|---|
| 1. 데이터 수집 | 381 firm-year DART 사업보고서 | lineage 전수 검증 |
| 2. 전처리 | DART 원문 → 분석 단위 토큰화 | Kiwi 형태소 + 사용자 사전·불용어 |
| 3. Feature 생성 | ESG 어휘강도 점수 | TF-IDF · FastText Expanded Dictionary · Cosine |
| 4. Validity 검증 | feature–등급 정합성 | Spearman · Mann-Whitney |
| 5. 회귀 분석 | 언어–등급 연관 | OLS · Ordered Logit · Binary Logit |
| 6. 알파 분석 | 말–평가 격차(Talk–Walk Gap) | 어휘강도 × 등급 4유형 |
| 7. 종합 결론 | 단계별 요약·발견·한계 | — |

## 기술 스택

| 구분 | 도구 |
|---|---|
| 수집 | requests (OpenDART API), xml.etree |
| 한국어 처리 | Kiwi (kiwipiepy) + 사용자 사전 |
| Feature | scikit-learn TF-IDF, gensim FastText, SentenceTransformer(보강), cosine similarity |
| 검증·회귀 | scipy (Spearman · Mann-Whitney · Kruskal), statsmodels (OLS · OrderedModel · Logit) |

## 동작 원리

DART API로 사업보고서를 수집(requests) → Kiwi 형태소로 토큰화 → TF-IDF·FastText로 ESG 어휘강도를 산출하고 기준 문장 cosine으로 보강 → Spearman·Mann-Whitney로 등급 정합성 검증 → statsmodels로 OLS·Ordered·Binary Logit 3종 회귀 → 어휘강도와 KCGS 등급의 격차(Talk–Walk Gap)를 4유형으로 분석.

## 역할 분담

- 루트 [`README.md`](../README.md): 프로젝트 개요.
- 이 폴더: 위 단일 정본 노트북의 단계별 지도.
- 모듈 파이프라인은 [`scripts/`](../scripts/README.md), 함수는 [`src/`](../src/README.md).

> 주요 의사결정은 노트북 내 Decision Box(①–⑱)에 근거와 함께 기록. 원본 사업보고서·KCGS 등급은 미포함(→ [`data/README.md`](../data/README.md)). API 키 설정은 [`scripts/README.md`](../scripts/README.md) 참고.
