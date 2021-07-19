# How to swap in python

## Use a temporary variable

```python
a, b = 3, 7
temp = a
a = b
b = temp
```

<br>

## Pythonic! 

```python
x, y = 1, 5
y, x = x, y
```



### _내부적으로 일어나는 일_ 

파이썬에서 `{somethings} = x, y` 와 같은 코드가 실행이 될 때, 내부적으로는 두 개의 elements 로 구성된  튜플 `(x, y)` 를 생성하게 된다.  즉 저러한 코드를 실행했을 때, 아래의 코드가 실행되는 상황과 equivalent 하다고 볼 수 있다. 아래 예시 참조.

```python 
x = "salil"
y = "Ajay"
temp = (x, y)  # evaluates to ("salil", "Ajay")
y, x = temp
```

_참조링크_ : <https://stackoverflow.com/questions/31374721/what-is-the-logic-for-x-y-y-x-to-swap-the-values>

<br>

## _cf. 쉽지만 창의적인 방법...!_

```python
x, y = 5, 8
x = x + y
y = x - y
x = x - y 
# Swap 완료!
```

