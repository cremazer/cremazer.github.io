---
title: "Python - 프로그래밍 기초 학습 (3)"
date: 2024-04-01 21:07:00
image: '/assets/img/python/20240402/python-programming-beginner.png'
description: Learn the basics of Python programming.
category: 'python'
tags:
  - python
  - stock
  - data analysis
twitter_text: Learn the basics of Python programming.
introduction: 파이썬 프로그래밍의 기초 내용을 학습한다.
---

[퀀트 투자를 위한 자동매매 플랫폼 구축 준비 (1)](https://cremazer.github.io/python/Prepare-for-Python-stock-data-analysis/)에서 언급한 내용을 바탕으로 파이썬 프로그래밍의 기초 내용을 학습한다. 

# 개요

파이썬 프로그래밍 기초 학습을 하기 위해 ["파이썬 증권 데이터 분석" (한빛미디어, 2020)](https://link.coupang.com/a/bv6rZZ) 도서의 "CHAPTER 2. 파이썬 프로그래밍"을 학습한다. 

# 파이썬 특징

간결한 코드와 풍부한 표준 라이브러리, 직관적인 문법이 특징이다.

# 파이썬 설치

[파이썬 홈페이지](https://www.python.org/)에 접속하여 Downloads 메뉴에는 3.12.2의 버전으로 다운로드 할 수 있다. (24년 4월 기준)

![그림2.](/assets/img/python/20240402/python-downloads-version-202404.png)

## Mac OS에서 파이썬 설치

- [Mac 에서 파이썬 개발 환경설정](https://nadocoding.tistory.com/101) 블로그를 참고하여 설치를 진행한다.

## Windows OS에서 파이썬 설치

- [최신 파이썬 기초 - 1강 파이썬이란 무엇인가? (2023 점프 투 파이썬)](https://youtu.be/mEeZoDGITGw?list=PLU9-uwewPMe05-khW3YcDEaHMk_qA-7lI&t=1301) 영상을 참고하여 설치를 진행한다.

# 파이썬 개발 도구

파이썬을 학습하기 위한 개발 도구로는 다음과 같은 것들이 있다.

- [주피터 노트북(Jupyter Notebook)](https://jupyter.org/) : 웹 브라우저에서 파이썬 코드를 작성하고 실행할 수 있는 도구이다.

- [구글 코랩(Google Colab)](https://colab.research.google.com/) : 구글에서 제공하는 클라우드 기반의 주피터 노트북 환경이다.

- [비주얼 스튜디오 코드(Visual Studio Code)](https://code.visualstudio.com/) : 마이크로소프트에서 제공하는 오픈소스 코드 에디터이다. (설치형)

- [파이참(PyCharm)](https://www.jetbrains.com/ko-kr/pycharm/) : 파이썬 개발을 위한 JET BRAINS의 통합 개발 환경(IDE)이다. (설치형)

파이썬 개발을 돕기 위한 AI 기반의 개발 도구로는 다음과 같은 것들이 있다.

- [ChatGPT](https://chat.openai.com/) : OpenAI에서 제공하는 GPT-3 기반의 챗봇으로, 코딩에 대한 질문을 하면 답변을 제공한다.(무료 / 유료)

- [Copilot](https://copilot.github.com/) : GitHub와 OpenAI에서 제공하는 AI 기반의 코드 자동 완성 도구로, 코드를 작성하면 코드를 분석하여 코드를 자동 완성해준다. (유료)

- [코딩도우미(Code Helper)](https://codehelper.ai/) : AI 기반의 코딩 도우미로, 코드를 작성하면 코드를 분석하여 코드를 작성하는데 도움을 준다. (유료)

- [DeepCode](https://www.deepcode.ai/) : AI 기반의 코드 리뷰 도구로, 코드를 분석하여 코드의 품질을 향상시키는데 도움을 준다. (무료 / 유료)

- [Tabnine](https://www.tabnine.com/) : AI 기반의 코드 자동 완성 도구로, 코드를 작성하면 코드를 분석하여 코드를 자동 완성해준다. (무료 / 유료)

- [Kite](https://www.kite.com/) : AI 기반의 코드 자동 완성 도구로, 코드를 작성하면 코드를 분석하여 코드를 자동 완성해준다. (무료 / 유료)

그 외 더 많은 AI 도구들이 있는 것 같지만, 위에서 언급했던 도구들 중에서 본인의 취향에 맞는 도구를 선택하여 사용하면 된다.

> 필자의 경우 Jet Brains의 PyCharm가 개발 도구의 사용이 익숙하여 사용했으며, AI 도구로는 ChatGPT와 Copilot을 사용하여 학습을 진행했다. 직접 작성하며 학습하는 것도 중요하지만, AI 도구를 활용하여 학습을 진행하면 더욱 빠르고 다양한 예제를 학습할 수 있고 그만큼 시간을 많이 단축시켜주는 효과가 있었다.

파이썬을 설치하고, 개발 도구에서 main.py 파일을 생성하여 아래의 코드를 작성하고 실행하면 "Hello, World!"가 출력되면 기본적인 개발환경 준비는 완료했다고 생각한다.

```python
print("Hello, World!")
```

![그림3.](/assets/img/python/20240402/python-hello-world.png)

# 실습용 패키지 한 번에 설치하기

PyCharm을 설치하고 파이썬이 실행됬으나, 패키지를 설치하기 위한 준비가 되지 않아 설치 과정을 기록합니다.

## Mac OS iTerm2 설치

- [iTerm2](https://iterm2.com/)에서 다운로드 후 설치한다.

## Mac OS 패키지 관리자 Homebrew 설치

- [Homebrew](https://brew.sh/ko/)에서 설치 과정을 참고한다,

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
실행 후 Password를 입력하면 설치가 완료된다.

![그림4.](/assets/img/python/20240402/homebrew-install.png)

## Python 프로젝트 생성

- 코드를 관리하기 위해 Github에 repository를 생성한다.
- PyCharm을 실행하고, Github에서 생성한 repository를 clone한다.
- [에제 코드 Github](https://github.com/INVESTAR/StockAnalysisInPython/blob/master/02_Python_Programming/requirements.txt)에서 requirements.txt 파일을 프로젝트에 추가한다.
- PyCharm에서 requirements.txt 파일에서 "Install requirements"를 클릭하여 패키지를 설치한다.

![그림5.](/assets/img/python/20240402/pycharm-install-requirements.png)

- Invalid Python SDK 경고가 발생하면, [PyCharm guide](https://www.jetbrains.com/help/pycharm/package-installation-issues.html)를 따라서 Python SDK를 설정한다. (troubleshooting package installation)

![그림6.](/assets/img/python/20240402/pycharm-invalid-python-sdk.png)

- PyCharm Settings에서 Project Interpreter를 선택하고, Python SDK를 설정한다.
- Project Interpreter에서 Package에 pip만 보였는데, pip3 virtualenv를 설치하니 이슈가 해결되었다.

```bash
pip3 install virtualenv
```

- 그래도 PyCharm에서 requirements.txt 파일의 패키지를 설치하면, 패키지가 설치되지 않는 이슈가 발생했다.

![그림7.](/assets/img/python/20240402/pycharm-install-requirements-error.png)

원인은 RuntimeError: Python version 2.7 or 3.4+ is required.

note: This error originates from a subprocess, and is likely not a problem with pip.

그래서 absl-py 패키지를 개별로 설치하고, 설치할 때 버전을 명시하지 않고 설치하니 이슈가 해결되었다.

```bash 
pip3 install absl-py
```

![그림8.](/assets/img/python/20240402/pycharm-install-absl-py.png)

그렇다면 requirements.txt 파일을 한 번에 설치하려면 버전 정보를 모두 삭제하고 설치해볼까?

![그림9.](/assets/img/python/20240402/pycharm-install-requirements-all.png)

그림과 같이 requirements.txt 파일을 수정하고, PyCharm에서 terminal에서 requirements.txt 파일을 아래의 명령어로 설치한다.

```bash 
pip3 install -r requirements.txt
```

예상했던 대로 모든 패키지가 `.venv > lib > python3.12 > site-packages` 아래 설치되었음을 확인할 수 있었다.

![그림10.](/assets/img/python/20240402/pycharm-install-requirements-all-success.png)

실습용 패키지 한 번에 설치하기 완료.

버전을 명시하지 않았기 때문에, 모든 패키지가 최신 버전으로 설치되었다.

# 기초 문법 학습하기

- 도서의 내용을 따라 예제를 실습해보며 문법을 학습한다.

- 주로 학습할 내용:
  - 문자열 (출력, 인덱싱, 슬라이싱)
  - 산술 연산
  - 흐름 제어 (if문, for문, while문, try-except문)
  - 반복 자료형 (리스트, 튜플, 딕셔너리, 집합)
  - 변수와 함수
  - 모듈과 패키지
  - 객체지향 프로그래밍 (클래스, 상속, 클래스 변수와 인스턴스 변수, 클래스 메서드)
  - 파일 처리 및 외부 라이브러리 활용 방법

또는 [파이썬 기초 (2023 점프 투 파이썬)](https://youtube.com/playlist?list=PLU9-uwewPMe05-khW3YcDEaHMk_qA-7lI&si=RqodvP8e6alylI-E) Youtube 영상을 참고하여 기초 문법을 학습할 수 있다.



---

참고 도서

- ["파이썬 증권 데이터 분석" (한빛미디어, 2020)](https://link.coupang.com/a/bv6rZZ)

- [Do it! 점프 투 파이썬 (박응용, 이지스퍼블리싱, 2023)](https://link.coupang.com/a/bwArYP)

---

참고 사이트

- [파이썬 증권 데이터 분석 예제 소스 Github](https://github.com/Investar/StockAnalysisInPython)

- [파이썬 기초 (2023 점프 투 파이썬) Youtube by 조코딩](https://youtube.com/playlist?list=PLU9-uwewPMe05-khW3YcDEaHMk_qA-7lI&si=RqodvP8e6alylI-E)

- [파이썬을 위해 pycharm을 써야만 하는 이유 5가지](https://tariat.tistory.com/73)

- [오류 파이참 '가상환경을 생성하지 못했습니다.; 해결 방법](https://subtlething.tistory.com/35)

- [PyCharm Package installation issues](https://www.jetbrains.com/help/pycharm/package-installation-issues.html)

- [Python virtualenv 정리 (Linux/Windows)](https://dgkim5360.tistory.com/entry/python-virtualenv-on-linux-ubuntu-and-windows)


"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
