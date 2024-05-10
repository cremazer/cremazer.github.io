---
title: "JAVA - Hello World 실행하기(Java Hello World!)"
date: 2014-09-16 02:05:00
image: '/assets/img/java/20140916/java_hello_world.jpg'
description: Java Hello World!.
category: 'java'
tags:
- java
- tutorial
twitter_text: JAVA - Hello World 실행하기(Java Hello World!).
introduction: 자바(Java) 프로그래밍으로 Console, Edit Plus, Eclipse 도구를 사용해 Hello World를 실행하는 방법을 설명합니다.
---

Java를 실행할 때 콘솔(Console)에서 직접 입력하여 실행하거나, EditPlus, Eclipse, Net Beans 등과 같은 코드편집 툴(Tool)을 이용해서 실행하여 결과를 확인합니다.

아래의 예제를 통해 윈도우의 cmd 를 이용한 콘솔(Console) 프로그램, EditPlus, Eclipse에서 Hello World 코드를 실행하는 과정을 알아보겠습니다.


1. 자바(Java)의 구조
2. 콘솔(Console) 프로그램에서 실행하기
3. Edit Plus에서 실행하기
4. Eclipse에서 실행하기

-----

# 1. 자바(Java)의 구조

자바의 구조를 간단하게 설명하면 `클래스`라는 틀 안에 `메서드` 또는 `함수`라고 불리는 작은 영역들로 구성되어 있습니다.
그림으로 보면 아래와 같이 간략하게 나타낼 수 있습니다.

![그림1. 20171206_001_Structure-of-Java_1](/assets/img/java/20140916/20171206_001_Structure-of-Java_1.jpg)

자바의 모든 코드는 클래스(Class) 안에 작성되어야 합니다.
그리고 자바를 실행하면 가장먼저 클래스 안의 main() 메서드를 실행시킵니다.



## 1.1. 코드 작성
```java
class Hello {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

## 1.2. 코드 설명

![그림2. 20171206_002_Structure-of-Java_2](/assets/img/java/20140916/20171206_002_Structure-of-Java_2.jpg)

코드는 바디( { } )안에 작성되며, main()메서드는 자바가 처음 실행할 때 시작하는 메서드입니다.

> System.out.println("Hello World!");

()안에 있는 "Hello World!" 문구를 화면에 보여주도록 하는 코드입니다.

> 왜 이렇게 작성하는지 궁금하겠지만, 자바를 공부하다보면 자연스럽게 알게되므로 이렇게 하면 저렇게 된다는 느낌으로 이해하면 됩니다.

## 1.3. 실행

![그림3. 20171206_003_Structure-of-Java_3](/assets/img/java/20140916/20171206_003_Structure-of-Java_3.jpg)

코드 입력이 끝나고 파일을 저장하면 java파일이 생성됩니다. 생성된 java 파일을 컴파일을 하면 class 파일이 생성됩니다.

> 컴파일 : 코드를 컴퓨터가 읽을 수 있도록 변경하는 과정.

java 명령어를 통해 생성된 클래스를 실행하면 입력한 결과를 모니터로 볼 수 있습니다.

지금까지의 내용을 이제 프로그램을 사용해서 확인해 보겠습니다.


# 2. 콘솔(Console) 프로그램에서 실행하기

윈도우OS에서는 기본 편집기인 `메모장`이 있습니다. 이 메모장으로 위의 자바 코드를 작성할 수 있으며, 저장할 때는 클래스 이름인 `Hello`와 동일하게 파일 이름을 `Hello` 대소문자 모두 같도록 입력하고, 파일 확장자는 .java 입력합니다.
위의 코드를 작성하고 저장하였다면, 저장한 위치에 Hello.java 파일이 생성됩니다.

> 콘솔 프로그램으로 테스트할 경우, 파일은 되도록이면 폴더를 생성하여 저장하는 것이 좋으며, 폴더명은 영문으로 간결하게 생성합니다.

이제 콘솔 프로그램을 실행해서, Hello.java 파일이 저장된 경로로 이동합니다.

![그림4. 20171204_024_java_test_2](/assets/img/java/20140916/20171204_024_java_test_2.png)

> 콘솔 프로그램에서 경로를 이동할 때는 "cd"라는 명령어를 사용합니다. "cd .."을 실행하면, 현재 경로에서 상위 폴더로 이동하고, "cd test"라고 입력하면, 현재 폴더에 test라는 폴더로 이동합니다.

## 2.1. 컴파일

저의 경우 E 드라이브에 폴더를 생성하여 그 안에 Hello.java 파일을 저장하였습니다.

콘솔 프로그램에서 이동하려면 아래와 같이 "cd" 명령어를 사용합니다.
1. e: 엔터
2. cd JavaStudy\src 엔터

이제 [자바설치 및 환경설정(Java installation and configuration)](https://cremazer.github.io/Java-installation-and-configuration/)에서 설정이 잘 되어 있는 상태라면, 자바 컴파일 프로그램인 "javac"를 사용할 수 있습니다.
자바 파일을 컴파일 하는 명령어는 다음과 같습니다.
컴파일을 할 때는 `javac`라는 명령어를 사용하고, **파일이름은 반드시 확장자까지** 써주어야 합니다.

> java Hello.java



![그림5. 20171206_005_java-Running-the-Console_1](/assets/img/java/20140916/20171206_005_java-Running-the-Console_1.jpg)

컴파일이 정상적으로 종료되면, 동일한 폴더(디렉토리) 안에 Hello.class 파일이 생성되는 것을 확인할 수 있습니다.

## 2.2. 실행

이제 컴파일된 Hello.class 파일을 "java"명령어를 사용하여 실행해 보겠습니다. 실행 명령어는 다음과 같습니다.
실행할 때는 `java`명령어를 사용하고, 파일 확장자(.class)를 뺀 클래스 이름 `Hello`만 써주면 됩니다.

> java Hello

![그림6. 20171206_006_java-Running-the-Console_2](/assets/img/java/20140916/20171206_006_java-Running-the-Console_2.png)

실행이 완료되면 결과를 확인할 수 있다.


# 3. Edit Plus에서 실행하기

Edit Plus는 유료 편집기 프로그램이며, 30일 무료 평가판을 다운로드 할 수 있습니다.

[Edit Plus 홈페이지 바로가기](https://www.editplus.com/kr/)

> 다운로드 및 설치과정은 생략합니다.

설치한 Edit Plus를 실행하고 코드를 작성한 후 파일을 저장합니다.

![그림7. 20171206_007_java-Running-the-EditPlus_1](/assets/img/java/20140916/20171206_007_java-Running-the-EditPlus_1.jpg)

## 3.1. 컴파일 단축키 설정하기

메뉴에서 **[도구] - [사용자 도구 구성]**을 클릭합니다.

![그림8. 20171206_008_java-Running-the-EditPlus_2](/assets/img/java/20140916/20171206_008_java-Running-the-EditPlus_2.jpg)

기본 설정 윈도우가 나타나면, **[추가(D)>>] - [프로그램(P)]**을 클릭합니다.

![그림9. 20171206_009_java-Running-the-EditPlus_3](/assets/img/java/20140916/20171206_009_java-Running-the-EditPlus_3.jpg)

프로그램 내용을 아래의 그림처럼 입력하여 봅니다.
- 메뉴제목은 본인이 알아보기 쉽게 입력합니다. (저는 '컴파일'로 작성했습니다.)
- 명령(O)은 컴파일 명령어 javac 로 입력합니다.
- 인수(E)는 파일이름이어야 하므로 옆에 역삼각형 버튼을 눌러 '파일 이름'을 클릭합니다.
- 디렉토리(I)는 현재 파일이 있는 '파일 디렉토리'를 클릭합니다.

![그림10. 20171206_010_java-Running-the-EditPlus_4](/assets/img/java/20140916/20171206_010_java-Running-the-EditPlus_4.jpg)

모두 입력하면 `[적용]`버튼을 누르고, `[확인]`버튼을 클릭합니다.

## 3.2. 실행 단축키 설정하기

3.1.의 컴파일 단축키를 설정하는 방법과 마찬가지로 기본 설정 화면에서 **[추가] - [프로그램]**을 클릭합니다.

![그림11. 20171206_011_java-Running-the-EditPlus_5](/assets/img/java/20140916/20171206_011_java-Running-the-EditPlus_5.jpg)

프로그램 내용을 아래의 그림처럼 입력하여 봅니다.
- 메뉴제목은 본인이 알아보기 쉽게 입력합니다. (저는 '실행'으로 작성했습니다.)
- 명령(O)은 실행 명령어 java 로 입력합니다.
- 인수(E)는 확장자가 없는 파일 이름이어야 하므로 옆에 역삼각형 버튼을 눌러 '확장자를 뺀 파일 이름'을 클릭합니다.
- 디렉토리(I)는 현재 파일이 있는 '파일 디렉토리'를 클릭합니다.

![그림12. 20171206_012_java-Running-the-EditPlus_6](/assets/img/java/20140916/20171206_012_java-Running-the-EditPlus_6.jpg)

모두 입력하면 `[적용]`버튼을 누르고 `[확인]`버튼을 클릭합니다.

이제 메뉴에서 `[도구]`를 클릭하면 아래 그림과 같이 컴파일과 실행 단축키가 생성되어 있습니다.

![그림13. 20171206_013_java-Running-the-EditPlus_7](/assets/img/java/20140916/20171206_013_java-Running-the-EditPlus_7.jpg)

단축키를 생성하였으면, 이제 컴파일하고 실행시켜 봅니다.

## 3.3. 컴파일

단축키 `[Ctrl + 1]`을 누르면 콘솔 윈도우가 나타나는데, 아무런 메세지가 보이지 않고, 아무키나 누르라는 메세지만 나타납니다. 이는 컴파일이 정상적으로 실행되었음을 의미합니다.
만약 에러가 발생할 경우 에러메시지를 보여줍니다.

![그림14. 20171206_014_java-Running-the-EditPlus_8](/assets/img/java/20140916/20171206_014_java-Running-the-EditPlus_8.jpg)


## 3.4. 실행

단축키 `[Ctrl + 2]`를 눌러 실행시켜 봅니다.

![그림15. 20171206_015_java-Running-the-EditPlus_9](/assets/img/java/20140916/20171206_015_java-Running-the-EditPlus_9.jpg)

콘솔 윈도우에 Hello World! 메시지를 확인할 수 있습니다.

※결과를 콘솔 윈도우가 아닌 EditPlus 에서 직접 확인하고 싶다면, **[도구] - [사용자 도구 구성]** 을 클릭하여 나타난 기본 설정 윈도우에서 `[출력 내용 캡쳐]` 체크박스를 선택하면 EditPlus에서 직접 결과를 확인할 수 있습니다.


# 4. Eclipse에서 실행하기

※본 내용은 [이클립스 설치 및 Hello World!(Eclipse installation and Hello World!)](https://cremazer.github.io/Eclipse-installation-and-Hello-World/)에서 작성된 내용과 동일한 내용이므로, 이미 알고 계시면 넘어가도 좋습니다.

먼저 설치된 이클립스를 실행합니다.

## 4.1. 프로젝트 생성

이클립스 메뉴에서 **[File] - [New] - [Java Project]**를 클릭합니다.

![그림16. 20171206_016_java-Running-the-Eclipse_1](/assets/img/java/20140916/20171206_016_java-Running-the-Eclipse_1.jpg)

New Java Project 윈도우가 나타나면 아래의 그림과 같이 프로젝트 이름을 입력하고 `[Finish]`버튼을 클릭하면 프로젝트가 생성됩니다.

![그림17. 20171206_017_java-Running-the-Eclipse_2](/assets/img/java/20140916/20171206_017_java-Running-the-Eclipse_2.jpg)

## 4.2. 클래스 생성

이클립의 왼쪽에 Package Explorer 에 보면 4.1에서 생성한 프로젝트가 생겨있습니다. 프로젝트를 클릭하고 마우스 오른쪽 버튼을 클릭하면 팝업메뉴가 나타납니다.

팝업 메뉴에서 **[New] - [Class]**를 클릭합니다.

![그림18. 20171206_018_java-Running-the-Eclipse_3](/assets/img/java/20140916/20171206_018_java-Running-the-Eclipse_3.jpg)

현재 클래스를 만들고 실행하는것이 목적이므로 다른 파트는 생략하고, 아래 그림과 같이 클래스 이름만 생성한 후 `[Finish]`버튼을 클릭합니다.

![그림19. 20171206_019_java-Running-the-Eclipse_4](/assets/img/java/20140916/20171206_019_java-Running-the-Eclipse_4.jpg)

## 4.3. 저장 & 컴파일

생성된 클래스에 코드를 작성하고 `저장(Ctrl + S)`을 누르면 파일이 저장되며, 동시에 자동으로 컴파일까지 됩니다.

![그림20. 20171206_020_java-Running-the-Eclipse_5](/assets/img/java/20140916/20171206_020_java-Running-the-Eclipse_5.jpg)

## 4.4. 실행

이제 화살표 버튼(▷)을 눌러 실행하면 이클립스 아래쪽 콘솔 윈도우에서 결과를 확인할 수 있습니다.

![그림21. 20171206_021_java-Running-the-Eclipse_6](/assets/img/java/20140916/20171206_021_java-Running-the-Eclipse_6.jpg)

Eclipse는 코드 자동완성 및 자동 컴파일 등 코드를 작성할 때 여러가지 다양한 기능을 제공하므로, 자바 개발자들이 가장 많이 사용하는 개발툴입니다.

그 기능들은 너무 많아서 툴 자체로도 공부를 따로 해야하므로, 자바 공부에 필요한 기능들 위주로 사용해보면서 툴을 사용하는데 익숙해지면 개발할 때 코딩하는 시간을 줄일 수 있을 것입니다.
