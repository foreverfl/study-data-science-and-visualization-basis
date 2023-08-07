# 데이터 사이언스와 시각화: 전반적인 이해와 실무

## 목차

1. 데이터 사이언스 개요\_데이터 분석 맛보기
2. 데이터 사이언스 개요\_분석 환경 준비하기
3. 데이터 조작 이해와 실무\_데이터 선택
4. 데이터 조작 이해와 실무\_데이터 변경
5. 데이터 조작 이해와 실무\_데이터 합치기
6. 데이터 조작 이해와 실무\_데이터 그룹핑
7. 데이터 조작 이해와 실무\_시계열 데이터 기초
8. 데이터 전처리 이해와 실무\_데이터 정제 – 결측 데이터 처리
9. 데이터 전처리 이해와 실무\_데이터 정체 – 이상 데이터 처리
10. 데이터 전처리 이해와 실무\_데이터 변환 – 정규화, 구간화
11. 데이터 전처리 이해와 실무\_데이터 변환 – 특징 생성
12. 데이터 전처리 이해와 실무\_데이터 축소 – 특징 선택
13. 데이터 탐색 이해와 실무\_일변량 비시각화 탐색
14. 데이터 탐색 이해와 실무\_일변량 시각화 탐색
15. 데이터 탐색 이해와 실무\_다변량 비시각화 탐색
16. 데이터 탐색 이해와 실무\_다변량 시각화 탐색
17. 데이터 분석 이해와 실무\_가설의 의의와 검정
18. 데이터 분석 이해와 실무\_상관 분석
19. 데이터 분석 이해와 실무\_회귀 분석
20. 데이터 분석 이해와 실무\_시계열 분석
21. 데이터 시각화 이해와 실무\_정적 시각화 개요
22. 데이터 시각화 이해와 실무\_정적 시각화 실습 – matplotlib 활용
23. 데이터 시각화 이해와 실무\_정적 시각화 실습 – seaborn 활용
24. 데이터 시각화 이해와 실무\_동적 시각화 개요
25. 데이터 시각화 이해와 실무\_동적 시각화 실습 – plotly 활용
26. 데이터 시각화 이해와 실무\_UI 시각화 실습 – streamlit 활용

## 2. 데이터 사이언스 개요\_분석 환경 준비하기

### 특정 파이썬 버전으로 새로운 conda 가상 환경 생성

```
conda create --name [ENV_NAME] python=[PYTHON_VERSION]
```

### 모든 conda 환경들을 나열

```
conda info --envs
```

### conda 환경 활성화 / 현재 conda 환경 비활성화

```
conda activate [ENV_NAME]
conda deactivate
```

### 현재 conda 환경에 Jupyter Notebook 설치

```
conda install jupyter notebook
```

### 현재 conda 환경에 특정 패키지 설치

```
conda install [PACKAGE_NAME]
```

### conda 환경을 Jupyter Notebook에 등록

```
python -m ipykernel install --user --name [ENV_NAME] --display-name "[DISPLAY_NAME]"
```

### Jupyter Notebook 시작

```
jupyter notebook
```

### 기존 환경을 복제하여 새로운 conda 환경 생성

```
conda create --name [NEW_ENV_NAME] --clone [EXISTING_ENV_NAME]
```

### conda 환경 제거

```
conda env remove --name [ENV_NAME]
```

### 현재 conda 환경을 YAML 파일로 내보내기

```
conda env export > [ENV_NAME].yaml
```

### YAML 파일로부터 새로운 conda 환경 생성

```
conda env create --file [ENV_NAME].yaml
```

## 3. 데이터 조작 이해와 실무\_데이터 선택

### Numpy: Python에서 수치 계산을 위한 핵심 라이브러리. 대규모 다차원 배열 및 행렬 연산에 필요한 다양한 함수를 제공하며, 이는 고성능의 수학 연산과 과학 연산 작업에 필수적.

#### 주요 특징

1. 다차원 배열 객체: NumPy의 핵심 기능은 ndarray라는 다차원 배열 객체.
2. 브로드캐스팅: 다른 크기의 배열 간 연산을 지원하는 기능.
3. 통합 수학 함수: 배열 데이터를 처리하는 데 필요한 기본적인 수학 함수를 제공.
4. 선형 대수, 난수 생성, 푸리에 변환과 같은 고급 수학 및 통계 연산 지원.
5. C, C++, 포트란과 같은 저수준 언어로 작성된 코드와 통합이 가능.

### Pandas: Python에서 데이터 분석을 위한 가장 인기 있는 라이브러리. 고성능의 DataFrame 객체를 제공하여 데이터 분석, 클린징, 처리, 시각화 등의 작업을 효과적으로 수행 가능.

#### 주요 특징

1. 데이터 구조: Series와 DataFrame이라는 두 가지 주요 데이터 구조를 제공.
2. Series: 1차원 배열과 같은 데이터 구조로, 여러 데이터 타입을 저장할 수 있음.
3. DataFrame: 2차원 레이블이 있는 데이터 구조로, 다양한 타입의 열을 가질 수 있음.
4. 데이터 처리: 데이터 병합, 조인, 리쉐이핑, 피벗, 슬라이싱, 인덱싱, 데이터 클린징 등의 다양한 데이터 처리 기능을 제공.
5. 데이터 분석: 그룹화, 집계, 통계 계산 등의 기능을 통해 데이터 분석을 지원.
6. 시계열 처리: 날짜 및 시간 데이터를 위한 기능을 제공하며, 시계열 분석 및 빈도 변환 등의 작업을 수행 가능.
7. 데이터 입출력: CSV, Excel, SQL, HDF5, Parquet 등 다양한 데이터 소스로부터 데이터를 읽고 쓸 수 있는 기능을 제공.

## 4. 데이터 조작 이해와 실무\_데이터 변경

### 주어진 data로부터 데이터프레임을 생성

```python
pandas.DataFrame(data):
```

#### 매개변수

- data: 배열, 딕셔너리 또는 다른 데이터프레임으로부터 생성될 수 있음.

### 주어진 데이터프레임에 다른 데이터프레임, 시리즈, 딕셔너리, 배열을 추가

```python
DataFrame.append(data, ignore_index=True):
```

#### 매개변수

- data: 추가할 데이터 (데이터프레임, 시리즈, 딕셔너리 등).
- ignore_index: 인덱스를 무시하고 리셋하려면 True, 그렇지 않으면 False.

### 특정 인덱스의 특정 열 값에 빠르게 접근

```python
DataFrame.at[index, 'column_name']:
```

### 특정 인덱스(행)을 제거한 새로운 데이터프레임을 반환

```python
DataFrame.drop(index)
```

### 특정 열을 제거한 새로운 데이터프레임을 반환

```python
DataFrame.drop(columns=column_name)
```

### 특정 열을 데이터프레임의 인덱스로 설정

```python
DataFrame.set_index(column_name, drop=True)
```

#### 매개변수

- drop: 설정한 열을 데이터프레임에서 제거할지 여부. 기본값은 True.

## 5. 데이터 조작 이해와 실무\_데이터 합치기

### 데이터 병합: 각기 다른 두 개 이상의 Dataframe을 하나로 병합하여 결과 집합을 만들어 내는 것.

- Inner Join: Dataframe 간 조인 조건을 만족하는 행을 합치는 것.

1. One-to-One
2. One-to-Many

- Outer Join: 조건에 부합하지 않는 행까지 포함시켜 결합하는 방법. NaN 처리를 함.
- Left Join: 첫 번째 Dataframe을 기준으로 두 번째 Dataframe을 결합하는 방법.
- Right Join: 첫 번째 Dataframe을 기준으로 첫 번째 Dataframe을 결합하는 방법.

### join

- 인덱스를 기준으로 함.
- DataFrame의 메소드로 사용함.
- 왼쪽 DataFrame을 기준으로함.
- 중복된 칼럼이 있다면, 두 개 칼럼 모두 Dataframe에 다른 이름올 저장됨.

### Merge

- 열을 기준으로 함.
- Pandas의 함수로 사용함.
- 기본적으로 inner join. how 파라미터를 통해 변경 가능.

### Concatenate

- 연결은 공유하는 Key 값을 사용하지 않고, 데이터를 기존 DataFrame 아래(또는 우측)에 붙여 연결함.

## 6. 데이터 조작 이해와 실무\_데이터 그룹핑

## 7. 데이터 조작 이해와 실무\_시계열 데이터 기초

## 8. 데이터 전처리 이해와 실무\_데이터 정제 – 결측 데이터 처리

## 9. 데이터 전처리 이해와 실무\_데이터 정체 – 이상 데이터 처리

## 10. 데이터 전처리 이해와 실무\_데이터 변환 – 정규화, 구간화

## 11. 데이터 전처리 이해와 실무\_데이터 변환 – 특징 생성

## 12. 데이터 전처리 이해와 실무\_데이터 축소 – 특징 선택

## 13. 데이터 탐색 이해와 실무\_일변량 비시각화 탐색

- 대상: 하나의 변수
- 방법: 시각화를 사용하지 않는 통계적 방법
- 예: 평균, 중앙값, 표준편차, 왜도, 첨도 등의 통계치 계산
- 목적: 해당 변수의 분포, 중심 경향, 변동성 등의 기본 통계적 특성 파악

## 14. 데이터 탐색 이해와 실무\_일변량 시각화 탐색

- 대상: 하나의 변수
- 방법: 시각화 방법 사용
- 예: 히스토그램, 박스 플롯, 도수 분포표 등
- 목적: 데이터의 분포나 이상치 등을 직관적으로 파악

## 15. 데이터 탐색 이해와 실무\_다변량 비시각화 탐색

- 대상: 두 개 이상의 변수
- 방법: 시각화를 사용하지 않는 통계적 방법
- 예: 상관 계수, 공분산, 두 변수의 평균 차이 검정 등
- 목적: 변수 간의 관계나 연관성 파악

## 16. 데이터 탐색 이해와 실무\_다변량 시각화 탐색

- 대상: 두 개 이상의 변수
- 방법: 시각화 방법 사용
- 예: 산점도, 히트맵, 버블 차트, 페어 플롯 등
- 목적: 변수 간의 관계나 패턴, 그룹 내의 차이를 직관적으로 파악

## 17. 데이터 분석 이해와 실무\_가설의 의의와 검정

## 18. 데이터 분석 이해와 실무\_상관 분석

## 19. 데이터 분석 이해와 실무\_회귀 분석

## 20. 데이터 분석 이해와 실무\_시계열 분석

## 21. 데이터 시각화 이해와 실무\_정적 시각화 개요

## 22. 데이터 시각화 이해와 실무\_정적 시각화 실습 – matplotlib 활용

## 23. 데이터 시각화 이해와 실무\_정적 시각화 실습 – seaborn 활용

## 24. 데이터 시각화 이해와 실무\_동적 시각화 개요

## 25. 데이터 시각화 이해와 실무\_동적 시각화 실습 – plotly 활용

## 26. 데이터 시각화 이해와 실무\_UI 시각화 실습 – streamlit 활용
