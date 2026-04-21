# 📚 파이썬 2학년 1학기 중간고사 총정리

## ✅ 리스트, 튜플, 딕셔너리 용어정리 및 작성방법

### 리스트(List)
- 여러 값을 순서 있게 저장
- 수정 가능
- 가장 많이 쓰는 자료형
```
[작성 방법]

a = [1, 2, 3]
b = ["apple", "banana", "cherry"]
c = [1, "hello", 3.14] # 여러 타입 섞기 가능
```

- 특징
  - 인덱싱 가능 : a[0] → 1
  - 값 변경 가능
  ```
  a[0] = 100
  ```
  - 추가 / 삭제 가능
  ```
  a.append(4)
  a.remove(2)
  ```

### 튜플(Tuple)
- 리스트와 거의 같지만
- 수정 불가능
```
[작성 방법]

a = (1, 2, 3)
b = ("apple", "banana")
c = (1, ) # 요소 1개일 때는 반드시 쉼표!
```

- 특징
  - 값 변경 ❌
  ```
  a[0] = 10 # 오류
  ```
  - 읽기 전용 데이터에 사용
  - 속도가 리스트보다 약간 빠름

### 딕셔너리(Dictionary)
- 키(key):값(value) 형태로 저장
- 순서보다는 키로 접근
```
[작성 방법]

a = {"name":"jian", "age":25}
```

- 특징
  - 값 접근
  ```
  a["name"] # "jian"
  ```
  - 값 수정
  ```
  a["age"] = 26
  ```
  - 추가
  ```
  a["height"] = 180
  ```
  - 키는 중복 ❌, 값은 중복 🅾️
 
- 핵심 차이 한방 정리
- 
| 구분 | 리스트 | 튜플 | 딕셔너리 |
|------|--------|-----|-----------|
| 기호 | [] | () | {} |
| 수정 | 가능 | 불가능 | 가능 |
| 구조 | 순서 있음 | 순서 있음 | key:value | 
| 접근 | 인덱스 | 인덱스 | 키 |
| 예시 | 데이터 모음 | 고정 데이터 | 데이터 매핑 |
- 언제 쓰는지?
  - 리스트 → 값 계속 바뀌고 추가될 때
  - 튜플 → 절대 바뀌면 안되는 값 (좌표, 설정값)
  - 딕셔너리 → {이름:값} 처럼 짝지어진 데이터

## ✅ 인덱싱(Indexing), 슬라이싱(Slicing)

### 인덱싱(Indexing)
- 하나의 요소를 딱 집어서 가져오는 것
```
[기본 문법]

a = [10, 20, 30, 40]

print(a[0]) # 10
print(a[2]) # 30
```

- 특징
  - 0부터 시작
  ```
  a[0] → 첫 번째
  a[1] → 두 번째
  ```
  - 음수 인덱스(뒤에서부터)
  ```
  a[-1] → 마지막 # 40
  a[-2] → 뒤에서 두 번째 # 30
  ```

### 슬라이싱(Slicing)
- 여러 개를 범위로 잘라서 가져오기
```
[기본 문법]

a = [10, 20, 30, 40, 50]

print(a[1:4]) # [20, 30, 40]

[의미]

[시작:끝]
→ 시작 포함, 끝 제외
```

- 다양한 슬라이싱
  - 처음부터 끝까지
  ```
  a[:] # 전체 복사
  ```
  - 앞부분만
  ```
  a[:3] # [10, 20, 30]
  ```
  - 뒷부분만
  ```
  a[2:] # [30, 40, 50]
  ```
  - 2칸씩
  ```
  a[::2] # [10, 30, 50]
  ```
  - 역순
  ```
  a[::-1] # [50, 40, 30, 20, 10]
  ```

- 인덱싱, 슬라이싱 핵심 차이
- 
| 구분 | 인덱싱 | 슬라이싱 |
|------|--------|----------|
| 의미 | 하나만 | 여러 개 |
| 결과 | 값 1개 | 리스트/문자열 |
| 형태 | a[2] | a[1:4] |

- 문자열에도 똑같이 적용됨
```
s = "python"

print(s[0]) # "p"
print(s[1:4]) # "yth"
```
- 자주 하는 실수
```
a[1:4] # 1 ~ 4 까지 ❌
       # 1 ~ 3 까지만 🅾️
```

## ✅ append, insert, extend, remove, del 용어 정리

### append()
- 맨 뒤에 요소 1개 추가
```
[작성 방법]

a = [1, 2, 3]
a.append(4)

print(a) # [1, 2, 3, 4]
```

- 특징
```
a.append([5, 6])

# 결과 → [1, 2, 3, 4, [5, 6]]
→ 리스트를 넣으면 "통째로 하나" 들어감
```

### insert()
- 원하는 위치에 요소 삽입
```
[작성 방법]

a = [1, 2, 3]
a.insert(1, 100)

print(a) # [1, 100, 2, 3]
```
- insert(위치, 값)

### extend()
- 리스트를 풀어서 추가
```
[작성 방법]

a = [1, 2, 3]
a.extend([4, 5])

print(a) # [1, 2, 3, 4, 5]
```
- append()와 차이
```
a.append([4, 5]) # [1, 2, 3, [4, 5]]
a.extend([4, 5]) # [1, 2, 3, 4, 5]
```

### remove()
- 값으로 삭제(첫 번째 값만 삭제)
```
[작성 방법]

a = [1, 2, 3, 2]
a.remove(2)

print(a) # [1, 3, 2]

→ 같은 값 여러 개면 첫 번째만 삭제
→ 값 없으면 에러 발생
```

### del
- 인덱스로 삭제
```
[작성 방법]

a = [1, 2, 3, 4]

del a[1]
print(a) # [1, 3, 4]
```
- 범위 삭제도 가능
```
del a[1:3]
```

- 핵심 차이 정리
- 
| 함수 | 기준 | 특징 |
|------|------|------|
| append | 값 | 맨 뒤에 1개 추가 |
| insert | 위치 | 원하는 위치에 추가 | 
| extend | 리스트 | 여러 개 풀어서 추가 |
| remove | 값 | 첫 번째 값 삭제 |
| del | 인덱스 | 위치로 삭제 |

## ✅ 리스트 덧셈, 곱셈, in 연산

### 리스트 덧셈(+)
- 리스트끼리 이어붙이기
```
[작성 방법]

a = [1, 2]
b = [3, 4]

c = a + b
print(c) # [1, 2, 3, 4]
```

- 특징
  - 원본은 안 바뀜
  ```
  print(a) # [1, 2]
  ```

### 리스트 곱셈(*)
- 리스트 반복 생성
```
[작성 방법]

a = [1, 2]

b = a * 3
print(b) # [1, 2, 1, 2, 1, 2]
```

- 특징
  - 같은 패턴 반복
  - 문자열도 동일하게 가능
  ```
  print("hi" * 3) # hihihi
  ```

### in 연산자
- 값이 리스트 안에 있는지 확인
```
[작성 방법]

a = [1, 2, 3]

print(2 in a) # True
print(5 in a) # False
```
- not in
```
print(5 not in a) # True
```

- 핵심 정리
- 
| 연산 | 의미 | 결과 |
|------|------|------|
| + | 이어붙이기 | 새 리스트 |
| * | 반복 | 패턴 반복 |
| in | 포함 여부 | True/False |

## ✅ 연산자 및 변수명

### 연산자
- 산술 연산자
```
a = 10
b = 3

print(a + b) # 13
print(a - b) # 7
print(a * b) # 30
print(a / b) # 3.333...
print(a // b) # 3 (몫)
print(a % b) # 1 (나머지)
print(a ** b) # 1000 (거듭제곱)
```
- 비교 연산자(결과 : True/False)
```
print(10 > 3) # True
print(10 == 3) # False
print(10 != 3) # True
```
- 논리 연산자
```
print(True and False) # False
print(True or False) # True
print(not True) # False
```
- 할당 연산자
```
a = 5
a += 3 # a = a + 3
a *= 2 # a = a * 2
```
- 멤버 연산자
```
a = [1, 2, 3]

print(2 in a) # True
print(5 not in a) # True
```

### 변수명
- 변수랑?
  - 값을 저장하는 이름
  ```
  x = 10
  name = "jian"
  ```
- 변수명 규칙
```
[가능 🅾️]

age = 20
name = "jian"
score1 = 100
```
```
[불가능 ❌]

1name = "x" # 숫자로 시작 ❌
my-name = 10 # - 사용 ❌
ckass = 10 # 예약어 ❌
```
  - 숫자로 시작 ❌
  - 공백 ❌
  - 특수문자 ❌ (_만 가능)
  - 예약어 사용 금지

## ✅ 조건문(코딩 작성 및 결과 예측)

### 기본 조건문(if)
```
[작성 방법]

x = 10

if x > 5:
     print("크다")
```

### if-else
```
[작성 방법]

x = 3

if x > 5:
     print("크다")
else:
     print("작다")
```

### if-elif-else
```
[작성 방법]

score = 85

if score >= 90:
     print("A")
elif score >= 80:
     print("B")
else:
     print("C")
```

### 조건문 결과 예측
- 예제 1
```
x = 7

if x % 2 == 0:
     print("짝수")
else:
     print("홀수")

- 결과
홀수
```
- 예제 2
```
x = 10

if x > 5:
    if x < 15:
        print("YES")

- 결과
YES
```
- 예제 3
```
x = 5

if x > 5:
    print("A")
elif x >= 5:
    print("B")
else:
    print("C")

- 결과
B
```
- 예제 4(논리 연산)
```
x = 8

if x > 5 and x < 10:
    print("OK")

- 결과
OK
```
- 예제 5
```
x = 0

if x:
    print("True")
else:
    print("False")

- 결과
False # 0은 False 취급
```
- 예제 6
```
x = 6

if x % 3 == 0:
    print("A")
elif x % 2 == 0:
    print("B")
else:
    print("C")

- 결과
A # 첫 번째 조건이 맞으면 바로 끝
```

## ✅ 반복문(코딩 수정 및 작성)

### for문
- 횟수 정해짐
```
[작성 방법]

for i in range(5):
    print(i)
```

### while문
- 조건 기반
```
[작서 방법]

i = 0

while i < 5:
    print(i)
    i += 1
```

### 반복문 작성
- 1 ~ 10합 구하기
```
sum = 0

for i in range(1, 11):
    sum += i

print(sum)

- 결과
55
```
- 짝수만 출력
```
for i in range(1, 11):
    if i % 2 == 0:
        print(i)

- 결과
2 4 6 8 10
```
- 구구단 (2단)
```
for i in range(1, 10):
    print(2 * i)

- 결과
2 4 6 8 10 12 14 16 18
```

### 반복문 코드 수정
- 문제 코드 1(무한루프)
```
i = 0

while i < 5:
    print(i)
```
```
[수정 ✅]

i = 0

while i < 5:
    print(i)
    i += 1
```
- 문제 코드 2(범위 오류)
```
for i in range(1, 10):
    print(i)
```
```
[수정 ✅]

for i in range(1, 11):
    print(i)
```
- 문제 코드3(합계 오류)
```
sum = 0

for i in range(1, 6):
    sum = i

print(sum)
```
```
[수정 ✅]

sum = 0

for i in range(1, 6):
    sum += i

print(sum)
```

### 반복문 + 조건문 🔥
- 3의 배수만 출력
```
for i in range(1, 10):
    if i % 3 == 0:
        print(i)
```
- 입력값까지 합
```
n = 5
sum = 0

for i in range(1, n+1):
    sum += i

print(sum)
```

### break / continue
- break : 0 ~ 4까지만 출력
```
for i in range(10):
    if i == 5:
        break
print(i)
```
- continue : 홀수만 출력
```
for i in range(10):
    if i % 2 == 0:
        continue
print(i)
```

## ✅ 양식문자 및 f-string 작성 방법

### 양식문자
- 문자열 안에 값을 형식 맞춰 넣기
```
[작성 방법]
# % 방식(옛날 방식)

name = "jian"
age = 20

print("이름 : %s, 나이 : %d" % (name, age))

- 결과
이름 : jian, 나이 : 20
```
- 주요 양식문자
```
%s # 문자열
%d # 정수
%f # 실수
```
- 소수점 자리수
```
pi = 3.141592

print("%.2f" % pi)

- 결과
3.14
```
- 정렬(폭 지정)
```
print("%10s" % "hi") # 오른쪽 정렬
print("%-10s" % "hi") # 왼쪽 정렬
```

### f-string
- 문자열 앞에 f 붙이고 {} 안에 변수/식 넣기
```
[작성 방법]

name = "jian"
age = 20

print(f"이름 : {name}, 나이 : {age}")

- 결과
이름 : jian, 나이 : 20
```
- 계산도 가능
```
a = 10
b = 3

print(f"합 : {a + b}")

- 결과
합 : 13
```
- 소수점
```
pi = 3.141592

print(f"{pi:.2f}")

- 결과
3.14
```
- 정렬
```
print(f"{'hi':>10}") # 오른쪽
print(f"{'hi':<10}") # 왼쪽
```

### 결과 예측
- 예제 1
```
name = "kim"
score = 95

print(f"{name}의 점수는 {score}점")

- 결과
kim의 점수는 95점
```
- 예제 2
```
print(f"{3.141592:.1f}")

- 결과
3.1
```

## ✅ 함수(코딩 수정 및 작성)

### 함수 기본 구조
```
[작성 방법]

def add(a, b):
    return a + b

print(add(3, 5)) # 8
```

### 함수 작성
- 두 수 더하기
```
def add(a, b):
    return a + b
```
- 짝수 판별 함수
```
def even(n):
    return n % 2 == 0

print(even(4)) # True
```
- 구구단 함수
```
def gugudan(n):
    for i in range(1, 10):
        print(n * i)

gugudan(2)
```

### 함수 코드 작성 🔥
- 문제 1 ❌(return 없음)
```
def add(a, b):
    a + b

print(add(3, 5))
```
```
[수정 ✅]

def add(a, b):
    return a + b
```
- 문제 2 ❌(들여쓰기 오류)
```
def test():
print("hello")
```
```
[수정 ✅]

def test():
    print("hello")
```
- 문제 3 ❌(매개변수 오류)
```
def square():
    return x * x

print(square(3))
```
```
[수정 ✅]

def square(x):
    return x * x

print(square(3))
```
- 문제 4 ❌(출력 vs 반환 혼동)
```
def add(a, b):
    print(a + b)

result = add(3, 5)
print(result)

- 결과
8
None
```
```
[수정 ✅]

def add(a, b):
    return a + b
```

### return 핵심 이해
- return 있는 경우
```
def test():
    return 10

x = test()
print(x) # 10
```
- return 없는 경우
```
def test():
    print("hello")

x = test()
print(x) # None
```

### 함수 + 조건문
- 큰 수 반환
```
def max_num(a, b):
    if a > b:
        return a
    else:
        return b
```

### 함수 + 반복문
- 1 ~ n 합
```
def total(n):
    sum = 0
    for i in range(1, n+1):
        sum += i
    return sum
```

### 실전 문제
- 문제 1(결과 예측)
```
def f(x):
    return x * 2

print(f(3))

- 결과
6
```
- 문제 2(틀린 코드 수정)
```
def add(a, b)
    return a + b

[수정 ✅]

def add(a, b):
    return a + b
```
- 문제 3(작성) : 숫자를 입력받아 3의 배수면 True 반환하는 함수 작성
```
def func(x):
    return x % 3 == 0

print(func(3))
print(func(4))

- 결과
True
False
```

## ✅ Numpy 라이브러리(리스트와 넘파이 차이점)

### Numpy 라이브러리
- 파이썬에서 수치 계산(배열 연산)을 빠르게 하기 위한 라이브러리
- 핵심 객체 : 배열(array)
```
[작성 방법]

import numpy as np

a = np.array([1, 2, 3])
```

### 리스트 vs Numpy 핵심 차이
- 1. 연산 방식 차이 🔥
```
[리스트]

a = [1, 2, 3]
print(a * 2) # [1, 2, 3, 1, 2, 3]
→ 반복됨(계산 아님)
[Numpy]

import numpy as np

a = np.array([1, 2, 3])
print(a * 2) # [2, 4, 6]
→ 각 요소 계산됨(벡터 연산)
```
- 2. 속도 차이
  - 리스트 → 느림
  - Numpy → 빠름
  - 대량 데이터에서 차이 큼
- 3. 자료형
```
[리스트]

a = [1, "hello", 3.14]
→ 서로 다른 타입 가능

[Numpy]

a = np.array([1, 2, 3])
→ 같은 타입만(자동 변환됨)
```
- 4. 차원 구조
```
[리스트]

a = [[1, 2], [3, 4]]
→ 단순 중첩 리스트

[Numpy]

a = np.array([[1, 2], [3, 4]])
→ 진짜 행렬처럼 연산 가능
```
- 5. 계산 편의성
```
[리스트]

a = [1, 2, 3]
b = [4, 5, 6]

result = [a[i] + b[i] for i in range(3)]
→ 직접 반복문 써야됨

[Numpy]

a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(a + b) # [5, 7, 9]
→ 그냥 더하면 끝
```

- 핵심 비교
- 
| 구분 | 리스트 | Numpy |
|------|--------|-------|
| 연산 | 반복 | 요소별 계산 |
| 속도 | 느림 | 빠름 |
| 자료형 | 혼합 가능 | 동일 타입 |
| 구조 | 단순 | 다차원 배열 |
| 사용 | 일반 데이터 | 수치 계산 |
```
[리스트]

[1, 2, 3] * 2 → [1, 2, 3, 1, 2, 3]

[Numpy]

[1, 2, 3] * 2 → [2, 4, 6]
```

## ✅ Numpy 배열속성(dtype, shape, ndim, flat, T, size, nbytes)
```
[설명 기본 배열]

import numpy as np

a = np.array([[1, 2, 3],
              [4, 5, 6]])
```

### dtype(데이터 타입)
- 배열 안 데이터의 자료형
```
[작성 방법]

print(a.dtype)

- 결과
int32 또는 int64 (환경에 따라 다름)
```

### shape(형태)
- 배열의 구조(행, 열)
```
[작성 방법]

print(a.shape)

- 결과
(2, 3) # 2행 3열
```

### ndim(차원)
- 배열의 차원 수
```
[작성 방법]

print(a.ndim)

- 결과
2 # 2차원
```

### size(전체 원소 개수)
- 총 데이터 개수
```
[작성 방법]

print(a.size)

- 결과
6
```

### nbytes(메모리 크기)
- 배열이 사용하는 총 바이트
```
[작성 방법]

print(a.nbytes)

- 결과
24 # (예시) int32 → 4Byte X 6개
```

### T(전치 행렬)
- 행과 열 바꾸기
```
[작성 방법]

print(a.T)

- 결과
[[1 4]
 [2 5]
 [3 6]]
```

### transpose(전치 행렬) = T
- 행과 열 바꾸기
```
[작성 방법]

print(a.transpose)

- 결과
[[1 4]
 [2 5]
 [3 6]]
```

### flat(1차원으로 펼치기)
- 배열을 1차원으로 바꿈
```
[작성 방법]

print(list(a.flat))

- 결과
[1, 2, 3, 4, 5, 6]
```

### flatten()
- 다차원 배열 → 1차원 배열로 복사해서 변환
```
[작성 방법]

import numpy as np

a = np.array([[1, 2, 3],
              [4, 5, 6]])
b = a.flatten()

print(b)
```

- 특징
  - 1. "복사본" 생성
  ```
  b[0] = 100

  print(a) # 원본 그대로
  print(b) # 변경됨

  - 결과
  [[1 2 3]
   [4 5 6]]

  [100 2 3 4 5 6]
  → 원본 영향 ❌
  ```
  - 2. 무조건 1차원으로 변환
    - 어떤 차원이든 → 한 줄 배열

## ✅ 배열의 구조 설정(reshape)

### reshape
- 배열의 데이터는 그대로 두고 "형태(shape)"만 바꾸는 것
```
[작성 방법]

import numpy as np

a = np.array([1, 2, 3, 4, 5, 6])

b = a.reshape(2, 3)
print(b)

- 결과
[[1 2 3]
 [4 5 6]]
```

### 핵심 규칙 🔥
- 총 개수 맞아야 함
```
a = np.array([1, 2, 3, 4, 5, 6])

a.reshape(2, 3) # 6개 → 가능
a.reshape(3, 2) # 6개 → 가능
a.reshape(4, 2) # 8개 필요 → 불가능 오류 ❌

→ size 동일해야 함
```

### 다양한 reshape
- (3, 2)
```
a.reshape(3, 2)

- 결과
[[1 2]
 [3 4]
 [5 6]]
```
- -1 사용 자동 계산 🔥
```
a.reshape(-1 ,3)

- 결과
[[1, 2, 3]
 [4, 5, 6]]

-1 → 자동으로 맞춰줘라는 뜻
```

### 2차원 → 1차원
```
a = np.array([[1, 2, 3], [4, 5, 6]])

b = a.reshape(6,)
print(b)

- 결과
[1 2 3 4 5 6]
```

### reshape vs flatten
- 
| 구분 | reshape | flatten |
|------|---------|---------|
| 형태 변경 | 🅾️ | 🅾️ |
| 차원 유지 | 원하는 형태 | 무조건 1차원 |
| 복사 | 경우에 따라 다름 | 항상 복사 |
```
reshape → "배열 모양 바꾸기"
flatten → "한 줄로 만들기"
```

### 시험 스타일 예제
```
a = np.arange(1, 7)
b = a.reshape(2, 3)
print(b)

- 결과
[[1 2 3]
 [4 5 6]]
```

## ✅ 1차원, 2차원, 3차원 배열생성

### 1차원 배열
- 한 줄로 나열된 배열(벡터)
```
[작성 방법]

import numpy as np

a = np.array([1, 2, 3, 4])
print(a)

- 결과
[1 2 3 4]
```

- 특징
```
print(a.shape) # (4,)
print(a.ndim) # 1
```

### 2차원 배열
- 행 + 열 구조
```
[작성 방법]

import numpy as np

a = np.array([[1, 2, 3],
              [4, 5, 6]])
print(a)

- 결과
[[1 2 3]
 [4 5 6]]
```

- 특징
```
print(a.shape) # (2, 3)
print(a.ndim) # 2
```

### 3차원 배열
- 면 + 행 + 열 구조
```
[작성 방법]

import numpy as np

a = np.array([[[1, 2], [3, 4]],
              [[5, 6], [7, 8]]])

print(a)

- 결과
[[[1 2]
  [3 4]]
 [[5 6]
  [7 8]]]
```

- 특징
```
print(a.shape) # (2, 2, 2)
print(a.ndim) # 3
```

- 핵심 비교
- 
| 구분 | 구조 | shape | ndim |
|------|------|-------|------|
| 1차원 | [1, 2, 3] | (3,) | 1 |
| 2차원 | [[1, 2], [3, 4]] | (2, 2) | 2 |
| 3차원 | [[[...]]] | (면, 행, 열) | 3 |

## ✅ 배열의 통합과 분할(행방향, 열방향)

### 배열의 통합(concatenate, vstack, hstack)
- 행 방향(세로, axis = 0)
```
import numpy as np

a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6]])

print(np.vstack((a, b)))

- 결과
[[1 2]
 [3 4]
 [5 6]]
```
- 열 방향(가로, axis = 1)
```
print(np.hstack((a, b.T)))

- 결과
[[1 2 5]
 [3 4 6]]
```

### 배열 분할(split)
- 행 분할
```
a = np.array([[1, 2], [3, 4], [5, 6]])

print(np.vsplit(a, 3))
→ 3개로 나눔
```
- 열 분할
```
a = np.array([[1, 2, 3, 4]])

print(np.hsplit(a, 2))
→ [array([[1, 2]]), array([[3, 4]])]
```

## ✅ 1차원, 2차원, 3차원 인덱싱 및 슬라이싱 작업

### 인덱싱 / 슬라이싱
- 1차원
```
a = np.array([10, 20, 30, 40])

print(a[1]) # 20
print(a[1:3]) # [20 30]
```
- 2차원
```
a = np.array([1, 2, 3],
             [4, 5, 6]])

print(a[0, 1]) # 2
print(a[:,1]) # [2 5]
print(a[0,:]) # [1 2 3]
```
- 3차원
```
a = np.array([[[1, 2], [3, 4]],
              [[5, 6], [7, 8]]])

print(a[0, 1, 1]) # 4
```

## ✅ 조건 필터 및 정렬(sort, argsort)

### 조건 필터 🔥
```
a = np.array([1, 2, 3, 4, 5, 6])

print(a[a % 2 == 0])

- 결과
[2 4 6]
```

### 정렬(sort, argsort)
- sort(값 정렬)
```
a = np.array([3, 1, 2])

print(np.sort(a))
→ [1 2 3]
```
- argsort(인덱스 반환)
```
print(np.argsort(a))
→ [1 2 0]

1이 제일 작음 → index 1
2 → index 2
3 → index 0
```

## ✅ 스칼라, 벡터, 행렬 용어 정리

### 스칼라 : 하나의 값
```
a = 5
```

### 벡터 : 1차원 배열
```
v = np.array([1, 2, 3])
```

### 행렬 : 2차원 배열
```
m = np.array([[1, 2],
              [3, 4]])
```

## ✅ 배열과 스칼라 연산

### 배열의 모든 요소에 동일하게 적용
```
import numpy as np

a = np.array([1, 2, 3])

print(a + 10) # [11 12 13]
print(a * 2) # [2 4 6]

- 특징
반복문 필요 없음
자동 계산됨(벡터 연산)
```

## ✅ 벡터의 내적(dot)

### 계산 : 같은 위치끼리 곱해서 더함
```
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

print(np.dot(a, b))

→ 계산 : 1x4 + 2x5 + 3x6 = 32
```

## ✅ 브로드캐스팅 🔥

### 브로드캐스팅?
- 크기가 다른 배열을 자동으로 맞춰서 계산

### 예제
- 예제 1(스칼라)
```
a = np.array([1, 2, 3])
print(a + 10)

→ [11 12 13]
```
- 예제 2(벡터 + 행렬)
```
a = np.array([[1, 2, 3],
              [4, 5, 6]])
b = np.array([10, 20, 30])

print(a + b)

→ [[11 22 33]
   [14 25 36]]
```

## ✅ arange / linspace

### arange
- 일정 간격으로 생성
```
np.arange(0, 10, 2)

→ [0 2 4 6 8]
```

### linspace
- 개수 기준으로 생성
```
np.linspace(0, 10, 5)

→ [0. 2.5 5. 7.5 10.]
```

##### ✍️작성자: 박지안
##### 🐧실습 환경: Anaconda - Jupyter
##### 🗓️ 작업일: 2026-04-21
