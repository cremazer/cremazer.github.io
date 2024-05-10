---
title: "Python - 스택"
date: 2021-04-08 07:48:34
image: '/assets/img/python/20210408/00-Python-Stack.jpg'
description: Practice writing stack in Python.
category: 'python'
tags:
- python
- data structure
- stack
twitter_text: Python - Practice writing stack in Python.
introduction: 파이썬으로 스택(Stack) 자료구조를 학습합니다.
---

# 개요

이 포스트에서는 자료구조 `스택(Stack)`에 대한 내용을 파일썬으로 코드를 작성하며 학습합니다.

# 1. 스택(Stack)이란?

- 가장 나중에 넣은 데이터를 가장 먼저 꺼낼 수 있는 데이터 구조.
- LIFO(Last In First Out)
- 예, 컴퓨터 내부에서 프로세스가 실행될 때 함수가 동작하는 방식. 가장 마지막에 실행된 함수가 가장 먼저 끝난다.

### 관련 용어

- push : 데이터를 넣는다.
- pop : 데이터를 꺼낸다.

### 시각화로 이해하기

- [VISUALGO.net](https://visualgo.net/ko/list)

![그림1.](/assets/img/python/20210408/01-visualgo-stack.png)


### 코드 연습

```python
# 재귀함수
def recursive(data):
    if data < 0:
        print("ended")
    else:
        print(data)
        recursive(data - 1)
        print("returned", data)

# 재귀함수 호출
recursive(4)
```

- output :

    4
    3
    2
    1
    0
    ended
    returned 0
    returned 1
    returned 2
    returned 3
    returned 4
---


### 장점

- 구조가 단순해서 구현이 쉽다.
- 데이터를 저장하고 읽는 속도가 빠르다.


### 단점

- 입력할 데이터의 최대 개수를 미리 정해야 한다.
- 파이썬에서는 재귀함수를 1000번까지 호출이 가능하다. 미리 공간을 1000개 만큼 정해져 있기 때문이다.


### 코드 연습

```python
# 리스트를 활용한 스택 사용해보기
data_stack = list()

data_stack.append(1)
data_stack.append(2)

# 리스트 출력
print(data_stack) 

# 리스트에서 데이터 꺼내기
print(data_stack.pop())

```

- output

    [1, 2]
    2


### 리스트를 활용한 Stack 기능 구현(push, pop)

스택의 원리를 이해하기 위해 stack의 기능을 구현해본다.

```python
# pop, push 기능 구현
stack_list = list()

def push(data):
    stack_list.append(data)

def pop():
    # 마지막 데이터를 data에 설정한다.
    data = stack_list[-1]
    del stack_list[-1]
    return data


# 데이터 넣기
for index in range(10):
    push(index)

# 데이터 꺼내기

print(pop())
```


- output

    9

