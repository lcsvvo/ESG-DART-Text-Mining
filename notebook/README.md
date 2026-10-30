# Notebook

**수집부터 회귀분석과 유형 분류까지의 통합 분석 코드**.

| Notebook | Content |
|---|---|
| [Analysis](3조_분석노트북.ipynb) | DART 수집, Kiwi 전처리, 어휘 점수, 통계 및 회귀분석, Talk–Walk 분류 |

## Setup

저장소 루트에서 환경 설정.

```bash
pip install -r requirements.txt
```

- Notebook 내 추가 라이브러리 설치 셀과 경로 설정을 실행 환경에 맞게 적용
- OpenDART API 키는 **`OPENDART_API_KEY` 환경변수**로 설정
- 공개 기업 목록은 `data/sample/company_master.csv`에 위치. Notebook 입력 경로는 `data/company_master.csv`
- 분석에는 별도로 확보한 **KCGS 등급을 결합한 입력** 필요. 공개 기업 목록에는 등급 미포함
- 파일과 API 키는 [Data](../data/README.md)의 공개 제외 범위 준수

## Outputs

- 공개본은 **저장된 셀 출력 제거** 상태
- 최종 그림과 집계표는 [Paper](../paper/README.md), [Results](../results/README.md) 참조
