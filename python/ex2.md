# 문자열 
### 1. 큰따옴표```"```로 양쪽 둘러싸기
```python
"Hello World"
```
### 2. 작은따옴표```'```로 양쪽 둘러싸기
```python
'Python is fun'
```
### 큰따옴표 3개를 연속```"""```으로 써서 양쪽 둘러싸기
```python
"""Life is too short, You need python"""
```
### 작은따옴표 3개를 연속(''')으로 써서 양쪽 둘러싸기
```python
'''Life is too short, You need python'''
```
### 3. 백슬래시```\```를 사용해서 작은따옴표(')와 큰따옴표(")를 문자열에 포함시키기
```python
>>> food = 'Python\'s favorite food is perl'
>>> say = "\"Python is very easy.\" he says."
```
*작은따옴표(')나 큰따옴표(")를 문자열에 포함시키는 또 다른 방법은 백슬래시```\```를 사용하는 것이다. 즉 백슬래시```\```를 작은따옴표(')나 큰따옴표(") 앞에 삽입하면 백슬래시```\``` 뒤의 작은따옴표(')나 큰따옴표(")는 문자열을 둘러싸는 기호의 의미가 아니라 문자 ('), (") 그 자체를 뜻하게 된다.*

### 여러 줄인 문자열을 변수에 대입하고 싶을 때
***
### 1. 줄을 바꾸기 위한 이스케이프 코드 \n 삽입하기
```python
>>> multiline = "Life is too short\nYou need python"
```
### 2. 연속된 작은따옴표 3개(''') 또는 큰따옴표 3개(""") 사용하기
```python
>>> multiline='''
... Life is too short
... You need python
... '''

>>> multiline='''
... Life is too short
... You need python
... '''
```
### 결과 
```python
>>> print(multiline)
Life is too short
You need python
```

# 문자열 연산하기
파이썬에서는 문자열을 더하거나 곱할 수 있다. 다른 언어에서는 쉽게 찾아볼 수 없는 재미있는 기능으로, 우리 생각을 그대로 반영해 주는 파이썬만의 장점이라고 할 수 있다. 

### 문자열 더해서 연결하기(Concatenation)
```python
>>> head = "Python"
>>> tail = " is fun!"
>>> head + tail
'Python is fun!'
```

### 문자열 곱하기 
```python
>>> a = "python"
>>> a * 2
'pythonpython'
```

### 문자열 곱하기 응용 
```python
print("=" * 50)
print("My Program")
print("=" * 50)
```
실행값
```
C:\Users>cd C:\doit
C:\doit>python multistring.py
==================================================
My Program
==================================================
```

### 문자열길이 구하기
```python
>>> a = "Life is too short"
>>> len(a)
17
```

# 문자열 인덱싱과 슬라이싱
인덱싱(Indexing)이란 무엇인가를 "가리킨다"는 의미이고, 슬라이싱(Slicing)은 무엇인가를 "잘라낸다"는 의미이다. 이런 의미를 생각하면서 다음 내용을 살펴보자.

### 문자열 인덱싱이란?
```python
>>> a = "Life is too short, You need Python"
위 소스 코드에서 변수 a에 저장한 문자열의 각 문자마다 번호를 매겨 보면 다음과 같다.
Life is too short, You need Python
0         1         2         3 
0123456789012345678901234567890123
```
```python
>>> a = "Life is too short, You need Python"
>>> a[3]
'e'
```
a[3]이 뜻하는 것은 a라는 문자열의 네 번째 문자 e를 말한다.

### 문자열 인덱싱 활용하기
```python
>>> a = "Life is too short, You need Python"
>>> a[0]
'L'
>>> a[12]
's'
>>> a[-1]
'n'
```
a[-1]은 뒤에서부터 세어 첫 번째가 되는 문자를 말한다.

### 문자열 슬라이싱이란?
```python
>>> a = "Life is too short, You need Python"
>>> a[0:4]
'Life'
```
a[0:4]가 뜻하는 것은 문장에서 자리 번호 0부터 4까지의 문자를 뽑아낸다는 뜻이다.

슬라이싱 기법으로 a[시작 번호:끝 번호]를 지정할 때 끝 번호에 해당하는 것은 포함하지 않기 때문이다. a[0:3]을 수식으로 나타내면 다음과 같다.

```python
0 <= a < 3
```

### 문자열을 슬라이싱하는 방법 
a[시작 번호:끝 번호]에서 끝 번호 부분을 생략하면 시작 번호부터 그 문자열의 끝까지 뽑아낸다.
```python
>>> a[19:]
'You need Python'
```
a[시작 번호:끝 번호]에서 시작 번호를 생략하면 문자열의 처음부터 끝 번호까지 뽑아낸다.
```python
>>> a[:17]
'Life is too short'
```

### 슬라이싱으로 문자열 나누기 
```python
>>> a = "20010331Rainy"
>>> date = a[:8]
>>> weather = a[8:]
>>> date
'20010331'
>>> weather
'Rainy'
```

## 문자열 포매팅 따라 하기
### 1. 숫자 바로 대입
```python
>>> "I eat %d apples." % 3
'I eat 3 apples.'
```
여기에서 %d는 문자열 포맷 코드라고 부른다.

### 2. 문자열 바로 대입
```python
>>> "I eat %s apples." % "five"
'I eat five apples.'
```
문자열을 넣기 위해서는 %s를 써야 한다

### 3. 숫자 값을 나타내는 변수로 대입
```python
>>> number = 3
>>> "I eat %d apples." % number
'I eat 3 apples.'
```

### 4. 2개 이상의 값 넣기 
```python
>>> number = 10
>>> day = "three"
>>> "I ate %d apples. so I was sick for %s days." % (number, day)
'I ate 10 apples. so I was sick for three days.'
```

### 문자열 포맷코드 
```
코드	설명
%s	    문자열(String)
%c 	    문자 1개(character)
%d	    정수(Integer)
%f	    부동소수(floating-point)
%o	    8진수
%x	    16진수
%%	    Literal % (문자 % 자체)
```

%s 포맷 코드는 떤 형태의 값이든 변환해 넣을 수 있다. 
```python
>>> "I have %s apples" % 3
'I have 3 apples'
>>> "rate is %s" % 3.234
'rate is 3.234'
```

### 포매팅 연산자 %d와 %를 같이 쓸 때는 %%를 쓴다
```python
>>> "Error is %d%%." % 98
'Error is 98%.'
```

## 포맷코드와 숫자 함께 사용하기
### 1. 정렬과 공백
```python
>>> "%10s" % "hi"
'        hi'
```
전체 길이가 10개인 오른쪽 정렬

```python
>>> "%10s" % "hi"
'        hi'
```
왼쪽정렬

### 2. 소수점 표현하기 
```python
>>> "%0.4f" % 3.42134234
'3.4213'
```
소수점 네 번째 자리까지만 나타내고 싶은 경우

```python
>>> "%10.4f" % 3.42134234
'3.4213'
```
소수점 네 번째 자리까지만 표시하고 전체 길이가 10개인 문자열 공간에서 오른쪽으로 정렬하는 예

## format 함수를 사용한 포매팅 
```python
숫자바로 대입하기 
>>> "I eat {0} apples".format(3)
'I eat 3 apples'

문자열 바로 대입하기 
>>> "I eat {0} apples".format("five")
'I eat five apples'

숫자 값을 가진 변수로 대입하기 
>>> number = 3
>>> "I eat {0} apples".format(number)
'I eat 3 apples'

2개 이상의 값 넣기 
>>> number = 10
>>> day = "three"
>>> "I ate {0} apples. so I was sick for {1} days.".format(number, day)
'I ate 10 apples. so I was sick for three days.'

이름으로 넣기 
>>> "I ate {number} apples. so I was sick for {day} days.".format(number=10, day=3)
'I ate 10 apples. so I was sick for 3 days.'

왼쪽 정렬 
>>> "{0:<10}".format("hi")
'hi     

오른쪽 정렬
>>> "{0:>10}".format("hi")
'        hi'

가운데 정렬
>>> "{0:^10}".format("hi")
'    hi 

공백 채우기 
>>> "{0:=^10}".format("hi")
'====hi===='
>>> "{0:!<10}".format("hi")
'hi!!!!!!!!'

소수점 표현하기 
>>> y = 3.42134234
>>> "{0:0.4f}".format(y)
'3.4213'
```
### f 문자열 포매팅
 파이썬 3.6 버전부터는 f 문자열 포매팅 기능을 사용할 수 있다

 ```python
>>> name = '홍길동'
>>> age = 30
>>> f'나의 이름은 {name}입니다. 나이는 {age}입니다.'
'나의 이름은 홍길동입니다. 나이는 30입니다.'
 ```
 f 문자열 포매팅은 표현식을 지원하기 때문에 다음과 같은 것도 가능하다.
 >※ 표현식이란 문자열 안에서 변수와 +, -와 같은 수식을 함께 사용하는 것을 말한다.
 ```python
>>> age = 30
>>> f'나는 내년이면 {age+1}살이 된다.'
'나는 내년이면 31살이 된다.'
 ```
 딕셔너리는 f 문자열 포매팅에서 다음과 같이 사용할 수 있다.
 >※ 딕셔너리는 Key와 Value라는 것을 한 쌍으로 갖는 자료형이다. 02-5에서 자세히 알아본다.
 ```python
>>> d = {'name':'홍길동', 'age':30}
>>> f'나의 이름은 {d["name"]}입니다. 나이는 {d["age"]}입니다.'
'나의 이름은 홍길동입니다. 나이는 30입니다.'
 ```

```python
정렬 
>>> f'{"hi":<10}'  # 왼쪽 정렬
'hi        '
>>> f'{"hi":>10}'  # 오른쪽 정렬
'        hi'
>>> f'{"hi":^10}'  # 가운데 정렬
'    hi    '

공백 채우기
>>> f'{"hi":=^10}'  # 가운데 정렬하고 '=' 문자로 공백 채우기
'====hi===='
>>> f'{"hi":!<10}'  # 왼쪽 정렬하고 '!' 문자로 공백 채우기
'hi!!!!!!!!'

f 문자열에서 { } 문자를 표시하려면 다음과 같이 두 개를 동시에 사용해야 한다.

>>> f'{{ and }}'
'{ and }'
```

# 문자열 관련 함수들 
## 문자 개수 세기 (count)
```python 
>>> a = "hobby"
>>> a.count('b')
2
```
## 위치 알려주기1 (find)
```python 
>>> a = "Python is the best choice"
>>> a.find('b')
14
>>> a.find('k')
-1
```
## 위치 알려주기2 (index)
```python 
>>> a = "Life is too short"
>>> a.index('t')
8
>>> a.index('k')
Traceback (most recent call last):
File "<stdin>", line 1, in <module>
ValueError: substring not found
```
앞의 find 함수와 다른 점은 문자열 안에 존재하지 않는 문자를 찾으면 오류가 발생
## 문자열 삽입 (join)
```python 
>>>> ",".join('abcd')
'a,b,c,d'
```
## 소문자를 대문자로 바꾸기 (upper)
```python 
>>> a = "hi"
>>> a.upper()
'HI'
```
## 대문자를 소문자로 바꾸기 (lower)
```python 
>>> a = "HI"
>>> a.lower()
'hi'
```

## 문자열 바꾸기 (replace)
```python 
>>> a = "Life is too short"
>>> a.replace("Life", "Your leg")
'Your leg is too short'
```

## 문자열 나누기 (split))
```python 
>>> a = "Life is too short"
>>> a.split()
['Life', 'is', 'too', 'short']
>>> b = "a:b:c:d"
>>> b.split(':')
['a', 'b', 'c', 'd']
```

[출처](https://wikidocs.net/13)