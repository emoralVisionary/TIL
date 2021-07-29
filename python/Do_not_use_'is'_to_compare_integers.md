# Do not use 'is' to compare integers

```python
a = 256
b = 256
a is b
# True          

a = 257
b = 257
a is b
# False # What happened here? Why is this False?
257 is 257
# True # Yet the literal numbers compare properly
```

## Python 2.x Document 내용

> "Plain integer objects"
>
> The current implementation keeps an array of integer objects for all integers between -5 and 256, when you create an int in that range you actually just get back a reference to the existing object. So it should be possible to change the value of 1. I suspect the behaviour of Python in this case is undefined.

정리하자면, 파이썬은 우리가 자주 사용하는 범위의 정수들에 대해서는 이미 integer object 들을 정의해놓고 있다. 따라서 assign 한 정수의 값에 따라 **'is'** 로 비교했을 때 _True_ 가 리턴될 때도 있고, _False_ 가 리턴될 때도 있는 것. **이미 정의되어있는 (사전에 책상 위에 놓여 있는) 정수의 범위는 [-5, 256] 이다.**



## Operator **_'is'_** 에 대한 코멘트 

> The operators [`is`](https://docs.python.org/2/reference/expressions.html#is) and [`is not`](https://docs.python.org/2/reference/expressions.html#is-not) test for object identity: `x is y` is true if and only if *x* and *y* are the same object.

같은 객체일 때만 _True_ 를 리턴한다고 한다! 즉,  **_'is'_** 를 통한 비교는 본질적으로 `id(var)` 의 결과를 비교하는 것과 동일하다.  `id(var)` : 변수의 고유 _Identity_ 값 (메모리 주소) 을 리턴한다. 

```python
a is b
id(a) == id(b)
```



## 고찰 

생각해보면, 우리가 자주 사용하는 숫자들을 assign 할 때마다 새로운 객체를 생성하는 것은 메모리 차원에서 상당히 큰 낭비가 될 수 있을 것이다. 이러한 메모리의 낭비를 줄이기 위해 이러한 방식을 채택한 듯!

_**참고 자료**_: <https://stackoverflow.com/questions/306313/is-operator-behaves-unexpectedly-with-integers>

__*__ __객체, OOP 진도 나가고 나서 링크 참조해서 내용 보충할 것! __  
