---
title: "Python - 배열"
date: 2021-03-30 07:31:34
image: '/assets/img/python/20210330/00-Python-Array.jpg'
description: Practice writing arrays in Python.
category: 'python'
tags:
- python
- data structure
- array
twitter_text: Python - Practice writing arrays in Python.
introduction: 파이썬으로 배열 자료구조를 학습합니다.
---

# 개요

이 포스트에서는 자료구조 `배열(Array)`에 대한 내용을 파일썬으로 코드를 작성하며 학습합니다.

# 1. 배열이란?

- 데이터를 나열하고, 각 데이터를 인덱스(index)에 대응하도록 구성한 데이터 구조.
- 유사한 데이터를 정해진 공간에 넣을 수 있다.
- 인덱스(index)는 0부터 시작한다.
- 배열의 2번째 값은 index = 1로 데이터 접근이 가능하다.

### 필요성

- 같은 종류의 데이터를 효과적으로 관리하기 위함.
- 같은 종류의 데이터를 순차적으로 저장.

### 장점

- 데이터의 접근이 빠르다.

### 단점

- 데이터의 공간을 미리 생성해야 한다.
- 데이터를 추가하거나 삭제하는 것이 쉽지 않다.

# 2. 파이썬의 배열

- 데이터의 공간을 미리 생성하지 않고, 값을 입력하면 자동으로 공간이 생성된다.

### 1차원 배열

```python
# 1차원 배열 (리스트로 구현)
data1 = [1,2,3,4,5]
print(data1)
```

- output

    [1, 2, 3, 4, 5]

```python
# 2차원 배열 (리스트로 구현)
data2 = [[1,2,3],[4,5,6],[7,8,9]]
print(data2)
print(data2[0])
print(data2[0][0])
print(data2[0][1])
print(data2[0][2])
print(data2[1][0])
```

- output

    [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    [1, 2, 3]
    1
    2
    3
    4

```python
# data2에서 9,8,7 순서로 출력
print(data2[2][2])
print(data2[2][1])
print(data2[2][0])
print(data2[2][2], data2[2][1], data2[2][0])
```

- output

    9
    8
    7
    9 8 7

```python
# dataset에서 문자 'M'이 포함된 문자열 개수 출력
dataset = [
'Vander',
'Miss. Ellen',
'Masselmani',
'Todoroff',
'Mr.William'
]

# 빈도수 변수 선언
m_count = 0
for str in dataset:
    #print(str)
    # 문자열 길이만큼 반복
    for index in range(len(str)):
        #print(str[index])
        if str[index] == 'M':
            #M이 있으면 빈도수 1씩 증가
            #m_count = m_count + 1 줄임표현식
            m_count += 1

print(m_count)
```

- output

    3

