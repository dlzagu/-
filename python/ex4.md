## 딕셔너리란?
-----
사람은 누구든지 "이름" = "홍길동", "생일" = "몇 월 며칠" 등으로 구별할 수 있다. 파이썬은 영리하게도 이러한 대응 관계를 나타낼 수 있는 자료형을 가지고 있다. 요즘 사용하는 대부분의 언어도 이러한 대응 관계를 나타내는 자료형을 갖고 있는데, 이를 연관 배열(Associative array) 또는 해시(Hash)라고 한다.

파이썬에서는 이러한 자료형을 딕셔너리(Dictionary)라고 하는데, 단어 그대로 해석하면 사전이라는 뜻이다. 즉 "people"이라는 단어에 "사람", "baseball"이라는 단어에 "야구"라는 뜻이 부합되듯이 딕셔너리는 Key와 Value를 한 쌍으로 갖는 자료형이다. 예컨대 Key가 "baseball"이라면 Value는 "야구"가 될 것이다.

딕셔너리는 리스트나 튜플처럼 순차적으로(sequential) 해당 요솟값을 구하지 않고 Key를 통해 Value를 얻는다. 이것이 바로 딕셔너리의 가장 큰 특징이다. baseball이라는 단어의 뜻을 찾기 위해 사전의 내용을 순차적으로 모두 검색하는 것이 아니라 baseball이라는 단어가 있는 곳만 펼쳐 보는 것이다.

## 딕셔너리는 어떻게 만들까??
------
```py
{Key1:Value1, Key2:Value2, Key3:Value3, ...}
```
Key와 Value의 쌍 여러 개가 { }로 둘러싸여 있다. 각각의 요소는 Key : Value 형태로 이루어져 있고 쉼표(,)로 구분되어 있다.

> ※ Key에는 변하지 않는 값을 사용하고, Value에는 변하는 값과 변하지 않는 값 모두 사용할 수 있다.

```py
ex))
>>> dic = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}

다음 예는 Key로 정수 값 1, Value로 문자열 'hi'를 사용한 예이다.

>>> a = {1: 'hi'}
또한 다음 예처럼 Value에 리스트도 넣을 수 있다.

>>> a = { 'a': [1,2,3]}
```

## 딕셔너리 쌍 추가, 삭제하기
-----
### 딕셔너리 쌍 추가하기 
```py
>>> a = {1 : 'a'
>>> a[2] = 'b'
>>> a
{1: 'a', 2: 'b'}

>>> a['name'] = 'pey'
>>> a
{1: 'a', 2: 'b', 'name': 'pey'}

>>> a[3] = [1,2,3]
>>> a
{1: 'a', 2: 'b', 'name': 'pey', 3: [1, 2, 3]}
```
{1: 'a'} 딕셔너리에 a[2] = 'b'와 같이 입력하면 딕셔너리 a에 Key와 Value가 각각 2와 'b'인 2 : 'b'라는 딕셔너리 쌍이 추가된다.

### 딕셔너리 요소 삭제하기
```py
>>> del a[1]
>>> a
{2: 'b', 'name': 'pey', 3: [1, 2, 3]}
```

## 딕셔너리에서 Key 사용해 Value 얻기
```py
>>> grade = {'pey': 10, 'julliet': 99}
>>> grade['pey']
10
>>> grade['julliet']
99
```
몇가지의 예 
```py
>>> a = {1:'a', 2:'b'}
>>> a[1]
'a'
>>> a[2]
'b'

>>> a = {'a':1, 'b':2}
>>> a['a']
1
>>> a['b']
2

>>> dic = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
>>> dic['name']
'pey'
>>> dic['phone']
'0119993323'
>>> dic['birth']
'1118'
```

### 딕셔너리 만들 때 주의 사항 
먼저 딕셔너리에서 Key는 고유한 값이므로 중복되는 Key 값을 설정해 놓으면 하나를 제외한 나머지 것들이 모두 무시된다는 점을 주의해야 한다. 다음 예에서 볼 수 있듯이 동일한 Key가 2개 존재할 경우 1:'a' 쌍이 무시된다.
```py 
>>> a = {1:'a', 1:'b'}
>>> a
{1: 'b'}
```
또 한 가지 주의해야 할 사항은 Key에 리스트는 쓸 수 없다는 것이다. 하지만 튜플은 Key로 쓸 수 있다. 리스트는 그 값이 변할 수 있기 때문에 Key로 쓸 수 없다. 

## 딕셔너리 관련 함수들 
### Key 리스트 만들기(keys)
```py
>>> a = {'name': 'pay', 'phone': '01032158847', 'birth': '1116'}
>>> a.keys()
dict_keys(['name', 'phone', 'birth'])
```

dict_keys 객체는 다음과 같이 사용할 수 있다. 리스트를 사용하는 것과 차이가 없지만, 리스트 고유의 append, insert, pop, remove, sort 함수는 수행할 수 없다.
```py
>>> for k in a.keys():
...    print(k)
...
name
phone
birth
``` 
> ※ print(k)를 입력할 때 들여쓰기를 하지 않으면 오류가 발생하니 주의

```py
>>> list(a.keys())
['name', 'phone', 'birth']

>>> a.values()
dict_values(['pey', '0119993323', '1118'])

-key value 쌍 얻기 (items)

>>> a.items()
dict_items([('name', 'pey'), ('phone', '0119993323'), ('birth', '1118')])

-Key: Value 쌍 모두 지우기(clear)

>>> a.clear()
>>> a
{}

-Key로 Value얻기(get)

>>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
>>> a.get('name')
'pey'
>>> a.get('phone')
'0119993323'

- 해당 Key가 딕셔너리 안에 있는지 조사하기 (in)

>>> a = {'name':'pey', 'phone':'0119993323', 'birth': '1118'}
>>> 'name' in a 
True
>>> 'email' in a
False
```
[***출처***](https://wikidocs.net/16)

