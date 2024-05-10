---
title: "Python - 큐"
date: 2021-04-01 07:48:34
image: '/assets/img/python/20210401/00-Python-Queue.jpg'
description: Practice writing queue in Python.
category: 'python'
tags:
- python
- data structure
- queue
twitter_text: Python - Practice writing queue in Python.
introduction: 파이썬으로 큐(Queue) 자료구조를 학습합니다.
---

# 개요

이 포스트에서는 자료구조 `큐(Queue)`에 대한 내용을 파일썬으로 코드를 작성하며 학습합니다.

# 1. 큐(Queue)란?

- 가장 먼저 넣은 데이터를 가장 먼저 꺼낼 수 있는 자료 구조.
- FIFO(First In First Out)
- 예, 매표소 앞 대기줄. 먼저 줄을 선 사람이 먼저 표를 산다.


### 관련 용어

- Enqueue : 데이터를 넣는다.
- Deququq : 데이터를 꺼낸다.


### 시각화로 이해하기

- [VISUALGO.net](https://visualgo.net/ko/list)

![그림1.](/assets/img/python/20210401/01-visualgo-queue.png)


### 코드 연습

```python
# 큐 라이브러리를 import
import queue

# 일반적인 큐 (FIFO : First-In, First-Out)
data_queue = queue.Queue()
# 데이터 넣기
data_queue.put('Lucky')
data_queue.put('20210401')

# 등록된 데이터 개수 확인
size = data_queue.qsize()
print('size=', size)

# 큐에서 데이터 꺼내기(get)
print(data_queue.get())
# 등록된 데이터 개수 확인
print('size=', data_queue.qsize())
print(data_queue.get())
```

- output

    size= 2
    Lucky
    size= 1
    20210401

---

### LIFO Queue

- LIFO : Last-In, First-Out
- 마지막에 넣은 데이터가 먼저 나온다.

`LIFO Queue`는 `Stack`의 구조와 같아 보이는데, 왜 LIFO Queue라고 정의해서 사용하는 것일까?

- LIFO Queue는 결국 Stack의 자료구조와 같음.
- 파이썬에서 queue 라이브러리에서 제공하는 방식 중에 LIFO Queue라고 있으며, 상황에 따라 결국 Stack을 사용하는 의미임.
- 결론 : LIFO Queue는 Stack이다.

### 코드 연습

```python
# 큐 라이브러리를 import
import queue

# Lifo 큐 (LIFO : Last-In, First-Out)
lifo_queue = queue.LifoQueue()
# 데이터 넣기
lifo_queue.put('Joy')
lifo_queue.put('20210401')

# 등록된 데이터 개수 확인
size = lifo_queue.qsize()
print('size=', size)

# 큐에서 데이터 꺼내기(get)
print(lifo_queue.get())
# 등록된 데이터 개수 확인
print('size=', lifo_queue.qsize())
print(lifo_queue.get())
```

- output

    size= 2
    20210401
    size= 1
    Joy

### PriorityQueue (우선순위 큐)

- 데이터를 넣는 우선순위에 따라 꺼내는 순서가 달라진다.
- 자료구조나 알고리즘 정책에서 쓰일 수 있음.

```python
# 큐 라이브러리를 import
import queue

# 우선순위 큐 (Priority Queue)
priority_queue = queue.PriorityQueue()

# 데이터 넣기 (우선순위, 데이터)
priority_queue.put((10, "Computer"))
priority_queue.put((5, "House"))
priority_queue.put((20, "Car"))

# 등록된 데이터 개수 확인
size = priority_queue.qsize()
print('size=', size)

# 큐에서 데이터 꺼내기(get)
print(priority_queue.get())
```

- output

    size= 3
    (5, 'House')

- 우선순위 큐에서는 우선순위로 설정한 숫자가 낮은 데이터가 가장 먼저 나온다.


### 큐의 사용

- 운영체제의 멀티태스킹을 위한 프로세스 스케쥴링 방식을 구현할 때 주로 사용됨.

### 리스트(list)를 사용하여 큐 기능 구현하기

```python
# 리스트를 활용하여 큐 기능 구현하기
queue_list = list()

# 데이터를 넣는 함수
def enqueue(data):
    queue_list.append(data)

# 데이터를 꺼내는 함수
def dequeue():
    data = queue_list[0]
    # 데이터를 꺼낸 후에 리스트에서 삭제해줘야 한다.
    del queue_list[0]
    return data

# 데이터 넣기 (0부터 9)
for index in range(10):
    enqueue(index)

# 등록된 리스트 개수 확인
print('list size=', len(queue_list))

# 큐에서 데이터 추출하기
print(dequeue())
print(dequeue())
print(dequeue())
```

- output

    list size= 10
    0
    1
    2

