# 6장 입력과 출력

### 1. 입력과 출력

> - 코딩할 때 **실행한 결과를 화면이나 파일로 출력**할 때
> - **입력을 키보드로 받거나 파일에 있는 데이터를 읽어서 처리**해야 할 때
> -  파이썬으로 코드를 작성할 때 키보드와 화면으로 입출력하는 방법과 파일로 입출력하는 방법



###  2.화면 출력

- 작성한 코드의 결과를 확인하는 가장 기본적인 방법 : **결과를 화면으로 출력하는 것**
- `print()` : 원하는 내용을 화면으로 출력
  - 기본 출력 : 출력 형식을 지정하지 않는 형식
  - 지정 출력 : 다양한 형식으로 출력할 수 있는 형식

1. 기본 출력

- `print()` : 문자열과 숫자열을 출력
  - 문자열 여러 개를 연결해서 출력 시 **콤마(,)**로 구분하고 **연속해서 입혁**
  - 콤마로 구분 시 출력에서 **자동으로 빈칸(공백)이 하나씩 들어감**
  - `sep = 문자열`빈칸 대신 다른 문자열 삽입 가능 / `sep=''`만 입력시 공백x
  - `+` : 빈 칸 없이 두 문자열을 연결

````python
print('Hello Python!')
print('best','python','book') 
print('best','python','book',sep = '-:*:-')
print('abcd'+'efgh')
print('best','python','book'+':','This book') #문자열 연견시 콤마와 연산자 동시 사용 가능

>Hello Python!
 best python book
 best-:*:-python-:*:-book
 abcdefgh
 best python book: This book
````

- 변수에 저장된 내용 출력 시 `print()`함수에 변수를 인자로 입력 

````python
x = 10
print(x) #변수 이름을 이용해 출력을 할 때는 따옴표 사용x
> 10
````

- **문자열과 숫자 함께 출력**시 둘을 **콤마**로 구분
- `+` : **문자열과 문자열**은 공백없이 연결해서 출력가능
  - **문자열과 숫자**는 더하기 연산자로 연결이 불가능/ `sep=''`이용 !

````python
name = 'jay'
ID_num = 789
print('Name:',name + ',','ID_Number:',ID_num)
````

- `print()` : 문자열 출력 시 결과가 한 줄씩 출력
- `\n`  : 출력 시 줄이 바뀜
  - `print()` : 기본적으로 출력을 위해서 줄을 바꿔 놓으므로 여러 번 사용하여 줄을 바꿀 수 있음
- `\n\n` : 한 줄 띄우고 줄이 바뀜 

````python
print('James is my best friend.\nHe is korean.')
print('Welcome to')
print("python!")
print('James is my best friend.\n\nHe is korean.')

>James is my best friend.
 He is korean.
 Welcome to
 python!
 James is my best friend.

 He is korean.
````

- `print(data,end = '');print(data2)` 추가 시 여러 줄로 출력된 결과를 한줄로 출력 가능
  - `end`미지정시 기본적으로 print함수 라인 끝에 개행문자(\n)가 들어감
- 개행문자(\n) 대신 다른 문자열을 입력하려면 `end=문자열`형태로 입력

````python
print('Welcom to',end="")
print('python!')
> Welcom topython!
````

2. 나머지 연산자(%)를 이용한 형식 및 위치 지정 출력

- `print()` 함수에서 문자열에 데이터가 출력될 위치와 형식을 지정하는 방식으로도 데이터 출력
- `%` : `print()`함수에서 데이터의 출력 형식과 위치를 지정할 때도 사용
- 기본형식 : `print("%type"%data)` **\#따옴표와 %data 사이에 콤마가 아닌 공백**
  - '%type' : data 형식에 따라 다른 값을 지정 
  - data : 문자열(%s), 정수(%d/%i), 실수(%f/%F) 지정
  - 실수의 경우 기본적으로 소수점 6자리까지 출력
- data가 두 개 이상이면
- `print("%type%type"%(data1,data2))`
  - data의 개수에 맞게 `%type`를 **순서대로 입력**하고 **튜플 형식으로 data를 묶어서 사용**

````python
name = '광재'#문자열을 대입한 변수
print('%s는 나의 친구입니다.' %name)

r=3 #정수 데이터 할당
PI=3.14159265358979 #실수 데이터 할당
print('반지름 %d, 원주율 %f' %(r,PI)) #지정된 위치에 데이터 출력(!!데이터 순서 중요!!)

>광재는 나의 친구입니다.
반지름 3, 원주율 3.141593 #실수는 최대 6자리까지
````

3. 형식 지정 문자열에서 출력 위치 지정

- 출력 양식을 좀 더 **자유롭게 표현**할 수 있는 **형식 지정 문자열 이용**
- `print()`함수에서 `string.format()`을 이용하는 형식 지정 문자열의 기본 구조

`print('{0}{1}{2}...{n}'.format(data_0,data_1,data_2,...,data_n))`

- '{0}{1}{2}...{n}' : n은 0부터 시작하는 숫자로 format()에서 데이터의 위치(0부터 시작)를 의미

  ````python
  animal_0 = 'cat'
  animal_1 = 'dog'
  animal_2 = 'fox'
  print('Animal : {0}'.format(animal_0))
  print('Animal : {0},{1},{2}'.format(animal_0,animal_1,animal_2))
  print('Animal : {2},{1},{0}'.format(animal_0,animal_1,animal_2))
  print('Animal : {0},{2}'.format(animal_0,animal_1,animal_2))
  print('Animal : {},{},{}'.format(animal_0,animal_1,animal_2))
  
  >Animal : cat
  Animal : cat,dog,fox
  Animal : fox,dog,cat #지정한 순서대로 출력
  Animal : cat,fox #첫번째와 세번째 데이터만 출력
  Animal : cat,dog,fox #format() 데이터를 순차적으로 지정하려면 {}만 써도 됨
  ````

- **정수나 실수**도 `string.format()`방식을 이용해 출력 가능
- 출력 형식을 별도록 지정하지 않아도 **데이터의 타입에 따라 자동으로 알아서 출력**됨
- {n}를 이용하여 **변수를 출력할 위치만 지정**하면 됨

```python
name = 'Thomas'
age = 10
a = 0.1234567890123456789
fmt_string = 'String:{0},Interger Number:{1},Floating Number:{2}'
print(fmt_string.format(name,age,a))
>String:Thomas,Interger Number:10,Floating Number:0.12345678901234568 
 #실수는 소수점 17자리까지 반올림하여 표기
```

4. 형식 지정 문자열에서 숫자 출력 형식 지정

- 데이터가 문자열이 아닌 숫자인 경우 `{N:'출력형식'}`형태로 좀 더 다양하게 출력 형식 지정 가능
- N은 format()에서 N번째 데이터의 위치

````python
a = 0.1234567890123456789
print('{0:.2f},{0:.5f}'.format(a))
>0.12, 0.12346
````

| 데이터      | 출력 형식 | 출력 결과 | 설명                                                         |
| ----------- | --------- | --------- | ------------------------------------------------------------ |
| 3           | {N:2d}    | -3        | 정수를 공백 포함해 두 자리로 표시(-공백 한 칸 의미)          |
| 3           | {N:05d}   | 00003     | 정수를 다섯 자리로 표시. 앞의 공백은 0으로 채움              |
| 12          | {N:>5d}   | ---12     | 정수를 다섯 자리로 표시. 숫자는 오른쪽으로 정렬              |
| 0.12345     | {N:.3f}   | 0.123     | 실수를 소수점 셋째 자리까지 표시                             |
| 7456000     | {N:,}     | 7,456,000 | 통화 표시처럼 끝에서 셋째 자리마다 콤마(,)를 표시            |
| 0.3258      | {N:.1%}   | 32.6%     | 소수를 퍼센트로 표시. '.' 다음에 소수점 자리 수 숫자로 표시  |
| 92500000000 | {N:.2e}   | 9.25e+10  | 숫자를 지수로 표시. 지수 표시에서 소수점 자리 수는 다음 숫자로 표시 |
| 16          | {N: #x}   | 0x10      | 숫자를 16진수로 표시. #기호가 없으면 0x없이 출력             |
| 8           | {N: #o}   | 0o10      | 숫자를 8진수로 표시. #기호가 없으면 0o없이 출력              |
| 2           | {N: #b}   | 0b10      | 숫자를 2진수로 표시. #기호가 없으면 0b없이 출력              |



### 3. 키보드 입력

1. 키보드 입력

- 키보드로 데이터 입력하기 위해서는 input()함수를 이용
  - 데이터를 입력하고 그 값을 받아서 처리하는 방법
- `data = input('문자열')`
  - '문잔열'은 화면에 표시-> 키보드로 데이터 입력 후 Enter -> 문자열 형태로 data 변수에 대입

````python
yourName = input('당신의 이름은?')
print('당신은 {}이군요.'.format(yourName))

>당신의 이름은?-------
 당신은 박현주이군요.
````

- 숫자를 입력
- input() 함수로부터 입력 받은 데이터는 **모두 문자열로 처리** / 숫자를 그대로 출력할 경우 문제 x
- 숫자를 **연산에 이용**한다면 연산 전에 **입력 받은 숫자를 정수 혹은 실수로 변환**

````python
num = input("숫자를 입력하세요 : ")
print('당신이 입력한 숫자는 {}입니다.'.format(num))
>숫자를 입력하세요 : -----
 당신이 입력한 숫자는 입니다.

#사각형변의 길이를 입력 받아 넓이를 구하기
a = input("정사각형 한 변의 길이는? : ")
area = int(a)**2 #연산에 이용시 입력받은 숫자를 정수 혹은 실수로 변환
area = int(b)**2
print("정사각형의 넓이 : {}".format(area))
>정사각형 한 변의 길이는? : 4 / 4 
 정사각형의 넓이 : 16 / 16.0 #정수로 변환시 값은 정수 / 실수로 변환시 값은 실수
````

