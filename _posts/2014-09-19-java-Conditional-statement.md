---
title: "JAVA - 조건문(if, switch)"
date: 2014-09-19 01:08:00
image: '/assets/img/java/20140919/java-Conditional-statement.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 조건문(if, switch).
introduction: 자바(Java)에서 사용하는 조건문인 if문과 switch문의 구조와 예제를 통해 내용을 이해합니다.
---

조건문은 조건식과 문장을 포함하는 블럭{}으로 구성되어 있으며, 조건식의 연산결과에 따라 프로그램의 실행흐름을 변경할 수 있습니다.

# if문

**▶ if ~ 구조**
```
if (조건식) {
    //조건식이 true일 때 수행될 코드들을 적습니다.
}
```

example)

```java
public class ConditionalStatementIfTest {
	public static void main(String[] args) {
		int a = 7;
		if( a < 10 ) {
		     System.out.println( a + "는 10보다 작은 수입니다." );
		}
	}
}
```
```
<결과>
7는 10보다 작은 수입니다.
```
<br>
**▶ if ~ else ~ 구조**
```
if (조건식) {
    //조건식이 true일 때 수행될 코드들을 적습니다.
} else {
    //조건식이 false일 때 수행될 코드들을 적습니다.
}
```

example)

```java
public class ConditionalStatementIfElseTest {
	public static void main(String[] args) {
		String sex = "여성";
		if ("남성".equals(sex)) {
		    System.out.println("남성입니다");
		}else {
		    System.out.println("여성입니다");
		}
	}
}
```
```
<결과>
여성입니다
```
<br>
**▶ if ~ else if ~ else ~ 구조**
```
if (조건식1) {
    //조건식1이 true일 때 수행될 코드들을 적습니다.
} else if (조건식2) {
    //조건식2가 true일 때 수행될 코드들을 적습니다.
} else {
    //위의 어느 조건식도 만족하지 않을 때 수행될 코드들을 적습니다.
}
```

example)

```java
public class ConditionalStatementElseIfTest {
	public static void main(String[] args) {
		int score = 85;
		if(score > 90) {
		    System.out.println("A학점");
		} else if (score > 80) {
		    System.out.println("B학점");
		} else {
		    System.out.println("C학점");
		}
	}
}
```
```
<결과>
B학점
```
<br>
# 중첩 if문

**▶ 구조**
```
if (조건식1) {
    //조건식1의 연산결과가 true일 때 수행될 코드들을 적습니다.

    if (조건식2) {
        //조건식1과 조건식2가 모두 true일 때 수행될 코드들을 적습니다.
    } else {
        //조건식1이 true이고, 조건식2가 false일 때 수행될 코드들을 적습니다.
    }
} else {
    //조건식1이 false일 때 수행될 코드들을 적습니다.
}
```

example)

```java
public class ConditionalStatementNestedIfTest {
	public static void main(String[] args) {
		int num = 37;
		if( num < 50 ) {
		    System.out.println("50보다 작은 수입니다.");

		    if( num > 25 ) {
		        System.out.println("25보다 큰 수입니다.");
		    } else {
		        System.out.println("25보다 작은 수입니다.");
		    }
		} else {
		    System.out.println("50보다 큰 수입니다.");
		}
	}
}
```
```
<결과>
50보다 작은 수입니다.
25보다 큰 수입니다.
```
<br>
# switch문

**▶ 구조**
```
switch (조건식) {
    case 값1:
        //조건식의 결과가 값1과 같은 경우 수행될 코드를 적습니다.
        break;
    case 값2:
        //조건식의 결과가 값2과 같은 경우 수행될 코드를 적습니다.
        break;
    case 값3:
        //조건식의 결과가 값3과 같은 경우 수행될 코드를 적습니다.
        break;

    //...

    default:
        //조건식의 결과가 일치하는 case문이 없을 때 수행될 코드들을 적습니다.
}
```

example)

```java
public class ConditionalStatementSwitchTest {
	public static void main(String[] args) {
		char type = 'B';

		switch(type){
		    case 'A':
		        System.out.println("A입니다.");
		        break;

		    case 'B':
		        System.out.println("B입니다.");
		        break;

		    case 'C':
		        System.out.println("C입니다.");
		        break;

		    default:
		        System.out.println("D입니다.");

		}
	}
}
```
```
<결과>
B입니다.
```


여기까지 Java에서 사용하는 조건문의 구조에 대해 알아봤습니다.

