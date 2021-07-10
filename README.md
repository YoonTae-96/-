# 머신러닝/딥러닝
4차 산업 혁명은 연결성과 인공지능이 중요.
# 머신러닝: 데이터를 이용하여 명시적으로 정의되지 않은 패턴을 학습하여 미래의 결과(값,분포)를 예측
# 딥러닝: 머신러닝의 한 분야로서 신경망(Neural Network)을 통하여 학습하는 알고리즘의 집합
cf)데이터 마이닝: 데이터간의 상관 관계나 속성을 찾는 것이 주 목적
# -머신러닝/딥러닝을 위한 python-
## •Data Type
list, tuple, dictionary, string
## 1.list
* a=[10, 20, 30, 40] ->list 함수 표시 [ ]대괄호 이용한다.
* index: 데이터의 위치를 알아내는 것
* list index는 0부터 시작하며, 파이썬에서는 '-'index를 지원하여 list의 마지막 부터 역순으로 값을 참조 가능하다.
* ※머신러닝 코드에서 슬라이스( ':' )와 함께 자주 사용됨 why? 머신러닝에서 -index와 함께 데이터 처리 속도가 빨리지기 때문이다
```python 
a=[10, 20, 30, 40] #list는 0,1,2,3칸으로 만들어진다
print(a)
print(a[:2]) #a의 0~1칸까지 데이터를 보여줘
print(a[1:4]) #a의 1~3번째칸 데이터를 보여줘
print(a[-4:-2]) #a의 -4~-3칸까지의 데이터를 보여줘
```
* list는 각 요소의 데이터 타입을 다르게 해서 생성할 수 있으며, 리스트안에 또 다른 리스트를 포함시킬 수 있다.
```python
b=[10,20,"Hello",[true,3.14]]
b=[10, 20, "Hello", [True, 3.14]]
print(b) #결과 값 [10, 20, 'Hello', [True, 3.14]]
print(b[:3]) 
print(b[2]) #list b의 2번째 데이터를 보여줘
print(b[3][0]) #list b의 3번째 데이터를 보여줘 ->데이터가 또 list형이네? -> 다시 0,1칸 생성 ->0번째칸인 True가 출력됌
```
*빈 list 생성후 append method를 이용하여 데이터 추가 ->머신러닝 코드에서 정확도 계산, 손실함수 값 저장위해 사용
```python
b.append(50) # append(x)는 리스트의 맨 마지막에 x를 추가하는 함수이다.
print(b) #[10, 20, 'Hello', [True, 3.14], 50]
```
* ※python list에는 (:)을 이용한 슬라이싱 기능이 있음. 슬라이싱 이용하면 범위를 지정해 부분 리스트를 얻기 가능.

## 2.Tuple
* tuple은 list와 거의 비슷하다
* 차이점
list는 [ ]으로 둘러쌈, tuple은 ( )으로 둘러싼다.
리스트 내의 원소를 변경할 수 있지만 tuple은 불가능 -> .append가 불가능하다
```python
a = (10, 20, 30, 40, 50)
print(a) #결과 (10,20,30,40,50)
```
## 3.Dictionary
* Dictionary는 Key와Value을 한 쌍으로 해서 데이터를 저장한다.
* 작성 방법은 다음과 같다
* score = {"kim":90, "lee":85, "jun":95} #여기서 kim이 Key이고 90이 Value 이다.
```python
score = {"kim":90, "LEE":85, "JUN":95}
print(score)
```

## 4.String
* Python 문자열(string)은 사용법은 4가지가 있다.
* 
1. 큰따옴표(")로 양쪽 둘러싸기
```
"Hello World"
```
2. 작은따옴표(')로 양쪽 둘러싸기
```
'Python is fun'
```
3. 큰따옴표 3개를 연속(""")으로 써서 양쪽 둘러싸기
```
"""Life is too short, You need python"""
```
4. 작은따옴표 3개를 연속(''')으로 써서 양쪽 둘러싸기
```
'''Life is too short, You need python'''
```
* string 내의 각각의 값 또한 문자열로 인식되며, 문자열을 분리하여 list로 반환하는 split( ) 함수는 머신러닝 코드에서 문자열 데이터 전처리(pre-process)하기 위해 자주 사용된다.
```python
a = "A73,CD"
print(a) # 결과 A73,CD -> 0칸에 A, 1칸에7, 2칸에 3, 3칸에 , ,4칸에 C, 5칸에 D 값이 있다. 
print(a[3])
b = a.split('3') #split 함수 사용법은 append 함수 사용법과 동일하다. 
print(b) # 결과 ['A7', ',CD'] separator 3을 기준으로 A7 과  ,CD 가 나왔다
```
## useful function
* type( ) len( ) size( ) list( ) str( ) int( )
* type(data)는 입력 data의 데이터 타입을 알려주는 함수
* len(data)은 입력 데이터의 길이(요소의 개수)를 알려주는 함수
* size(data) 함수는 모든 원소의 개수를 알려주는 함수
* list(data)는 압력 data를 리스트로 만들어 리턴하는 함수
* str(data)는 입력되는 data를 문자열로 반환하여 리턴하는 함수
* int(data)는 문자열 형태로 입력되는 숫자나 소주점이 있는 숫자등을 정수 형태로 리턴하는 함수








