---
title: "React + TypeScript + Vite 환경 세팅 및 GitHub 연동 (1)"
date: 2025-09-20 15:30:00
image: '/assets/img/react/20250920/vite-react-github.png'
description: In this post, we set up a React + TypeScript project using Vite, troubleshoot issues with Yarn and GitHub authentication, and successfully connect the project to a GitHub repository.
categories: [react]
tags:
  - react
  - typescript
  - vite
  - github
  - setup
twitter_text: Setting up a React + TypeScript project with Vite, resolving Yarn and GitHub issues, and connecting to a repository.
introduction: React + TypeScript 프로젝트를 Vite 기반으로 세팅하고, Yarn 설치 문제와 GitHub 인증 충돌을 해결하면서 최종적으로 GitHub 저장소에 성공적으로 연동한 과정을 정리합니다. 
redirect_from:
  - /posts/2025-09-20-react-vite-typescript-github-setup.md
  - /posts/2025-09-20-react-vite-typescript-github-setup/
---

# React + TypeScript + Vite 환경 세팅 및 GitHub 연동

프론트엔드 학습을 위해 **React + TypeScript + Vite** 환경을 구성하고,  
이 프로젝트를 GitHub에 연동하기까지의 과정을 기록합니다.

## 1. Node.js와 nvm 설치

```bash
brew install nvm

# 환경 변수 (~/.zshrc)
export NVM_DIR="$HOME/.nvm"
source "$(brew --prefix nvm)/nvm.sh"

nvm install --lts
nvm use --lts

node -v
npm -v
```

v22.19.0으로 설치 성공

## 2. Yarn 설치

처음에는 corepack enable을 시도했으나, macOS 권한 문제(EACCES)로 실패.
→ Homebrew 설치 방식으로 해결.

```bash
brew install yarn
yarn -v
```

## 3. React 프로젝트 생성 (Vite + TS)

```bash
yarn create vite hello-react --template react-ts
```
yarn create → 스캐폴딩 실행

vite → 생성기

hello-react → 프로젝트 이름

--template react-ts → React + TypeScript 템플릿

## 4. 프로젝트 실행

```bash
cd hello-react
yarn install
yarn dev
```

http://localhost:5173 에서 React + Vite 초기 화면 확인 성공

## 5. GitHub 연동

저장소 생성:
https://github.com/cremazer/hello-react-2025.git

```bash
git init
git remote add origin https://github.com/cremazer/hello-react-2025.git
git add .
git commit -m "Initialize React + TypeScript project with Vite"
git branch -M main
```

### 문제 발생

git push -u origin main 실행 시:

Updates were rejected because the remote contains work that you do not have locally.

* 원인: GitHub에서 저장소 생성 시 기본 README.md가 포함됨 → 충돌 발생.

### 해결 방법

시도 방법 1 (권장)

```bash
git pull origin main --rebase
git push -u origin main
```

선택한 방법 (빠른 해결)

```bash
git push -u origin main --force
```

최종적으로 로컬 프로젝트가 원격 저장소에 정상 업로드됨.

### GitHub 인증 문제 해결

처음 push 시 macOS 키체인 암호 팝업이 반복 발생.
→ GitHub CLI를 통해 인증 처리.

```bash
brew install gh
gh auth login
```

* HTTPS 선택

* 브라우저 로그인

* Keychain에 토큰 저장

확인:

```bash
gh auth status
```

* 이후 push 시 인증 문제 해결됨.

## 6. 정리 및 배운 점

1. Node.js + nvm으로 안정적인 버전 관리

2. Yarn 설치는 Corepack → 권한 에러 → Homebrew 방식으로 해결

3. CRA는 deprecated → Vite + TypeScript로 프로젝트 세팅

4. yarn start 대신 yarn dev 사용

5. GitHub repo 생성 시 README 옵션 충돌 → --force push로 해결

6. GitHub CLI를 활용해 인증 문제 해결


> Lucky’s Tip

* 에디터: VS Code 대신 Cursor AI를 사용 → AI 리팩토링, 커밋 메시지 제안, 테스트 코드 자동 생성으로 학습 효율 증가.

* 실습 경험: 단순히 코드만 실행하지 않고, 에러를 직접 겪으며 최신 프론트엔드 트렌드를 체감할 수 있었음.

* GitHub 관리 팁: Repo 생성 시 “Add README” 옵션을 끄면 충돌 방지 가능. 그래도 충돌 시 git pull --rebase 또는 --force push로 해결 가능.

---

이번 과정을 통해 단순히 React 환경 세팅을 넘어,
환경 구축 → 에러 발생 → 해결 과정을 모두 경험할 수 있었습니다.

앞으로는 도서 *"리액트를 다루는 기술"*의 예제를 TypeScript 버전으로 변환하며 학습을 이어가며 겪는 시행착오 과정을 공유할 예정입니다.


---

참고 도서

- ["리액트를 다루는 기술 (개정판)" (길벗, 2019)](https://link.coupang.com/a/cR1vTu)

---

참고 사이트

- [벨로퍼트와 함께하는 모던 자바스크립트](https://learnjs.vlpt.us/)
- [JavaScript 첫걸음](https://developer.mozilla.org/ko/docs/conflicting/Learn_web_development/Core/Scripting)
- [길벗 - 리액트를 다루는 기술 예제코드](https://github.com/gilbutITbook/080203)
- [TypeScript 공식 문서](https://www.typescriptlang.org/ko/docs/handbook/typescript-from-scratch.html)

"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
