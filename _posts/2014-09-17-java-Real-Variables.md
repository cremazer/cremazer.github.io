---
title: "JAVA - 실수형 변수 float, double"
date: 2014-09-17 23:48:00
image: '/assets/img/java/20140917/java_Real_Variables.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 실수형 변수 float, double.
introduction: 자바(Java)에서 사용하는 실수형 변수 float, double에 대해 설명합니다.
---

실수형 변수 float, double는 Java에서 소수점 단위의 숫자를 표현하고 할 때 사용합니다.

실수형 변수의 자료형 크기는 아래와 같습니다.

<table>
  <tr>
    <td colspan="2">float < double</td>
  </tr>
  <tr>
    <td>float</td><td>double</td>
  </tr>
  <tr>
    <td>4 byte</td><td>8 byte</td>
  </tr>
</table>

각 변수들의 초기값은 아래와 같은 형태로 입력하여 코드를 작성합니다.

```java
public class RealVariablesTest {
	public static void main(String[] args) {
		float a = 3.4f;        //float 자료형은 뒤에 '대문자 F' 또는 '소문자 f'를 반드시 붙여야 한다.
		double b = 9.9;     //double는 뒤에 d를 생략할 수 있다.

		System.out.println("a : " + a);
		System.out.println("b : " + b);
	}
}
```

```
<결과>
a : 3.4
b : 9.9
```

> 실수형 변수의 default 자료형은 double입니다.
