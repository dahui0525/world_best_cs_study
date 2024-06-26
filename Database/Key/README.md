# Key

- 데이터베이스에서 데이터를 식별하고, 데이터 간의 관계를 정의하는 중요한 요소

## 고유성 및 무결성 기준

### 기본키
- 데이터베이스 테이블의 각 행을 고유하게 식별하는 데 사용되는 하나 이상의 속성 집합
- 고유성 : 테이블 내의 모든 행이 고유하게 식별될 수 있어야 함
- NULL 불가 : 기본 키는 NULL 값을 가질 수 없음

### 후보키
- 기본 키로 사용할 수 있는 속성 또는 속성 집합
- 유일성 : Key로 하나의 Tuple을 유일하게 식별할 수 있음
- 최소성 : 꼭 필요한 속성으로만 구성

### 대체키
- 대체 키는 후보 키 중에서 기본 키로 선택되지 않은 나머지 키

### 슈퍼키
- 유일성은 만족하지만, 최소성은 만족하지 못하는 키

## 관계 기준

### 외래키
- 외래 키는 한 테이블의 속성이 다른 테이블의 기본 키를 참조하는 키
- 참조 무결성 : 외래 키는 참조하는 테이블의 기본 키와 일치해야 함.

## 구성 기준

### 복합키
- 복합 키는 두 개 이상의 속성을 결합하여 고유성을 보장하는 키

## 생성 및 의미 기준
### 자연키
- 자연 키는 비즈니스 의미를 지닌 속성을 사용하는 키   <br>
ex) email
- 데이터의 본래 속성을 사용하여 키로 활용

### 인공키
- 인공 키는 시스템에서 생성된 고유 식별자로, 비즈니스 의미가 없는 키   <br>
ex) userSeq

## 사용 이유
- 무결성 유지: 키를 적절히 선택함으로써 데이터 무결성을 유지할 수 있음.
- 성능 최적화: 인덱스를 통해 키 기반 검색의 성능을 최적화할 수 있음.
- 관계 모델링: 외래 키를 사용하여 데이터 간의 관계를 명확히 정의할 수 있음.

### 면접 질문
- **Key란 무엇이고, 종류에는 무엇이 있나요?** <br>
키란 특정 조건에 맞는 튜플을 구분할 수 있는 기준이 되는 속성입니다.  <br>
후보키, 기본키, 대체키, 슈퍼키, 외래키, 복합키 등이 있습니다.