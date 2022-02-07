## if문의 기본 구조
-------
```py
if 조건문:
    수행할 문장1
    수행할 문장2
    ...
else:
    수행할 문장A
    수행할 문장B
    ...
```
if문을 만들 때는 if 조건문: 바로 아래 문장부터 if문에 속하는 모든 문장에 들여쓰기(indentation)를 해주어야 한다
또 들여쓰기는 언제나 같은 너비로 해야 한다.
> **[조건문 다음에 콜론(:)을 잊지 말자!]**

## x in s, x not in s
파이썬은 다른 프로그래밍 언어에서 쉽게 볼 수 없는 재미있는 조건문을 제공한다.

바로 다음과 같은 것들이다.
```py
  in	      not in
x in 리스트	x not in 리스트
x in 튜플	x not in 튜플
x in 문자열	x not in 문자열

>>> 1 in [1, 2, 3]
True
>>> 1 not in [1, 2, 3]
False

```
앞에서 첫 번째 예는 "[1, 2, 3]이라는 리스트 안에 1이 있는가?" 조건문이다. 1은 [1, 2, 3] 안에 있으므로 참이 되어 True를 돌려준다. 두 번째 예는 "[1, 2, 3] 리스트 안에 1이 없는가?" 조건문이다. 1은 [1, 2, 3] 안에 있으므로 거짓이 되어 False를 돌려준다.

> "만약 주머니에 돈이 있으면 택시를 타고, 없으면 걸어 가라."
```py
>>> pocket = ['paper', 'cellphone', 'money']
>>> if 'money' in pocket:
        print("택시를 타고 가라")
    else:
        print("걸어가라")
...
택시를 타고 가라
```

### [조건문에서 아무 일도 하지 않게 설정하고 싶다면?]
> "주머니에 돈이 있으면 가만히 있고 주머니에 돈이 없으면 카드를 꺼내라."
이럴 때 사용하는 것이 바로 pass이다. 위 예를 pass를 적용해서 구현해 보자.

```py
>>> pocket = ['paper','money','cellphone']
>>> if 'money' in pocket:
        pass
    else:
        print("카드를 꺼내라")

```
pocket 리스트 안에 money 문자열이 있기 때문에 if문 다음 문장인 pass가 수행되고 아무 결괏값도 보여 주지 않는다.

## 다양한 조건을 판단하는 elif
-----
if와 else만으로는 다양한 조건을 판단하기 어렵다. 다음 예를 보더라도 if와 else만으로는 조건을 판단하는 데 어려움을 겪게 된다.
> "주머니에 돈이 있으면 택시를 타고, 주머니에 돈은 없지만 카드가 있으면 택시를 타고, 돈도 없고 카드도 없으면 걸어 가라."

다중 조건 판단을 가능하게 하는 elif를 사용하면 이런 복잡함을 해결해준다.
```py
>>> pocket = ['paper', 'cellphone']
>>> card = True
>>> if 'money' in pocket:
        print("택시를 타고 가라")
    elif card:
        print("택시를 타고 가라")
    else:
        print("걸어가라")
    ...
    택시를 타고가라
```
## 조건부 표현식
```py
if score >= 60:
    message = "success"
else:
    message = "failure"
```
위 코드는 score가 60 이상일 경우 message에 문자열 "success"를, 아닐 경우에는 "failure"를 대입하는 코드이다.

파이썬의 조건부 표현식(conditional expression)을 사용하면 위 코드를 다음과 같이 간단히 표현할 수 있다.
```py
message = "success" if score >= 60 else "failure"
```
조건부 표현식은 다음과 같이 정의한다.

*조건문이 참인 경우* if *조건문* else *조건문이 거짓인 경우*

조건부 표현식은 가독성에 유리하고 한 줄로 작성할 수 있어 활용성이 좋다.

[출처](https://wikidocs.net/20)