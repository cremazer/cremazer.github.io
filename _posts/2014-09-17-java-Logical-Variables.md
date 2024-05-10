---
title: "JAVA - 논리형 변수 boolean"
date: 2014-09-17 00:46:00
image: '/assets/img/java/20140917/java_Logical_Variables.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 논리형 변수 boolean.
introduction: 자바(Java)에서 사용하는 논리형 변수 boolean에 대해 설명합니다.
---

논리형 변수 `boolean`은 **참(true)**과 **거짓(false)**으로 구분할 때 사용합니다.

이 변수의 크기는 기본형중에서 가작 작은 1 byte입니다.

변수의 초기화 방법은 아래와 같이 입력합니다.

```java
boolean check = true;
boolean check = false;
```

값은 대문자가 아닌 소문자만 줄 수 있으며, 대문자로 설정하면 에러가 발생합니다.

```java
public class BooleanTest {
	public static void main(String[] args) {
		boolean test2 = true;
		boolean test1 = TRUE; //error message : TRUE cannot be resolved to a variable
	}
}
```

논리형 변수는 조건문(if)의 조건 또는 반복문(for, while)의 조건에 사용되며, 무한반복문을 빠져나올 때도 쓰입니다.

※ 무한반복문 예

```java
while(true){
  //조건문을 사용하여 빠져나오는 코드를 작성합니다.
}
```
