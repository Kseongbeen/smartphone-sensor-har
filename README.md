# 📱 스마트폰 센서 데이터 기반 행동 분류 (Human Activity Recognition)

스마트폰에 내장된 3축 가속도계(Accelerometer) 및 자이로스코프(Gyroscope) 센서의 시간-주파수 도메인 피처(563개)를 정밀 분석하고, 분류 기계학습 모델(Random Forest 등)을 구축하여 사용자의 6가지 물리적 행동(걷기, 계단 오르기/내려가기, 앉기, 서기, 눕기)을 예측 분류하는 머신러닝 솔루션입니다.

본 프로젝트는 **AI+X 기초 2차 프로젝트**로 수행되었습니다.

---

## 📂 프로젝트 구조

* **[SMU_AIX_스마트폰센서데이터기반모션분류_2차프로젝트.pdf](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/AI+X_3/SMU_AIX_스마트폰센서데이터기반모션분류_2차프로젝트.pdf)**: 모션 분류 시스템 연구 최종 보고서
* **[스마트폰센서데이터_탐색적데이터분석_학생용111.ipynb](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/AI+X_3/스마트폰센서데이터_탐색적데이터분석_학생용111.ipynb)**: 데이터 탐색(EDA), 상관관계 시각화 및 머신러닝 학습 모델 구현 노트북
* **[features.csv](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/AI+X_3/features.csv)**: 센서 신호 필터링을 통해 획득한 563개 입력 피처 정보 리스트
* **[fi_analysis.csv](file:///c:/Users/5174k/Code/202210822/AI+X/AI+X_기초/AI+X_3/fi_analysis.csv)**: 피처 기여도(Feature Importance) 분석 결과 테이블

---

## ✨ 핵심 기능 및 분석 내용

1. **다차원 센서 데이터 정제 (563 Dimensions)**
   * 가속도계(Body, Gravity) 및 자이로스코프 센서의 로우 시그널 필터링 데이터 처리.
   * X, Y, Z 각 축에 대한 시간 영역 평균, 표준편차, 중앙값 절대 편차(MAD), 에너지, 에이징 계수 등의 통계 특징 추출.
2. **설명 가능한 탐색적 데이터 분석 (EDA)**
   * **Bivariate Jointplot / Pairplot**: 정적 상태(Sitting, Standing)와 동적 상태(Walking) 간의 특징 분포 전이 분석.
   * **Correlation Heatmap**: 공선성(Collinearity)이 높은 가속도 변수군을 필터링하기 위한 히트맵 매핑.
3. **Random Forest 기반 피처 기여도 정밀 평가**
   * 고차원 피처 공간에서 결정 나무들의 정보 획득량(Information Gain)을 합산하여 모션 분류에 물리적으로 지대한 영향을 준 핵심 피처 상위 20개 선정 및 해석.

---

## 🛠️ 기술 스택

* **Language**: `Python`
* **Machine Learning**: `Scikit-learn` (Random Forest, Decision Tree)
* **Data Science**: `Pandas`, `Numpy`
* **Visualization**: `Seaborn` (Boxplot, Jointplot, Heatmap), `Matplotlib`
