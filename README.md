# StudyAnaconda

### 1일차 

- Anaconda 설치
- 웹 크롤링
- 파일 읽기 
  - read_csv
  - read_excel

### 2일차

- pandas 사용(내장데이터)
  - import pandas as pd
  - Series
  - dataframe
  - list
  - 서로서로 변환하기
  - Null 데이터 프레임 만들기
		
- 데이터 프레임 조작하기
  - pd_merge(how =" ")
  - 데이터 조회하는 방법
  - 데이터 삭제하기 drop( )
  - loc, iloc (인덱스 기준 행 조회, 행의 순서대로 조회)
  - 변수명.iat [x,y]
  - 컬럼 추가하기 -> 변수명["컬럼명"] = 0
  - 데이터 타입 변환
  - 데이터 갯수 확인 데이터셋.count( )
  - 컬럼명 확인하기 데이터셋.columns
  - 정렬하기  행 단위 정렬 : asix = 0 
	     컬럼 단위 정렬 : asix = 1 뒤에 Ascending = True일 경우 오름차순 False인 경우 내림차순
  - 데이터 합치기 : 열과 행의 갯수가 같을 때 사용

### 3일차 
  - 빈도교차분석
   - 빈도분석 : #데이터셋["day"].values_counts( )
   - 교차분석 : #pd.crosstab(tips["sex"],tips["day"])
   - 결측치 처리

### 4일차 
  
  - 이상치 처리하기
    -  drop = True
  -  boxplot 그리기
  
  - 라이브러리 가져오기
     #import matplotlib as mpl
     #import matplotlib.pylab as plt
   
    - 그리기  
     #plt.boxplot(데이터프레임["컬럼명"])
     #plt.show( )
  
  - 데이터에 대한 기초통계 조회하기.. 
      #데이터프레임["컬럼명"].describe( )
  
  - 최대값/최소값 계산하기
    - np.percentile(데이터프레임["데이터명"], [%값,%값] )
  
  - iqr값 계산하기 
      #iqr = q3 - q1
   - 최대값 : q1 - (iqr * 1.5), 최대값 : q3 +(iqr * 1.5)

  - 함수로 만들기 
   - def (함수 정의하기)
    
    #def outliers_iqr( ): 
    #q1, q3 = np.percentile(df_drop_allrow["나이"], [25, 75])
    
    #print(q1)
    #print(q3)
    
    # iqr 값 계산하기 
    iqr = q3 - q1
    print(iqr)
    
    # 최대값 계산하기 
    upper_bound = q3 + (iqr*1.5)
    print(upper_bound)
    
    # 최소값 계산하기
    lower_bound = q1 - (iqr*1.5)
    print(lower_bound)
    
    # 나이 데이터에서 이상치값 조회하기 
    변수명 = (데이터프레임[(데이터프레임["컬럼명"] > 변수명)|
                              (데이터프레임["컬럼명"] < 변수명)])
                    
    #print(len(df_temp))
    #print(df_temp)
    #outliers_iqr( )
 
  - 행번호만 조회하기
    - np.where((함수로 만들었던 것))

  - #### 이상치가 아닌 값만 추출...
    
    #### 아닌 값 따로 저장하기..

    #age_non_outlier_index = [ ]

  - #### 이상치 인덱스가 아닌 정상 인덱스만 추출하기..
    
    #for idx in df_drop_allrow.index :
    ####    if idx not in age_outlier_index[0]:
    ####        age_non_outlier_index.append(idx)
        
    age_non_outlier_index

  - 인덱스 번호 재배열 후 최종결과물 변수에 자장하고 조회
    - #df_new = df_new.reset_index(drop = True)
     #df_new

### 5일차 
  - 그룹 분석하기
    - describe( ) 함수 : 기초통계
  
  - 그룹화하기  
    - groupby( ) 함수 ["컬럼명"]
     - 특정 그룹의 데이터 조회 get_group( ) (단, 숫자값이 있는 컬럼에 대해서만 실행됨)
  - 변수명.groups : 실제 데이터가 어떻게 구성되어 있는지 확인(인덱스 값 추출됨)
  
  - 재구조화
    - cut : 동일한 길이(값의 범위)로 나누기
    - qcut : 무작위 범위로 범위의 갯수만 설정해주면 알아서 묶어줌
  - agg( ) 함수 : 변수명.agg(["조회하고싶은컬럼명"])
  
  - pd.qcut(df["math"], 3, labels = np.arange(3, 0, -1))
    - 첫번째값 : 시작값
    - 두번째값 끝값 -1
    - 세번째값 : 증가값 or 감소값
  
  - One-Hot Encoding
    - get_dummies( ) 함수
      -  범주형 컬럼에 대해서만 가능
      -  범주형이 아닌 컬럼에 대해서는 범주형으로 만들면 가능
      -  get_dummies() : 숫자값을 제외한 object 데이터 타입만 가능
      -  해당 원-핫 인코딩 되는 원본 컬럼은 없어지고 
      -  해당 컬럼명_범주명 으로 컬럼이 만들어진다.
  - 두개의 데이터를 옆으로 합치는 방법 == concat( ) 함수 사용
  - 데이터 전치 : 행과 열의 위치를 바꾼다 컬럼-> 행 인덱스로 
				    행 인덱스번호-> 컬럼명으로 
      - 데이터프레임.T


   