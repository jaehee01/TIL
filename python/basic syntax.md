# Python : Basic syntax1

# 파이썬 실행

### 인터프리터 Interpreter

파이썬 프로그램  ↔ ***파이썬 인터프리터*** ↔ 운영체제

인터프리터가 사용자의 명령어를 운영체제가 이해하는 언어로 바꿈(확장성)

### 인터프리터 사용법

1. **shell 프로그램**으로 한 명령어씩 입력하여 실행
2. 확장자가 **.py인 파이썬 프로그램** 실행

# 표현식과 값

### 표현식 Expression

값으로 평가될 수 있는 코드 조각

표현식이 **평가**되어 값이 나옴

### 값 Value

표현식이 평가된 결과

값이 나오지 않는다는 건 표현식이 잘못되었다는 것

### 평가 Evaluate

표현식을 실행하여 값을 얻는 과정

표현식을 순차적으로 평가하여 프로그램의 동작을 결정

### 문장 Statement

실행 가능한 동작을 기술하는 코드

조건식, 반복문, 함수 정의 등

문장은 여러 개의 표현식을 포함 함

# 타입

### 타입 Type

변수나 값이 가질 수 있는 **데이터의 종류**

어떤 종류의 데이터인지, 어떻게 해석되고 처리되어야 하는지 정의

“값”과 “값에 적용할 수 있는 연산”의 두 가지 요소로 이루어짐

타입의 중요성: 타입에 맞는 연산을 수행할 수 있기 때문

# 변수와 메모리

### 변수 Variable

값을 저장하기 위한 이름

→ 값을 **참조**하기 위한 이름

### 변수 할당

표현식을 통해 **변수에 값을 저장**

이미 값을 할당한 뒤 다른 값을 재할당 가능

### 할당문

*Variable = expression*

1. 할당 연산자(=) 오른쪽에 있는 표현식을 평가하여 값(메모리 주소)을 생성
2. 값의 메모리 주소를 = 왼쪽에 있는 변수에 저장
    1. 할당: 존재하지 않는 변수라면 새 변수를 생성
    2. 재할당: 기존에 존재한 변수하면 기존 변수를 재사용하여 메모리 주소 변경

메모리의 모든 위치에는 그 위치를 고유하게 식별하는 메모리 주소가 존재

**객체(object)**: 값이 들어 있는 상자. 타입을 갖는 메모리 주소 내 값

**변수**는 그 변수가 **참조**하는 **객체의 메모리 주소**를 가짐

# Data Types

**값의 종류**와 그 값에 적용 **가능한 연산과 동작**을 결정하는 속성

값들을 구분하고, 어떻게 다뤄야 하는지 알 수 있음

연산자 우선순위 중요

### 1. Numeric Types(숫자형 타입)

int(정수), float(실수), complex(복소수)

산술 연산자와 조합

- **int(integer)**
    
    정수를 표현하는 자료형
    
    ```python
    # 정수 자료형
    a = 10
    b = 0
    c = -5
    ```
    
    *연산자 우선순위
    
    | 우선순위 | 연산자 | 연산 |
    | --- | --- | --- |
    | 높음 | ** | 지수(거듭제곱) |
    |  | - | 음수 부호 |
    |  | *, /, //, % | 곱셈, 나눗셈, 정수 나눗셈, 나머지 |
    | 낮음 | +, - | 덧셈, 뺄셈 |

### *진수 표현

```python
# 2진수(binary)
print(0b10)  # 2

# 8진수(octal)
print(0o30)  # 24

# 16진수(hexadecimal)
print(0x10)  # 16

```

- **float**
    
    실수를 표현하는 자료형
    
    프로그래밍 언어에서는 실수에 대한 근삿값 
    

```python
# 실수 자료형
d = 3.14
e = -2.7

# 지수 표현
# 314 ∗ 0.01
number = 314e-2

print(number)  # 3.14
print(type(number))  # float

# 유한 정밀도
# 컴퓨터 메모리 용량이 한정돼 있고, 한 숫자에 대해 저장하는 용량이 제한 됨.
# 제한된 양의 메모리에 저장할 수 있는 가장 가까운 값
print(2 / 3)  # 0.6666666666666666
print(5 / 3)  # 1.6666666666666667

# 부동소수점 에러
# 컴퓨터가 실수를 표현하는 방식으로 인해 발생하는 작은 오차
# 실수를 2진수로 변환하는 과정에서 발생하는 근사치 표현 때문

# 해결 전
a = 3.2 - 3.1
b = 1.2 - 1.1

print(a)  # 0.10000000000000009
print(b)  # 0.09999999999999987
print(a == b)  # False

# 해결 후
# decimal 모듈을 사용해 부동소수점 연산의 정확성을 보장함
from decimal import Decimal

a = Decimal('3.2') - Decimal('3.1')
b = Decimal('1.2') - Decimal('1.1')

print(a)  # 0.1
print(b)  # 0.1
print(a == b)  # True

```

### 2. Sequence Type(열거형 타입)

여러 개의 값들을 순서대로 나열하여 저장하는 자료형

str, list, tuple, range

- **순서(Sequence)**: 값들이 순서대로 저장됨(정렬X)
- **인덱싱(Indexing)**: 각 값에 고유한 인덱스 번호를 가지며, 인덱스를 사용하여 특정 위치 값을 선택하거나 수정할 수 있음
- **슬라이싱(Slicing)**: 인덱스 범위를 조절해 부분적인 값을 추출할 수 있음
- **길이(Length)**: len() 함수를 사용해 저장된 값의 개수(길이)를 구할 수 있음
- **반복(Iteration)**: 반복문을 활용해 저장된 값을 반복적으로 처리할 수 있음

# Text Sequence Type(문자형 타입)

- **str(문자열)**
    
    문자들의 순서가 있는 **변경 불가능한** 시퀀스 자료형
    
    문자열은 단일 문자나 여러 문자의 조합으로 이뤄짐
    

```python
# 문자열 표현
# ‘작은따옴표’나 “큰따옴표”로 감싸서 표현
print('Hello, World!')  # Hello, World!
print(type('Hello, World!'))  # str

# 중첩 따옴표
print(
    '문자열 안에 "큰따옴표"를 사용하려면 작은 따옴표로 묶는다.'
)  # 문자열 안에 "큰따옴표"를 사용하려면 작은 따옴표로 묶는다.
print(
    "문자열 안에 '작은따옴표'를 사용하려면 큰따옴표로 묶는다."
)  # 문자열 안에 '작은따옴표'를 사용하려면 큰따옴표로 묶는다.

# Escape sequence
# 파이썬의 일반적인 문법규칙을 잠시 탈출 = 줄바꿈
# \n 줄바꿈, \t 탭, \\ 백슬래쉬, \' 작은따옴표, \" 큰따옴표
print('철수야 \'안녕\'')
print('이 다음은 엔터\n입니다.')

# String Interpolation "f-string"
# 문자열 내 변수나 표현식의 결과를 삽입하는 방법
# 문자열에 f 또는 F접두어를 붙이고 표현식을 {expression}으로 작성하는 문법
bugs = 'roaches'
counts = 13
area = 'living room'
print(f'Debugging {bugs} {counts} {area}') # Debugging roaches 13 living room

# 문자열의 시퀀스 특징
my_str = 'hello'
# 1. 인덱싱
# 인덱스: 시퀀스 내의 값들에 대한 고유한 번호. 각 값의 위치를 식별하는 데 사용되는 숫자
print(my_str[1])  # e

# 2. 슬라이싱
# 시퀀스의 일부를 선택하여 추출하는 작업
print(my_str[2:4])  # ll
print(my_str[:3])  # hel
print(my_str[3:])  # lo
print(my_str[0:5:2])  # hlo # 스텝을 지정하여 추출
print(my_str[::-1])  # olleh # -1부터 거꾸로 추출

# 3. 길이
print(len(my_str))  # 5

# 4. 문자열은 불변(변경 불가)
# TypeError: 'str' object does not support item assignment
# my_str[1] = 'z'

```

*인덱스

| h | e | l | l | o |
| --- | --- | --- | --- | --- |
| 0 | 1 | 2 | 3 | 4 |
| -5 | -4 | -3 | -2 | -1 |


# Sequence Type

## ⭐list

여러 개의 값을 순서대로 저장하는 **변경 가능한** **시퀀스 자료형**

0개 이상의 객체를 포함하며, 데이터 목록을 저장

```python
# 리스트 표현
# 어떤 자료형도 저장할 수 있음
# 리스트 안에 리스트가 들어갈 수 있음
my_list_1 = []
my_list_2 = [1, 'a', 3, 'b', 5]
my_list_3 = 1, 2, 3, 'Python', ['hello', 'world', '!!!']

my_list = [1, 'a', 3, 'b', 5]

# 인덱싱
print(my_list[1])  # a

# 슬라이싱
print(my_list[2:4])  # [3, 'b']
print(my_list[:3])  # [1, 'a', 3]
print(my_list[3:])  # ['b', 5]
print(my_list[0:5:2])  # [1, 3, 5]
print(my_list[::-1])  # [5, 'b', 3, 'a', 1]

# 길이
print(len(my_list))  # 5

# 중첩된 리스트 접근
my_list = [1, 2, 3, 'Python', ['hello', 'world', '!!!']]
print(len(my_list))  # 5
print(my_list[4][-1])  # !!! # 리스트의 4번째 값의 마지막값
print(my_list[-1][1][0])  # w # 리스트의 마지막 값의 1번째 인덱스의 0번째 인덱스 값

# 리스트는 가변
# 리스트의 요소를 바꿀 수는 있지만, 문자열의 일부는 변경할 수 없음
my_list = [1, 2, 3]
my_list[0] = 100
print(my_list) # [100, 2, 3]

```

## tuple

여러 개의 값을 순서대로 저장하는 **변경 불가능한 시퀀스 자료형**

0개 이상의 객체를 포함하며 데이터 목록을 저장

튜플의 불변 특성을 사용하여 **내부 동작과 안전한 데이터 전달**에 사용됨

실제 개발 환경에서는 자주 사용하지 않음

```python
# 튜플 표현
# 어떤 자료형도 저장 가능
my_tuple_1 = ()
# 단일 요소 튜플을 만들 때 반드시 후행 쉼표를 사용해야 함
my_tuple_2 = (1,)
my_tuple_3 = (1, 'a', 3, 'b', 5)

my_tuple = (1, 'a', 3, 'b', 5)

# 인덱싱
print(my_tuple[1])  # a

# 슬라이싱
print(my_tuple[2:4])  # (3, 'b')
print(my_tuple[:3])  # (1, 'a', 3)
print(my_tuple[3:])  # ('b', 5)
print(my_tuple[0:5:2])  # (1, 3, 5)
print(my_tuple[::-1])  # (5, 'b', 3, 'a', 1)

# 길이
print(len(my_tuple))  # 5

# 튜플은 변경할 수 없음
# my_tuple[1] = 'z'
# TypeError: 'tuple' object does not support item assignment

# 다중 할당
x, y = 10, 20
print(x)  # 10
print(y)  # 20
# 실제 내부 동작
(x, y) = (10, 20)

# 값 교환
x, y = 1, 2
x, y = y, x
# 실제 내부 동작
temp = (y, x)  # 튜플 생성
x, y = temp  # 튜플 언패킹
print(x, y)  # 2 1

# 그룹화
student = ('Kim', 20, 'CS')
name, age, major = student  # 언패킹
print(name, age, major)  # Kim 20 CS

#튜플 주의사항
result = 100,
print(type(result)) # tuple
```

## range

연속된 정수 시퀀스를 생성하는 변경 불가능한 자료형

모든 매개변수는 정수만 사용 가능

range(시작 값, 끝 값, 증가 값)

```python
# range
# 0부터 4까지 1씩 증가(기본 증가값이 1)
my_range_1 = range(5)
# 1부터 9까지 1씩 증가
my_range_2 = range(1, 10)
# 5부터 1까지 -1만큼 증가 (음수 증가값의 경우 감소하는 수열 생성)
my_range_3 = range(5, 0, -1)
# 증가 값이 0이면 에러

print(my_range_1)  # range(5)
print(my_range_2)  # range(1, 10)
print(my_range_3)  # range(5, 0, -1)

# 리스트로 형 변환 시 데이터 확인 가능
print(list(my_range_1))  # [0, 1, 2, 3, 4]
print(list(my_range_2))  # [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(my_range_3))  # [5, 4, 3, 2, 1]

# 값의 범위 규칙

# 음수 증가 시
# 시작 값이 끝 값보다 큰 경우 (정상)
print(list(range(5, 1, -1)))  # [5, 4, 3, 2]
# 시작 값이 끝 값보다 작은 경우
print(list(range(1, 5, -1)))  # []

# 양수 증가 시
# 시작 값이 끝 값보다 작은 경우 (정상)
print(list(range(1, 5)))  # [1, 2, 3, 4]
# 시작 값이 끝 값보다 큰 경우
print(list(range(5, 1)))  # []

# 주로 반복문과 함께 활용 예정
# 이터레이터: 반복문의 값의 돌려주는 역할
for i in range(1, 10):
    print(i)  # 1 2 3 4 5 6 7 8 9

for i in range(1, 10, 2):
    print(i)  # 1 3 5 7 9
```

## ⭐dict

**key-value 쌍**으로 이루어진 **순서와 중복이 없**는 **변경 가능**한 자료형

key는 변경 불가능한 자료형만 사용 가능(str, int, float, tuple, range)

value는 모든 자료형 사용 가능

```python
# 딕셔너리 표현
my_dict_1 = {}
my_dict_2 = {'key': 'value'}
my_dict_3 = {'apple': 12, 'list': [1, 2, 3]}
print(my_dict_1)  # {}
print(my_dict_2)  # {'key': 'value'}
print(my_dict_3)  # {'apple': 12, 'list': [1, 2, 3]}

# 딕셔너리는 key에 접근해 value를 얻어냄
# 따라서 key는 중복되면 안됨
my_dict = {'apple': 12, 'list': [1, 2, 3]}
print(my_dict['apple']) # 12
print(my_dict['list']) # [1, 2, 3]
print(my_dict['list'][1]) # 2

# 추가
my_dict['banana'] = 50
print(my_dict)  # {'apple': 12, 'list': [1, 2, 3], 'banana': 50}

# 변경(value만 변경 가능)
my_dict['apple'] = 100
print(my_dict)  # {'apple': 100, 'list': [1, 2, 3], 'banana': 50}
```

## set(집합 자료형)

순서와 중복이 없는 변경 가능한 자료형

인덱스가 존재하지 않음

```python
# 세트 표현
# 빈 set을 만들려면 dict와 구분하기 위해 set()으로 명시해줘야 함
my_set_1 = set()
my_set_2 = {1, 2, 3}
my_set_3 = {1, 1, 1}
print(my_set_1)  # set()
print(my_set_2)  # {1, 2, 3}
print(my_set_3)  # {1} # 중복값을 하나로 처리

# 세트의 집합 연산
my_set_1 = {1, 2, 3}
my_set_2 = {3, 6, 9}

# 합집합
print(my_set_1 | my_set_2)  # {1, 2, 3, 6, 9}

# 차집합
print(my_set_1 - my_set_2)  # {1, 2}

# 교집합
print(my_set_1 & my_set_2)  # {3}

```

# Other Types

## None

파이썬에서 ‘값이 없음’을 표현하는 자료형

```python
# None # N은 꼭 대문자로 써야 함
variable = None
print(variable)  # None
```

## Boolean

참(True)과 거짓(False)을 표현하는 자료형

비교, 논리 연산의 평가 결과로 사용됨

주로 조건, 반복문과 함께 사용

```python
# Boolean # T와 F는 꼭 대문자로 써야 함
bool_1 = True
bool_2 = False

print(bool_1)  # True
print(bool_2)  # False
print(3 > 1)  # True
print('3' != 3)  # True
```

## Collection

여러 개의 항목 또는 요소(str, list, tuple, set, dict)를 담는 자료 구조

| 컬렉션 | 변경 가능 여부 | 순서(시퀀스) 여부 |
| --- | --- | --- |
| str | X | O |
| list | O | O |
| tuple | X | O |
| dict | O | X |
| set | O | X |

```python
# immutable (불변) # 값을 바꾸려면 재할당 해야 함
my_str = 'hello'
my_str[0] = 'z'  # TypeError: 'str' object does not support item assignment

# mutable (가변)
my_list = [1, 2, 3]
my_list[0] = 100
print(my_list)  # [100, 2, 3]
```

# 형변환 Type Conversion

한 데이터 타입을 다른 데이터 타입으로 변환하는 과정

## 암시적 형변환 Implicit Type conversion

파이썬이 자동으로 수행하는 형변환

정수와 실수의 연산에서 정수가 실수로 변환됨

Boolean과 Numeric Type에서만 가능

```python
# 암시적 형변환
print(3 + 5.0) # 8.0
print(True + 3) # 1 + 3 # 4
print(True + False) # 1 + 0 # 1
```

## 명시적 형변환 Explicit Type conversion

프로그래머가 직접 지정하는 형변환

```python
# str -> int 형식에 맞는 숫자만 가능
print(int('1')) # 1
print(int('3.5')) # 오류
print(int(3.5)) # 3
print(float('3.5')) # 3.5

# int -> str 모두 가능
print(str(1) + '등') # 1등
```

# 연산자

## 산술 연산자

## 복합 연산자

연산과 할당이 함께 이뤄짐

코드의 명시도가 떨어지기 때문에 자주 사용하지 않음

| 기호 | 예시 | 의미 |
| --- | --- | --- |
| += | a += b | a = a + b |
| -= | a -= b | a = a - b |
| *= | a *= b | a = a * b |
| /= | a /= b | a = a / b |
| //= | a //= b | a = a // b |
| %= | a %= b | a = a % b |
| **= | a **= b | a = a ** b |

```python
# 복합 연산자
y = 10
y -= 4
# y = y - 4
print(y)  # 6

z = 7
z *= 2
print(z)  # 14

w = 15
w /= 4
print(w)  # 3.75

q = 20
q //= 3
print(q)  # 6
```

## 비교 연산자

| 기호 | 내용 |
| --- | --- |
| < | 미만 |
| < = | 이하 |
| > | 초과 |
| > = | 이상 |
| == | 같음 |
| ! = | 같지 않음 |
| is | 같음 |
| is not | 같지 않음 |

값 비교에는 ==을 사용, 객체 비교에는 is를 사용

```python
# 비교 연산자
print(3 > 6)  # False

# == 비교 연산자
# 값이 같은지(동등성)를 비교
# 1 == True는 파이썬이 내부적으로 True를 1로 간주하기 때문에 True임
print(2.0 == 2)  # True
print(2 != 2)  # False
print('HI' == 'hi')  # False

# is 비교 연산자
# 객체 자체가 같은지(식별성)를 비교
# 두 변수가 동일한 메모리 주소(레퍼런스)를 가리키고 있을 때만 True
# SyntaxWarning: "is" with a literal. Did you mean "=="?
print(1 is True)  # False
print(2 is 2.0)  # False

# 왜 is 대신 ==를 사용해야 하나?
print(1 is True)  # False
print(2 is 2.0)  # False
print(1 == True)  # True
print(2 == 2.0)  # True

# is 연산자는 언제 사용하는가?
# None과 비교할 때
x = None

# 권장
if x is None:
    print('x는 None입니다.')

# 비권장
if x == None:
    print('x는 None입니다.')
    

# 싱글턴 객체와 비교할 때
# 프로그램 전체에서 오직 1개만 존재하도록 만들어진 특별한 객체
# None, True, False
# 하나의 객체가 계속 재사용되기 때문에 여러 곳에서 쓰더라도 같은 메모리 주소를 가리킴
x = True
y = True

print(x is y) # True
print(True is True) # True
print(False is False) # True
print(None is None) # True

# 추가 예시: 리스트나 객체 비교
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)  # True (두 리스트의 값은 동일)
print(a is b)  # False (서로 다른 리스트 객체)

# b가 a를 그대로 참조하도록 할 경우
b = a
print(a is b)  # True (같은 객체를 가리키므로 True)
```

## 논리 연산자

```python
# 논리 연산자
print(True and False)  # False
print(True or False)  # True
print(not True)  # False
print(not 0)  # True

# 논리 연산자 & 비교 연산자
num = 15
result = (num > 10) and (num % 2 == 0)
print(result)  # False

name = 'Alice'
age = 25
result = (name == 'Alice') or (age == 30)
print(result)  # True
```

## 단축평가

논리 연산에서 두 번째 피연산자를 평가하지 않고 결과를 결정하는 동작

코드 실행을 최적화하고, 불필요한 연산을 피할 수 있도록 함

```python
# 단축 평가

vowels = 'aeiou'
# ''빈 문자열은 False, 'a'문자열 안에 뭐라도 있으면 True
print(('a' and 'b') in vowels)  # False
print(('b' and 'a') in vowels)  # True

# 0은 False
# and는 뒤에까지 봐야 함 -> 뒤에 값까지 평가하고 결정
print(3 and 5)  # 5
print(3 and 0)  # 0
print(0 and 3)  # 0
print(0 and 0)  # 0

# or는 앞만 봐도 됨 -> 앞에 값만 평가하고 결정
print(5 or 3)  # 5
print(3 or 0)  # 3
print(0 or 3)  # 3
print(0 or 0)  # 0
```

## 멤버십 연산자

특정 값이 시퀀스나 다른 컬렉션에 속하는지 여부 확인

| in | 왼쪽 피연산자가 오른쪽 피연산자의 시퀀스에 속하는지를 확인 |
| --- | --- |
| not in | 왼쪽 피연산자가 오른쪽 피연산자의 시퀀스에 속하지 않는지를 확인 |

```python
# 멤버십 연산자

word = 'hello'
numbers = [1, 2, 3, 4, 5]

print('h' in word)  # True
print('z' in word)  # False

print(4 not in numbers)  # False
print(6 not in numbers)  # True

```

## 시퀀스형 연산자

시퀀스 간 연산에서 산술연산자와 다른 역할

| + | 결합 연산자 |
| --- | --- |
| * | 반복 연산자 |

```python
# 시퀀스형 연산자

print('Gildong' + 'Hong')  # Gildong Hong
print('hi' * 5)  # hihihihihi

print([1, 2] + ['a', 'b'])  # [1, 2, 'a', 'b']
print(1, 2] * 2)  # [1, 2, 1, 2]
```

## 연산자 우선순위 정리
| 우선순위 | 연산자 | 내용 |
| --- | --- | --- |
| 높음 | ( ) | 소괄호 grouping |
|  | [ ] | 인덱싱, 슬라이싱 |
|  | ** | 거듭제곱 |
|  | +, - | 단항 연산자(양수, 음수) |
|  | *, /, //, % | 산술 연산자 |
|  | +, - | 산술 연산자 |
|  | <, < =, >, > =, ==, ! = | 비교 연산자 |
|  | is, is not | 객체 비교 |
|  | in, not in | 멤버십 연산자 |
|  | not | 논리 부정 |
|  | and | 논리 and |
| 낮음 | or | 논리 or |
