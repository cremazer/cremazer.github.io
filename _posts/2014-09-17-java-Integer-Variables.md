---
title: "JAVA - 정수형 변수 byte, short, int, long"
date: 2014-09-17 23:46:00
image: '/assets/img/java/20140917/java_Integer_Variables.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 정수형 변수 byte, short, int, long.
introduction: 자바(Java)에서 사용하는 정수형 변수 byte, short, int, long에 대해 설명합니다.
---

Java에서 사용하는 정수형 변수들을 각 자료형을 크기별로 나열하면 아래와 같습니다.

<table>
  <tr>
    <td colspan="4">byte < short < int < long</td>
  </tr>
  <tr>
    <td>byte</td><td>short</td><td>int</td><td>long</td>
  </tr>
  <tr>
    <td>1 byte</td><td>2 byte</td><td>4 byte</td><td>8 byte</td>
  </tr>
</table>

각 정수형 변수들의 초기값은 아래와 같은 형태로 입력하여 코드를 작성합니다.

```java
byte a = 1;
short b = 2;
int c = 3;
long = 4L;      //long형은 반드시 뒤에 '대문자 L' 또는 '소문자 l'을 붙여야 한다.
```

> 자바에서의 숫자의 default 자료형은 int 입니다.
