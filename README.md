# [주제]
### 서울시 상권 입지선정과 생존전략 컨설팅 서비스
#
# [데이터 수집]
### -공공데이터 포털: ‘우리마을가게 상권분석 서비스’ 데이터: 2018-2021년도 서울시 생활인구, 직장인구, 상권별 추정매출, 상권변화지표, 점포, 집객시설에 대한 공공 데이터
### -서울시 상권분석 서비스: 2018-2021년도 서울시 점포 생존율, 가구 소득분위, 지역 임대시세에 대한 공공 데이터
#
# [프로젝트 진행 방향]
####  1.인구에 대한 데이터 전처리: 상주인구, 생활인구, 직장인구 데이터 통합
#### 2.소득, 상권에 대한 데이터 전처리: 상권변화지표, 소득소비 데이터 통합
#### 3.업종별 매출에 대한 데이터 전처리 후, 업종을 총 10개로 카테고리 나누기
#### 4.‘공공데이터 포털 데이터 프레임’과 ‘서울시 상권분석 서비스’ 데이터 프레임 통합
#### 5.10개 업종을 통한 군집화
#### 6.군집별로 폐업률 예측모델에 따른 중요변수 선정
#### 7.군집별로 주중매출 예측모델에 따른 중요변수 선정 
#### 8.군집별로 주말매출 예측모델에 따른 중요변수 선정
#
# [데이터 전처리]
### 1-1 상주, 생활, 직장인구 통합.ipynb 
##### 서울시 상주인구, 생활인구, 직장인구 데이터 통합
##### ‘stay_live_work_multiindex_drop_data.csv’ 데이터 프레임 생성
##
### 1-2 상권변화지표, 소득소비 통합.ipynb
##### 상권변화지표, 소득소비 데이터 통합
##### ‘money.csv’ 데이터 프레임 생성
##
### 1-3 업종별 매출액 변수 추가+top10 분류.ipynb
##### 업종별 매출 금액(amount), 업종별 매출 비율(prob) 변수 추가, 업종 카테고리 분류
##### 'category10_amount_prob.csv' 데이터 프레임 생성
##
### 1-4 서울시 상권분석 서비스 변수 추가.ipynb
##### 'stay_live_work_multiindex_drop_data.csv','money.csv','category10_amount_prob.csv' 세 가지 데이터 파일을 통합 서울시 상권분석 서비스에서 가져온 점포 생존율, 가구 소득분위, 지역 임대시세 데이터를 ‘행정동 기준’으로 통합 
#
# [군집화]
### 2-1 클러스터링(업종).ipynb
#### 업종 10개를 선정하여, 주성분 분석과 Elbow Method를 통해 업종에 따른 군집화
#
# [예측모델]
### 3-1 로지스틱(폐업률).ipynb
### 3-2 랜덤포레스트(폐업률).ipynb
### 3-3 XG 부스트(폐업률).ipynb
### 3-4 의사결정나무(폐업률).ipynb
##### 종속변수를 폐업률로 둔 예측모델에서 중요변수 선정
##### 각 모델마다 기본모델, 그리드 서치, 컷오프 방법 중 가장 적절한 모델링 기법 선택
##### 로지스틱, 랜덤포레스트, XG Boost, 의사결정 나무 4개의 모델 중 최적의 모델 찾기
#
###  4-1 로지스틱(주중매출).ipynb
###  4-2 랜덤포레스트(주중매출).ipynb
###  4-3 XG 부스트(주중매출).ipynb
###  4-4 의사결정나무(주중매출).ipynb
##### 종속변수를 주중매출로 둔 예측모델에서 중요변수 선정
##### 그리드 서치를 통한 모델링 진행 후, 로지스틱, 랜덤포레스트, XG Boost, 의사결정 나무 4개의 모델 중 최적 모델 선정
#
### 5-1. 로지스틱(주말매출).ipynb
### 5-2. 랜덤포레스트(주말매출).ipynb
### 5-3. XG부스트(주말매출).ipynb
### 5-4. 의사결정나무(주말매출).ipynb
##### 종속변수를 주말매출로 둔 예측모델에서 중요변수 선정
##### 그리드 서치를 통한 모델링 진행 후, 로지스틱, 랜덤포레스트, XG Boost, 의사결정 나무 4개의 모델 중 최적 모델 선정

