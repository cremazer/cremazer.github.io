---
title: "Flutter - Test first app"
date: 2021-03-07 22:43:00
image: '/assets/img/flutter/20210307/00-Test-drive.jpg'
description: Test for Flutter first app on Windows.
category: 'flutter'
tags:
- flutter
- test
- tutorial
twitter_text: Flutter - Test first app on Windows
introduction: 윈도우 환경에서 Flutter를 첫 번째 앱을 실행해봅니다.
---

블로그를 작성하던 중에 `Flutter 2`가 발표되었고 공식문서의 한글버전 링크도 생겼습니다. (기존에 생겼는데 제가 몰랐던 것일수도 있습니다.)

- [2021.3.4 키노트(Flutter Engage) - Youtube](https://youtu.be/zSbsIiluixw)

# 개요

> 공식 사이트 > 시작하다 > 3.시운전

이 포스트에서는 템플릿을 활용하여 새로운 Flutter 앱을 만들고, 실행하고, 앱을 변경한 후에 `hot reload`를 하는 방법을 연습해 보려고 합니다.

에디터는 Android Studio를 활용했습니다.

### 1. Android Studio IDE를 실행하고 `Create New Flutter Project`를 선택합니다.

![그림1.](/assets/img/flutter/20210307/01-Test-drive-welcome.png)

### 2. 프로젝트 타입으로 Flutter Application을 선택하고, Next를 클릭합니다.

![그림2.](/assets/img/flutter/20210307/02-Test-drive-New-Flutter_Project.png)

### 3. Flutter Application의 Configure를 모두 입력하고, Next를 클릭합니다.

- Project name : 프로젝트 이름입니다. (예: flutter_app)
- Flutter SDK path : Flutter를 설치한 경로입니다. (예: G:\src\flutter)
- Project location : 소스코드가 설치될 경로입니다. (예: G:\project\FlutterApp)
- Description : 프로젝트를 설명합니다. (예: A new Flutter application)

![그림3.](/assets/img/flutter/20210307/03-Test-drive-Configure-New-Flutter-Application.png)

### 4. package 이름을 입력하고, Finish를 클릭합니다.

> 새로운 Flutter 앱을 만들 때 일부 Flutter IDE 플러그인은 com.example과 같이 역순으로 회사 도메인 이름을 요청합니다. 회사 도메인 이름과 프로젝트 이름은 앱이 출시 될 때 Android 용 패키지 이름 (iOS 용 번들 ID)으로 함께 사용됩니다. 앱이 출시 될 수 있다고 생각되면 지금 패키지 이름을 지정하는 것이 좋습니다. 앱이 출시되면 패키지 이름을 변경할 수 없으므로 이름을 고유하게 만드세요.

![그림4.](/assets/img/flutter/20210307/04-Test-drive-Set-the-package-name.png)

---

이제 Android Studio가 SDK를 설치하고 프로젝트를 생성할 때까지 기다립니다.
프로젝트가 생성되면, main.dart 파일이 열리고, Demo 코드가 작성되어 있습니다.
Demo 코드에는 [머티리얼 컴포넌트](https://material.io/guidelines)를 사용한 간단한 예시 코드가 포함된 앱이 들어있는 Flutter 프로젝트가 생성됩니다.

![그림5.](/assets/img/flutter/20210307/05-Test-drive-main-dart.png)

기본으로 생성된 코드에서 주석을 제거하면 코드가 좀 더 간결해지네요.
코드 구조에 대해서는 이후에 좀 더 자세히 살펴보도록 하겠습니다.

![그림6.](/assets/img/flutter/20210307/06-Test-drive-main-dart-remove-comments.png)

### 5. 앱 실행하기

앱을 실행해 보려면 Android Studio 오른쪽 상단에 툴바가 있습니다.

![그림7.](/assets/img/flutter/20210307/07-Test-drive-android-studio-toolbar.png)

앱을 실행할 Android 기기를 선택하고, 세모(Run) 버튼을 클릭합니다.

앱을 실행할 Android 기기가 리스트에 없으면 아래의 경로에서 사용할 새 기기를 생성합니다.

> Tools > ADV Manager

![그림8.](/assets/img/flutter/20210307/08-Test-drive-adv-manager.png)

자신의 핸드폰에서 실행하는 방법등 다양한 방법들이 있지만, 이 포스트에서는 다루지 않으므로 [ADV 관리](https://developer.android.com/studio/run/managing-avds)를 참고하여 좀 더 다양한 환경에서 실행해 볼 수 있습니다.

Android Studio에서 처음 앱 빌드가 진행되는 시간이 꽤 걸리는 느낌이 드네요.
앱 빌드가 완료되면, 가상 기기에서 초기 앱이 뜨는 것을 확인할 수 있습니다.

![그림9.](/assets/img/flutter/20210307/09-Test-drive-firstapp-hot-reload.png)

### 6. Hot reload

Flutter는 Stateful Hot Reload를 통해 소스코드를 변경하더라도 앱을 재시작하거나 앱 상태를 잃어버리지 않고 실행중인 앱의 코드를 다시 로드할 수 있습니다.

- lib/main.dart 파일을 엽니다. (처음 생성되었을 때 열린 파일입니다.)
- 문자열을 변경합니다.

> class _MyHomePageState > Widget build > Scaffold > body > child: Column > children: <Widget> > Text

Text 안에 문자열 내용이 `You have pushed the button this many times:`로 되어 있는데, 여기서 `pushed -> clicked `으로 변경하고 저장(Ctrl+S)합니다.

Android Studio 아래 Console 창에서 hot reload가 빠르게 실행되는 로그를 확인할 수 있습니다.

![그림10](/assets/img/flutter/20210307/10-Test-drive-firstapp-hot-reload-console.png)

앱을 재시작하지 않고 가상 기기에서 문자열이 바뀌어 있는 것도 즉시 확인할 수 있습니다.

![그림11](/assets/img/flutter/20210307/11-Test-drive-firstapp-hot-reload-changed.png)

### 주의!!

앱이 `debug나 hot reload` 상태에서는 성능테스트를 하지않은 것이 좋다고 공식 사이트에 언급되어 있습니다.

![그림11](/assets/img/flutter/20210307/12-Test-drive-do-not-test-the-performance.png)

성능을 분석하거나 앱을 출시할 준비가 되면 [Flutter 빌드 모드](https://flutter-ko.dev/docs/testing/build-modes)를 참조하여 확인하시면 좋겠습니다.

### Github 연동하기

지금까지의 소스코드에서 계속 작업을 하기 위해 작성한 코드를 관리해야 합니다.
아래의 링크를 참고하여 Github에 코드를 공유하여 관리할 수 있습니다.

- [Android 안드로이드 스튜디오 GitHub 연동하기 initial commit](https://ppomelo.tistory.com/50)

---

여기까지 Flutter 공식 문서에서 가이드한 내용에 대해 연습해 봤습니다.

저와 같이 Flutter도 처음이고, App 개발도 처음인 분들께 작성하는 이 포스트가 도움이 되었으면 좋겠습니다.


### Reference

[Flutter - 시작하기 - 3.시운전](https://flutter-ko.dev/docs/get-started/test-drive?tab=androidstudio)

[Flutter Meterial Component 디자인](https://material.io/guidelines)

[Android 가상 기기 만들기 및 관리하기](https://developer.android.com/studio/run/managing-avds)

[Android 안드로이드 스튜디오 GitHub 연동하기 initial commit](https://ppomelo.tistory.com/50)