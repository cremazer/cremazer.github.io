---
title: "JAVA - 문자형 변수 char"
date: 2014-09-17 00:43:00
image: '/assets/img/java/20140917/java_Character_Variables.jpg'
description: Java programming language.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - 문자형 변수 char.
introduction: 자바(Java)에서 사용하는 문자형 변수 char에 대해 설명합니다.
---

문자형 변수 `char`는 하나의 문자만 저장합니다.

특정한 문자 하나에 해당하는... 예를 들어 'A'라는 문자를 아래와 같이 ch라는 변수에 저장할 수 있습니다.

> char ch = 'A';

char형 변수는 [유니코드(Unicode)](http://terms.naver.com/entry.nhn?docId=1181043&mobile&cid=40942&categoryId=32841)라는 문자 체계를 사용하기 때문에 크기가 2 Byte입니다.

char형 변수는 하나의 문자만 저장하기 때문에 두개의 문자를 입력하려고 하면 에러가 발생합니다.

아래 예제는 <u>문자 'A'가 어떤 값을 가지고 있는지 확인하는 예제</u>입니다.

```java
public class CharToCode {
    public static void main(String[] args) {
        char ch = 'A';
        int code = (int) ch; // ch에 저장된 값을 int형으로 변환

        System.out.println(ch);
        System.out.println(code);
    }
}
```

```
<결과>
A
65
```

**char ch = 'AA';** 라고 할 경우 에러가 발생합니다.

아래의 예제는 </u>유니코드값(숫자)이 어떤 문자를 나타내는지 확인하는 예제</u>입니다.

```java
public class CharToCode {
    public static void main(String[] args) {
        int code = 66;
        char ch = (char) code;

        System.out.println(code);
        System.out.println(ch);
    }
}
```

66은 문자 'B'를 나타내는 유니코드값입니다.
이는 [ASCII코드](http://terms.naver.com/entry.nhn?docId=1168708&mobile&cid=40942&categoryId=32837)에 정의된 값이므로 문자에 해당하는 코드값을 위의 예제를 통해 확인할 수 있습니다.

> 문자형 변수 char 를 사용할 때는 한글자만 저장되는 것을 꼭 기억하세요.
