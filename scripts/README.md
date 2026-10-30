# Scripts

**수집, 전처리, 분석**의 단계별 실행 코드.

| Script | Content |
|---|---|
| [01_collect.py](01_collect.py) | DART 기업번호 조회와 사업보고서 수집 |
| [02_extract_sections.py](02_extract_sections.py) | II, IV, VI 섹션 추출 |
| [03_preprocess_experiment.py](03_preprocess_experiment.py) | 형태소 분석과 정규화 설정별 전처리 |
| [04_evaluate_preprocessing.py](04_evaluate_preprocessing.py) | 전처리 결과 비교 |
| [05_full_analysis.py](05_full_analysis.py) | 특성 생성, 통계 및 회귀분석 |
| [collect_expanded.py](collect_expanded.py) | 확장 수집용 보조 스크립트 |

## Setup

저장소 루트에서 의존성 설치 후 `config.example.py`를 `config.py`로 복사.

```bash
pip install -r requirements.txt
```

- API 키는 **`OPENDART_API_KEY` 환경변수**에 설정
- 수집 대상과 입력 경로는 `config.py`에서 지정
- 최종 381개 기업-연도 통합 분석은 [Notebook](../notebook/README.md) 참조
- 단계별 스크립트의 기본 표본과 설정은 통합 Notebook과 구분 필요

## Data

- 원문, 등급 원자료, API 키와 중간 산출물은 공개 제외
- 공개 입력 파일은 [Data](../data/README.md), 결과표는 [Results](../results/README.md) 참조
