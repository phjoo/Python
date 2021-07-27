## 4장 변수와 자료형

### 1. 변수

1) 변수 : 자료를 넣을 수 있는 상자 / 반복적으로 데이터를 입력하지 않아도 됨

- 파이썬에서 지원하는 자료형(데이터 타입)
- 선언 후 변수 대입하는 것이 원칙 ; 선언 생략 가능
- 등호(=)를 이용해 변수에 자료를 넣음(할당)
- **'변수명 = data'**
  - 공백 여부 상관x
- 변수로 할당한 경우 print(변수명)을 이용하지 않더라도 변수명 실행시 할당된 값 출력 가능

2) 규칙을 지키면서 변수명 작성

- 변수명을 **문자, 숫자, 밑줄 기호(_)**를 이용해 만듦
  - 밑줄 기호로 시작하는 변수명은 특별한 용도에 사용 / 보통은 사용X
- **숫자로 시작하는 변수명** 불가능
- **대소문자 구분** 필요
  - ace != Ace
- **공백**을 포함할 수 **없음**
- 밑줄 이외의 **기호는 변수로 사용할 수 없음** 
- **예약어**는 변수명으로 **이용할 수 없음**  #파이썬에서 쓰는 문법
  - None, and, True, elif, def...등

3) 상수

- 프로그래밍 언어에서 어떤 숫자를 변수에 할당한 후에 프로그램이 끝날 때까지 그 변수의 값을 

- 한 번 지정한 후 **그 값이 변하지 않는 변수**



*질문> 역슬래쉬 \\(원화표시)사용시 \#과 같은 것을 문자로 사용 가능*



### 2. 문자열(String)

1) 문자열 만들기

- **문자의 나열**, 파이썬에서는 **큰/작은 따옴표로 둘러싸인** 문자의 집합

- 큰/작은 따옴표 상관x, 양쪽에 같은 따옴표를 사용해야 함

- 문자열에 **따옴표를 포함**하려면?

  - 큰 따옴표를 포함하려면 문자열을 작은 따옴표로 감싸고 작은 따옴표를 포함하려면 큰 따옴표 감쌈

  - 문자열에 큰 따옴표와 작은 따옴표를 **모두 포함** 혹은 **문장을 여러 행 넣고 싶거나 입력한 그대로 출력**하고 싶은 경우 ** 삼중 큰 따옴표나 삼중 작은 따옴표**

    ```python
    string3 = 'I "Love" u'
    string1 = '''"삼중 '작은 따옴표'를 사용한 예"'''
    
    >I "Love" u
     "삼중 '작은 따옴표'를 사용한 예"
    ```

- 문자열에는 **더하기 연산자**와 **곱하기 연산자**를 이용할 수 있음

  - 더하기 연산자 : 문자열 끼리 **연결**해 문자열을 하나로 만듬

  - 곱하기 연산자 : 곱한 만큼 문자열을 반복함

    ```python
    a = 'enjoy '
    b = 'python'
    c = a+b
    print(c) == print(a+b)
    print(a * 3)
    
    > enjoy python
      enjoy enjoy enjoy
    ```



### 3. 리스트(List)

1) **리스트[원소]**  \#비교) 튜플(원소) , 딕셔너리{key:value}, 세트(=>집합)

- 숫자, 문자열, 불 데이터 타입(이런 데이터 타입은 데이터를 하나씩만 처리할 수 있음)
- 데이터를 묶어서 처리하면 관리가 편리
  - ex) 학교에서 학생의 과목별 시험 점수 처리, 학급별로 학생의 이름 지정
- 리스트 안에 **튜플, 딕셔너리, 세트, 리스트, 숫자, 문자열, 불 등**을 **넣을 수 있음**
  - 공백을 데이터로 만들고 싶다면 \' ' 형태로 입력
- 리스트를 만들 때 **각 항목의 데이터 타입은 같지 않아도** 됨
  - [1,'apple',[1,2]]와 같이 여러 데이터 타입 입력 가능
- 데이터는 **입력한 순서대로 지정**, 요소 간 구분은 **콤마(,)**로 구분
- 빈 리스트에는 데이터는 없지만 데이터 형태는 리스트임
  - list1 = [ ]  ;  수집할 데이터 양을 알 수 없을 경우 빈 리스트 생성하여 유동성을 만들어줌

-  type(list 이름) << list #데이터 타입

2) 리스트 만들기

- 리스트 변수의 구조 : 리스트에서 각 항목은 변수명[i]로 지정할 수 있음
  - i를 리스트 변수의 인덱스(index)
- **N개 항목이 있는 리스트 타입**의 데이터가 있다면 **인덱스 i의 범위는 0부터 'N-1'**
- 리스트 항목 : **변수명[i]**
- **마지막 항목**은 **변수명[-1]**로 지정 가능
- 리스트의 **특정 항목 변경 '변수명[i] = new_data**'

3)리스트 다루기

- 리스트 **더하기** 연산자 (+) : 리스트를 **연결**

- 리스트 **곱하기** 연산자(*) : 리스트를 곱한 수만큼 **반복**

- 리스트 중 **일부 항목** 가져오기
  - `리스트[ i_start : i_end ]` #각각 인덱스의 시작, 끝
  - `리스트[i_start : i_end : i_step]` # i_step : 증가단계

- 인덱스의 범위를 지정하면 **'i_start'에서 'i_end-1'**까지의 리스트를 반환

- **i_start를 생략**하면 인덱스는 **0으로 간주**

- **i_end를 생략**하면 인덱스는 **마지막이라고 간주**

  ```python
  list_d = [0,1,2,3,4,5,6,7,8,9]
  print(list_d)
  #list[-1]=list[9]
  #list[-9]=list[0]
  print(list_d[0:3])
  print(list_d[:2])
  print(list_d[7:])
  print(list_d[::2])
  
  >[0,1,2,3,4,5,6,7,8,9]
   [0,1,2]
   [0,1,2]
   [7,8,9]
   [0,2,4,6,8]
  ```

- 리스트 항목 변경/삭제 

  - 변경 : `list명[위치] = 변경할 데이터`
  -  삭제 : `dle 리스트명[i]` 

  ```python
  print(list_d)
  list_d[i] = 데이터
  del list_d[i] #[인덱스 위치]
  print(list_d)
  
  >[0,1,2,3,4,5,6,7,8,9]
   [0,1,2,3,4,5,7,8,9] #인덱스 위치 6번째 삭제됨
  ```

- 리스트에서 항목의 존재 여부 확인하기 : `항목 in 리스트`를 이용

  - 리스트 항목이 있으면 True, 없으면 False로 반환

  ```python
  list_da = [1,2,3,4,5]
  print(5 in list_da)
  print(6 in list_da)
  
  >True
   False
  ```

4) 리스트 메서드 활용하기

- 메서드란 ? **데이터 타입(자료형)별로 이용할 수 있는 다양한 함수**

- 메서드의 형식
  - 자료형.메서드이름()
  - 변수명.메서드이름()  \#데이터를 변수에 할당했을 경우

| 리스트 메서드 |                             설명                             |             사용예             |
| :-----------: | :----------------------------------------------------------: | :----------------------------: |
|   .append()   |       리스트에서 항목 하나를 **맨 마지막**에 **추가**        |       list1.append('안')       |
|   .insert()   |          리스트에서 **특정 위치**에 항목을 **삽입**          |     list1.insert( i, '안')     |
|   .extend()   |      리스트에서 항목 **여러 개**를 **맨 마지막에 추가**      |  list1.extend(['안녕'하이'])   |
|   .remove()   |      입력값과 첫 번째로 일치하는 항목을 리스트에서 삭제      |       list1.remove('안')       |
|     pop()     |         리스트의 **마지막 항목을 제거한 후에 반환**          |    list1.pop = list1.pop()     |
|    index()    | 리스트에서 인자와 일치하는 **첫 번째 항목**의 **위치**를 반환 | indexlist1 = list1.index('안') |
|    count()    |    리스트에서 **인자와 일치**하는 항목의 **개수**를 반환     | countlist1 = list1.count('안') |
|    .sort()    | 숫자나 문자열로 구성된 리스트 항목을 **순방향**으로 정렬 <br />(원소의 자료형이 다른 경우는 정렬불가) |          list1.sort()          |
|  .reverse()   |          리스트 항목을 끝에서부터 **역순**으로 정렬          |        list1.reverse()         |

- `sort() , reverse()`메서드는 기존 리스트에서 재정렬
- `soreted()`메서드는 새로운 리스트를 생성해서 재정렬
  - 새 데이터 이름 = sorted(정렬할 데이터)



### 4. 튜플(Tuple)

1. 튜플(Tuple)

- 리스트와 유사,  **데이터 여러 개를 하나로 묶는데 이용**
- **숫자, 문자열, 불, 리스트, 튜플, 세트, 딕셔너리 등**으로 만들 수 있음
- 리스트와 차이점 : 튜플 데이터는 **한 번 입력(혹은 생성)하면 그 이후에는 항목을 변경할 수 없음**

2. 튜플 만들기

- **소괄호**를 사용, 항목은 콤마(,)로 구분
- 괄호를 사용하지 않고 데이터 입력
- 변수명[i] : 튜플의 각 요소 지정
- **인자가 하나만** 있는 튜플 : 항목 하나를 입력 후 **반드시 콤마(,) 입력**

```python
tuple1 = (1,2,3)
tuple2 = 1,2,3, 4
print(tuple1)
print(tuple2)
type(tuple2)
tuple3 = (9,)(==9,) #tuple3 = 9 입력시 숫자열로 인식
print(tuple3)

>(1,2,3)
 (1,2,3,4)
 tuple
 (9)
```

3. 튜플 다루기

- 한 번 생성된 튜플은 **요소를 변경/삭제가 불가능**
- 한번 생성한 후에 요소를 변경할 필요가 없고나 변경할 수 없도록 하고 싶을 때 주로 이용

- 변경/삭제하는 메서드는 튜플에서 이용 불가능
- `index(), 'count()'`는 튜플에서 사용 가능
  - `index()` : 요소와 일치하는 **첫 번째 항목의 위치** 반환
  - `count()` : 요소와 **일치하는 항목의 개수**를 반환

```python
tuple1 = (1,2,3)
tuple2 = 1,2,3, 4
tuple1.index(2)
tuple2.count(4)

> 1
  1
```



### 5. 딕셔너리(Dictionary)

- **사전과 유사하게 구성**
- 사전의 표제어 : 설명 = 키(key) : 값(value)
- **키와 값이 항상 쌍으로** 구성
- 리스트나 튜플은 인덱스를 이용해 항목을 다루지만, **딕셔너리는 키를 이용해 값을 다룸** (**순서가 상관x**)
- **딕셔너리의 키** : **임의로 지정한 숫자나 문자열, 튜플 가능**, 변할 수 없는 자료형!!(**리스트 불가능**)
  - 리스트나 튜플 : 인덱스가 0부터 시작하는 숫자
- **값** : **어떤 데이터 타입(리스트,튜플,딕셔너리,숫자,문자열 등)도 사용 가능**

1. 딕셔너리 만들기

- 딕셔너리 데이터 전체를 **중괄호**로 감싸면 됨
- key : 변할 수 없는 자료형 -> 리스트는 안 되고, 튜플은 가능
  - **튜플** : **여러 자료의 묶음**   
- **키와 값의 구분은 콜론(:)**
- 키와 값으로 이뤄진 **각 쌍은 콤마로 구분**
- `dict_name = {key1:value1,key2:value2}`
- `dict_name['key1']` : **지정한 키의 값만 출력**

```python
country_city = {'한국':'서울','일본':'도쿄','중국':'상하이','프랑스':'파리'}
country_city
print(type(country_city))
country_city["한국"]

> {'한국': '서울', '일본': '도쿄', '중국': '상하이', '프랑스': '파리'}
 <class 'dict'>
    '서울'
    
```

2. 딕셔너리 다루기

- 딕셔너리에 데이터 추가/변경 및 삭제
  - `dict_name[new key]=Newname` : 데이터 추가
  - `dict_name[existing key]=Newname2` : 데이터 변경
  - `del dict_name[existing key]` : 데이터 삭제

```python
country_city["독일"] = "베를린" #데이터 추가
country_city["호주"] = "캔버라" #데이터 변경
print(country_city)

>
{'한국': '서울', '일본': '도쿄', '중국': '상하이', '프랑스': '파리', '호주': '캔버라', '독일': '베를린'}
```

3. 딕셔너리 메서드 활용하기

|  딕셔너리 메서드   |                             설명                             |           사용 예            |
| :----------------: | :----------------------------------------------------------: | :--------------------------: |
|       keys()       |      딕셔너리에서 **키 전체**를 **리스트 형태로 반환**       |       dict_name.keys()       |
|      values()      |      딕셔너리에서 **값 전체**를 **리스트 형태로 반환**       |      dict_name.values()      |
|      items()       | 딕셔너리에서 **키와 값의 쌍을 (키,값)처럼 튜플 형태로 반환** |      dict_name.items()       |
| update(dict_date2) |      딕셔너리에서 **딕셔너리 데이터(dict_date2) 추가**       | dict_date.update(dict_data2) |
|      clear()       |                딕셔너리의 **모든 항목 삭제**                 |      dict_data.clear()       |

- list() 함수를 이용해 리스트로 변환 가능
  - list(dict_name.**keys/values/items()**)
- clear() 사용 시 **빈 딕셔너리({})**가 됐지만 데이터 타입은 **여전히 딕셔너리**임을 알 수 있음

### 6. 세트(Set)

1. 세트

- **수학의 집합 개념**을 파이썬에서 이용할 수 있도록 만든 데이터 타입
  - 리스트와 튜플과 다른 점 : **데이터의 순서가 없고 중복해서 쓸 수 없음**
    - **순서가 없으므로 인덱스에 의한 접근 불가능**
    - 오른차순으로 자동정렬
  - **리스트에서 사용한 메서드 + 교집합/합집합/차집합 메서드** 사용 가능
  - set의 원소는 **immutable한 것만 사용 가능** ex) list는 원소로 사용 불가능

2. 세트 만들기

- 세트 생성 : **중괄호{}**로 데이터를 감싸면 됨, 항목과 항목 사이에는 콤마(,) 사용

  ```python
  set1 = {3,1,2}
  set2 = {1,2,3,3}
  print(set1)
  print(set2)
  type(set1)
  >{1,2,3} # 오름차순으로 정렬
   {1,2,3} # 중복된 데이터는 하나만 입력됨
   set
  ```

3. 세트의 교집합/합집합/차집합 구하기

- 교집합 : A and b / `A.Intersection(B)` / &
- 합집합 : A or B / `A.union(B) ` / |
- 차집합 : A - B /  `A.difference(B)` / -

```python
A = {1,2,3,4,5}
B = {4,5,6,7,8,9}
A.intersection(B) == A&B
A.union(B) == A|B
A.difference(B) == A-B

>{4, 5}
 {1, 2, 3, 4, 5, 6, 7, 8, 9}
 {1, 2, 3}
```

4. 리스트, 튜플, 세트 간 타입 변환

- 여러 데이터를 다루다 보면 연산이나 처리를 할 때 데이터의 타입을 변환할 필요 O
- 데이터 타입은 **list(), tuple(), set()** 서로 **변환 가능**

```python
a = [1,2,3,4,5]
print(type(a))
b = tuple(a) #리스트a를 튜플로 변환
print(type(b))
c = set(a) #리스트 a를 세트로 변환
print(type(c))
list(b) #튜플b와 세트c를 다시 리스트로 변환
list(c)

><class 'list'>
<class 'tuple'>
<class 'set'>
[1, 2, 3, 4, 5]
```
