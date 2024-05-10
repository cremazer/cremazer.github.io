---
title: "이클립스 설치 및 Hello World!(Eclipse installation and Hello World!)"
date: 2014-09-16 02:01:00
image: '/assets/img/java/20140916/eclipse-installation-and-He.jpg'
description: Eclipse installation and Hello World!.
category: 'java'
tags:
- java
- tutorial
- eclipse
twitter_text: 이클립스 설치 및 Hello World!(Eclipse installation and Hello World!).
introduction: 자바(Java)를 실행하기 위한 무료 개발 툴(Tool)인 이클립스(Eclipse)의 설치 과정 및 실행 방법을 설명합니다.
---

2017.12.05 updated.
이미지 변경
- Eclipse.org

-----


**이클립스(Eclipse)**란?

> 이클립스(Eclipse)는 다양한 플랫폼에서 쓸 수 있으며, 자바(Java)를 비롯한 다양한 언어를 지원하는 프로그래밍 통합 개발 환경을 목적으로 시작하였으나, 현재는 OSGi를 도입하여, 범용 응용 소프트웨어 플랫폼으로 진화하였다. - 위키백과


이클립스는 오픈소스 통합개발환경으로 자바 프로그래밍을 하기에 적합한 **무료 소프트웨어**입니다.

Edit Plus, Ultra Edit, Net Beans 등등 다양한 개발 툴이 있지만, 개발자들이 가장 많이 사용하는 이클립스를 선택한 이유는, Java 뿐만 아니라 향후 이어질 Jsp, Spring 등등 다양한 개발환경에 대한 확장성을 가지고 있으며, 무엇보다도 자바를 코딩하기에 있어서 편리한 기능들을 제공하기 때문입니다.


그럼 이클립스는 어떻게 설치하는 지 아래의 순서대로 진행하며 알아봅시다.


1. 이클립스 다운받기

2. 이클립스 실행하기

3. Hello World!

-----

## 이클립스 다운받기


이클립스를 다운받으려면 아래의 링크를 클릭해서 이클립스 홈페이지에 접속합니다.


[Eclipse.org](http://www.eclipse.org/)


홈페이지에 접속하면 왼쪽에 **"DOWNLOAD"**라고 보이며, 이것을 클릭하면 이클립스 다운로드 페이지로 이동합니다.

![그림1. 20171205_001_Eclipse_download_1](/assets/img/java/20140916/20171205_001_Eclipse_download_1.png)

다운로드 페이지로 이동하면 본인의 PC 운영체제에 맞춰 이클립스를 다운로드하도록 링크버튼이 보입니다.

![그림2. 20171205_002_Eclipse_download_2](/assets/img/java/20140916/20171205_002_Eclipse_download_2.png)

이클립스 홈페이지에서는 사용자가 접속한 PC의 OS 환경에 맞게 다운로드 경로가 표시됩니다.

가운데 **"DOWNLOAD"**를 클릭하면 이클립스 설치파일이 PC에 다운로드 됩니다.

![그림3. 20171205_003_Eclipse_download_3](/assets/img/java/20140916/20171205_003_Eclipse_download_3.png)

다운로드 된 이클립스 설치파일을 실행하면, 아래와 같이 사용자에 맞게 설치할 수 있는 항목이 나타납니다.

스크롤바를 내리면 여러가지 설치 항목들이 보이는데, 여기서는 JAVA를 공부하기 위한 용도로 설치할 예정이므로, 가장 위에 있는 **"Eclipse IDE for Java Developers"**를 선택합니다.

![그림4. 20171205_004_Eclipse_install_1](/assets/img/java/20140916/20171205_004_Eclipse_install_1.png)

그 다음 설치 폴더(Installation Folder) 경로를 설정하고, 아래 주황색 `INSTALL` 버튼을 클릭합니다.

> 설치경로를 변경하고자 하면, 변경할 경로로 바꿔서 입력하면 됩니다.

![그림5. 20171205_005_Eclipse_install_2](/assets/img/java/20140916/20171205_005_Eclipse_install_2.png)

사용자 동의 창이 뜨면, 아래쪽에 `Accept Now`를 클릭합니다.

![그림6. 20171205_006_Eclipse_install_3](/assets/img/java/20140916/20171205_006_Eclipse_install_3.png)

설치하는데 시간이 좀 걸리네요...(약 1~2분)

![그림7. 20171205_007_Eclipse_install_4](/assets/img/java/20140916/20171205_007_Eclipse_install_4.png)

여기까지 실행되었다면 이클립스 설치는 완료되었습니다.
이제 `LAUNCH` 버튼을 클릭해서 이클립스를 실행합니다.

![그림8. 20171205_008_Eclipse_install_5](/assets/img/java/20140916/20171205_008_Eclipse_install_5.png)


## 이클립스 실행하기

위에서 설치한 후 곧바로 실행하거나, 아래의 설치된 경로의 eclipse.exe 파일을 실행하여 이클립스를 실행합니다.

> 기본 설치경로 : C:\Users\사용자계정\eclipse\java-oxygen\eclipse\eclipse.exe

이클립스가 실행되면, Workspace를 설정하는 Workspace Launcher 윈도우가 나타납니다. 아래의 `Launch`버튼을 클릭합니다.

> Eclipse Launcher 윈도우에서 Workspace는 Java 소스파일들이 저장할 장소를 의미하며, 이 경로는 바꿀 필요가 없지만, 소스코드를 관리하기 위해 알아볼 수 있을 폴더를 만들어 지정하기도 합니다. 경로를 변경하려면 오른쪽 [Browse...]를 클릭하여 변경할 수 있습니다.

![그림9. 20171205_009_Running-Eclipse_1](/assets/img/java/20140916/20171205_009_Running-Eclipse_1.png)

이클립스 실행중...

![그림10. 20171205_010_Running-Eclipse_2](/assets/img/java/20140916/20171205_010_Running-Eclipse_2.png)

이클립스가 실행되고 이클립스에 오신것을 환영하는 Welcome 화면이 나타납니다.

![그림11. 20171205_011_Running-Eclipse_3](/assets/img/java/20140916/20171205_011_Running-Eclipse_3.png)

`[X]`버튼을 눌러 Welcome 화면을 닫으면, 이클립스의 기본화면으로 전환됩니다.

![그림12. 20171205_012_Running-Eclipse_4](/assets/img/java/20140916/20171205_012_Running-Eclipse_4.png)

이클립스의 기본구조를 간단히 살펴보면,

위쪽은 **메뉴 및 툴바**로 구성되어 있고, 왼쪽은 **프로젝트 및 소스를 확인**하고, 아래쪽은 **프로그램 실행결과**를 볼 수 있는 View 파트, 가운데는 실제로 Java 코드를 입력하는 **Editor 파트**로 구성되어 있습니다.


## Hello World!


이제 이클리스에서 Java 코드를 생성하여 실행해봅시다.


이클립스의 왼쪽에 Package Explorer 에서 `마우스 오른쪽을 클릭`하면 메뉴가 팝업됩니다.

팝업메뉴에서 `[New] - [Java Project]`를 클릭합니다.

![그림13. 20171205_013_Hello-World_1](/assets/img/java/20140916/20171205_013_Hello-World_1.png)

New Java Project 윈도우가 나타면, 여기서 Java Project 생성에 대한 다양한 설정을 할 수 있습니다. 특이한 사항이 없다면 기본적으로 설정이 되어 있으므로 **프로젝트 이름(Project name)을 입력**하고 아래쪽에 `[Finish]`버튼을 클릭하여 진행합니다.

> 프로젝트 이름은 임시로 HelloWorld 로 입력했습니다.

![그림14. 20171205_014_Hello-World_2](/assets/img/java/20140916/20171205_014_Hello-World_2.png)

그러면 아래의 화면처럼 왼쪽 Package Explorer에 HelloWorld 라는 프로젝트가 생성됩니다.

![그림15. 20171205_015_Hello-World_3](/assets/img/java/20140916/20171205_015_Hello-World_3.png)

이제 Java 코드를 만들려면, Class 라는 파일을 만들어야 합니다.

HelloWorld 프로젝트에 마우스 커서를 놓고, `마우스 오른쪽 버튼`을 누르면 팝업메뉴가 나타납니다.

팝업메뉴에서 `[New] - [Class]`를 클릭합니다.

![그림16. 20171205_016_Hello-World_4](/assets/img/java/20140916/20171205_016_Hello-World_4.png)

New Java Class 윈도우가 나타나는데, 여기서 클래스에 관련된 내용들을 설정할 수 있으며, 특이한 사항이 없다면, **클래스 이름(Name)을 입력**하고 아래쪽에 `[Finish]`버튼을 클릭합니다.

> 클래스 이름은 임시로 HelloWorld 로 입력했습니다.

![그림17. 20171205_017_Hello-World_5](/assets/img/java/20140916/20171205_017_Hello-World_5.png)

클래스 파일을 만들고 나면, 아래의 화면처럼 왼쪽 HelloWorld 프로젝트에 HelloWorld.java 파일이 생성되어 있으며, 가운데 Editor 에는 HelloWorld.java 파일이 열려있고, 기본적인 코드가 입력되어 있습니다.

![그림18. 20171205_018_Hello-World_6](/assets/img/java/20140916/20171205_018_Hello-World_6.png)

이클립스에서 클래스 파일을 생성하면, 이처럼 기본적으로 입력해야 할 코드는 자동으로 입력되어 만들어집니다.


이제 HelloWorld.java 코드에 추가코드를 더 입력하여 봅시다.

아래의 그림과 같이 HelloWorld 클래스의 바디( {  } )에 `main`을 입력하고 **컨트롤+스페이스(Ctrl+Space)**키를 누르면 main 메서드에 대한 코드템플릿 도움말이 나타납니다. 여기서 `main - main method`를 클릭합니다.

![그림19. 20171205_019_Hello-World_7](/assets/img/java/20140916/20171205_019_Hello-World_7.png)

그러면 아래의 화면처럼 main method 코드가 자동으로 입력됩니다.

저 코드들의 의미는 무엇인지 궁금하겠지만, 나중에 차차 알아보기로 하고 계속 코드를 입력합니다.

![그림20. 20171205_020_Hello-World_8](/assets/img/java/20140916/20171205_020_Hello-World_8.png)

새로 생성된 main method 의 바디( {   } ) 안에 `sysout`를 입력하고 **컨트롤+스페이스(Ctrl+Space)**키를 누르면 자동으로 System.out.println(); 코드가 입력됩니다.

![그림21. 20171205_021_Hello-World_9](/assets/img/java/20140916/20171205_021_Hello-World_9.png)

계속해서 System.out.println(); 의 **괄호()안에 "Hello World!"를 입력**하여 봅시다.

> System.out.println();은 괄호()안의 내용을 화면에 보여주는 Java 코드입니다. 계속 공부하다보면 이 메서드에 대해서 상세하게 알 수 있으므로 지금은 '화면에 보여주기 위한 코드'인가 보구나하고 넘어갑시다.

![그림22. 20171205_022_Hello-World_10](/assets/img/java/20140916/20171205_022_Hello-World_10.png)

여기까지 Hello World!를 출력하기 위해 기본으로 입력하여야 할 Java 코드를 모두 입력하였습니다.


이제 **컨트롤+S(Ctrl+S)**나 `저장`버튼을 눌러서 코드를 저장합니다. 저장이 완료되면 Editor창에 열려 있는 HelloWorld.java 의 제목 부분 앞에 (*) 표시가 있다가 없어집니다. 

![그림23. 20171205_023_Hello-World_11](/assets/img/java/20140916/20171205_023_Hello-World_11.png)

```
※ Tip.

컨트롤+쉬프트+F (Ctrl+Shift+F)를 누르면 코드가 자동으로 들여쓰기 되어 보기좋게 정리됩니다. 이 단축키를 실행하면 코드가 수정되므로 저장해야 합니다.
```
![그림24. 20171205_024_Hello-World_12](/assets/img/java/20140916/20171205_024_Hello-World_12.png)


이제 코드를 실행시켜 봅시다.

코드를 실행하려면, 이클립스 상단의 툴바에서 `실행`버튼을 클릭하거나, HelloWorld.java 에디터(Editor) 창에서 `마우스 오른쪽 클릭`으로 보이는 메뉴에서 **[Run As] - [Java Application]**을 클릭합니다.

![그림25. 20171205_025_Hello-World_13](/assets/img/java/20140916/20171205_025_Hello-World_13.png)

![그림26. 20171205_026_Hello-World_14](/assets/img/java/20140916/20171205_026_Hello-World_14.png)


그러면 이클립스 아래쪽에 Console 뷰(View)가 생기면서 Hello World!라는 결과값이 찍혀 있는것이 보인다.

![그림27. 20171205_027_Hello-World_15](/assets/img/java/20140916/20171205_027_Hello-World_15.png)


여기까지 이클립스 설치부터 자바코드 생성 및 실행까지 살펴보았습니다.



