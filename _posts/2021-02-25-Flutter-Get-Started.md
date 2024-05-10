---
title: "Flutter - Getting started on Windows"
date: 2021-02-25 07:17:34
image: '/assets/img/flutter/20210225/00-get-started.jpg'
description: Getting started Flutter on Windows.
category: 'flutter'
tags:
- flutter
- install
- tutorial
twitter_text: Flutter - Getting started on Windows
introduction: 윈도우 환경에서 Flutter를 시작하기 위한 설치과정입니다. 
---

# Flutter 시작하기

> 공식 사이트 > 시작하다 > 1.설치

이 문서는 Flutter [공식 사이트](https://flutter.dev/docs/get-started/install)를 참고하여 `Windows OS`에서 Flutter를 설치하고 실행하는 내용을 정리했습니다.

`Mac OS`에서 Flutter를 설치하려면 아래의 문서를 참고하세요.

* [플러터(Flutter) 시작하기 — (1) 개발 환경 구축](https://medium.com/@hj.veronica.shim/%ED%94%8C%EB%9F%AC%ED%84%B0-flutter-%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-1-%EA%B0%9C%EB%B0%9C-%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%B6%95-1131711dd651)



# 설치

> 공식 사이트 > 시작하다 > 1.설치 > Windows 설치

Flutter를 설치하기 에서 위한 운영체제를 선택합니다.

Windows, Mac OS, Lunux, Chrome OS를 지원하네요.

저는 Windows에서 개발해야 하는 환경이므로 Windows를 선택했습니다.

![그림1.get-started-install](/assets/img/flutter/20210225/01-get-started-install.png)


## 시스템 요구 사항

Flutter를 Windows에 설치하기 위한 `최소 요구 사항`입니다.

* 운영 체제 : Windows 7 SP1 이상 (64 비트), x86-64 기반
* 디스크 공간 : 1.32GB (IDE / 도구 용 디스크 공간은 포함되지 않음)
* 도구
  * PowerShell 5.0 이상 (Windows 10에 사전 설치됨)
  * Git

## Flutter SDK 다운로드

현재(2021.02.25) 시점을 기준으로 최신 릴리스 버전은 `1.22.6` 으로 확인되며, 설치할 번들을 다운로드 합니다.

#### Git이 설치되어 있는 경우

GitHub의 [Flutter Repository](https://github.com/flutter/flutter)에서 소스코드를 가져와 필요에 따라 브랜치 또는 태그를 변경할 수 있습니다.

> 예: C:\src>git clone https://github.com/flutter/flutter.git -b stable

![그림2.get-started-install-git-clone](/assets/img/flutter/20210225/02-get-started-install-git-clone.png)

#### Git이 설치되어 있지 않은 경우

아래 설치 파일 다운로드를 클릭하여 설치할 번들을 직접 다운로드합니다.

[1.22.6 설치 파일 다운로드](https://storage.googleapis.com/flutter_infra/releases/stable/windows/flutter_windows_1.22.6-stable.zip)

* 다른 릴리스 채널 및 이전 버전 빌드 파일을 다운로드 하려면 [SDK 릴리스](https://flutter.dev/docs/development/tools/sdk/releases) 페이지를 참조하세요.

> ※ 설치 주의사항
> C:\Program Files\ 에서는 설치하지 말라고 합니다.
> 다운로드한 SDK zip 파일은 다른 위치에 압축을 풀어줍니다.

`예 : C:\src\flutter 또는 g:\src\flutter`


## PATH 설정 추가

Windows 콘솔창에서 Flutter 명령을 실행하려면 `PATH`를 추가해야 합니다.

윈도우 왼쪽 아래 검색 입력란에 `고급 시스템 설정`을 입력하여 `시스템 속성` 창을 엽니다.

![그림3.get-started-install-path-setting](/assets/img/flutter/20210225/03-get-started-install-path-setting.png)

![그림4.get-started-install-Environment-variable](/assets/img/flutter/20210225/04-get-started-install-Environment-variable.png)

![그림5.get-started-install-Environment-variable-path](/assets/img/flutter/20210225/05-get-started-install-Environment-variable-path.png)

![그림6.get-started-install-Environment-variable-path-new](/assets/img/flutter/20210225/06-get-started-install-Environment-variable-path-new.png)


## Flutter doctor 실행

PATH 설정을 완료했으면, 이제 콘솔창(cmd)을 열어서 위에서 flutter를 설치한 경로로 이동하여 `flutter doctor` 명령어를 실행합니다.

이 명령어를 실행하는 이유는 flutter 설정에서 플랫폼에 필요한 의존성 데이터가 있는지 확인하여 해결하기 위함입니다.

![그림7.get-started-flutter-doctor](/assets/img/flutter/20210225/07-get-started-flutter-doctor.png)

저의 실행결과는 초록색 체크 표시 1개와 느낌표 4개가 발생했습니다.

![그림8.get-started-flutter-doctor-report1](/assets/img/flutter/20210225/08-get-started-flutter-doctor-report1.png)

원활한 개발환경을 설정하기 위해 하나씩 느낌표를 없애보겠습니다.

### Android-toolchain 문제해결

report에 의하면 android licenses 문제를 해결하기 위해 `flutter doctor --android-licenses`명령어를 실행하라고 언급되어 있습니다.

명령어를 실행하면, 아래의 그림과 같이 라이센스를 확인하기 위한 동의여부를 여러번 물어보면서 입력하는 란이 나오는데, 여기서 `y`를 입력하면 계속해서 넘어가서 문제를 해결할 수 있습니다.

![그림9.get-started-flutter-doctor-resolve-for-android](/assets/img/flutter/20210225/09-get-started-flutter-doctor-resolve-for-android.png)

![그림10.get-started-flutter-doctor-resolve-for-android](/assets/img/flutter/20210225/10-get-started-flutter-doctor-resolve-for-android.png)

다시 `flutter doctor` 명령어를 실행하여 결과를 확인해보면 Android toolchain의 느낌표가 체크되었습니다.

![그림11.get-started-flutter-doctor-resolve-for-android](/assets/img/flutter/20210225/11-get-started-flutter-doctor-resolve-for-android.png)

### Android Studio Plugin 설치

이 문제를 해결하려면 먼저 Android Studio가 설치되어 있어야 합니다. 

> 아직 설치를 하지 않았다면, 아래의 링크에서 다운로드하여 설치하세요.

[https://developer.android.com/studio](https://developer.android.com/studio)

설치하는 내용은 아래의 Reference의 영상이나 총정리 블로그를 참고하세요.

Android Studio 설치 후에 실행한 후에 flutter plugin을 설치합니다.

저는 기존에 미리 설치해 놓고 실행해보니, plugin을 설치하는 참고 문서가 제 상황과 달라서 Flutter 강좌 01 문서를 참고하여 plugin을 설치했습니다.

> File > Settings...

![그림12.get-started-android-studio-fluggin-install](/assets/img/flutter/20210225/12-get-started-android-studio-fluggin-install.png)

### VSCode Extensions 설치

> VSCode가 아직 설치하지 않았다면, 아래의 링크에서 다운로드하여 설치하세요.

[VSCode 다운로드 사이트](https://code.visualstudio.com/download)

VSCode를 실행시킨 후에 EXTENSIONS에서 flutter를 설치합니다.

![그림13.get-started-vscode-extensions-flutter](/assets/img/flutter/20210225/13-get-started-vscode-extensions-flutter.png)

![그림14.get-started-vscode-extensions-flutter](/assets/img/flutter/20210225/14-get-started-vscode-extensions-flutter.png)

---

여기까지 진행했음에도 불구하고 `flutter doctor`를 실행해보면 저는 아직 Android Studio 문제는 해결되지 않았다고 표시되네요.

![그림15.get-started-flutter-doctor-report2](/assets/img/flutter/20210225/15-get-started-flutter-doctor-report2.png)

이 문제를 해결하기 위해 구글에서 `flutter doctor android studio 4.1 flutter plugin not installed`라고 검색했더니 `stackoverflow`에서 비슷한 상황이 있었습니다.

Mac OS와 Windows OS의 해결방법이 있으므로 참고하시면 됩니다.

Windows OS에서는 콘솔창(cmd)에서 아래의 명령어를 차례대로 실행하면 됩니다.

> flutter channel dev

![그림16.get-started-flutter-channel-dev](/assets/img/flutter/20210225/16-get-started-flutter-channel-dev.png)

> flutter upgrade

![그림17.get-started-flutter-upgrade](/assets/img/flutter/20210225/17-get-started-flutter-upgrade.png)


### Flutter Emulator 실행

이제 Android Emulator에서 Flutter를 실행시키는 과정입니다.

콘솔창(cmd)에서 `flutter emulator` 명령어를 실행하면, 사용가능한 에뮬레이터 이름과 에뮬레이터 실행 방법이 보입니다.

![그림18.get-started-flutter-emulator](/assets/img/flutter/20210225/18-get-started-flutter-emulator.png)

`flutter emulators --launch Pixel_2_API_30`을 실행하면 안드로이드 에뮬레이터가 실행되는 것을 확인할 수 있습니다.

![그림19.get-started-flutter-emulator-excute](/assets/img/flutter/20210225/19-get-started-flutter-emulator-excute.png)

---

여기까지 진행되었다면 마지막으로 `flutter doctor`을 확인해봅니다.

아래의 그림과 같이 `No issues found!` 메세지가 보이신다면 Windows OS에서 Flutter를 시작하기 위한 설치과정이 모두 완료되었습니다.

![그림20.get-started-flutter-doctor-completed](/assets/img/flutter/20210225/20-get-started-flutter-doctor-completed.png)



### Reference

[윈도(Windows) 10 환경 변수 Path 설정 방법(+ 환경 변수 추가 방법)](https://wnw1005.tistory.com/263)

[Flutter 완벽 설치 - Windows편 영상](https://youtu.be/R_TVi_HLb78?t=273)

[플러터와 안드로이드 스튜디오 설치 총정리](https://blockdmask.tistory.com/420)

[Flutter 강좌 01 - 개발환경 만들기 및 앱 실행하는 방법](https://webnautes.tistory.com/1409)

[Update to Android Studio 4.1 ,flutter plugin and dart plugin not Installed](https://stackoverflow.com/questions/64395106/update-to-android-studio-4-1-flutter-plugin-and-dart-plugin-not-installed)
