# Source

**자료 수집, 한국어 전처리, 특성 생성**의 공통 모듈.

| Module | Content |
|---|---|
| [dart_api.py](dart_api.py) | OpenDART API 호출과 보고서 다운로드 |
| [section_extractor.py](section_extractor.py) | 사업보고서 섹션 추출 |
| [passage_filter.py](passage_filter.py) | ESG 관련 단락 추출 |
| [preprocessor.py](preprocessor.py) | 형태소와 정규화 처리 |
| [chunked_tokenize.py](chunked_tokenize.py) | 배치 토큰화 |
| [token_classifier.py](token_classifier.py) | 토큰 범주 분류 |
| [token_audit.py](token_audit.py), [apply_manual_taxonomy.py](apply_manual_taxonomy.py) | 토큰 분류 점검과 수동 보정 |
| [feature_builder.py](feature_builder.py) | 기업-연도별 ESG 특성과 분량 계산 |
| [kcgs_merge.py](kcgs_merge.py) | 기업 식별자 기준 등급 결합 |

실행 진입점은 [Scripts](../scripts/README.md), 최종 통합 분석은 [Notebook](../notebook/README.md) 참조.
