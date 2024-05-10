---
title: "JAVA - 참조변수 this"
date: 2014-09-23 00:02:34
image: '/assets/img/java/20140923/Reference-this.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 참조변수 this
introduction: 자바(Java) 클래스에서 자기 자신을 가리키는 참조변수 this에 대해서 배우게 됩니다. 
---

Java에서 this는 [참조변수](http://terms.naver.com/entry.nhn?docId=835113&cid=50376&categoryId=50376)로 인스턴스 자신을 가리킵니다. 참조변수를 통해 인스턴스의 멤버변수에 접근할 수 있는 것처럼, this를 통해서 인스턴스 변수에 접근할 수 있는 것입니다.

쉽게 생각하면 this는 자기 자신을 가리키는 것이라고 볼 수 있습니다.

아래의 코드를 예로 살펴보겠습니다.

```java
class ThisTest1 {

	int a; //인스턴스 변수

	ThisTest1 (int a) {
		//a = a; //이름이 같아서 a가 서로 구분이 안된다.
		this.a = a; //ThisTest1.a = a; 와 같다.
	}
}
```

위의 코드에서 볼 수 있듯이 `this`는 **ThisTest1을 의미하는 것**이며, this.a 는 ThisTest1 클래스의 인스턴스 변수 a를 의미합니다.

하지만, this를 사용할 수 있는 것은 인스턴스 멤버뿐입니다. [static 메서드](https://en.wikipedia.org/wiki/Method_(computer_programming)#Static_methods)(클래스 메서드)에서는 인스턴스 멤버들을 사용할 수 없는 것처럼, this 역시 사용할 수 없습니다. 왜냐하면 static메서드는 인스턴스를 생성하지 않고도 호출될 수 있으므로, static메서드가 호출된 시점에는 인스턴스가 존재하지 않을 수도 있기 때문입니다.

<br>
# 생성자에서 다른 생성자 호출하기 - this()

<br>
<b>▶ 조건</b>

- 생성자의 이름으로 클래스이름 대신 this를 사용합니다. 
- 한 생성자에서 다른 생성자를 호출할 때는 반드시 첫 줄에서만 호출이 가능합니다.

<br>
<b>▶ 예제코드</b>

Card.java

```java
/**
 * @file name : CardTest.java
 * @date : 2013. 8. 15.
 * @discription : 카드를 생성하는 클래스
 * @file name : Card.java
 * @author Cremazer(cremazer@gmail.com)
 */
public class Card {

	String shape = "Spade"; // 카드 모양
	int num = 1; // 카드 번호

	Card() {
		System.out.println(shape + " " + num + " 카드를 생성하였습니다.");
	}

	Card(int num) {
		this("Heart", num);
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
		Card card2 = new Card(7);
	}

}
```

<br>
<b>▶ 결과</b>

```
Spade 1 카드를 생성하였습니다.
Heart 7 카드를 생성하였습니다.
```

<br>
위의 코드를 보면 첫번째 card1을 생성하면 기본 생성자를 호출하여 초기에 설정된 값인 Spade 1 카드를 만들었지만, card2를 생성할 때 7 을 인자로 넘기면, 매개변수를 숫자로 받는 생성자가 호출되어 this() 메서드를 이용하여 매개변수가 2개인 생성자를 호출하여 Heart 7 을 생성하였습니다.
