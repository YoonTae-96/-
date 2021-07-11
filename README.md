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


## 조건문, 반복문
* 조건 if문
* 파이썬은 코딩블럭을 표시하기 위해 들여쓰기(indentation)를 사용함 즉, c,java등과 같이 코딩블럭을 { }으로 나타내지 않음
* 동일한 블럭의 들여쓰기는 모두 동일 후의 공백을 사용해야함
```python
a = 1
if a > 0:
    print("a==", a)
    print("positive number")
elif a == 0: #elif는 조건을 여러개 주기 위해 사용된다.
    print("a==", a)
    print("zero")
else:
    print("a==", a)
    print("negative number")
```    
```python
list_data = [10, 20, 30, 40, 50]
dict_data = {'key1': 1, 'key2': 2}

if 45 in list_data:
    print("45 is in list_data")
else:
    print("45 is not in list_data")

if 'key1' in dict_data:
    print("key1 is in dict_data")
else:
    print("key1 is not in dict_data")
```

* 반복문 for
* for variable in range( ): #사용법 
```python
for data in range(10): #range( ) 함수는 시작값~마지막 값-1
    print(data, "", end='')
```
```python
for data in range(10): #range( ) 함수는 시작값~마지막 값-1
    print(data, "", end='')

for data in range(0,10):
    print(data, "", end='')

for data in range(0,10,2):
    print(data, "", end='')
```

## end=
* end옵션을 사용하면 그 뒤의 출력값과 이어서 출력한다. (즉, 줄바꿈을 하지 않게 된다.)
```python
print("I like", end=" ")
print("money")
```
출력 >>>>> I like money
* 그리고, 저 end=' ' 사이에 무언가를 입력하게되면, sep와 비슷한 기능을 한다.(구분자를 사용할 수 있다) 첫번째 출력문과, 두번째 출력문 사이에 end에 넣어준 문자열이 출력된다.
```python
print("I like", end=" gold and ")
print("money")

출력 >>>>> I like gold and money
```
* for variable in list,dict...:
```python
list_data = [10, 20, 30, 40, 50]

 for data in list_data:
    print(data, "", end='') # key값만 출력된다 /value 값은 출력되지 않는다.

dict_data = {'key1': 1, 'key2': 2}

for data in dict_data:
    print(data, "", end='')

for key, value in dict_data.items():
    print(key, "", value)
```
## for ~ dict문에서 key, value 값 출력하기
* for 키, 값 in 딕셔너리.items( ): #in 뒤의 딕셔너리.items( )을 딕셔너리.key( ) 혹은 딕셔너리.value( )을 이용해 key,value 값을 따로따로 볼 수도 있다. 
ex) for key in 딕셔너리.key( )

```python     
x = {'a': 10, 'b': 20, 'c': 30, 'd': 40}
for key, value in x.items():
    print(key, "", value)
a 10
b 20
c 30
d 40
```

* 반복문 lsit comprehension -> list안에 for문이 들어있는 형태
```python
raw_data = [[1, 10], [2, 15], [3, 30], [4, 55]]
all_data = [x for x in raw_data]
x_data = [x[0] for x in raw_data]

print("all_data==", all_data)
print("x_data==", x_data)

all_data== [[1, 10], [2, 15], [3, 30], [4, 55]]
x_data== [1, 2, 3, 4]
```

* 반복분 while,break,continue

# function, lambda
* 함수정의
=>특정기능을 수행하는 function는 파이썬에서 다음과 같이 정의함.
* def 함수이름 (입력1, 입력2,...):
```python
def sum(x, y):
    s = x + y
    return s


result = sum(10, 20)
print(result)
```
* 함수 반환 값
=> 파이썬 함수는 한개 이상의 return 값을 반환할 수 있음. return 값은 , 로 분리하여 받거나 tuple 형태로 받을 수 있음
```python
def mulit_ret_func(x):
    return x + 1, x + 2, x + 3 # return(x+1, x+2, x+3)


x = 100
y1, y2, y3 = mulit_ret_func(x) # (y1, y2, y3)= mulit_ret_func(x)
print(y1, y2, y3)
```
* default parameter
* => 함수의 입력 파라미터에 기본값을 저장하는 것
* => 이러한 default parameter는, 함수가 호출되었을 경우 입력 파라미터에 명시적인 값이 전달되지 않으면 기본으로 저장한 값을 사용하겠다는 의미이다.
```python
def print_name (name, count=2):
    for i in range(count):
        print("name==", name)
print_name("DAVE") #print_name("DAVE", 5) -> DAVE 다섯번 출력함
```
* mutable / immutable parameter
* => 입력 파라미터가 mutable(list, dic, numpy 등) 데이터형인 경우는 원래의 데이터에 변형이 일어남.
* => immutable(숫자, 문자, tuple 등)은 원래의 데이터에 변형이 일어나지 않음.
```python






