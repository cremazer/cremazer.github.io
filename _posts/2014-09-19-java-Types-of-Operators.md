---
title: "JAVA - 연산자의 종류(Types of Operators)"
date: 2014-09-19 00:54:00
image: '/assets/img/java/20140919/java-Types-of-Operators.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 연산자의 종류(Types of Operators).
introduction: 자바(Java)에서 사용하는 연산자의 종류와 각각의 개념 및 예제를 통해 내용을 이해합니다.
---

Java에서 두 변수를 두고 사이에 연산을 할 경우에는 여러가지 형태에 따라 연산자를 사용합니다.

각 연산자의 종류와 연산자의 우선순위를 아래의 표를 통해 쉽게 확인할 수 있습니다.

![그림1. 20171207_001_java-Types-of-Operators](/assets/img/java/20140919/20171207_001_java-Types-of-Operators.jpg)

연산자는 수학시간에 배우는 연산자라고 생각하면 이해하기 쉽습니다.

-----
<br><br>
# 단항연산자

Java의 단항 연산자의 종류는 증감 연산자, 부호 연산자, 비트전환 연산자, 논리부정 연산자로 구성됩니다.

각 단항 연산자의 종류별 연산방법과 그 예제를 살펴보겠습니다.

### 1. 증감 연산자 : ++ , --

**증가 연산자 ++** : 피연산자를 1 증가시킵니다.
**감소 연산자 --** : 피연산자를 1 감소시킵니다.

증감연산자는 피연산자 앞에 쓰는 전위형과 뒤에 쓰는 후위형이 있습니다.

전위형 : i값을 1 증가시킨 후 i를 읽어옵니다.
> ++i;

후위형 : i를 읽어온 후 1 증가시킵니다.
> i++;

**▶ 전위형의 연산방법**

```java
i = 5;
j = 0;;

j = ++i;     //i값을 먼저 1 증가시킨 뒤 값을 j에 대입한다.
```
그러므로 i = 6, j = 6 이 된다.

**▶ 후위형의 연산방법**

```java
i = 5;
j = 0;;

j = i++;     //i값을 먼저읽어 j에 대입한 후 i값을 1 증가시킨다.
```

그러므로 i = 6, j = 5 가 된다.

증감연산자는 피연산자의 앞에 있는지 뒤에 있는지에 따라 연산순서가 다르기 때문에 자주사용하지 않으면 헷갈리기 쉽습니다.

### 2. 부호연산자 : +, -

수학에서 변수 앞의 부호라고 생각하면 됩니다.

- +x :  +1 * x
- -x :  -1 * x

```java
int x = -10;
int y = +x;         // +1 * -10   =>   y = -10 이 된다.

y = -x;             // -1 * -10   =>   y = 10 이 된다.
```

### 3. 비트전환 연산자 : ~

비트전환 연산자(~)는 정수형과  char형에만 사용됩니다.

피연산자를 2진수로 표현했을 때 0을 1로, 1을 0으로 바꿀 때 사용합니다.

![그림2. 20171207_002_Bit-conversion-operator](/assets/img/java/20140919/20171207_002_Bit-conversion-operator.jpg)

```
※ 2진수 계산법
00001010 = 2^3 + 2^1 = 8 + 2 = 10 (부호비트가 0 이므로 +부호 생략)
(2^3은 2 * 2 * 2, 즉 2를 3번 곱한 것을 의미합니다.)

11110101 = 11110101의 보수 + 1 = 00001010 + 1 = 00001011 = 2^3 + 2^1 + 1 = 8 + 2 + 1 = 11 (부호비트가 1 이므로 - 부호 붙임) => -11
```

### 4. 논리부정 연산자 : !

논리부정연산자(**!**)는 `boolean`형에만 사용할 수 있습니다.

true는 false로, false는 true로 바꿀때 사용합니다.
```java
boolean check = true;
check = !check;           //true를 false로 바꾸기 때문에 check = false가 됩니다.
```

<br><br>
# 산술연산자

산술 연산자는 연산을 수행하기 전에

- 크기가 4byte 이하인 자료형을 int로 변환합니다. (byte, char, short -> int)
- 피연산자들의 타입을 서로 일치시킵니다.

각 산술 연산자의 종류별 연산방법과 그 예제를 살펴보겠습니다.

### 1. 사칙연산자 : +, -, *, /

- int형 (4byte)보다 크기가 작은 자료형은 int형으로 형변환 후에 연산을 수행합니다.
  - byte + short  =>  int + int  =>  int

- 두 개의 피연산자 중 자료형의 표현범위가 큰 쪽에 맞춰서 형변환 된 후 연산을 수행합니다.
  - int + float  =>  float + float  =>  float

- 정수형 간의 나눗셈에서 0으로 나누는 것은 금지되어 있습니다.


**※주의사항**

```java
byte a = 10;
byte b = 20;
//byte c = a + b;    //컴파일 에러
byte c = (byte)(a+b);
```

> a + b 의 결과는 int형이므로 char 변수에 값을 대입하려면 반드시 [형변환](https://cremazer.github.io/java-type-conversion/) 해야합니다.

### 2. 나머지연산자 : %

왼쪽의 피연산자를 오른쪽 피연산자로 나누고 난 나머지 값을 돌려주는 연산자입니다.

```java
10 % 8   =  2
```

### 3. 쉬프트연산자 : <<. >>, >>>

쉬프트연산자는 정수형 변수에만 사용할 수 있습니다.

**x << n** 은 **x * 2^n**의 결과와 같다.

**x >> n** 은 **x / 2^n**의 결과와 같다.

'**<<**'연산자의 경우, 피연산자의 부호에 상관없이 자리를 왼쪽으로 이동시키며, 빈칸을 0으로 채웁니다.

'**>>**'연산자의 경우, 피연산자가 양수인경우 자리를 이동시키면서 0으로 채우고, 피연산자가 음수인 경우 음수의 부호를 유지시키기위해 빈자리를 1로 채웁니다.

'**>>>**'연산자의 경우, 부호에 상관없이 항상 0으로 빈자리를 채웁니다.

아래의 예제를 통해 쉬프트 연산자가 어떻게 연산이 되는지 살펴보겠습니다.

**8 << 0**

![그림3. 20171207_003_Shift-operator-1](/assets/img/java/20140919/20171207_003_Shift-operator-1.jpg)

**8 << 1**

![그림4. 20171207_004_Shift-operator-2](/assets/img/java/20140919/20171207_004_Shift-operator-2.jpg)

**8 << 2**

![그림5. 20171207_005_Shift-operator-3](/assets/img/java/20140919/20171207_005_Shift-operator-3.jpg)

**-8 << 0**

![그림6. 20171207_006_Shift-operator-4](/assets/img/java/20140919/20171207_006_Shift-operator-4.jpg)

**-8 << 1**

![그림7. 20171207_007_Shift-operator-5](/assets/img/java/20140919/20171207_007_Shift-operator-5.jpg)

**-8 << 2**

![그림8. 20171207_008_Shift-operator-6](/assets/img/java/20140919/20171207_008_Shift-operator-6.jpg)

위와 같은 과정으로 연산이 진행됩니다.

<br><br>
# 비교연산자

비교 연산자는 크기를 비교하는 대소비교 연산자와 같은지를 비교하는 등가비교 연산자로 분류됩니다.

### 1. 대소비교 연산자 : <, >, <=, >=

두 피연산자의 크기를 비교하는 연산자입니다.
연산결과는 boolean형으로 나옵니다.

### 2. 등가비교 연산자 : ==, !=

**x == y** : x와 y가 같으면 true, 다르면 false.

**x != y** : x와 y가 다르면 true, 같으면 false.

```
※ String은 예외적으로 문자열 결합에 '+'를 사용하는 것을 허용합니다.
== 대신 equals()를 사용해야 합니다.
== 는 주로 null인지 확인할 때 사용합니다.
```

<br><br>
# 논리연산자, 비트연산자

피연산자로 참, 또는 거짓을 구분할 때는 **논리 연산자**와 이진 비트연산을 하는 **비트 연산자**가 있습니다.

### 1. 논리연산자 : &&, ||

논리연산자는 피연산자로 boolean형 또는 boolean형 값을 결과로 하는 조건식만을 허용합니다.

그리고 `&&`가 `||`보다 우선순위가 높기때문에 한 조건식에서 함께 사용될 때는 괄호를 사용해서 우선순위를 명확히 해주는 것이 좋습니다.

`&&` : 피연산자 양쪽 모두 true이어야 true 결과를 얻습니다.

`||` : 피연산자 중 어느 한 쪽만 true이면 true를 결과로 얻습니다.

![그림9. 20171207_009_Logical-operator](/assets/img/java/20140919/20171207_009_Logical-operator.jpg)

### 2. 비트연산자 : &, |, ^

비트연산자는 이진 비트연산을 수행합니다.

`&` : 피연산자 양 쪽이 모두 1 이어야 1을 결과로 얻습니다.

`|` : 피연산자 중 한 쪽의 값이 1이면, 1을 결과로 얻습니다.

`^` : 피연산자의 값이 서로 다를 때 1을 결과로 얻습니다.

![그림10. 20171207_010_Bitwise-operator](/assets/img/java/20140919/20171207_010_Bitwise-operator.jpg)

아래의 예제를 통해 비트 연산자가 어떻게 연산이 되는지 살펴보겠습니다.

**3 & 5 = 1**

![그림11. 20171207_011_Bitwise-operator-ex-1](/assets/img/java/20140919/20171207_011_Bitwise-operator-ex-1.jpg)

<b>3 | 5 = 7</b>

![그림12. 20171207_012_Bitwise-operator-ex-2](/assets/img/java/20140919/20171207_012_Bitwise-operator-ex-2.jpg)

**3 ^ 5 = 6**

![그림13. 20171207_013_Bitwise-operator-ex-3](/assets/img/java/20140919/20171207_013_Bitwise-operator-ex-3.jpg)

<br><br>
# 삼항연산자

삼항연산자는 연산에 필요한 피연산자가 세 개입니다.

**▶ 연산방법**

![그림14. 20171207_014_Ternary-operator](/assets/img/java/20140919/20171207_014_Ternary-operator.jpg)

삼항연산자를 사용하려면 참(true) 또는 거짓(false)일 경우 return 할 식1, 식2(또는 값) 를 저장할 매개변수(check)를 함께 사용해야 합니다. return 할 식은 boolean 형이거나, int, String, 기타 Object 형으로 분류할 수 있습니다.

아래의 예제를 통해 삼항 연산자가 어떻게 연산이 되는지 살펴보겠습니다.

**▶ 사용예제 : int**

```java
public class TernaryOperatorExample1 {
	public static void main(String[] args) {
		int sal = 5000;
		int salAverage = (sal > 4000) ? 50 : 100;

		System.out.println("salAverage : " + salAverage);
	}
}
```
```
<결과>
salAverage : 50
```

**▶ 사용예제 : String**

```java
public class TernaryOperatorExample2 {
	public static void main(String[] args) {
		int num = 27;
		String result = (num % 2 == 0) ? "짝수" : "홀수";

		System.out.println("result : " + result);
	}
}
```
```
<결과>
result : 홀수
```

**▶ 사용예제 : Object**

```java
class Product extends Object{
	public String toString() {
		return "Product";
	}
}

class Audio extends Product{
	public String toString() {
		return "Audio";
	}
}

class TV extends Product{
	public String toString() {
		return "TV";
	}
}

public class TernaryOperatorExample3 {
	public static void main(String[] args) {
		Product audio = new Audio();
		Product tv = new TV();

		Product product = (audio instanceof Product) ? audio : tv;

		System.out.println("product : " + product);
	}
}
```
```
<결과>
product : Audio
```

<br><br>
# 대입연산자

대입연산자는 변수에 값 또는 수식의 연산결과를 저장하는데 사용됩니다.

대입연산자의 왼쪽에는 반드시 변수가 위치해야 하며, 오른쪽에는 리터럴이나 변수 또는 수식이 올 수 있습니다.

변수 앞에 키워드 `final`을 붙이면 **상수(constant)**를 의미합니다.
상수는 선언과 동시에 값을 저장해야 하며, <u>한 번 저장된 값은 바꿀 수 없습니다.</u>

**▶ 대입연산자의 종류**

![그림15. 20171207_015_Assignment-operator](/assets/img/java/20140919/20171207_015_Assignment-operator.jpg)


여기까지 Java에서 사용하는 연산자의 종류에 대해 알아봤습니다.

