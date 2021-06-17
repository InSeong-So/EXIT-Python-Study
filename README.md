# 0. 파이썬 언어의 장점

1. 문법이 간결하다.
2. 다양한 운영체제를 지원한다.
3. GUI Applictaion 개발이 가능하다.
4. 방대한 라이브러리 지원이 가능하다.
5. 범용 언어(네트워크, 웹, 데이터분석, 기계학습)이다.

# 1. Print 함수의 이해

```py
# 기본 출력
print('Hello Python!')
print("Hello Python!")
print('''Hello Python!''')
print("""Hello Python!""")

print()

# separator 옵션 : 문자열을 이어주는 역할
print('T', 'E', 'S', 'T', sep='')
print('2019', '02', '19', sep='-')
print('isso', 'naver.com', sep='@')

print()

# end 옵션 : 문자열의 끝을 어떻게 처리할지 지정
print('Welcome To', end=' ')
print('the black parade', end=' ')
print('piano notes')

print()

# format 옵션 : 원하는 형태의 문자를 대입해준다.
print('{} and {}'.format('You', 'Me'))  # 순서대로
print("{0} and {1} and {0}".format('You', 'Me'))  # 인덱스 순서대로 매핑
print("{a} are {b}".format(a='You', b='Me'))  # 키-밸류 형태로 매핑
# %s : 문자, %d : 정수, %f : 실수
print("%s's favorite number is %d" % ('isso', 7))
# %5d : 5자리 정수, %4.2f : 실수형태이나 소수점은 2자리까지
print("Test: %5d, Price: %4.2f" % (776, 6534.123))
print("Test: {0: 5d}, Price:{1: 4.2f}".format(776, 6534.123))
print("Test: {a: 5d}, Price:{b: 4.2f}".format(a=776, b=6534.123))

# escape 코드
'''
\n : 개행
\t : 탭
\\ : 문자
\' : 문자
\" : 문자
\r : 캐리지 리턴
\f : 폼 피드
\a : 벨 소리
\b : 백 스페이스
\000 : 널 문자
'''

# 유의
print("'You'")
print('\'You\'')
print('"You"')
print("""'You'""")
print('\\You\\\n\n\n\n')
print('줄 바꿈!')
print('\t\t\t탭 누름!')
```

## 2. 파이썬 구성요소

```py
#import this
import sys

# 기본 인코딩
print(sys.stdin.encoding)   # 입력
print(sys.stdout.encoding)  # 출력

# 출력문
print('My name is Goodboy!')

# 변수 선언 : 한글 변수 선언은 지양
# my_name = 'Goodboy' # 어떤 값을 할당할 때 쓰는 것
my_name = 'Badboy'

# 조건문
if my_name == 'Goodboy':
    print('Ok')


# 반복문
for i in range(1, 10):
    for j in range(1, 10):
        print('%d * %d = ' % (i, j), i*j)

# 함수 선언
def greeting():
    print('hi!')

# 함수 실행
greeting()

# 클래스(객체의 설계도)
class Cookie:
    pass

# 객체 생성
cookie = Cookie()

print(id(cookie))
print(dir(cookie))
```

## 3. 파이썬 가상환경 설정

- 가상환경 생성
- 가상환경 실행/해제 (window: Scripts, mac: Bin)
- 패키지 설치 및 삭제
- 패키지 리스트 출력
- 패키지 검색

```sh
# root 이동
cd \

# 파이썬 가상환경 설치, 이미 존재하는 가상환경이면 pass
python -m venv python_basic

cd python_basic

cd Scripts

# 활성화
activate.bat

# 비활성화
dactivate.bat

# 플러그인 탐색 : 종료, 웹( https://pypi.org/ )에서 실행하도록 변경
pip search simplejson
# 또는
pip search simple*

# 플러그인 설치
pip install simplejson

# 설치된 플러그인 조회
pip list

# 설치된 플러그인 삭제
# pip uninstall simplejson

# 플러그인 업그레이드
pip install --upgrade simplejson

# 플러그인 세부정보 조회
pip show simplejson
```

```py
# Section03
# 파이썬 가상환경 개념, 설정 및 pip 사용법, vscode 연동

#외부 설치 패키지 테스트
import simplejson as json

test_dict = {'1': 95, '4': 77, '3': 65, '5': 100, '2': 88}

#simplejson 실행
print(json.dumps(test_dict, sort_keys=True, indent=4 * ' '))
```

## 4. 파이썬 자료형
- 자료형
  ```py
  # Boolean
  v_bool = True
  # Numbers - Int
  v_int = 7
  # Numbers - Float
  v_float = 10.3
  # String
  v_str = "Good"
  # Bytes
  v_bytes = bytes(10)
  # List
  v_list = [3, 5, 7]
  # Tuple
  v_tuple = 3, 5, 7
  # Set
  v_set = {7, 8, 9}
  # Dictionary
  v_dict = {
      "name": "capt",
      "age": 100
  }

  print(type(v_list))    # 어떤 데이터 타입인지 알려주는 함수 type()
  print(type(v_tuple))
  print(type(v_set))
  ```

- 숫자형 연산
  ```py
  import math

  int1 = 39
  int2 = 939
  big_int1 = 9999999999999999999999999999999999999999999999
  big_int2 = 7777777777777777777777777777777777777777777777
  float1 = 1.234
  float2 = 3.784
  float3 = .5
  float4 = 10.

  print(int1 + int2)      # + 더하기
  print(int2 - int1)      # - 빼기
  print(float1 * float2)  # * 곱하기
  print(int2 / float3)    # / 나누기
  print(int2 // int1)     # // 나눈 후 몫만 반환
  print(int1 % float1)    # % 나눈 후 나머지만 반환
  print(int1**2)          # ** 지수(제곱)

  # 다른 타입 간의 연산
  print(type(int1), type(float1))
  result = int1 + float1
  print(result)
  # 형변환 : int, float, complex(복소수)
  print(int(result))
  print(float(result))
  print(complex(result))
  # Boolean
  print(int(True))        # 1
  print(int(False))       # 0
  print(int('3'))         # 3
  print(complex(False))

  # 단항 연산자
  y = 100
  y += 100
  y *= 100
  print(y)

  # 절대값
  print(abs(-7))

  n, m = divmod(100, 8)   # 100을 8로 나눠서 몫을 n, 나머지를 m으로 대입
  print(n, m)

  # math 라이브러리
  print(math.ceil(5.1))       # 무조건 올림
  print(math.floor(3.874))    # 무조건 내림
  ```

- 문자열 연산
  ```py
  str1 = 'test'
  str2 = 'perfect'
  str3 = 'yes'
  str4 = str('ace')   # 굳이 불필요하게 선언하는 방법

  # 문자열의 길이 반환
  print(len(str1), len(str2), len(str3), len(str4))

  # escape
  escape_str1 = "Have a niceday! \"haha!\""
  print(escape_str1)
  escape_str2 = "Tab : \tTab\tTab"
  print(escape_str2)

  # raw string
  raw_s1 = r'C:\Programs\Test\Bin'    # escape 적용 안됨
  print(raw_s1)
  raw_s2 = r"\\a\\a"
  print(raw_s2)

  # multi line : 그냥 엔터로 줄 띄움하면 안됨
  multi = \
  """
  문자열
  멀티라인
  테스트
  """
  print(multi)

  # 문자열 연산
  str_operator = '*'
  str_target = 'abc'
  print(str_operator * 100)
  print(str_target + 'def')   
  # print(str_operator + 3)   # 에러 : 숫자형을 더할 순 없음
  print(str_operator + '3')   # 에러 : 숫자형을 더할 순 없음
  print('a' in str_target)    # a가 다음에 오는 문자에 포함되어있는지 여부
  print('z' not in str_target)    # a가 다음에 오는 문자에 불포함되어있는지 여부

  # 형변환
  print(str(777) + 'a')
  print(str(10.4))

  # 문자열 함수
  print(str3.islower())               # 문자열이 소문자인지 여부
  print(str1.endswith('s'))           # 문자열이 s로 끝나는지 여부
  print(str2.capitalize())            # 문자열을 첫글자만 대문자로
  print(str2.replace('per', 'lel'))   # 문자열을 변경
  print(list(reversed(str1)))         # 문자열을 뒤집어서 리스트로 변환

  # 문자열 슬라이싱
  print(str2[0:3])                    # 0부터 3까지(3 미포함) : 0, 1, 2
  print(str2[0:])                     # 0부터 끝까지
  print(str2[:])                      # 전체
  print(str2[0:4:2])                  # 0부터 4까지 출력하나 2씩 점프
  print(str2[1:-2])                   # 1부터 뒤에서 두번째 이전까지
  print(str2[::-1])                   # 역순으로 출력하기
  ```

## 5. 파이썬 자료구조
- 리스트와 튜플
  ```py
  # 리스트 - 순서 O, 중복 O, 수정 O, 삭제 O
  # 선언
  a = []
  b = list()                              # 명시적으로 선언하기
  c = [1, 2, 3, 4]                        # 값을 저장함과 동시에 리스트 선언
  d = [10, 100, 'Pen', 'Banana', 4.21]    # 다양한 타입 저장 가능
  e = [10, 100, ['Pen', 'Banana']]        # 리스트 내 리스트도 가능

  # 인덱싱
  print(d[3])                             # 앞에서부터 4번째(0, 1, 2, 3)
  print(d[-2])                            # 뒤에서부터 2번째(-1, -2)
  print(d[0] + d[1])                      # numbers 연산
  print(e[2][1])                          # 리스트 내의 리스트 가져오기

  # 슬라이싱
  print(d[0:1])
  print(d[0:2])
  print(e[2][1:3])

  # 연산
  print(c + d)
  print(c * 3)
  print(str(c[0]) + 'hi')

  # 수정/삭제
  c[0] = 77
  print(c)
  c[0:2] = [100, 1000, 10000]
  print(c)
  c[1] = ['a', 'b', 'c']
  print(c)

  del c[1]
  print(c)
  del c[-1]
  print(c)

  # 함수
  y = [5, 2, 3, 1, 4]
  print(y)
  y.append(6)                             # 리스트의 끝에 삽입
  y.sort()                                # 리스트 오름차순 정렬
  y.reverse()                             # 리스트 뒤집기
  y.insert(2, 7)                          # 2번 인덱스에 7을 삽입
  y.remove(7)                             # 7의 값을 삭제
  y.pop()                                 # 마지막 원소를 삭제하고 반환
  x = [88, 77]
  y.extend(x)                             # 붙이기, + 와 동일

  # 튜플 - 순서 O, 중복 O, 수정 X, 삭제 X : 중요한 키 데이터 - 변경되거나 수정되면 크리티컬한 영향을 끼치는 데이터는 튜플에 저장한다.
  # 선언
  a = ()
  b = (1, )
  c = (1, 2, 3, 4)
  d = (10, 100, ('a', 'b', 'c'))

  # 인덱싱
  print(c[2])
  print(c[3])
  print(d[2][2])
  print(c[2:])
  print(d[2][0:2])

  # 연산
  print(c + d)
  print(c * 3)

  # 함수
  z = (5, 2, 1, 3, 4)
  print(z)
  print(3 in z)
  print(z.index(3))       # 값이 3인 인덱스
  print(z.count(1))       # 개수가 1인 원소의 갯수
  ```

- 딕셔너리와 집합
  ```py
  # 딕셔너리 - 순서 X, 중복 X 수정 O, 삭제 O : key, value 형태로 저장
  # 선언
  a = {'name': 'capt', 'age': 100, 'skill': 'shield', 'death': False}
  b = {0: 'capt', 1: 'thor'}
  c = {'arr': [1, 2, 3, 4, 5]}

  print(type(a))

  # 출력
  print(a['name'])        # name 키가 없다면 에러가 발생
  print(a.get('name'))    # get 메소드로 접근하면 에러가 안남
  print(a.get('life'))    # 에러 안남
  print(c['arr'][1:2])    # 슬라이싱 가능

  # 딕셔너리 추가
  a['life'] = '1'
  print(a)
  a['rank'] = [1, 3, 4]
  a['rank2'] = (1, 2, 3,)
  print(a)

  # keys, values, items
  print(a.keys())         # a의 키들만 리스트 형태로 반환
  # print(a.keys()[0])      # 에러, not supported index
  print(list(a.keys()))   # 리스트로 변환한 뒤 인덱싱

  temp = list(a.keys())
  print(temp[1:3])

  print(a.values())       # values를 리스트 형태로 반환
  print(list(a.values()))

  print(a.items())        # key, value 한 쌍을 리스트로 반환한다.
  temp = list(a.items())
  print(temp)             # list 안에 튜플 형태로 반환한다.

  print(2 in b)               # 없다
  print('name2' in a)         # 없다
  print('name2' not in a)     # 있다

  # 집합 - 순서 X, 중복 X
  a = set()
  b = set([1, 2, 3, 4])
  c = set([1, 4, 5, 6, 6])    # 중복을 허용하지 않음

  print(c)

  # 리스트는 대괄호, 튜플은 중괄호, 셋은 소괄호

  s1 = set([1, 2, 3, 4, 5, 6])
  s2 = set([4, 5, 6, 7, 8, 9])

  print(s1.intersection(s2))  # s1과 s2의 교집합을 반환
  print(s1 & s2)              # 동일

  print(s1.union(s2))         # s1과 s2의 합십합을 반환
  print(s1 | s2)              # 동일

  print(s1.difference(s2))    # s1과 s2의 차집합을 반환
  print(s1 - s2)              # 동일

  # 추가 & 제거
  s3 = set([7, 8, 10, 15])
  s3.add(18)
  # s3.add(7)                 # 중복이라 안됨
  print(s3)
  s3.remove(15)
  print(s3)
  ```

## 6. 파이썬 조건문
```py
# 조건문
print(type(True))
print(type(False))

if True:
    print("실행!")

if False:
    print("실행 안됨")

if False:
    print("실행 안됨2")
else:
    print("실행!2")

# 관계 연산자 : >, >=, <, <=, ==, !=

a = 10
b = 0

print(a == b)
print(a != b)
print(a > b)
print(a >= b)
print(a < b)
print(a <= b)

# 참 거짓 종류
# True : "내용", [내용], (내용), {내용}, 1
# False : "", [], (), {}, 0

city = ""

if city:
    print("실행")
else:
    print("실행 안됨")

# 논리 연산자 : and or not
a = 100
b = 60
c = 15

print('and : ', a > b and b > c)
print('or : ', a > b or c > b)
print('not : ', not a > b)
print(not False)
print(not True)

# 산술 > 관계 > 논리 순서로 적용
print('ex1 : ', 5 + 10 > 0 and not 7 + 3 == 10)

score1 = 90
score2 = 'A'

if score1 >= 90 and score2 == 'A':
    print('A 클래스')
else:
    print('과락')

# 다중 조건문
num = 90
if num >= 90:
    print('등급 A')
elif num >= 80:
    print('등급 B')
else:
    print('등급 C')

# 중첩 조건문
age = 27
height = 175
if age >= 20:
    if height >= 170:
        print("통과")
```

## 7. 파이썬 반복문
```py
# 반복문 : for, while

v1 = 1
while v1 < 11:
    print("v1 : ", v1)
    v1 += 1

for v2 in range(10):
    print("v2 : ", v2)

for v3 in range(1, 11):
    print("v3 : ", v3)

sum1 = 0
cnt1 = 1

while cnt1 <= 100:
    sum1 += cnt1
    cnt1 += 1

print('합1 : ', sum1)
print('합2 : ', sum(range(1, 101)))
print('합2 : ', sum(range(1, 101, 2)))

# 시퀀스 자료형 반복 : 문자열, 리스트, 튜플, 집합, 사전
# iterable 리턴 함수 : range, reversed, enumerate, filter, map, zip

names = "tao"
for s in names:
    print("char : ", s)

names = ["a", "b", "c", "d", "e"]
for name in names:
    print("name : ", name)

info = {
    "name": "capt",
    "age": 100,
    "skill": "shield"
}
# 키를 반환
for key in info:
    print("info : ", key)
# 키를 반환
for key in info.keys():
    print("info : ", key)
# 값을 반환
for key in info.values():
    print("info : ", key)
# 키와 값
for key in info.items():
    print("info : ", key)

name = "Thor"
for n in name:
    if not n.isupper():
        print(n.upper())
        # print(n.lower())
    else:
        print(n)

# break
numbers = [14, 3, 4, 7, 10, 24, 17, 2, 33, 15, 34, 36, 38]
for num in numbers:
    if num == 33:
        print("found 33!")
        break
    else:
        print("not found 33!")

# for-else  : for문 안에 break가 작동하면 else를 무시하나, break가 작동되지 않으면 else를 수행한다.
#           : 반복문이 정상적으로 수행 되었다면 else 블럭 수행
for num in numbers:
    if num == 33:
        print("found 33!")
        break
    else:
        print("not found 33!")
else:
    print("not found 33!")

# continue
tp = ["1", 2, 5, True, 4.3, complex(4)]
for v in tp:
    if type(v) is float:
        continue
    print("타입 : ", v)

# 자료구조 변환
name = "capt"
print(reversed(name))
print(list(reversed(name)))
print(tuple(reversed(name)))
```

## 8. 파이썬 함수
```py
# 반복되는 기능을 사전에 정의하여 사용할 수 있다. 코드의 가독성도 증가한다.
# 하나의 기능을 수행하게 만들어야 함


# 함수 정의 방법 : define으로 선언
def function_name(parameter):
    # 코드 선언부
    pass

# 함수 호출 : 선언 위치 중요
function_name()


# 리턴 값 없음
def hello(world):
    print("Hello, ", world)

hello("Niceman")


# 리턴 값 있음
def hello_return(world):
    return "Hello, " + str(world)

print(hello_return("Niceman"))


# 다중 값 리턴
def func_mul1(x):
    y1 = x * 2
    y2 = x * 4
    y3 = x * 6
    return y1, y2, y3

val1, val2, val3 = func_mul1(3)
print(val1, val2, val3)


# 튜플 리턴
def func_mul2(x):
    y1 = x * 2
    y2 = x * 4
    y3 = x * 6
    return (y1, y2, y3)

tup = func_mul2(4)
print(type(tup), tup, list(tup))


# 리스트 리턴
def func_mul2(x):
    y1 = x * 2
    y2 = x * 4
    y3 = x * 6
    return [y1, y2, y3]


lis = func_mul2(6)

print(type(lis), lis, set(lis))


# 딕셔너리 리턴
def func_mul3(x):
    y1 = x * 2
    y2 = x * 4
    y3 = x * 6
    return {'ret1': y1, 'ret2': y2, 'ret3': y3}

dic = func_mul3(8)
print(type(dic), dic, dic.get('ret3'), dic.items(), dic.keys(), dic.values())


# *args : 가변, 튜플형태로 넘어감
def args_func(*args):  # 매개변수명 자유롭게 변경 가능
    for i, v in enumerate(args):    # 인덱스 : 값
        print('{}'.format(i), v, end=' ')

args_func('Kim')
args_func('Kim', 'Park')
args_func('Kim', 'Park', 'Lee')


# kwargs    :keyword arguments
def kwargs_func(**kwargs):  # 매개변수명 자유롭게 변경 가능, key:value
    for v in kwargs.keys():
        print('{}'.format(v), kwargs[v], end=' ')

kwargs_func(name1='Kim')
kwargs_func(name1='Kim', name2='Park')
kwargs_func(name1='Kim', name2='Park', name3='Lee')


# 혼합하여 사용하기
def example(arg_1, arg_2, *args, **kwargs):
    print(arg_1, arg_2, args, kwargs)

example(10, 20, 'park', 'kim', 'lee', age1=33, age2=34, age3=44)


# 중첩함수 : 파이썬 데코레이터
def nested_func(num):
    def func_in_func(num):
        print(num)

    print("In func")
    func_in_func(num + 100)

nested_func(1)
# 실행불가
# func_in_func(1)


# Hint
def tot_length1(word: str, num: int) -> int:
    return len(word) * num

print('hint exam1 : ', tot_length1('i love you', 10))

def tot_length2(word: str, num: int) -> None:
    print('hint exam2 : ', len(word) * num)

tot_length2("niceman", 10)


# 람다식 : 메모리 절약, 가독성 향상, 코드 간결
# 함수는 객체 생성 -> 리소스(메모리) 할당
# 람다는 즉시 실행 함수(Heap 초기화) -> 메모리 초기화

# 예제7
# def mul_10(num) -> int:
#     return num * 10
#
# def mul_10_one(num): return num * 10
#
# lambda x: x * 10

# 일반적 함수 -> 변수 할당
def mul_10(num):
    return num * 10

mul_func = mul_10

print(mul_func(5))
print(mul_func(6))

# 람다 함수 -> 할당
# 데이터를 대량으로 가져와서 일괄적용하는데에 유용
# num = input, num * 10 = return
lambda_mul_func = lambda num: num * 10

print('>>>>> ', lambda_mul_func(10))

def func_final(x, y, func):
    print(x * y * func(10))
    
func_final(10, 10, lambda_mul_func)

print(func_final(10, 10, lambda x : x * 1000))
```

## 9. 파이썬 클래스
- 클래스 선언 및 Self
  ```py
  # 프로그램이 커지면 처리해야 하는 메소드가 너무 많다.
  # 서로 간의 결합을 느슨하게 해서 기능에 대한 유연성을 확보, 생산성을 향상시킨다.
  # self, class, instance
  
  # 선언
  class UserInfo:
      # 속성, 메소드 정의
      def __init__(self, name): # magic method
          # UserInfo의 인스턴스 변수 내에 name을 정의
          self.name = name
      def user_name(self):
          print('Name : ', self.name)
  
  # 인스턴스가 갖고 있는 각각의 저장장소인 네임스페이스는 전부 다르다.
  user1 = UserInfo('capt')
  user1.user_name()
  print(user1.name)
  user2 = UserInfo('thor')
  user2.user_name()
  print(user2.name)

  # 네임스페이스 확인 : 서로 다름
  print(id(user1))
  print(id(user2))
  # 각각의 인스턴스 네임스페이스 호출 : 서로 다름
  print(user1.__dict__)
  print(user2.__dict__)

  # 클래스와 인스턴스의 차이를 구분하는 것은 중요하다.
  # 네임스페이스 : 객체를 인스턴스화 할 때 저장된 공간
  # 클래스 변수 : 직접 사용 가능, 객체보다 먼저 생성
  # 인스턴스 변수 : 객체마다 별도로 존재, 인스턴스를 생성 후 사용한다.

  # self란?
  def SelfTest:
      def function1():      # 클래스 메서드
          print('function1 called!')
      def function2(self):  # 인스턴스 메서드
          print(id(self))
          print('function2 called!')

  self_test = SelfTest()
  # self_tst.function1()  # self 인자가 업서서불가능
  SelfTest.function1()  # 인스턴스가 없다면 클래스에서 직접 호출
  self_tst.function2()  # 인스턴스가 있다면 인스턴스를 생성하고 호출

  print(id(self_test))
  SelfTest.function2(self_test) # 클래스에서 직접 호출할 거라면 인스턴스를 인자로 넘겨서 호출

  # 클래스 변수, 인스턴스 변수
  class WareHouse:
      # 클래스 변수
      stock_num = 0 # 재고
      def __init__(self, name):
          self.name = name
          WareHouse.stock_num += 1
      def __del__(self):
          WareHouse.stock_num -= 1

  user1 = WareHouse('capt')
  user2 = WareHouse('thor')
  user3 = WareHouse('loki')

  print(user1.__dict__)     # stock_num 호출 안됨
  print(user2.__dict__)
  print(user3.__dict__)

  print(WareHouse.__dict__) # stock_num 호출 됨, 클래스 네임스페이스, 클래스 변수는 공유된다.

  print(user1.name)
  print(user2.name)
  print(user3.name)

  print(user1.stock_num)     # 접근 가능, 자신의 네임스페이스에 없다면 클래스 네임스페이스에서 변수를 찾고, 없으면 에러를 뱉는다.
  print(user2.stock_num)     # 접근 가능, 자신의 네임스페이스에 없다면 클래스 네임스페이스에서 변수를 찾고, 없으면 에러를 뱉는다.
  print(user3.stock_num)     # 접근 가능, 자신의 네임스페이스에 없다면 클래스 네임스페이스에서 변수를 찾고, 없으면 에러를 뱉는다.

  del user1     # 메모리에서 인스턴스를 제거

  print(user2.stock_num)
  print(user3.stock_num)
  ```

- 다중 상속
  ```py
  # 상속 : 슈퍼클래스(부모) 및 서브클래스(자식) -> 모든 속성, 메소드 사용 가능
  # 코드를 재사용하고, 중복되는 코드를 최소화한다.

  # 자동차 -> 속성(브랜드, 바퀴, 색상, 기능, 시리즈) : 부모
  class Car:
      """Parent Class"""
      def __init__(self, tp, color):
          self.type = tuple
          self.color = color

      def show(self):
          return 'Car Class "Show Method!"'

  class BmwCar(Car): # 상속
      """Child Class"""
      def __init__(self, car_name, tp, color):
          super().__init__(tp, color)   # 부모의 init 메소드를 호출한다.
          self.car_name = car_name

      def show_model(self) -> None:
          return "Your Car : %s" % self.car_name

  class BenzCar(Car): # 상속
      """Child Class"""
      def __init__(self, car_name, tp, color):
          super().__init__(tp, color)   # 부모의 init 메소드를 호출한다.
          self.car_name = car_name

      def show_model(self) -> None:
          return "Your Car : %s" % self.car_name

      def show(self):   # 부모에게도 있는 메소드이지만 동일하게 선언
          print(super().show())    # 부모 메소드도 호출
          return 'Car Info : %s %s %s' % (self.car_name, self.type, self.color)


  model1 = BmwCar('520d', 'sedan', 'red')

  print(model1.color)           # super
  print(model1.type)            # super
  print(model1.car_name)        # child
  print(model1.show())          # 부모의 메소드 호출
  print(model1.show_model())    # 자식의 메소드 호출
  print(model1.__dict__)        # 부모, 자식 인스턴스 출력

  # Method Overriding(오버라이딩)
  model2 = BenzCar('220d', 'suv', 'black')
  print(model2.show())  # 부모에 있는 것을 동일한 이름으로 자식에서 기능을 개선하거나 새로 정의한다.

  # Parent Method Call
  model2 = BenzCar('350s', 'sedan', 'black')
  print(model3.show())

  # super라는 예약어를 통해 부모 클래스에 접근이 가능하다.

  # Inheritance Info : a가 b를, b가 c를 상속... 이를 표현해주는 메소드
  print(BmwCar.mro())   # 상속관계를 출력
  print(BenzCar.mro())   # 상속관계를 출력


  # 다중 상속
  class ChildClass1(object):
      pass
  class ChildClass2(object):
      pass
  class ChildClass3(object):
      pass

  class A(ChildClass1, ChildClass2)
      pass
  class B(ChildClass2, ChildClass3)
      pass
  class C(ChildClass1, ChildClass3)
      pass

  class M(A, B, C):
      pass

  print(A.mro())
  print(M.mro())
  ```

## 10. 파이썬 모듈
```py
# 상대 경로
# .. : 상위
# . : 현재

# 모듈 만들기 : package/fibonacci.py
class Fibonacci:
    def __init__(self, title="fibonacci"):
        self.title = title
    
    def fib(n):
        while a < n:
            print(a, end=' ')
            a, b = b, a+b
        print()

    def fib2(n):
        result = []
        a, b = 0, 1
        while a < n:
            result.append(a)
            a, b = b, a+b
        return result

# 모듈 만들기 : package/prints.py
def prt1():
    print("Capt!")

def prt2():
    print("Thor!")

# 모듈 만들기 : calculations.py
def add(l, r):
    return l + r

def mul(l, r):
    return l * r

def div(l, r):
    return l / r

# 모듈 사용하기 1
from package.fibonacci import Fibonacci

Fibonacci.fib(300)

print("ex2 : ", Fibonacci.fib2(400))
print("ex2 : ", Fibonacci().title)  # 인스턴스 초기화 후 변수 접근

# 모듈 사용하기 2 : 비권장, 메모리가 많아서... 모듈의 모든 기능을 전부 가져옴
# 위와 동일하게 동작
from package.fibonacci import *

Fibonacci.fib(500)

print("ex2 : ", Fibonacci.fib2(600))
print("ex2 : ", Fibonacci().title)

# 모듈 사용하기 3
from package.fibonacci import Fibonacci as fb

fb.fib(1000)

print("ex2 : ", fb.fib2(600))
print("ex2 : ", fb().title)

# 모듈 사용하기 4
import package.calculations as c

print("ex4 : ", c.add(10, 100))
print("ex4 : ", c.mul(10, 100))
print("ex4 : ", c.div(10, 100))

# 모듈 사용하기 5 : 권장
import package.calculations import div as d
print("ex5 : ", int(d(100,10)))

# 모듈 사용하기 6
import package.prints as p
import builtins # 기본적으로 가져오므로 명시적 선언이 필요하지 않다.

p.prt1()
p.prt2()
print(dir(builtins))

# python2 버전에서는 __init__.py 가 존재하는데, 해당 디렉토리가 패키지임을 선언한다.
# python3 존재하지 않아도 패키지로 인식, 하위호환을 위해 생성하는걸 추천한다.

# 단위실행(독립적으로 파일 실행) : prints 파일에서 기록해야함, 해당 모듈의 맨 하위에 테스트코드를 작성하여 확인한다.
if __name__ == "__main__":
    prt1()
    prt2()
```

## 11. 파이썬 파일 입출력
```py
# 읽기 모드 : r, 쓰기 모드(덮어쓰기) : w, 추가 모드(파일 생성/추가) : a

# 파일 읽기1
f = open('./resources/review.txt', 'r')
content = f.read()
print(content)
print(dir(f))
# 한 번 사용한 리소스는 반드시 close 함수로 리소스 반환하여야 오류가 나지 않는다.
f.close()


# 파일 읽기2 : close 문 생략 가능
with open('./resources/review.txt', 'r') as f:
    c = f.read()
    print(c)
    print(list(c))
    print(iter(c))


# 파일 읽기3
with open('./resources/review.txt', 'r') as f:
    for c in f:
        print(c)            # 한 라인 단위로 출력
        print(c.strip())    # 양쪽 공백 제거, 줄바꿈도 없애줌


# 파일 읽기4 : 문제
with open('./resources/review.txt', 'r') as f:
    content = f.read()  # 커서가 끝까지 감 : 내용 있음
    print("> ", content)
    content = f.read()  # 커서가 끝에 있으므로 내용이 없음
    print("> ", content)


# 파일 읽기5 : 문제 해결
with open('./resources/review.txt', 'r') as f:
    line = f.readline()  # 한줄 씩 가져옴
    while line:
        print(line, end='#####')
        line = f.readline()


# 파일 읽기6
with open('./resources/review.txt', 'r') as f:
    contents = f.readlines()
    print(contents)  # 마지막의 escape 문자를 포함하여 리스트 형태로 가지고 있는다.
    for c in contents:
        print(c, end='*****')

# 파일 읽기 7
score = []
with open('./resources/score.txt', 'r') as f:
    for line in f:
        score.append(int(line))
    print(score)

print('Average : {:6.3}'.format(sum(score)/len(score)))


# 파일 쓰기1
with open('./resources/text1.txt', 'w') as f:
    f.write('Capt\n')

# 파일 쓰기2
with open('./resources/text1.txt', 'a') as f:
    f.write('Thor')

# 파일 쓰기3
from random import randint
with open('./resources/text2.txt', 'w') as f:
    for cnt in range(6):
        f.write(str(randint(1, 50)))
        f.write('\n')

# 파일 쓰기4
# writelines : 리스트 -> 파일로 저장
with open('./resources/text3.txt', 'w') as f:
    list = ['capt\n', 'thor\n', 'loki\n']
    f.writelines(list)

# 파일 쓰기5
with open('./resources/text4.txt', 'w') as f:
    print('Test Contents1 : ', file=f)
    print('Test Contents2 : ', file=f)
```

## 12. 파이썬 에러 및 예외 처리
```py
# 예외 종류
# 문법적으로 에러가 없으나 코드 실행(런타임) 프로세스에서 발생하는 예외 처리가 중요하다.
# linter : 코드 스타일 및 문법 체크

# 문법 에러 : SyntaxError
"""
print('Test)

if True
    pass

x => y
"""

# 참조변수 에러 : NameError
"""
a = 10
b = 20
print(c)
"""

# 0 나누기 에러 : ZeroDivisionError
"""
print(10 / 0)
"""

# 인덱스 범위 에러 : IndexError
"""
x = [10, 20, 30]
print(x[0]) # 정상
print(x[3]) # 예외 발생
"""

# 키 에러 : KeyError
"""
dict1 = {'name': 'Capt', 'age':100}
print(dict1['skill'])
"""

# 모듈, 클래스에 있는 잘못된 속성 사용 시 에러 : AttributeError
"""
import time
print(time.time())  # time 모듈에 time 함수는 없음
"""

# 참조 값이 없을 때 에러 : ValueError
"""
x = [1, 5, 8]
x.remove(10)
x.index(10)
"""

# 파일 참조 불가 에러 : FileNotFoundError
"""
f = open('존재하지않는텍스트.txt', 'r')
"""

# 타입 에러 : TypeError
"""
x = [1, 2]
y = (1, 2)

print(x + y)
"""

# 항상 에외가 발생하지 않을 것으로 가정하고 개발
# 그 후 런타임이나 예외 발생 시 예외를 처리할 것(EAFP 코딩 스타일)

# 예외 처리
# try : 에럭가 발생할 가능성이 있는 코드 실행
# except: 에러명 * n
# else : 에러가 발생하지 않았을 경우 실행
# finally : 무조건 실행

# 1
name = ['capt', 'thor', 'loki']

try:
    z = 'capt'
    x = name.index(z)
    print('{} Found it!'.format(z, x+1))
except ValueError:
    print('Not found it, Value not exists')
except:
    print("모든 에러 발생")
else:
    print('no excuted Exception')


# 2
try:
    z = 'capt'
    x = name.index(z)
    print('{} Found it!'.format(z, x+1))
except ValueError:
    print('Not found it, Value not exists')
except: # except Exception: 과 동일
    print("모든 에러 발생")
else:
    print('no excuted Exception')
finally:
    print('finally...')

# 3 : 예외처리는 하지 않으나 무조건 수행되는 코딩 패턴
try:
    print("test")
finally:
    print("ok!")


# 4
try:
    z = 'capt'
    x = name.index(z)
    print('{} Found it!'.format(z, x+1))
except ValueError:
    print('Not found it, Value not exists')
except IndexError as e:
    print("에러 발생", e)


# 5 : 예외발생(raise) 키워드로 예외 직접 발생
try:
    a = 'capt'
    if a == 'capt':
        print("확인")
    else:
        raise ValueError
except ValueError:
    print("예상치 못한 문제 발생")
except Exception as f:
    print(f)
else:
    print('성공')
```

## 13. 파이썬 외부 파일 처리
```py
# CSV : MIME = text/csv
import csv
with open('./resources/sample1.csv', 'r') as f:
    # ======================================================== 1 라인별 반환
    # reader = csv.reader(f)

    # # 라인 스킵, 지금은 헤더 다음 행부터 출력되게 만듦
    # next(reader)

    # # reader에 대한 검증
    # print(reader)
    # print(type(reader))
    # print(dir(reader))

    # for c in reader:
    #     print(c)

    # ======================================================== 2 구분자로 리스트 반환
    # reader = csv.reader(f, delimiter='|')
    # for c in reader:
    #     print(c)

    # ======================================================== 3 딕셔너리 형태로 변환
    reader = csv.DictReader(f)

    # 라인 스킵, 지금은 헤더 다음 행부터 출력되게 만듦
    next(reader)

    for c in reader:
        for k, y in c.items():
            print(k, y)
        print('====================================')

# 4 원소를 줄별로 작성하기
w = [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12], [13, 14, 15], [16, 17, 18]]

# with open('./resources/sample3.csv', 'w') as f:           # 개행문자 처리(줄바꿈 있음)
with open('./resources/sample3.csv', 'w', newline='') as f: # 개행문자 미처리(줄바꿈 없음)
    wt = csv.writer(f)

    for v in w:
        wt.writerow(v)

# 5 줄별이 아니라 한 번에 쓰기
with open('./resources/sample4.csv', 'w', newline='') as f: # 개행문자 미처리(줄바꿈 없음)
    wt = csv.writer(f)
    wt.writerows(w)


# XSL, XLSX
# openpyxl, xlsxwriter, xlrd, xlwt, xlutils, pandas
# pandas(openpyxl, xlrd) : 열과 행의 데이터셋, 프레임셋을 만들어서 정확하게 통계를 추출할 수 있다. numpy라는 라이브러리를 쓸 수 있다.
# pip install xlrd
# pip install openpyxl
# pip install pandas
# 의존관계에 의해 패키지가 설치된다.
import pandas as pd

# sheetname='시트명', 또는 숫자, header=숫자, skiprow=숫자
xlsx = pd.read_excel('./resources/sample.xlsx')

# 상위 데이터 확인
print(xlsx.head())  # 기본적으로 처음부터 5번째까지 값을 가져온다.

# 데이터 확인
print(xlsx.tail())  # 기본적으로 5번째부터 끝까지 값을 가져온다.

# 데이터 확인
print(xlsx.shape) # 행, 열

# 엑셀 or CSV 다시 쓰기
xlsx.to_excel('./resources/result.xlsx', index=False)   # 열에다가 인덱스를 붙여줌, False는 생략
xlsx.to_csv('./resources/result.csv', index=False)
```

## 14. 파이썬 데이터베이스 연동
```py
# 테이블 생성 및 삽입
import sqlite3
import datetime

# 삽입 날짜 생성
now = datetime.datetime.now()   # 현재시간
print('now : ', now)

now_date_time = now.strftime('%Y-%m-%d %H:%M:%S')
print('now date time : ', now_date_time)

# sqlite3
print('sqlite3.version : ', sqlite3.version)
print('sqlite3.sqliite : ', sqlite3.sqlite_version)

# DB 생성 및 Auto Commit(Rollback) 설정   : 쿼리를 실행할 때마다 데이터베이스에 반영하겠다는 뜻
conn = sqlite3.connect('C:/python_basic/resources/database.db', isolation_level=None)    # Auto Commit : True, Default는 False

# Cursor : 커서가 이동하면서 데이터를 반환한다.
c = conn.cursor()
print('Cursor Type : ', type(c))

# 테이블 삭제
c.execute(
    """
    DROP TABLE IF EXISTS users
    """)

# 테이블 생성(Data Type : TEXT, NUMERIC, INTEGER, REAL, BLOB)
c.execute(
    """
    CREATE TABLE IF NOT EXISTS users(
        id INTEGER PRIMARY KEY,
        username TEXT,
        email TEXT,
        phone TEXT,
        site TEXT,
        regdate TEXT
    )
    """)

# 데이터 삽입 : ?를 통해 파라미터를 넣는다.
c.execute(
    """
    INSERT INTO users VALUES(
        1, 'capt', 'capt@mail.com', '999-9999-9999', 'none', ?
    )
    """,
    (now_date_time,)
)

c.execute(
    """
    INSERT INTO users(
        id, username, email, phone, site, regdate
    ) VALUES (
        ?,?,?,?,?,?
    )
    """,
    (2, 'thor', 'thor@mail.com', '777-7777-7777', 'avengers', now_date_time)
)

# 데이터 삽입 : 대용량(튜플, 리스트)
user_list = (
    (3, 'loki1', 'loki@mail.com', '123', 's', now_date_time),
    (4, 'loki2', 'loki@mail.com', '456', 'b', now_date_time),
    (5, 'loki3', 'loki@mail.com', '789', 'c', now_date_time),
)

c.executemany(
    """
    INSERT INTO users(
        id, username, email, phone, site, regdate
    ) VALUES (
        ?,?,?,?,?,?
    )
    """,
    user_list
)

# 테이블 데이터 삭제
# c.execute("DELETE FROM users")
# print("users db deleted : ", c.execute("DELETE FROM users").rowcount)   # 삭제한 행 반환

# 데이터베이스 커밋 & 롤백 : isolation_level = None 이라면 자동 반영(auto commit)
# conn.commit()
# conn.rollback()

# 리소스를 사용했다면 닫아야 한다.
conn.close()
```

## 15. 파이썬 테이블 조회
```py
import sqlite3

# DB 파일 조회 : 없으면 생성
conn = sqlite3.connect('C:/python_basic/resources/database.db',
                       isolation_level=None)    # Auto Commit : True, Default는 False

# 커서 바인딩
c = conn.cursor()

# 데이터 조회(전체)
c.execute("SELECT * FROM users")

# 커서 위치 변경, 1개 로우 선택
print('One : ', c.fetchone())

# 지정 로우 선택
print('Three : ', c.fetchmany(size=3))

# 전체 로우 선택
print('All : ', c.fetchall())
# print('All : ', c.fetchall())   # 실행 해봤자 데이터 없음

# 순회1
rows = c.fetchall()  # 데이터베이스에 대한 위치 정보가 있음
for row in rows:
    print(row)

# 순회2
for row in c.execute("SELECT * FROM users ORDER BY id desc"):
    print(row)

# WHERE Retrieve1
param1 = (3,)
c.execute(
    """
    SELECT * FROM users WHERE id=?
    """,
    param1
)
print(c.fetchone())

# WHERE Retrieve2
param2 = 4
c.execute(
    """
    SELECT * FROM users WHERE id=%s
    """
    % param2
)
print(c.fetchone())

# WHERE Retrieve3
c.execute(
    """
    SELECT * FROM users WHERE id=:Id
    """,
    {"Id": 5}
)
print(c.fetchone())

# WHERE Retrieve4
param4 = (3, 5)
c.execute(
    """
    SELECT * FROM users WHERE id IN (?,?)
    """,
    param4
)
print(c.fetchall())

# WHERE Retrieve5
c.execute(
    """
    SELECT * FROM users WHERE id IN ('%d', '%d')
    """
    % (3, 4)
)
print(c.fetchall())

# WHERE Retrieve6
c.execute(
    """
    SELECT * FROM users WHERE id=:id1 OR id=:id2
    """,
    {"id1": 2, "id2": 5}
)
print(c.fetchall())


# Dump 출력 : 데이터베이스를 백업하고 재구성할 때 사용
with conn:
    with open('C:/python_basic/resources/dump.sql', 'w') as f:
        for line in conn.iterdump():
            f.write('%s\n' % line)
        print('Dump Complete')
        # f.close(), conn.close() 전부 호출됨
```

## 16. 파이썬 테이블 수정
```py
import sqlite3

# DB 파일 조회 : 없으면 생성
conn = sqlite3.connect('C:/python_basic/resources/database.db',
                       isolation_level=None)    # Auto Commit : True, Default는 False

# 커서 바인딩
c = conn.cursor()

# 데이터 수정1
c.execute(
    """
    UPDATE users SET username = ? WHERE id = ?
    """,
    ('blackwidow', 2)
)

# 데이터 수정2
c.execute(
    """
    UPDATE users SET username = :name WHERE id = :id
    """,
    {'name':'hawkeye', 'id':3}
)

# 데이터 수정3
c.execute(
    """
    UPDATE users SET username = '%s' WHERE id = '%d'
    """
    % ('superman', 1)
)

# 데이터 확인
for user in c.execute("SELECT * FROM users"):
    print(user)


# 데이터 행 삭제1
c.execute("DELETE FROM users WHERE id = ?", (2,))

# 데이터 행 삭제2
c.execute("DELETE FROM users WHERE id = :id", {"id":1})

# 데이터 행 삭제3
c.execute("DELETE FROM users WHERE id = '%s'" % 4)

# 데이터 확인
for user in c.execute("SELECT * FROM users"):
    print(user)

# 테이블 전체 데이터 행 삭제
print("users db deleted : ", c.execute("DELETE FROM users").rowcount, " ROWS")   # 삭제한 행 반환

conn.close()
```

## task runner 설치

- vscode의 설정파일 : `tasks.json`
  ```json
  {
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the documentation about the tasks.json format
    "version": "2.0.0",
    "tasks": [
      {
        "label": "Project Label",
        "type": "shell",
        "command": "python",
        "args": ["${file}"],
        "presentation": {
          "reveal": "always",
          "panel": "new"
        },
        "options": {
          "env": {
            "PYTHONIOENCODING": "UTF-8"
          }
        },
        "group": {
          "kind": "build",
          "isDefault": true
        }
      }
    ]
  }
  ```
