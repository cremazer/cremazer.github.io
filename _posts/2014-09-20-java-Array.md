---
title: "JAVA - 배열(Array)"
date: 2014-09-20 00:36:00
image: '/assets/img/java/20140920/java-Array.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 배열(Array).
introduction: 자바(Java)에서 사용하는 배열의 개념을 예제를 통해 내용을 이해합니다.
---

# 배열(array)이란?

[배열](http://terms.naver.com/entry.nhn?docId=815369&cid=42344&categoryId=42344)이란 동일한 특성을 가지며 일정한 규칙에 따라 나열되어 있는 데이터의 집합을 말합니다.

- 같은 타입의 여러 변수를 하나의 묶음으로 다룹니다.
- 많은 양의 값(데이터)을 다룰 때 유용합니다.
- 배열의 각 요소는 서로 연속적입니다.

예를 들어, 5명의 점수를 변수에 저장한다고 가정합시다.

```java
int score1 = 0, score2 = 0. score3 = 0, score4 = 0, score5 = 0;
```

코드로 작성한다면, 위와 같이 5개의 변수를 선언하고, 각 변수값을 0으로 초기화 합니다.

이 내용을 그림으로 설명하면 아래와 같은 구조로 되어 있을 것입니다.

![그림1. 20171212_001_java-Array](/assets/img/java/20140920/20171212_001_java-Array.jpg)

> 그렇다면 100명의 점수를 저장하려면 어떻게 할까요?

100개의 변수를 선언하고 각 변수값을 초기화 하면 됩니다. -_-;

정말 그렇게 한다면, 작성할 것도 많고, 시간도 오래 걸릴 것입니다.

이와 같은 문제를 좀더 쉽게 해결하기 위해 `배열`이라는 개념이 생겼습니다.

위의 내용을 배열을 사용하여 타나내려면 아래와 같이 선언할 수 있습니다.

```java
int[] score = new int[5];
```
위의 코드에서 대괄호 [ ]안의 숫자 5는 `배열의 개수`를 의미합니다.

![그림2. 20171212_002_java-Array](/assets/img/java/20140920/20171212_002_java-Array.jpg)

`score[0]`은 값을 나타내며, 배열의 `[index]`없이 변수 `score`는 임의의 메모리주소(0x100)을 나타냅니다.

그러면 배열을 사용하여 100명의 점수를 저장한다면 어떻게 할까요?

```java
int[] score = new int[100];
```
위의 코드와 같이 `배열의 개수(크기)`만 100으로 바꿔주면 메모리에 저장할 공간을 만들 수 있습니다.

100개의 변수를 하나씩 선언하는 것보다 매우 간단하죠?


<br>
# 배열의 선언

배열은 아래와 같이 선언합니다.

**▶ 선언방법**
```
타입[] 변수명;
타입 변수명[];
```

example)
```java
int[] score;
String[] name;
```
또는
```java
int score[];
String name[];
```
<br>
# 배열의 생성

배열을 선언한다고 값을 저장할 수 잇는 공간이 생기는 것은 아닙니다. 배열을 선언한 후에는 배열을 생성해야 비로소 값을 저장할 공간이 생겨납니다.

```java
//배열의 선언
int[] score;

//배열의 생성
score = new int[5];
```

위의 코드를 아래와 같이 1줄로 작성할 수 있습니다.

```java
int[] score = new int[5];
```

<br>
# 배열의 초기화

배열을 생성 한 후에는 아래와 같이 각 배열공간에 원하는 값으로 초기 설정을 할 수 있습니다.

```java
int[] score = new int[5];
score[0] = 100;
score[1] = 90;
score[2] = 80;
score[3] = 70;
score[4] = 60;
```

위의 코드는 아래의 코드와 같이 { }를 사용하여 초기값을 설정 할 수도 있습니다. 이 때는 배열의 크기를 지정하지 않아도 자동으로 크기를 결정합니다.

```java
int[] score = {100, 90, 80, 70, 60};
```

또는

```java
int[] score = new int[]{100, 90, 80, 70, 60};
```

![그림3. 20171212_003_java-Array-init](/assets/img/java/20140920/20171212_003_java-Array-init.jpg)

<br>
# 다차원배열

다차원 배열은 아래와 같이 선언합니다.

**▶ 선언방법**

```
타입[][] 변수명;
타입[] 변수명[];
타입 변수명[][];
```

example)

```java
int[][] score;
int[] score[];
int score[][];
```

**▶ 배열 생성**

```java
int[][] score = new int[5][3];
```

**▶ 초기화**

![그림4. 20171212_004_java-Multidimensional-arrays](/assets/img/java/20140920/20171212_004_java-Multidimensional-arrays.jpg)

다차원배열을 위의 표 내용으로 초기화 한다고 가정해 봅시다.

먼저 `5행 3열`인 2차원 배열을 생성한 후, 각 배열의 값을 초기화 합니다.

```java
int[][] score = new int[5][3];
score[0][0] = 100;
score[0][1] = 100;
score[0][2] = 100;

score[1][0] = 20;
score[1][1] = 20;
score[1][2] = 20;

score[2][0] = 30;
score[2][1] = 30;
score[2][2] = 30;

score[3][0] = 40;
score[3][1] = 40;
score[3][2] = 40;

score[4][0] = 50;
score[4][1] = 50;
score[4][2] = 50;
```

위의 코드처럼 생성 할 경우, 배열의 크기가 커질수록 초기화 하는데 꽤 긴 코드를 작성해야 합니다. 이런 문제점을 해결하기 위해 아래의 코드처럼 중괄호{ }를 사용하여 초기화 하는 방법도 있습니다.

```java
int[][] score = new int[][] {
          { 100, 100, 100 }
		, { 20, 20, 20 }
		, { 30, 30, 30 }
		, { 40, 40, 40 }
		, { 50, 50, 50 }
};
```

<br>
# 가변 배열

Java에서는 2차원 이상의 다차원 배열에 대해서 `'배열의 배열'`의 형태로 처리한다는 사실을 이용하면 보다 자유로운 형태의 배열을 구성할 수 있습니다.

`5행 3열`의 2차원 배열을 생성해 봅시다.

```java
int[][] score = new int[5][3];
```

위 코드를 아래와 같이 표현할 수도 있습니다.

```java
int[][] score = new int[5][];

score[0] = new int[3];
score[1] = new int[3];
score[2] = new int[3];
score[3] = new int[3];
score[4] = new int[3];
```

2차원 배열을 생성할 때, 열의 수를 입력하지 않고 선언하면, 위와 같이 각 행에 대하여 열의 수를 자유로이 지정할 수 있습니다.

```java
int[][] score = new int[5][];

score[0] = new int[4];
score[1] = new int[3];
score[2] = new int[2];
score[3] = new int[2];
score[4] = new int[3];
```

아래의 그림은 위의 코드를 도식화한 것입니다.

![그림5. 20171212_005_java-A-variable-array](/assets/img/java/20140920/20171212_005_java-A-variable-array.jpg)

> 가변 배열은 있다는 것은 알았는데, 잘 써본적은 없습니다... 어디에 쓰는거지..?

아래의 가변 배열 예제를 살펴보겠습니다.

![그림6. 20171212_006_java-A-variable-array](/assets/img/java/20140920/20171212_006_java-A-variable-array.jpg)

위 표의 내용을 배열에 저장합니다.

```java
/**
 * 가변배열
 * 
 * @author cremazer (cremazer@gmail.com)
 * @date 2013.08.13
 */
public class AdjustableArray {
	public static void main(String[] args) {
		String[] subject = { "국어", "영어", "수학", "컴퓨터" };

		int[][] score = {
				  { 100, 100, 100, 100 }
				, { 20, 20, 20 }
				, { 30, 30 }
				, { 40, 40 }
				, { 50, 50, 50 }
		};

		// 화면 출력
		for (int row = 0; row < score.length; row++) {

			// 과목명 출력 - 첫번째 행 출력전에만!
			if (row == 0) {

				for (int index = 0; index < subject.length; index++) {
					System.out.print(subject[index] + "\t");
				}

				System.out.println();
				System.out.println("-------------------------------");

			}

			// 점수 출력
			for (int col = 0; col < score[row].length; col++) {
				System.out.print(score[row][col] + "\t");
			}

			System.out.println();
		}
	}
}
```

첫번째 for문의 조건식을 살펴보면, `row < score.length` 에서 `score.length` 는 배열의 행의 수를 의미하며 값은 5가 됩니다.

그러므로 첫번째 for문은 5번을 반복하게 됩니다.

두번째 for문의 조건을 살펴보면, `col < score[row].length` 에서 `score[row].length`는 각 행의 열의 수를 의미합니다.

예를들면, score[0].length 는 4 가 되고, score[1].length 는 3 이 됩니다.

그러므로 두번째 for문은 각 행의 열의 수만큼 반복하게 됩니다.

모든 for문의 반복이 종료되면, 점수를 출력하는 for문을 통해 아래와 같은 결과를 확인할 수 있습니다.

![그림7. 20171212_007_java-A-variable-array](/assets/img/java/20140920/20171212_007_java-A-variable-array.jpg)


<br>
# 배열의 복사

배열은 한번 생성하면 그 크기를 변경할 수 없기 때문에 더 많은 저장공간이 필요하다면, 보다 큰 배열을 새로 만들고 이전 배열로부터 내용을 복사해야 합니다.

배열간의 내용을 복사하려면 for문을 사용하거나, System 클래스의 arraycopy()를 사용하면 됩니다.

아래의 에제를 통해 배열을 복사하는 방법을 알아봅시다.

```java
/**
 * 배역복사
 * 
 * @author cremazer (cremazer@gmail.com)
 * @date 2013.08.13
 */
public class ExampleArrayCopy {
	public static void main(String[] args) {
		int[] number = { 1, 2, 3, 4, 5 };
		int[] newNumber = new int[10];

		// 배열복사
		for (int i = 0; i < number.length; i++) {
			// 배열 number의 값을 newNumber에 저장한다.
			newNumber[i] = number[i]; 
		}

		// 새로만든 배열 값 출력
		for (int i = 0; i < newNumber.length; i++) {
			System.out.print(newNumber[i]);
		}
	}
}
```

배열을 복사할 때는 for 문이 반복하는 조건을 **배열의 크기가 작은 배열의 길이만큼 반복**하도록 설정하면 됩니다.

위의 코드를 실행하면 아래와 같은 결과값을 얻게 됩니다.

```
<결과>
1234500000
```

이번에는 System 클래스의 arraycopy()를 사용하는 방법에 대해서 알아봅시다.

arraycopy()의 syntex는 다음과 같습니다.

```java
/**
 * 배열복사
 *
 * @param src 원본배열(크기가 작은배열)
 * @param srcPos 원본배열의 시작위치
 * @param dest 대상배열(크기가 큰 배열)
 * @param destPos 대상배열의 시작위치
 * @param length 복사할 배열의 길이
 */
public static void arraycopy(Object src,
                             int srcPos,
                             Object dest,
                             int destPos,
                             int length)
```

아래의 예제를 통해 `arraycopy()` 사용법을 살펴보겠습니다.

```java
/**
 * 배역복사
 * 
 * @author cremazer (cremazer@gmail.com)
 * @date 2013.08.13
 */
public class ExampleArrayCopy {
	public static void main(String[] args) {
		int[] number = { 1, 2, 3, 4, 5 };
		int[] newNumber = new int[10];

        // 배열복사
        System.arraycopy(number, 0, newNumber, 0, number.length);

        // 새로만든 배열 값 출력
        for (int i = 0; i < newNumber.length; i++) {
            System.out.print(newNumber[i]);
        }
	}
}
```

위의 코드의 흐름을 그림으로 보면 아래와 같습니다.

![그림8. 20171212_008_java-Copying-an-array](/assets/img/java/20140920/20171212_008_java-Copying-an-array.jpg)

number배열과 newNumber 배열이 생성되고, `System.arraycopy(number, 0, newNumber, 0, number.length);` 에 의해 `number.length` 는 5 가 되므로, number 배열의 0 번째부터 길이 5 만큼의 값들을 newNumber 배열의 0 번째부터 길이 5 만큼의 공간에 복사합니다.

그러므로 newNumber의 결과를 출력하면 위의 그림과 같이 1234500000의 값이 출력되는 것입니다.

```
<결과>
1234500000
```

여기까지 Java에서 사용하는 배열의 구조에 대해 알아봤습니다.

