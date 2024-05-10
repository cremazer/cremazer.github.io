---
title: "JAVA - 형변환 (캐스팅, casting)"
date: 2014-09-17 23:49:00
image: '/assets/img/java/20140917/java-type-conversion.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 형변환 (캐스팅, casting).
introduction: 자바(Java)에서 사용하는 변수(variable)를 다른 타입(type)으로 변환하는 방법에 대해 설명합니다.
---

형변환이란, 변수 또는 [리터럴](http://terms.naver.com/entry.nhn?docId=754453&cid=50324&categoryId=50324)의 타입을 다른 타입으로 변환하는 방법입니다.

아래의 코드들을 실행하여 결과를 확인해 보겠습니다.

```java

public class CastingTest {
	public static void main(String[] args) {
		byte a = 24;
		int b = 0;

		//크기가 작은 변수형을 큰 자료형에 값을 대입시키려 하기 때문에 정상으로 대입됩니다.
		b = a;

		System.out.println("a : " + a);
		System.out.println("b : " + b);
	}
}

```

코드를 실행해 보면, byte 변수 a 에는 24, int 변수 b 에도 24의 값이 들어있습니다.

```
<결과>
a : 24
b : 24
```


int 변수 b에 10을 더해 다시 변수 b 에 대입해 보겠습니다.

```java

public class CastingTest {
	public static void main(String[] args) {
		byte a = 24;
		int b = 0;

		//크기가 작은 변수형을 큰 자료형에 값을 대입시키려 하기 때문에 정상으로 대입됩니다.
		b = a;

		// b에 10을 더한값을 b에 저장한다.
		b = b + 10;

		System.out.println("a : " + a);
		System.out.println("b : " + b);
	}
}
```

코드를 실행해 보면, int 변수 b에는 34의 값이 들어있습니다.

```
<결과>
a : 24
b : 34
```


이제 byte 변후 a에 int 변수 b의 값을 대입해 보겠습니다.

```java

public class CastingTest {
	public static void main(String[] args) {
		byte a = 24;
		int b = 0;

		//크기가 작은 변수형을 큰 자료형에 값을 대입시키려 하기 때문에 정상으로 대입됩니다.
		b = a;

		//b에 10을 더한값을 b에 저장한다.
		b = b + 10;

		//b를 a에 대입
		a = b;

		System.out.println("a : " + a);
		System.out.println("b : " + b);
	}
}

```

이클립스에서 위의 코드를 작성하고 저장을 하면, 크기가 큰 변수형을 작은 자료형에 값을 대입시키려 하기 때문에 에러가 발생합니다. 

```
error message : Type mismatch: cannot convert from int to byte.
```

이클립스에서 코드를 강제로 실행하면, 아래와 같은 메시지를 확인할 수 있습니다.

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
	Type mismatch: cannot convert from int to byte

	at CastingTest.main(CastingTest.java:14)

```

실제로 byte 변수 a에는 34의 값이 들어갈 수는 있지만, **컴파일러**는 <u>자료형의 크기를 먼저 비교하기 때문에</u> 코드 에러를 발생시켰습니다.


이런 경우, **크기가 큰 자료형(int)을 작은 자료형(byte)으로 변환해 주어서** a에 b의 값을 대입할 수 있습니다.

아래와 같이 코드를 변경해 보겠습니다.
```java

public class CastingTest {
	public static void main(String[] args) {
		byte a = 24;
		int b = 0;

		//크기가 작은 변수형을 큰 자료형에 값을 대입시키려 하기 때문에 정상으로 대입됩니다.
		b = a;

		//b에 10을 더한값을 b에 저장한다.
		b = b + 10;

		//b를 a의 데이터형으로 변환(casting)하여 a에 대입
		a = (byte) b;

		System.out.println("a : " + a);
		System.out.println("b : " + b);
	}
}
```

코드를 실행해 보면 위와같이 a에는 34, b에도 34가 들어있게 됩니다.

```
<결과>
a : 34
b : 34
```

위의 예제를 통해 살펴봤듯이, 크기가 큰 자료형 변수를 작은 자료형 변수에 값을 대입할 때는 **반드시 작은 자료형으로 형변환(casting)을 해 주어야 합니다.**
