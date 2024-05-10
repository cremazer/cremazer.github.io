---
title: "JAVA - 변수와 메서드(Variable and Method)"
date: 2014-09-22 00:11:00
image: '/assets/img/java/20140922/java-Variable-and-Method.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 변수와 메서드(Variable and Method).
introduction: 자바(Java)의 변수와 메서드에 대한 개념을 이해하고 메서드의 호출 원리를 배우게 됩니다.
---

# 1. 변수(variable)의 종류

변수는 클래스 변수(정적 변수), 인스턴스 변수(전역 변수), 지역 변수 모두 세 종류로 분류됩니다.

변수의 종류는 클래스에서 선언되는 위치에 따라 파악할 수 있습니다.

아래의 코드를 통해 변수의 종류를 살펴보겠습니다.

```java
public class Variables {

	int iv; // 인스턴스 변수

	static int cv; // 클래스 변수(정적 변수)

	void method() {
		int mv = 0; // 지역 변수
	}
}
```

여기서 알아둘 것은, 인스턴스 변수는 변수를 초기화 하지 않아도 항상 기본값이 설정됩니다.

```
int형 : 0
double형 : 0.0
boolean형 : false
레퍼런스형 : null (ex: String, ArrayList, .. 등)
```

메서드 안에서 생성되는 지역 변수는 초기값이 없기 때문에 반드시 변수의 초기화를 해주어야 합니다.

`클래스 변수(정적 변수)`는 그 클래스의 객체가 처음으로 만들어 지기 전에 초기화됩니다. 그리고 같은 클래스에 속하는 모든 인스턴스에서 정적 변수를 공유합니다.

아래의 예제 코드를 통해 변수의 값이 어떻게 변하는지 살펴보겠습니다.

**변수를 정의한 클래스**와 클래스를 만들고 **실행할 클래스**를 만들어 보겠습니다.

Variables.java

```java

public class Variables {

	int iv; // 인스턴스 변수

	static int cv; // 클래스 변수

	Variables() {
		iv++;
		cv++;
	}

	void method() {
		int mv = 0;

		System.out.println("지역 변수 : " + mv);
		System.out.println();
	}

	void print() {

		System.out.println(cv + "번째 객체가 생성되었습니다.");
		System.out.println("------------------------------");
		System.out.println("인스턴스 변수 : " + iv);
		System.out.println("클래스 변수 : " + cv);

	}
}
```

VariablesTest.java

```java
public class VariablesTest {
	public static void main(String[] args) {

		Variables v1 = new Variables();

		v1.print();
		v1.method();

		Variables v2 = new Variables();

		v2.print();
		v2.method();

		Variables v3 = new Variables();

		v3.print();
		v3.method();
	}
}
```

▶ 결과

```
1번째 객체가 생성되었습니다.
------------------------------
인스턴스 변수 : 1
클래스 변수 : 1
지역 변수 : 0

2번째 객체가 생성되었습니다.
------------------------------
인스턴스 변수 : 1
클래스 변수 : 2
지역 변수 : 0

3번째 객체가 생성되었습니다.
------------------------------
인스턴스 변수 : 1
클래스 변수 : 3
지역 변수 : 0
```

위의 결과에서 알 수 있듯이 `인스턴스 변수`는 인스턴스가 생성될 때마다 생성되어 초기화 되기 때문에 모두 1로 초기화 되지만, `클래스 변수`는 각 인스턴스가 변수를 공유하고 있기 때문에 인스턴스가 생성될 때마다 참조하고 있는 변수값을 읽어 사용하기 때문에 1,2,3으로 변화되는 것을 확인할 수 있습니다.


<br>
# 2. 메서드(method)

메서드(method)는 어떤 작업을 수행하기 위한 명령문의 집합을 의미합니다. <u>메서드를 사용하는 가장 큰 이유</u>는 **반복적으로 사용되는 코드를 줄이기 위해서**입니다.

메서드는 호출 될 때 어떤 값을 입력받아서 그 결과를 되돌려 주지만, 경우에 따라서는 되돌려 주는 값이 없는 경우도 있습니다.

- 하나의 메서드는 한 가지 기능만 수행하도록 작성하는 것이 좋습니다.
- 반복적으로 수행되어야 하는 여러 문장을 하나의 메서드로 정의해 놓으면 좋습니다.
- 관련된 여러 문장을 하나의 메서드로 만들어 놓는 것이 좋습니다.

▶ 메서드의 호출 원리

![그림1. 20180105_001_java-Variable-and-Method](/assets/img/java/20140922/20180105_001_java-Variable-and-Method.jpg)

메서드는 AA() 처럼  ()안에 아무것도 전달하지 않고 호출하는 방법이 있는가 하면, BB(3) 처럼 3이라는 값을 전달하여 호출할 수 있습니다. 여기서 3은 메서드가 전달하는 값이며 이것을 `인자`라고 합니다.

BB(3)이 호출되면 int BB(int x){} 가 호출되며, 전달된 인자값 3 을 BB 에서드에서 x라면 변수(지역 변수)에 저장하여 사용합니다. 여기서 x를 메서드에서 사용하는 `매개변수`라고 부릅니다.

CC(a,3) 처럼 인자를 상수가 아닌 변수로 보낼 수도 있으며, int CC(int x, int y)에서는 보내는 인자값 a, 3을 매개변수 x와 y로 받아서 CC 메서드에서 사용합니다. 그러면 a값은 x에 저장되고, 3은 y에 저장되는 것입니다.

이처럼 메서드에서는 매개변수를 여러개를 사용하여 실행할 수도 있습니다.


<br>
# 3. 메서드의 return

2.의 그림에서 AA()를 보면 void AA()라고 되어있는데, 여기서 `void`는 AA()메서드의 `리턴타입`을 의미합니다.

void는 리턴값이 없을 때 작성하는 keyword이며 아래와 같이 사용합니다.

```java
AA(){

}
```

또는

```java
AA(){
  return;
}
```

위와 같이 리턴타입이 void인 경우에는 return; 을 작성해도 되고 작성하지 않아도 됩니다.

일반적으로 리턴값이 없는 void 메서드는 return을 작성하지 않지만, 프로그램의 로직 내부에서 if문이나 while문에서 강제적으로 메서드의 수행을 멈추고자 할 때, 코드 중간에 return;을 사용하여 메서드의 흐름을 변경시킬 때 사용하기도 합니다.

int BB(int x) 나 int CC(int x, int y)를 보면 메서드 이름 앞에 `int`라고 리턴타입이 있습니다. 이것은 반드시 메서드의 끝에 위의 코드에서 처럼 return bb, return cc라고 int 형 변수를 작성해 줄 수 있고, return 숫자 (예: return 1;  또는 return 100;) 의 형태로 사용할 수도 있습니다.

메서드 이름 앞의 타입과 return 타입이 같으면 컴파일 할 때 에러가 발생하지 않고 프로그램이 잘 실행됩니다.

return 타입은 기본 타입 이외에 레퍼런스 타입도 가능합니다. 예를 들어, String DD() 라는 메서드를 예로 살펴보겠습니다.

```java
String DD(){

  //DD() 실행
  String str = "OK";

  return str;
}
```

또는

```java
String DD(){

  //DD() 실행
  return "Good";
}
```

와 같이 사용할 수 있습니다.

첫 번째의 경우 str 변수값은 프로그램이 진행되면서 그 값이 바뀔 수도 있고, 결과값도 그에 따라 바뀔 수 있습니다.

두 번째의 경우 return 값은 항상 "Good" 입니다.

String의 경우 아래와 같이 '+'연산자를 이용하여 사용할 수 있습니다.

```java
String DD(){

  //DD() 실행
  int x = 4;

  return x + "번째 메서드";
}
```

와 같이 사용할 수 있습니다.

int x 와 String 타입의 " " 문자열이 만나면 int + String = String이 되어서 return 타입은 String 이 되는 것입니다.
