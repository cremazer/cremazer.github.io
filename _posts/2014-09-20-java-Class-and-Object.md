---
title: "JAVA - 클래스와 객체(Class and Object)"
date: 2014-09-20 00:42:00
image: '/assets/img/java/20140920/java-Class-and-Object.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 클래스와 객체(Class and Object).
introduction: 자바(Java)의 클래스(Class)와 객체(Object)에 대한 개념 및 이해를 돕기 위해 구현 예제로 설명합니다.
---

# 1. 클래스와 객체의 정의와 용도

[클래스(Class)](http://terms.naver.com/entry.nhn?docId=817824&cid=42344&categoryId=42344)란 '객체를 정의해 놓은 것', 또는 클래스는 '객체의 설계도 또는 틀'이라고 정의할 수 있습니다. 클래스는 객체를 생성하는 데 사용되며, 객체는 클래스에 정의된 대로 생성됩니다.

- 클래스의 정의 - 클래스란 객체를 정의해 놓은 것.
- 클래스의 용도 - 클래스는 객체를 생성하는데 사용됩니다.


[객체(Object)](http://terms.naver.com/entry.nhn?docId=844903&cid=42346&categoryId=42346)의 사전적인 정의는 '실제로 존재하는 것'입니다. 우리가 주변에서 볼 수 있는 책상, 의자, 자동차와 같은 사물들이 곧 객체입니다.

- 객체의 정의 - 실제로 존재하는 것, 사물 또는 개념.
- 객체의 용도 - 객체가 가지고 있는 기능과 속성에 따라 다릅니다.


> 이렇게 생각해보면 어떨까요?

추운 겨울이 오면, 길가에서 파는 붕어빵이 생각납니다.

붕어빵은 무엇인가요?

밀가루 반죽에 노릇노릇 구워진 붕어 모양의 빵 안에 맛있는 팥이 들어있는 빵입니다.


[붕어빵](https://ko.wikipedia.org/wiki/%EB%B6%95%EC%96%B4%EB%B9%B5)을 정의해 보면,

- 밀가루 반죽으로 된 빵.
- 붕어모양.
- 실제 붕어는 아니다.(죽어있다?)
- 팥이 들어있음.

으로 정의할 수 있습니다.

이렇게 <b><u>생각하여 정의한 것</u></b>을 `클래스(Class)`라고 하고 실제로 <b><u>붕어빵 틀에 의해 생성된 붕어빵</u></b>을 `객체(Object)`라고 합니다.


아래 그림을 살펴봅시다.

![그림1. 20180105_001_java-Class-and-Object](/assets/img/java/20140920/20180105_001_java-Class-and-Object.jpg)

위의 그림에서 보듯이 `붕어빵 모양 틀`을 <u>클래스</u>, 붕어빵 모양 틀에 의해 만들어진 `붕어빵`을 <u>객체</u>라고 합니다.

<br>
# 2. 객체와 인스턴스

클래스로부터 객체를 만드는 과정을 **클래스의 인스턴스화**라고 하며, 어떤 클래스로부터 만들어진 객체를 그 클래스의 **인스턴스**라고 합니다.

![그림2. 20180105_002_java-Objects-and-Instances](/assets/img/java/20140920/20180105_002_java-Objects-and-Instances.jpg)

인스턴스와 객체는 같은 의미이므로 헷갈리지 않게 그냥 객체라고 이해하세요. 문맥상 인스턴스라고 해야 하겠지만, 공부하다보면 흔히 객체라고 이야기 합니다.

<br>
# 3. 객체의 구성요소

객체는 속성(attribute)과 기능(방법, method), 두 종류의 구성요소로 이루어져 있으며, 일반적으로 객체는 다수의 속성과 기능을 가지고 있습니다.

- 속성 - 멤버변수, 특성, 필드, 상태
- 기능 - 메서드, 행위, 함수

TV를 예로 들어 보겠습니다.

> 아래의 그림과 같이 TV의 색상, 전원상태, 채널 등을 속성이라고 하고, TV가 하는 켜거나 끈다, 채널을 돌린다(높이거나 낮춤) 등을 기능이라고 보시면 됩니다.

![그림3. 20180105_003_java-The-components-of-an-object](/assets/img/java/20140920/20180105_003_java-The-components-of-an-object.jpg)

<br>
# 4. 객체의 생성과 사용예제

위의 3.에서 TV클래스를 살펴보았으니, 이제 TV클래스를 이용해서 Java 객체를 만들어 봅시다. 클래스를 이용하여 객체를 만드는 방법은 다음과 같이 두 가지 방법으로 만들 수 있습니다.


첫 번째 방법은 클래스 변수를 선언하고, 변수에 new 연산자를 사용하여 클래스를 생성합니다.

▶ 방법1

```
클래스명 변수명;

변수명 = new 클래스명();
```

두 번째 방법은 클래스 변수를 선언함과 동시에 new 연산자를 사용하여 클래스를 생성하는 방법입니다. 즉, 방법1을 짧게 줄여 표현한 식입니다.


▶ 방법2

```
클래스명 변수명 = new 클래스명();
```
```java
TV t = new TV();
```

위와 같은 코드로 TV 객체를 생성할 수 있습니다.

객체를 생성할 때는 `new` 연산자를 사용한다는게 포인트!


**자바의 정석**에서는 예제코드를 파일 하나에 모두 작성하였지만, 여기서는 클래스가 TV 클래스, TvTest 클래스 2개이므로 파일도 2개로 분리하였습니다.

```
※ 주의!
파일이 2개로 분리되었을 때 함께 사용할 경우, 2개의 파일은 같은 폴더내에 존재해야 합니다.
(나중에 패키지를 공부할 때는 클래스가 같은 폴더에 없어도 참조하여 사용할 수 있습니다.)
```

▶ 예제1

TV.java

```java
/**
 * @file name : TV.java
 * @date : 2013. 8. 14.
 * @discription : TV 클래스
 * @author Cremazer
 */
public class TV {

	// TV의 속성(멤버변수)
	String color;

	boolean power;

	int channel;

	// TV의 기능(메서드)
	void power() {
		power = !power;
	}

	void channelUp() {
		++channel;
	}

	void channelDown() {
		--channel;
	}

}
```

TV클래스는 클래스를 정의한 것이기 때문에 실행할 수 없습니다.

TvTest.java

```java
/**
 * @file name : TvTest.java
 * @date : 2013. 8. 14.
 * @discription : TV 객체를 생성하고 컨트롤하는 클래스
 * @author Cremazer
 */
public class TvTest {
	public static void main(String[] args) {
		TV t = new TV(); // TV객체 생성
		t.channel = 7; // TV객체의 멤버변수 channel값을 7로 설정
		t.channelDown(); // TV객체의 채널을 낮추는 메서드 실행
		System.out.println("현재 채널은 " + t.channel + " 입니다.");
	}
}
```

TvTest 를 실행시키면 아래의 결과를 얻을 수 있습니다.


▶ 결과
```
현재 채널은 6 입니다.
```

TvTest의 TV객체를 나타내는 변수 t는 TV객체를 컨트롤 할 수 있는 리모콘이라고 생각하면 어떨까요?

리모콘(t)으로 숫자를 눌러 채널을 설정하거나 ( t.channel = 7 )

TV를 끄고 켜거나( void power() ),

채널을 올리거나( void channelUp() ), 내릴 수 있습니다.( void channelDown() )

![그림4. 20180105_004_java-The-components-of-an-object](/assets/img/java/20140920/20180105_004_java-The-components-of-an-object.jpg)


▶ 예제2

이번에는 TV객체 2개를 만들어 봅시다.

TvTest.java파일을 수정하여 컴파일을 한 다음, 다시 실행해 봅시다.

TvTest.java

```java
/**
 * @file name : TvTest.java
 * @date : 2013. 8. 14.
 * @discription : TV 객체를 생성하고 컨트롤하는 클래스
 * @author Cremazer
 */

public class TvTest {
	public static void main(String[] args) {
		TV t1 = new TV(); // TV객체 생성 - t1
		TV t2 = new TV(); // TV객체 생성 - t2

		t1.channel = 7;
		t1.channelDown(); // 채널 내리기

		t2.channel = 7;
		t2.channelUp(); // 채널 올리기
		t2.channelUp(); // 채널 올리기
		t2.channelUp(); // 채널 올리기

		System.out.println("현재 t1 채널은 " + t1.channel + " 입니다.");
		System.out.println("현재 t2 채널은 " + t2.channel + " 입니다.");
	}
}
```

▶ 결과
```
현재 t1 채널은 6 입니다.
현재 t2 채널은 10 입니다.
```

t1과 t2는 형태는 같은 TV지만 서로 다른 객체이므로 t1은 채널이 7에서 한번 내려서 채널이 6이 되었고, t2는 채널이 7에서 세번 올려서 채널이 10이 되었습니다.

![그림5. 20180105_005_java-The-components-of-an-object](/assets/img/java/20140920/20180105_005_java-The-components-of-an-object.jpg)

붕어빵과 TV를 통해 클래스와 객체의 개념을 간단하게 알아보았습니다.
