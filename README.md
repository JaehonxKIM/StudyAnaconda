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
  - 데이터 갯수 확인 tips.count( )
  - 컬럼명 확인하기 tips.columns
  - 정렬하기  행 단위 정렬 : asix = 0 
	     컬럼 단위 정렬 : asix = 1 뒤에 Ascending = True일 경우 오름차순 False인 경우 내림차순
  - 데이터 합치기 : 열과 행의 갯수가 같을 때 사용

### 3일차 
  - 빈도교차분석
   - 빈도분석 : tips["day"].values_counts( )
   - 교차분석 : pd.crosstab(tips["sex"],tips["day"])
   - 결측치 처리