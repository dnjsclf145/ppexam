# 000 포트폴리오
데이터 분석 포트폴리오 예시

## 1. 비전 AI를 활용한 식물 성장 분석 스마트 화분(2023.07 - 2023.09)
- **여행지 자동 추천 시스템 개발**
  * 연속적인 장소 데이터로부터 장소간의 연관성 점수를 학습 및 예측 하는 LSTM 기반의 딥러닝 모델 개발
  * SNS에 작성된 여행 일정으로부터 연속적인 장소 데이터 세트 추출하기 위한 크롤링 프로세스 구현
- **모델 배포를 위한 Flask API 개발**
  *  모바일에 입력된 사용자의 장소로부터 추천 장소를 제공하기 위해 학습된 모델을 Flask API 서버에 배포하여 네트워크 구축


## 2. 감기진료 건수 데이터와 기상청 데이터를 활용한 시간변화에 따른 기후와 감기 관계 분석 (2024.01 - 2024.02)
### 목적
- 감기와 기후의 변화가 관계성이 있는지에 대한 인사이트를 얻기 위해 감기 진료건수 데이터와 기상청 기후 데이터를 활용하여 EDA 및 회귀 분석
### 활용 데이터
- 국민건강보험공단에서 제공한 시도별 감기진료 발생건수 데이터
 * 시도지역코드, 날짜, 발생건수
- 기상청에서 제공한 서울의 기후 데이터
 * 날짜, 기온, 강수량, 상대습도, 풍속
### 분석 과정
- 시각화를 활용한 EDA 분석
 * 피어슨 상관 관계 계수를 히트맵 시각화 하여 컬럼간의 관계 분석
 * 감기 발생건수에 대한 각 기후데이터의 산점도 시각화를 통한 관계 분석
 * 년도, 월, 일 별 감기 발생건수와 기후 변화의 추이를 선그래프로 시각화 하여 분석 
- 모델을 활용한 회귀 분석
 * 특성 및 타겟 데이터 선정
 * 학습을 위한 특성 데이터 스케일링 전처리
 * 윈도우 슬라이딩 방식으로 10을 시간단위로 묶어 시계열 데이터 구성
 * 시계열 데이터 학습을 위한 keras LSTM 모델 모델링
 * 모델 학습 및 평가
### 결과
- 월, 요일에 따른 감기 발생건수와 기후데이터가 특정한 패턴이 있음을 확인
- 기후 시계열 데이터로 감기 발생건수의 회귀 예측 결과 높은 정확성으로 예측은 어렵지만 전반적인 경향성은 파악 할수 있음
 * mape : 약 40%
 * R2 스코어 : 약 0.5
