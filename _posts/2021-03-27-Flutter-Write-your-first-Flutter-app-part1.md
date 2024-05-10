---
title: "Flutter - 첫 번째 앱 작성하기, Part 1"
date: 2021-03-27 14:40:34
image: '/assets/img/flutter/20210327/00-First-Flutter-app-part1.jpg'
description: This is a guide to creating your first Flutter app.
category: 'flutter'
tags:
- flutter
- tutorial
twitter_text: Flutter - Practice write your first Flutter app, part 1
introduction: Flutter 첫 번째 앱을 작성하고, 앱의 기본 구조, 패키지를 찾고 사용하여 기능을을 확장하는 등 앱이 어떻게 동작하는지에 대해 학습합니다.
---

# 개요

> 공식 사이트 > 시작하기 > 4. 첫 번째 앱 작성하기

이 포스트에서는 첫 Flutter 앱을 만드는 방법에 대해 학습합니다.

변수, 반복문, 조건문 등 기본 프로그래밍 개념과 객체지향에 친숙하다면, 이 튜토리얼을 완료할 수 있고, Dart 언어의 경험이나 모바일, 웹 프로그래밍 경험이 없어도 상관없다고 설명되어 있는데, 그 수준이 어느정도인지 한 번 살펴보겠습니다.

이 가이드는 `Google Developers`의 [코드랩](https://codelabs.developers.google.com/)에서 [1부](https://codelabs.developers.google.com/codelabs/first-flutter-app-pt1)와 [2부](https://codelabs.developers.google.com/codelabs/first-flutter-app-pt2)로 나뉘어 볼 수 있습니다.

### 학습할 내용 (Part 1)

간단한 모바일 앱을 구현하여 앱이 어떻게 동작하는지 알아봅니다.

- iOS와 Android, 그리고 웹에서 자연스럽게 보이는 Flutter 앱을 작성하는 방법.
- Flutter 앱의 기본 구조.
- 패키지를 찾고, 패키지를 사용하여 기능을 확장하기.
- 더 빠른 개발 사이클을 위한 hot reload 사용.
- Stateful 위젯을 구현하는 방법
- Lazy하게 로드하는 무한 리스트를 만드는 방법

위의 6개 항목중에 처음 접하는 용어(패키지, Stateful, Lazy)가 보이는데, 무슨 내용인지 잘 모르겠지만 계속해서 살펴보겠습니다.

### 학습 준비

이번 학습에서 필요한 도구(?)들입니다.

- Flutter SDK
- 에디터 (Android Studio, VS Code 등)
- 컴퓨터에 연결되어 있고 개발자 모드로 되어 있는 실제 기기 (안드로이드 또는 iOS)
- iOS 시뮬레이터
- Android 에뮬레이터
- 브라우저 (Chrome 사용 권장)

이미 이전 포스트 [Flutter - Getting started on Windows](https://cremazer.github.io/Flutter-Get-Started/)를 읽어보셨거나 기본적인 개발환경이 준비되어 있다면 `Flutter SDK`와 `에디터`는 설치되어 있을 것입니다.

[Flutter - Test first app](https://cremazer.github.io/Flutter-Test-drive/) 포스트에서  Android 에뮬레이터 실행도 해봤기 때문에 iOS 시뮬레이터와 실제 기기만 준비되어 있으면 좋을듯 합니다.

> 저는 MacBook과 iPhone이 준비되어 있지 않아서 iOS 시뮬레이터와 실제 기기를 연동하는 과정은 생략하겠습니다.


# 1단계: Starter Flutter app 만들기

[Flutter - Test first app](https://cremazer.github.io/Flutter-Test-drive/) 포스트를 참고하여 간단한 템플릿 기반 Flutter 앱을 만듭니다.

![그림1.](/assets/img/flutter/20210327/01.Write-your-first-app-pt1-new-flutter-project.png)

스타트업 회사를 위해 이름을 생성하여 제안하는 모바일 앱을 구현할 예정이기 때문에 Project name은 myapp 대신 `startup_namer`로 지정합니다.

![그림2.](/assets/img/flutter/20210327/02.Write-your-first-app-pt1-configure.png)

코드랩에서는 주로 Dart 코드가 있는 `lib/main.dart`를 수정합니다.

> Android Studio에서 생성하면 처음에 보이는 main.dart 코드가 lib/main.dart입니다.

화면 중앙에 "Hello World"를 표시하기 위해 lib/main.dart의 모든 코드를 삭제하고, 아래의 코드를 복사하여 붙여넣습니다.

```dart
// Copyright 2018 The Flutter team. All rights reserved.
// Use of this source code is governed by a BSD-style license that can be
// found in the LICENSE file.

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Welcome to Flutter',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
    );
  }
}
```

- 윈도우 Android Studio 코드 포맷 단축키 `Ctrl + Alt + L`

코드를 붙여넣고, Andriod 에뮬레이터를 실행하면 아래와 같은 화면을 볼 수 있습니다.

![그림3.](/assets/img/flutter/20210327/03.Write-your-first-app-pt1-run-the-app.png)

> 처음 실행할 때는 로딩 시간이 조금 걸릴 수 있습니다. 이후에는 hot reload를 사용하여 빠르게 업데이트 되는 모습을 확인할 수 있습니다.

- 이 예제에서는 Material App을 만듭니다.

  [Meterial](https://material.io/design/)은 모바일 및 웹에서 표준으로 사용되는 `시각 디자인 언어`이며, Flutter는 다양한 Meterial 위젯을 제공합니다.

- main() 메서드는 화살표(=>) 표기법을 사용합니다.

> void main() => runApp(MyApp());

- 앱은 StatelessWidget을 상속받아 앱 자체를 위젯으로 만듭니다.

- Meterial 라이브러리의 Scaffold 위젯은 홈(`home`) 스크린의 위젯 트리를 구성하는 `app bar, title, body` 속성을 기본으로 제공합니다.

```dart
// ...
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          child: Text('Hello World'),
        ),
      ),
// ...
```

- 위젯의 주된 임무는 다른 하위 위젯을 어떻게 표현할 지를 설명하는 `build()` 메서드를 제공하는 것입니다.

```dart
// ...
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Welcome to Flutter',
      home: Scaffold(
        ...
      ),
    );
  }
// ...
```

- 이 예제에서 body 부분을 보면 자식(`child`) 위젯으로 `Text`를 포함하는 `Center` 위젯으로 구성되어 있습니다. Center 위젯은 하위 위젯을 화면 중앙으로 정렬하게 합니다.

```dart
// ...
        body: Center(
          child: Text('Hello World'),
        ),
// ...
```

---

# 2단계 : 외부 패키지 이용하기

이번 단계에서는 영어 단어가 수 천개 포함되어 있는 오픈 소스 패키지인 `english_words`를 사용하여 앱에서 영어 단어를 랜덤으로 출력하게 만듭니다.

- package [english_words](https://pub.dev/packages/english_words)

> 위의 english_words package 링크에 접속하면 최종 버전(Latest)을 확인합니다. 이 글을 작성하는 시점에서 최종 버전은 3.1.5로 확인됩니다.

그 외에 [pub.dev](https://pub.dev/flutter/packages?q=english_words)에서 검색을 통해서 더 많은 패키지를 찾을 수 있습니다.

Flutter 앱에서 의존성(dependencies) 및 asset 관리는 pubspec 파일이 담당합니다.

> 파일 위치 : Project ROOT > pubspec.yaml

![그림4.](/assets/img/flutter/20210327/04.Write-your-first-app-pt1-pubspec.png)

english_words 패키지를 위의 pubspec.yaml 파일의 의존성 목록(dependencies)에 추가합니다.

![그림5.](/assets/img/flutter/20210327/05.Write-your-first-app-pt1-use-english-words-package.png)

Android Studio의 코드 편집기 화면에서 추가한 패키지에 커서가 있으면, 전구 모양 아이콘이 나타납니다. 이녀석을 클릭하면 `Pub get`이 팝업되고 클릭하면 추가한 english_words 패키지를 프로젝트로 가져옵니다.

![그림6.](/assets/img/flutter/20210327/06.Write-your-first-app-pt1-get-english-words-package.png)

그러면 아래와 같이 콘솔창에서 메세지를 확인할 수 있습니다.

![그림7.](/assets/img/flutter/20210327/07.Write-your-first-app-pt1-get-english-words-package-finished.png)

또한 pubspec.lock 파일이 자동으로 생성되는데, 이 파일에는 방금 가져온 패키지 목록과 버전 번호를 포함하고 있습니다.

![그림8.](/assets/img/flutter/20210327/08.Write-your-first-app-pt1-add-pubspec-lock-english-words-package.png)

여기까지 패키지를 프로젝트에 가져오는 과정이었고, 이제 dart코드에 가져온 패키지를 적용해봅니다.

1. lib/main.dart 파일에 가져온 패키지를 import
2. build 위젯안에 `WordPair`를 선언하는 코드를 작성
3. "Hello World"를 영어 단어를 출력하는 코드로 변경

![그림9.](/assets/img/flutter/20210327/09.Write-your-first-app-pt1-write-WordPair-code.png)

`WordPair` class의 자세한 내용은 pub.dev의 [english_words library](https://pub.dev/documentation/english_words/latest/english_words/WordPair-class.html) 문서에 자세히 설명되어 있으므로 참고하면 좋을 것 같습니다.

이제 앱이 실행중이라면, `hot reload`를 클릭해보세요.

![그림10.](/assets/img/flutter/20210327/10.Write-your-first-app-pt1-click-hot-reload.png)

`hot reload`를 클릭하거나, 코드를 수정하고 저장하면 랜덤하게 보이는 영어 단어를 볼 수 있습니다.

---

# 3단계 : Stateful 위젯 추가하기

`Stateful`은 간략하게 '사용자가 터치하여 뭔가를 바꿔야 하는 경우'에 사용한다고 합니다.

이번에는 Stateful 위젯인 `RandomWords`를 추가하고, 그 위젯에서 State 클래스인 RandomWordsState를 생성할 것입니다. 그리고 RandomWords를 기존 Stateless 위젯인 MyApp의 자식으로 사용할 것입니다.

> 1.main.dart 아래쪽에 최소한의 상태를 가지는 클래스를 생성합니다.

```dart
class RandomWordsState extends State<RandomWords> {
  // TODO Add build() method
}
```

RandomWordsState 클래스는 RandomWords로 지정된 제네릭으로 State클래스를 사용하고 있는 State<RandomWords>를 상속받고 있습니다. RandomWords로 위젯을 위해 상태를 보관하여 대부분의 앱 로직과 상태는 여기서 유지됩니다.

RandomWordsState는 RandomWords 클래스에 의존적(Dependent)이라고 말하여, 아래 2.에서 RandomWords 클래스를 생성합니다.

> 2.RandomWordsState class 아래쪽에 Stateful 위젯을 상속받은 RandomWords를 생성합니다.

`RandomWords` 위젯은 상태 클래스를 만드는 것 이외에는 특별히 하는 기능은 없습니다.

```dart
class RandomWords extends StatefulWidget {
  @override
  RandomWordsState createState() => RandomWordsState();
}
```

RandomWords 상태 클래스를 추가해도 아직 에러가 발생합니다. build() 메서드가 없기 때문인데요, 1.에서 RandomWordsState 클래스의 build() 메서드를 추가해야 하기 때문입니다.

> 3.RandomWordsState 클래스에 build() 메서드를 추가합니다.

```dart
class RandomWordsState extends State<RandomWords> {
  @override
  Widget build(BuildContext context) {
    final wordPair = WordPair.random();
    return Text(wordPair.asPascalCase);
  }
}
```

여기까지 코드를 작성하셨다면, Android Studio에서 에러가 발생하는 부분이 모두 사라졌을 것입니다.

마지막으로, MyApp에서 영어 단어 쌍을 보여주는 코드를 3단계에서 생성한 RandomWords 클래스를 호출하는 코드로 바꿔줍니다.

> 4.MyApp의 build() 메서드 안에 입력했던 wordPair 변수를 삭제하고, MeterialApp 의 body에 입력한 child를 Text에서 RandomWords()를 호출하도록 변경합니다. 코드를 수정하면 아래와 같은 코드를 작성할 수 있습니다.

```dart
// ...
class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // final wordPair = WordPair.random(); // 삭제된 wordPair 변수
    return MaterialApp(
      title: 'Welcome to Flutter',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          // child: Text(wordPair.asPascalCase),  // 변경된 child
          child: RandomWords(),
        ),
      ),
    );
  }
}
// ...
```

이제 앱을 재시작합니다. 새로운 class를 생성하면 hot reload는 사용할 수 없나봅니다.

2단계에서처럼 `hot reload`를 클릭하거나, 코드를 수정하고 저장하면 랜덤하게 보이는 영어 단어를 볼 수 있습니다.

![그림11.](/assets/img/flutter/20210327/11.Write-your-first-app-pt1-add-Stateful-Widget.png)

---

# 4단계 : 무한 스크롤 ListView 생성하기

이 단계에서는 3단계에서 만든 `RandomWordsState` 클래스를 확장하여 영어 단어 쌍 목록을 생성하고 리스트로 보여줍니다. `ListView` 위젯 안에 보여주는 단어 쌍 목록이 사용자가 스크롤할 때마다 계속 늘어납니다. ListView의 builder 팩토리 생성자를 사용하면 필요에 따라 lazy한(게으른?) 방식으로 목록을 만들어줍니다.

> 1.RandomWordsState 클래스에 아래에 final로 선언된 _suggestions와 _biggerFont 변수를 선언합니다.

- _suggestions : 제안된 영어 단어 쌍을 저장하기 위한 배열
- _biggerFont : 글자 크기를 키우기 위한 폰트 스타일

```dart
class RandomWordsState extends State<RandomWords> {
  final _suggestions = <WordPair>[];
  final _biggerFont = const TextStyle(fontSize: 18.0);
  // ···
}
```

※ Dart언어에서 private한 변수를 선언하려면 식별자(변수) 앞에 밑줄(_)을 붙입니다.

> Unlike Java, Dart doesn’t have the keywords public, protected, and private. If an identifier starts with an underscore (_), it’s private to its library. For details, see Libraries and visibility.

<br>

> 2.RandomWordsState 클래스에 _buildSuggestions() 함수를 추가합니다.

- _buildSuggestions() : 제안된 영어 단어 쌍을 표시하는 ListView를 만들기 위함.

```dart
class RandomWordsState extends State<RandomWords> {
  
  // ...
  
  Widget _buildSuggestions() {
    return ListView.builder(
        padding: const EdgeInsets.all(16.0),
        itemBuilder: /*1*/ (context, i) {
          if (i.isOdd) return Divider(); /*2*/

          final index = i ~/ 2; /*3*/
          if (index >= _suggestions.length) {
            _suggestions.addAll(generateWordPairs().take(10)); /*4*/
          }
          return _buildRow(_suggestions[index]);
        });
  }
}
```

> ※ 코드설명

- ListView를 생성할 때, 기본적으로 16픽셀 여백을 표현?하기 위해 [EdgeInsets](https://api.flutter.dev/flutter/painting/EdgeInsets-class.html) Class를 사용한듯 합니다. (이 부분이 정확히 무엇인지 잘 모르겠어서 일단 넘어갑니다.)
- `/*1*/` itemBuilder 콜백에서 context와 i를 매개변수로 선언했는데, 여기서 context는 어디서 사용하는 것인지 궁금하네요.
- `/*2*/` i는 0부터 시작하며, 홀수일 때, [Divider](https://api.flutter.dev/flutter/material/Divider-class.html) Class를 사용하여 구분선 위젯으로 return 합니다.
- `/*3*/` i ~/ 2 는 i를 2로 나눈 뒤 정수 결과를 반환합니다. (예: 1,2,3,4,5 ~/ 2 => 0,1,1,2,2 )
  - [~/ : 참고]((https://dart.dev/guides/language/language-tour#operators)
  - 이렇게 `index`가 계산되어 ListTile과 구분선이 각각 ListView에 생성됩니다.
- `/*4*/` index가 생성된 영어 단어 쌍 개수 이상이 되면, generateWordPairs()를 통해 10개씩 생성하여 `_suggestions` 배열에 추가합니다.
- 마지막으로 `_buildRow()`를 호출하여 ListTile에 표시합니다. (다음 과정에서 진행..)

<br>

> 3.RandomWordsState에 _buildRow()를 추가합니다.

```dart
class RandomWordsState extends State<RandomWords> {
  
  // ...
  
  Widget _buildSuggestions() {
    // ...
  }
  
  Widget _buildRow(WordPair pair) {
    return ListTile(
      title: Text(
        pair.asPascalCase,
        style: _biggerFont,
      ),
    );
  }
} // end RandomWordsState class
```

<br>

> 4.이제 1.에서 생성했던 RandomWordsState 클래스의 build 메서드를 아래의 코드로 변경합니다.

기존의 build 메서드에서는 단어 생성 라이브러리를 직접 호출했는데, 아래의 코드에서는 [Scaffold](https://api.flutter.dev/flutter/material/Scaffold-class.html) 클래스를 활용하여 레이아웃을 구현하여 2.에서 생성한 `_buildSuggestions()`를 호출하도록 하는 내용입니다.

```dart

class RandomWordsState extends State<RandomWords> {
  final _suggestions = <WordPair>[];
  final _biggerFont = const TextStyle(fontSize: 18.0);

  @override
  Widget build(BuildContext context) {
    // 기존코드
    // final wordPair = WordPair.random();
    // return Text(wordPair.asPascalCase);
    
    // 변경코드
    return Scaffold(
      appBar: AppBar(
        title: Text('Startup Name Generator'),
      ),
      body: _buildSuggestions(),
    );
  }

  Widget _buildSuggestions() {
  // ...

} // end RandomWordsState class
```

<br>

> 5.마지막으로 MyApp 클래스의 build()를 아래의 코드로 변경합니다.

기존에 Scaffold 클래스로 보여주던 MeterialApp의 내부 코드를 RandomWords()를 호출하여 보여지도록 변경하는 내용입니다.

- 변경하는 속성은 title과 home입니다.

```dart

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // final wordPair = WordPair.random(); // 삭제된 wordPair 변수
    return MaterialApp(
      // 변경코드
      title: 'Startup Name Generator',
      home: RandomWords(),
      
      /* 기존코드
      title: 'Welcome to Flutter',
      home: Scaffold(
        appBar: AppBar(
          title: Text('Welcome to Flutter'),
        ),
        body: Center(
          // child: Text(wordPair.asPascalCase),  // 변경된 child
          child: RandomWords(),
        ),
      ),
      */
    );
  }
} // end MyApp class

```

<br>

> 6.이제 에뮬레이터를 다시 시작합니다.

앱이 실행되면 아래와 같이 영어 단어 리스트가 나타나는 것을 확인할 수 있으며, 아래쪽으로 스크롤하면 계속해서 나오는 것을 볼 수 있습니다.

![그림12.](/assets/img/flutter/20210327/12.Write-your-first-app-pt1-running-the-MyApp.png)

---

여기까지 인터랙티브한 Flutter 앱을 작성해 보았습니다.

- [전체 코드 보기 Github](https://github.com/cremazer/startup_namer/blob/master/lib/main.dart)

<br>

`첫 번째 앱을 작성하기`를 실습해 보면서 Dart 코드 작성, Flutter의 API를 활용하는 방법과 외부 서드파티 라이브러리를 활용하는 방법에 대해 알게되었고, hot reload의 편리함을 경험할 수 있었습니다. 그 외에 처음으로 접하는 앱 개발에 필요한 용어들에 대한 개념의 이해가 있다면 좀 더 다양한 앱을 개발해 볼 수 있을 것이라는 생각이 들었습니다.

<br>


### Reference

[Flutter 첫 Flutter 앱 작성하기 - 1부](https://flutter-ko.dev/docs/get-started/codelab)

[Google Developers Codelabs](https://codelabs.developers.google.com/)

[Meterial Design](https://material.io/design)

[Dart => 화살표 코드 의미](https://ska0225.tistory.com/14)

[flutter에서 사용하는 dart 언어의 함수 알아보기](https://minwook-shin.github.io/flutter-dart-lang-tour-function/)

[pub.dev Flutter packages](https://pub.dev/flutter/packages)

[플러터 - Stateless Widget과 Stateful Widget 차이점](https://itwise.tistory.com/29)

[Flutter Stateful & Stateless](https://greenhelix.tistory.com/105)

[Dart Tour - Important concepts related to private](https://dart.dev/guides/language/language-tour#important-concepts)

- API

  [EdgeInsets class](https://api.flutter.dev/flutter/painting/EdgeInsets-class.html)

  [Divider class](https://api.flutter.dev/flutter/material/Divider-class.html)

  [Scaffold class](https://api.flutter.dev/flutter/material/Scaffold-class.html)
