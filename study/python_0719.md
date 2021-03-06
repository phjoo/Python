# 07.19 강의 내용 정리



 ## 3장. 파이썬을 계산기처럼 이용 

> 1) 파이썬을 이용하는 이유?
>
> - 가독성 : 문법이 간결, 들여쓰기(4칸 권고) 
> - 확장성 : 풍부한 라이브러리 ex) numpy, math..등
> - 접착성 : c로 구현된 모듈을 쉽게 적용 가능
> - 유니코드 : 문자열은 모두 유니코드(한글도 많이 활용 가능)
> - 동적타이핑 : 동적언어, 인터프리터형 언어
>
> 
>
> 2) 파이썬 코딩 규칙
>
> - 들여쓰기 : 공백 4칸 
> - 한 줄은 최대 79자까지 작성 권장
> - 클래스 내의 메서드 정의는 1줄씩 띄어씀
> - 표현식,문장 : 공백 x
>   - 대괄호와 소괄호 안
>   - 쉼표,쌍점과 쌍반점 앞
> - #은 주석
>
> 
>
> 3) 프로그램어
>
> - 명령어 집합 ; 인터프리터 언어 
> - 순차적 명령어
>
> 
>
> 4) 파이썬 데이터 처리
>
> - 변수 및 자료형
> - 제어문(조건문, 반목문)
> - 입력과 출력
> - 함수
> - 객제와 클래스(객체지향언어)
> - 문자열, 텍스트 > 파일 read, write
> - 데이터 분석을 위한 패키지(numpy, pandas)
> - 시각화



### 1. 간단한 사칙연산

1. 사칙연산 : **정수와 실수** 연산이 가능

   - **더하기(+), 빼기(-), 곱하기(*), 나누기(/)** 기호 이용

   - 숫자와 연산자 사이의 **공백**은 무시하기 때문에 **상관 x**

   - **나눗셈** 연산은 **실수**로 처리 

     실수형 입력 -> 실수형 출력 / 정수형 입력 -> 정수형 출력

     - *ex) 10/2 = 5.0*

   - 정수 : **자연수와 자연수의 음수, 0**으로 이뤄진 수의 집합

   - 실수 : **유리수와 무리수**의 이뤄진 집합

   - 프로그램에서는 **소수점이 없으면 정수(int)**이고 **소수점이 있으면 실수(float)**

   - 연산 기호 2개 이상 : 일반적인 연산 규칙

     - **괄호 -> 지수 -> 곱셈과 나눗셈 -> 덧셈과 뺄셈**

   - 같은 순서의 연산 : 왼쪽에서 오른쪽 순서로 계산, 중복된 괄호는 안쪽 괄호부터

2. **`type()`** : 데이터 타입을 알려주는 함수

   ```python
   type(3)
   type(3.5)
   >int
    float
   ```

3. 거듭제곱 : 지수 연산자(******)를 사용하여 표현

   - 두 별표 사이에는 공백이 없어야 함
   - 정수뿐만 아니라 실수도 거듭제곱
   - 수학 라이브러리를 이용하여 거듭제곱, 거듭제곱근 외에 다양한 수학 함수 사용 가능

   ```python
   2**2
   4**(1/2)
   > 4
     2
   ```

4. 몫과 나머지 : **몫 연산자(/)와 나머지 연산자(%)** 를 이용하여 구할 수 있음

   ``` python
   13 // 5
   13 % 5
   > 2
     3
   ```

   | 연산자 기호 |   의미   |
   | :---------: | :------: |
   |      +      |  더하기  |
   |      -      |   빼기   |
   |      *      |  곱하기  |
   |      /      |  나누기  |
   |     **      | 거듭제곱 |
   |     //      |  나머지  |
   |      %      |    몫    |



### 2. 과학적 표기법

1. 과학적 표기법 : 아주 큰 수나 작은 수를 다뤄야 할 때

   - 10의 거듭제곱(10n) : **en**으로 입력 (단, n은 정수)

   - en 앞에는 **항상** 숫자가 있어야 함

   - 지수가 양수(+)/음수(-)에 따라 기호가 들어감

     ``` python
     3*10**8 = 3e8 #en으로 표현
     1e15 #지수가 양수
     2e-4 #지수가 음수
     ```

2. 진수표현과 변환

   - 10진법 외에 2진법(0,1), 8진법(0,1,2,3,4,5,6,7), 16진법(0,1,2,3,4,5,6,7,8,9,a,b,c,d,e,f)으로 숫자를 입출력/ 변환하는 방법을 제공

   - **0b(2진수), 0o(8진수), 0x(16진수)** : 각 진법을 입력하기 위해서는 숫자 앞에 기입

   - 10진수 -> 2/8/16진수로 입력하는 함수 : bin() , oct() , hex() 

     cf) 10진수 함수는 int("수", 진수)

   - 함수(bin,oct,hex)의 출력 결과는 숫자가 아닌 **문자열**이기 때문에 **산술 연산에 이용할 수 없음**

   - 따라서 **진수 변환**은 **연산이 모두 끝난 후**에 해야 함

     ```python
     17 #10진법
     0b10001 #2진법
     0o21 #8진법
     0x11 #16진법
     >17
     
     bin(17) #2진법으로 변환
     oct(17) #8진법으로 변환
     hex(17) #16진법으로 변환
     > '0b10001'
       '0o21'
       '0x11'
     
     0b10*0o10+0x10-10
     > 22
     bin(0b10*0o10+0x10-10)
     >'0b10110' #진수 변환시 문자열
     int("0b10110",2)
     >22
     ```

3. 논리 연산

   - 참(True) / 거짓(False) 이용해 연산하는 논리 연산(=불린 연산)

   - **bool** : 논리 연산을 위한 데이터 타입

   - 'true' 혹은 'false' 처럼 **따옴표 사용 불가능** -> **문자열** 데이터로 인식하게 됨

   - **True, False**만 가능(TRUE,FALSE/true,false 불가능)

   - **불 데이터**의 경우 **논리 연산만** 가능

     - **논리곱(and : &)** : 두 개의 불 데이터가 **모두 참일 때만 참, 나머지는 거짓**
     -  **논리합(or : |)**  : 두 개의 불 데이터 중 **하나라도 참이면 참, 둘 다 거짓이면 거짓**
     -  **논리 부정(not )** : 하나의 불 데이터가 **참이면 거짓, 거짓이면 참**

     ``` python
     print(True) #논리 연산
     print('True') #문자열
     
     type(True)
     > bool #논리 연산(=불린 연산)
     
     print(True and False)
     >False
     print(True or False)
     >True
     print(not True)
     >False
     ```

4. 비교연산과 혼합연산

   - 두 개의 숫자를 비교하는 비교 연산

   - 비교 연사자의 결과는 **불 데이터**

     |      비교 연산자      |    의미     | 활용 예 |         설명          |
     | :-------------------: | :---------: | :-----: | :-------------------: |
     | == (대입/치환 연산자) |    같다     | a == b  |     a는 b와 같다      |
     |          !=           |  같지 않다  | a != b  |   a는 b와 같지 않다   |
     |           <           |    작다     |  a < b  |    a는 b보다 작다     |
     |           >           |    크다     |  a > b  |    a는 b보다 크다     |
     |          <=           | 작거나 같다 | a <= b  | a는 b보다 작거나 같다 |
     |          >=           | 크거나 같다 | a >= b  | a는 b보다 크거나 같다 |

   - **비교 연산자**의 우선 순위가 논리 연산자의 **우선 순위보다 높음**

   - 괄호와 연산이 함께 있으면 **괄호의 우선 순위가 높음**

   - 괄호가 여러 겹 있을 때는 **가장 안쪽 괄호부터** 먼저 계산

     ``` python
     print(5==3)
     >False
     print(5!=3)
     >True
     print(5<3)
     >False
     print(5>3)
     >True
     print(5<=3)
     >False
     print(5>=3)
     >True
     
     print((3>0)or((-5>0)and(1>5)))
     >True
     print(((3>0)or(-5>0))and((4>8)or(3<0)))
     >False
     ```

     



