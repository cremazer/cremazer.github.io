---
title: "JAVA - 메서드 오버로딩(Method overloading)"
date: 2014-09-22 00:15:00
image: '/assets/img/java/20140922/method-overloading.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 메서드 오버로딩(Method overloading).
introduction: 하나의 클래스에 같은 이름의 메서드를 여러 개 정의하는 것을 메서드 오버로딩, 간단히 오버로딩이라고 합니다.
---


# 메서드 오버로딩(Method Overloading)이란? 

`하나의 클래스에 같은 이름의 메서드를 여러 개 정의하는 것`을 메서드 오버로딩, 간단히 오버로딩이라고 합니다.

<br>
<b>▶ 오버로딩의 조건</b>

- 메서드의 이름이 같아야 합니다.
- 매개변수의 개수 또는 타입이 달라야 합니다.
- 매개변수는 같고, 리턴타입이 다른 경우는 오버로딩이 성립하지 않습니다.(리턴타입은 오버로딩을 구현하는데 아무런 영향을 주지 못하기 때문입니다.)

<br>
<b>▶ 오버로딩의 예</b>

대표적인 예제는 Java에서 자주 사용하는 [println()](https://docs.oracle.com/javase/8/docs/api/java/io/PrintStream.html#println--)메서드입니다.

```java
void println()

void println(boolean x)

void println(char x)

void println(char[] x)

void println(double x)

void println(float x)

void println(int x)

void println(long x)

void println(Object x)

void println(String x)
```

<br>
아래의 add() 메서드도 오버로딩으로 구현되었습니다.

```java
int add(int a, int b){
	return a + b;
}

long add(double c, double d){
	return a + b;
}
```

<br>
예제를 통해 확인해보자.

```java
/**
 * @file name : OverloadingTest.java
 * @date : 2013. 8. 15.
 * @discription : 오버로딩 테스트 클래스
 * @author Cremazer(cremazer@gmail.com)
 */
public class OverloadingTest {

	int a = 1;
	int b = 2;
	double c = 1.5;
	double d = 2.5;

	int add() {
		return a + b;
	}

	int add(int x) {
		return a + x;
	}

	int add(int a, int b) {
		return a + b;
	}

	double mul() {
		return c * d;
	}

	double mul(double x) {
		return c * x;
	}

	double mul(double c, double d) {
		return c * d;
	}

	public static void main(String[] args) {
		OverloadingTest ot = new OverloadingTest();
		System.out.println(ot.add());
		System.out.println(ot.add(5));
		System.out.println(ot.add(4, 7));
		System.out.println(ot.mul());
		System.out.println(ot.mul(5.5));
		System.out.println(ot.mul(2.4, 5.5));
	}
}
```

<br>
<b>▶ 결과</b>
```
3
6
11
3.75
8.25
13.2
```

<br>
코드를 살펴보면

```java
int add(){ //매개변수 없음
	return a + b;
}

int add(int x){ //매개변수 1개
	return a + x;
}

int add(int a, int b){ //매개변수 2개
	return a + b;
}

double mul(){ //매개변수 없음
	return c * d;
}

double mul(double x){ //매개변수 1개
	return c * x;
}

double mul(double c, double d){ //매개변수 2개
	return c * d;
}
```

<br>
add() 메서드와 mul()에 대해 오버로딩을 사용하였습니다.

이와 같이 메서드명이 같고, 매개변수 가 다르게 구현된 메서드를 `메서드 오버로딩`이라고 합니다.

