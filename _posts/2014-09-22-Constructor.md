---
title: "JAVA - 생성자(Constructor)란?"
date: 2014-09-22 00:23:59
image: '/assets/img/java/20140922/Constructor.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 생성자(Constructor)란?
introduction: 자바(Java)에서의 생성자에 대해 알아봅니다.
---


# 1. 생성자(Constructor)란??

- 인스턴스가 생성될 때마다 호출되는 인스턴스 초기화 메서드 
- 인스턴스 변수의 초기화 또는 인스턴스 생성시 수행할 작업에 사용 
- 몇가지 조건을 제외하고는 메서드와 같습니다. 
- 모든 클래스에는 반드시 하나 이상의 생성자가 있어야 합니다.

<br>
<b>▶ 생성자의 조건</b>

- 생성자의 이름은 클래스의 이름과 같아야 합니다. 
- 생성자는 리턴값이 없습니다.

<br>
<b>▶ 생성자 정의</b>

```
클래스이름 (타입 변수명, 타입 변수명, ...) {
	//인스턴스 생성시 수행될 코드

	//주로 인스턴스 변수의 초기화 코드를 적습니다.
}
```

<br>
<b>▶ 생성자의 유형</b>

```java
class Card{
	...

	Card(){        //매개변수가 없는 생성자.
		//...
	}

	Card(String shape, int num)( //매개변수가 있는 생성자
		//...
	}

	...
}
```

<br>
<b>▶ 생성자 호출하기</b>

```java
Card card = new Card(); //인자가 없는 생성자 호출
Card card2 = new Card("Heart", 7); //인자가 있는 생성자 호출
```

<br>
<b>▶ 생성자 예제코드</b>

Card.java

```java
/**
 * @file name : Card.java
 * @date : 2013. 8. 15.
 * @discription : 카드 클래스
 * @author Cremazer(cremazer@gmail.com)
 */
public class Card {

	String shape = "Spade"; // 카드 모양
	int num = 1; // 카드 번호

	Card() {
		System.out.println(shape + " " + num + " 카드를 생성하였습니다.");
	}

	Card(String shape, int num) {
		System.out.println(shape + " " + num + " 카드를 생성하였습니다.");
	}
}
```

<br>
CardTest.java

```java
/**
 * @file name : CardTest.java
 * @date : 2013. 8. 15.
 * @discription : 카드를 생성하는 클래스
 * @author Cremazer(cremazer@gmail.com)
 */
public class CardTest {
	public static void main(String[] args) {
		Card card1 = new Card();
		Card card2 = new Card("Heart", 4);
	}
}
```

<br>
<b>▶ 결과</b>

```
Spade 1 카드를 생성하였습니다.
Heart 4 카드를 생성하였습니다.
```

<br>
`card1`인스턴스는 생성할 때 인자값이 없으므로 디폴트 카드가 생성되었고, `card2`인스턴스는 생성할 때 인자값을 넘겨주어 모양과 값이 있는 카드가 생성되었습니다.

이처럼 Java에서 생성자는 클래스를 처음 만들 때 사용하는 `new` 연산자를 통해 호출되며, `객체(Object)를 생성`하려면 반드시 `생성자`가 호출되어야 합니다.
