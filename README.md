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
def mutable_immutable_func(int_x, input_list):
    int_x +=1
    input_list.append(100)
x=1
test_list = [1, 2, 3]
mutable_immutable_func(x, test_list)
print("x==", x ,",test_list ==", test_list)
x== 1 ,test_list == [1, 2, 3, 100] # immtubale(숫자,문자,tuple 등)은 원래의 데이터에 변형이 일어나지 않음.
```
* lambda
* => lambda는 한 줄로 함수를 작성하는 방법으로, 익명(anonymous) 함수 또는 람다 표현식(lambda expression)등으로 불림
* => lambda는 다른 함수의 인수(parameter)로 넣을때 주로 사용하며, 특히 머신 러닝에서 미분을 계산하기 위해 필요한 수치미분과 활성화 함수 등을 표현할때, 수학에서 함수 표현처럼 사용되며 마지막 표현으로 대체된다는 의미이다.
* => 함수명 = lambda 입력1, 입력2... : 대체되는 표현식
```python
f = lambda x: x + 100
for i in range(3):
    print(f(i))
```

```python
# lambda에서 입력 값을 반드시 이용할 필요는 없다.
def print_hello():
    print("Hello python")
def test_lambda(s,t):
    print("input1==", s, ",input2==", t)

s=100
t=200

fx = lambda x,y : test_lambda(s,t)
fy = lambda x,y : print_hello()

fx(500, 1000)
fy(300, 600)
```
# Class
* 반복되는 불필요한 소스코드를 최소화하면서 현실 세게의 사물을 컴퓨터 프로그래밍 상에서 쉽게 표현할 수 있ㅁ도록 해주는 프로그래밍 기술
* 인스턴스: 클래스로 정의된 객체를 프로그램상에서 이용할 수 있게 만든 변수
* 클래스 멤버: 클래스 내부에 포함되는 변수
* 클래스 함수: 클래스 내부에 포함되는 함수: 메소드
* 상속: 다른 클래스의 멤버 변수와 메소드를 물려받아 사용하는 기법
* 파이썬에서는 __init__ 메서드가 생성자(constructor)역할을 수행하여, 인스턴스가 만들어질때 한번만 호출됨
* 파이썬에서는 클래스 메서드의 첫번째 인수로 '자신의 인스턴스'를 나타내는 self를 반드시 기술해야함
* 기본적으로 파이썬에서는 메서드와 속성 모두 public
* 클래스 변수는 해당 클래스로 생성된 모든 인스턴스가 공통으로 사용하는 변수임 => 클래스 변수는 클래스 내외부에서 "클래스명.클래스 변수명" 으로 접근할 수 있음
* 클래스 메서드는 메서드 앞에 @classmethod를 반드시 표시하여 해당 메서드가 클래스 메서드임을 표시함 => 클래스 메서드는 객체 인스턴스를 의미하는 self 대신 cls라는 클래스를 의미하는 파라미터를 인수로 전달 받음

# 파이썬 numpy
## numpy 임포트하는 방법 4가지
* 1. import numpy
* 2. import numpy as np
* 3. from nummpy import exp.
* 4. from numpy import *
### numpy
#### vector/matrix 생성
* numpy: 머신러닝 코드 개발할 경우 자주 사용되는 벡터, 행렬 등을 표현하고 연산할떄 반드시 필요한 라이브러리
* numpy vs list => 머신러닝에서 숫자, 사람, 동물등의 인식을 하기 위해서는 이미지 데이터를 행렬(matrix)로 변환하는 것이 중요함 => 행렬 연산을 하기 위해서는 numpy 필수!
* 벡터 생성 => vextor은 np.arry([])를 사용하여 생성함(import numpy as np) => 머신러닝 코드 구현시, 연산을 위해서 vector, matrix등의 형상(shape), 차원(dimension)을 확인하는 것이 
* 벡터 산술 연산 => vector 간 (+,-,*,/) 은 벡터의 각각의 원소에 대해서 행해짐
* reshape 가능: 벡터를 행렬로 reshape 가능
* 행렬곱 (dot productor)
# 머신러닝
## 머신러닝 supervised learning / unsupervised learning
* 머신러닝은 supervised learning와 unsupervised learning으로 나뉜다.
* 여기서 supervised learning는 regression과 classification으로 나뉜다.
* unsupervised learning는 clustering이 있다.
* supervised learning는 입력 값(x)과 정답(t,lable)을 포함하는 training data를 이용해 학습하고, 그 핟습된 결과를 바탕으로 미지의 데이터(test data)에 대해 미래 값을 예측하는 방법이다
* regression는 training data를 이용하여 연속적인(숫자) 값을 예측하는 것을 말하며, 집평수와 가격관계, 공부시간과 시험성적 등의 관계이다.
* 분류는 training data를 이용하여 주어진 입력값이 어떤 종류의 ㅂ값인지 구별하는 것을 지칭한다.
* unspervised learning는 트레이닝 데이터에 정답은 없고 입력 데이터만 있기 때문에, 입력에 대한 정답을 찾는 것이 아닌 입력 데이터의 패턴, 특성 등을 학습을 통해 발견하는 방법을 말한다.

# CNN
* CNN에서 은닉층의 역할을 컨볼루션층과 완전 연결층이 그 역할을 대신한다.
* Conv -> Relu -> Pooling 이 세단계를 컨볼루션 층이라 한다
## Conv(컨볼루션, Convoultion)
* 입력 데이터와 가중치들의 집합체인 다양한 필터와의 컨볼루션 연산을 통해 입력 데이터의 특징을 추출하는 역할을 수행한다.
## Relu
* 활성화 함수로서 값이 0보다 크면 그대로 값을 내보내고 0보다 작으면 0으로 내보낸다. (여기서 입력되는 값은 conv에서 나온 출력을 입력으로 받는 값이다)
## Pooling
* 입력정보를 최댓값, 최솟값, 평균값 등으로 압축하여 데이터 연산량을 줄여주는 역할을 수행한다
### 컨볼루션 연산
* 필터(가중치의 집합체)를 일정간격(스트라이드)으로 이동해 가면서, 입력 데이터와 필터에서 대응하는 원시끼리 곱한 후 그 값을 모두 더해주는 연산이다. 주로 Max pooling가 많이 쓰인다.
# 패딩(padding)
* 패딩이란 컨볼루션 연산을 수행하기 전에 입력 데이터 주변을 특정 값(예를 들면 0)으로 채우는 것을 말하며, 컨볼루션 연산에서 자주 이용된다-> 컨볼루션 연산을 수행하면 데이터 크키(shape)이 줄어드는 단점을 방지하기 위해 사용
## 컨볼루션 연산을 통한 출력 테이터 크기(shape) 계산법
* 입력 데이터의 크기(H,W), 필터 크기(FH, FW), 패딩 P, 스트라이드 S, 일떄 출력 데이터 크기(OH, OW)/ 여기서 H는 행, W는 열이다.
* OH = (H+2P-FH)/S + 1      OW = (W+2P-FW)/S + 1
### 필터를 통해 데이터의 특징을 추출하는 원리
* 1. 입력데이터와 1개 이상의 필터들과 컨볼루션 연산을 통해서
* 2. 입력 데이터 특징을 추출하여 특징 맵을 만들고
* 3. 특징 맵에서 최댓값을 뽑아내어 다음층으로 전달

# RNN
* 내부적으로 순환(recurrent)되는 구조를 이용하여, 순서가 있는 데이터를 처리하는데 강점을 가진 신경망이다
* 활성화 함수가 Relu가 아닌 tanh이고, 은닉층에서 출력된 값이 다시 은닉층에 들어간다
## 순서가 있는 데이터
* 문장이나 음성같은 연속적인 데이터를 말하는데, 이런 데이터는 문장에서 놓여진 위치(순서)에 따라 의미가 달라지는 것을 알 수 있다. ex)I work at goole / I goole at work
* 즉, 현재의 데이터 의미를 알기 위해서는 이전에 놓여 있는 과거 데이터도 알고 있어야한다.
* 그래서 RNN은 이러한 과거의 데이터를 알기 위해서, 은닉층내에 순환(recurrent) 구조를 이용하여 과거의 데이터를 기억해 두고 있다가 새롭게 입력으로 주어지는 데이터와 은닉층에서 기억하거 있는 과거의 데이터를 연결시켜서 그 의미를 알아내는 기능을 가지고 있다.
# Transfer Learning(전이학습)
* 실무에서는 고해상도 칼라 이미지를 학습하는 경우, CNN 아키텍쳐를 구축하고 임의의 값으로 초기화된 파라미터 값(가중치,바이어스등)들을 처음부터 학습 시키지 않고, 대신 고해상도 칼라 이미지에 이미 학습되어 있는 (Pre-Trained) 모델의 가중치와 바이어스를 자신의 데이터로 전달(Transfer)하여 빠르게 학습하는 방법이 일반적이다. 이처럼 고해상도 칼라 이미지 특성을 파악하는데 있어 최고의 성능을 나타내는 ResNet, GoogleNet을 이용하여 우리가 원하는 데이터에 미세조정 즉, Fine tuning으로 불리는 작은 변화만을 주어 학습시키는 방법을 전이 학습이라고 한다.


