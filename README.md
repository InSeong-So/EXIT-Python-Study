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
