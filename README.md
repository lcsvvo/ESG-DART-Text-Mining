# ESG Disclosure Language vs. ESG Ratings

ESG 공시 언어와 외부 ESG 평가(KCGS 등급) 사이의 간극을 측정하는 텍스트 마이닝 프로젝트입니다. 상장기업 사업보고서의 ESG 관련 서술을 분석해, 공시에서 사용하는 언어가 외부 평가와 얼마나 정합하는지를 살펴봅니다.

4인 팀 프로젝트로, 데이터 수집·전처리·feature 설계·통계 분석을 공동으로 수행했습니다.

## 사용 기술

| 구분 | 도구 |
|---|---|
| 언어 | Python 3.x |
| 데이터 수집 | OpenDART API, requests, BeautifulSoup |
| 한국어 처리 | Kiwi (kiwipiepy), KoNLPy |
| Feature | scikit-learn TF-IDF, FastText |
| 통계 | Spearman, Mann-Whitney, OLS, Ordered/Binary Logit |

## 실행 방법

```bash
git clone https://github.com/jiwooo411/ESG_DART_Project.git
cd ESG_DART_Project
pip install -r requirements.txt

cp config.example.py config.py
export OPENDART_API_KEY=<발급받은 키>

jupyter notebook notebook/3조_분석노트북.ipynb
```

원본 사업보고서와 KCGS 등급 데이터는 라이선스 문제로 미포함되어 있습니다.

## 저장소 구조

```
.
├── notebook/      # 분석 노트북
├── src/           # 수집·전처리·feature 빌드 모듈
├── scripts/       # 파이프라인 실행 스크립트
├── data/          # 데이터 설명 (원본 미포함)
├── paper/         # 분석 보고서
└── results/       # 검증 결과
```
