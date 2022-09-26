# 2021 교내 캡스톤디자인

## 프로젝트 명 : 카카오 맵 리뷰 텍스트에 대한 감성 분석
- 진행 기간 : 20210.09.01 ~ 2021.12.17

## 1. 개발 배경
- 근래 사람들은 음식점들을 찾아가고는 할때 리뷰를 항상 보곤한다. 그 리뷰 텍스트 안에서의 의견이나 감성, 태도, 평가 등의 주관적인 정보를 알아보고자 하였다.

## 2. 과정
### 데이터 수집 및 저장
- Web Crawling은 BeautifulSoup을 이용하였고, 지도 이름을 검색하면 주변 음식점의 1-5페이지 분량의 리뷰 데이터를 가져와 csv 파일로 저장하였다.

### 데이터 전처리
- 텍스트 정제를 통하여 한글이외의 문자는 전부 제거하였고, 한 글자 이상의 텍스트만 가지고 있는 데이터만 추출하였다.
- 추가로 konlpy라이브러리를 활용하여 형태소 단위로 추출하였고, 형태소를 벡터 형태의 학습 데이터로 변경하여 TF-IDF 방법을 사용하였다.

### 데이터 분류 및 분석
- 데이터의 긍정 부정 리뷰를 분류하였다.
- 결과로 ROC Curve를 내고 회귀모델의 중요 피처 형태소를 추출하였다.
