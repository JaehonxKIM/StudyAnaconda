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
   - 최대값 : q1 - (iqr * 1.5)
   - 최대값 : q3 +(iqr * 1.5)

  - 함수로 만들기 
   - def
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

  - # 이상치가 아닌 값만 추출...
    
    #### 아닌 값 따로 저장하기..

    #age_non_outlier_index = [ ]

  - # 이상치 인덱스가 아닌 정상 인덱스만 추출하기..
    
    #for idx in df_drop_allrow.index :
    ####    if idx not in age_outlier_index[0]:
    ####        age_non_outlier_index.append(idx)
        
    age_non_outlier_index

  - 인덱스 번호 재배열 후 최종결과물 변수에 자장하고 조회
   - #df_new = df_new.reset_index(drop = True)
     #df_new