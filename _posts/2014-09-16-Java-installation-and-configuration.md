---
title: "자바설치 및 환경설정(Java installation and configuration)"
date: 2014-09-16 01:54:00
image: '/assets/img/java/20140916/java-installation-and-confi.jpg'
description: Java installation and configuration.
category: 'java'
tags:
- java
- tutorial
twitter_text: 자바설치 및 환경설정(Java installation and configuration).
introduction: 자바(Java)를 다운로드하여 설치하고, 사용하기 위해 환경을 설정하는 내용을 설명합니다.
---

2017.12.01 updated.

이미지 변경
- Windows7 -> Windows10
- Java7 -> Java9

-----

Java 는 Sun Microsystems에서 제공하는 개발언어였으나, 지금은 Oracle에서 제공하고 있습니다.

아래의 순서대로 Java를 설치합니다.

1. Java 다운로드
2. Java 설치하기
3. Java 환결설정하기
4. Java 설치 테스트


## Java 다운로드

Java를 다운로드하기 위해 오라클 홈페이지로 접속합니다.
- [ORACLE 홈페이지](http://www.oracle.com/index.html)
- [JAVA 다운로드 Quick Click]( http://www.oracle.com/technetwork/java/javase/downloads/index.html)

오라클 메인화면 상단에서 **[Menu - Downloads and Trials - Java - All Java Downloads]**를 클릭합니다.

![그림1. 20171201_001_java_download](/assets/img/java/20140916/20171201_001_java_download.png)

여기서 Top Downloads 의 `Java SE`를 클릭합니다.

![그림2. 20171201_002_javaSE_download](/assets/img/java/20140916/20171201_002_javaSE_download.png)

Java SE Downloads 페이지에서 화면중앙에 보이는 `Java 아이콘`을 클릭합니다.
(오른쪽에 NetBeans 아이콘을 클릭하면 Java와 NetBeans라는 개발툴을 함께 다운로드 할 수 있습니다.)

![그림3. 20171201_003_javaSE_JDK_download](/assets/img/java/20140916/20171201_003_javaSE_JDK_download.png)

`"Accept License Agreement"`를 선택합니다.

![그림4. 20171201_004_javaSE_JDK_download_accept](/assets/img/java/20140916/20171201_004_javaSE_JDK_download_accept.png)

본인의 PC OS 버전에 맞는 `설치파일을 다운로드` 합니다.

![그림5. 20171201_005_javaSE_JDK_download_accept](/assets/img/java/20140916/20171201_005_javaSE_JDK_download_accept.png)


## Java 설치하기

다운로드한 **Java 설치파일을 실행**합니다.

설치시작 화면이 나오면 `[Next >]` 를 클릭합니다.

![그림6. 20171201_006_javaSE_JDK_install_1](/assets/img/java/20140916/20171201_006_javaSE_JDK_install_1.png)

설치위치를 변경하려면 `[Change...]`을 클릭하여 설정할 수 있습니다.
기본 설치경로로 하려면 `[Next >]` 를 클릭합니다.

![그림7. 20171201_007_javaSE_JDK_install_2](/assets/img/java/20140916/20171201_007_javaSE_JDK_install_2.png)

![그림8. 20171201_008_javaSE_JDK_install_3](/assets/img/java/20140916/20171201_008_javaSE_JDK_install_3.png)

설치 도중 JRE 를 설치하는 윈도우가 나타나면 `[다음(N) >]`를 클릭합니다.
> JRE는 Java가 실행할 수 있는 환경입니다.

![그림9. 20171201_009_javaSE_JDK_install_4](/assets/img/java/20140916/20171201_009_javaSE_JDK_install_4.png)

![그림10. 20171201_010_javaSE_JDK_install_5](/assets/img/java/20140916/20171201_010_javaSE_JDK_install_5.png)

Java 설치가 완료되면 [Next Steps]를 클릭하여 더 많은 정보를 얻을 수 있으며,
`[Close]`를 클릭하면 설치가 완료됩니다.

![그림11. 20171201_011_javaSE_JDK_install_6](/assets/img/java/20140916/20171201_011_javaSE_JDK_install_6.png)

## Java 환결설정하기

Java를 어느 경로에서든 실행하기 위해서는 Path에 등록을 해줘야 합니다.
Path를 설정하려면 윈도우의 환경 변수 설정을 해야합니다.

바탕화면의 왼쪽 아래 `돋보기를 클릭`해서 `"내 PC"`를 입력하면, 데스크톱 앱이 보입니다.
여기서 마우스 우측 버튼을 클릭하면 메뉴가 팝업되는데, `"속성"`을 클릭합니다.

![그림12. 20171201_012_java_env_setting_1](/assets/img/java/20140916/20171201_012_java_env_setting_1.png)

시스템 윈도우가 팝업되면,
컴퓨터 이름, 도메인 및 작업 그룹 설정 부분에서 `[설정 변경]` 을 클릭합니다.

![그림13. 20171201_013_java_env_setting_2](/assets/img/java/20140916/20171201_013_java_env_setting_2.png)

시스템 속성 윈도우가 나타나면 `[고급] - [환경 변수(N)...]`을 클릭합니다.

![그림14. 20171201_014_java_env_setting_3](/assets/img/java/20140916/20171201_014_java_env_setting_3.png)

환경 변수 윈도우에서 `[시스템 변수(S)] - [새로 만들기(W)...]`를 클릭합니다.

![그림15. 20171201_015_java_env_setting_4](/assets/img/java/20140916/20171201_015_java_env_setting_4.png)

새 시스템 변수 윈도우가 나타나면, 변수 이름은 `JAVA_HOME` 이라 입력하고, 
변수 값은 기본 설치경로로 했을 경우 C:\Program Files\Java\jdk-9.0.1 를 입력한 후 `[확인]`을 클릭합니다.
> 변수 값은 Java 설치 시 설치경로를 변경했을 경우, 변경한 경로를 입력해야 합니다.

![그림16. 20171201_016_java_env_setting_5](/assets/img/java/20140916/20171201_016_java_env_setting_5.png)

시스템 변수를 새로 만들면 변수에 `JAVA_HOME`이라고 생성됩니다.

![그림17. 20171201_017_java_env_setting_6](/assets/img/java/20140916/20171201_017_java_env_setting_6.png)

이제 시스템 변수 중에서 **"Path"**를 선택하여 `[편집(I)...]`을 클릭합니다.

![그림18. 20171201_018_java_env_setting_7](/assets/img/java/20140916/20171201_018_java_env_setting_7.png)

환경 변수 편집 윈도우에서 `[새로 만들기(N)]`를 클릭합니다.

![그림19. 20171201_019_java_env_setting_8](/assets/img/java/20140916/20171201_019_java_env_setting_8.png)

아까 생성한 시스템 변수를 이용하여 Java 실행경로를 설정합니다.
입력 값은 `%JAVA_HOME%\bin;` 이라고 입력합니다.
bin 다음에 **';'(세미콜론)**을 꼭 붙여야 합니다.

![그림20. 20171201_020_java_env_setting_9](/assets/img/java/20140916/20171201_020_java_env_setting_9.png)

그리고 `[위로 이동(U)]`을 계속 눌러 가장 위로 배치시킨 후, `[확인]`을 클릭합니다.

![그림21. 20171201_021_java_env_setting_10](/assets/img/java/20140916/20171201_021_java_env_setting_10.png)

Path 에 Java 설치경로가 추가되어있음을 확인하고 `[확인]`을 클릭합니다.

![그림22. 20171201_022_java_env_setting_11](/assets/img/java/20140916/20171201_022_java_env_setting_11.png)



## Java 설치 테스트

이제 Java가 제대로 설치되었는지 테스트해 봅시다.

`[윈도우키 + R]` 을 실행하거나, `[시작] `에서 **"cmd"**를 입력하여 Console 창을 실행합니다.

![그림23. 20171204_023_java_test_1](/assets/img/java/20140916/20171204_023_java_test_1.png)

![그림24. 20171204_024_java_test_2](/assets/img/java/20140916/20171204_024_java_test_2.png)

Console 창에서 **"java -version"**을 입력하면 다음과 같이 나타납니다.

![그림25. 20171204_025_java_test_3](/assets/img/java/20140916/20171204_025_java_test_3.png)

여기까지 모두 완료되면 Java가 정상적으로 설치되었으며,

앞으로 Java 개발을 시작하면 됩니다. 









