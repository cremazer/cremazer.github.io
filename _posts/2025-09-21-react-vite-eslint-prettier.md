---
title: "React + TypeScript + Vite 환경 세팅 및 GitHub 연동 (2)"
date: 2025-09-21 22:00:00
image: '/assets/img/react/20250920/vite-react-github.png'
description: In this post, we resolve App.tsx JSX errors in Cursor AI, configure ESLint and Prettier, and commit the changes to GitHub.
categories: [react]
tags:
  - react
  - typescript
  - vite
  - github
  - eslint
  - prettier
twitter_text: Fixing JSX errors in Cursor AI, setting up ESLint and Prettier, and pushing updates to GitHub in a Vite + React + TypeScript project.
introduction: 지난 포스팅에 이어 App.tsx 오류 해결 과정과 ESLint + Prettier 설정, GitHub 반영까지의 과정을 정리합니다.
redirect_from:
  - /posts/2025-09-21-react-vite-eslint-prettier.md
  - /posts/2025-09-21-react-vite-eslint-prettier/
---

# React + TypeScript + Vite 환경 세팅 및 GitHub 연동 (2)

지난 포스팅에서는 **React + TypeScript + Vite 프로젝트 생성과 GitHub 연동**까지 마무리했습니다.  
이번 포스팅에서는 이후 학습 과정에서 발생한 **App.tsx 오류 해결**, **ESLint & Prettier 설정**, **GitHub 반영** 과정을 공유합니다.


## 1. App.tsx 오류 발생과 원인 파악

프로젝트 실행(`yarn dev`)은 정상 동작했지만, 에디터(Cursor AI)에서는 `App.tsx`의 JSX 태그(`div`, `a`, `img`, `button`) 전체에 오류 표시가 나타났습니다.

- 브라우저: 정상 화면 출력
- IDE: JSX 관련 오류 메시지

### 원인 분석
1. `@types/react` 타입 선언 누락 가능성
2. `tsconfig.app.json` 설정 문제
3. Cursor AI(TypeScript 서버)의 캐싱 문제


## 2. 해결 과정

### (1) 타입 선언 패키지 설치

```bash
yarn add -D @types/react @types/react-dom
```

### (2) tsconfig.app.json 수정

기존 설정:
```json
"moduleResolution": "bundler"
```

수정 후:
```json
"moduleResolution": "node"
```

* bundler는 최신 ESM 방식 지원을 위해 도입되었지만, IDE 호환성 이슈가 있어 JSX 해석 시 에러를 유발할 수 있습니다.
* node로 바꾸면 IDE에서 JSX 타입 인식이 안정적으로 작동합니다.

### (3) Cursor AI 재시작 & TS Server 리스타트

* 설정 변경 후에도 캐시된 타입 정보 때문에 오류 표시가 남아 있었음

* IDE 재시작 후 왼쪽 하단 팝업에서 TS 서버 재시작 → 오류 표시가 사라짐

## 3. ESLint & Prettier 설정

코드 품질과 스타일을 자동으로 관리하기 위해 ESLint와 Prettier를 함께 사용했습니다.

설치
```bash
yarn add -D eslint prettier eslint-config-prettier eslint-plugin-prettier
```

실행
```bash
yarn lint    # 코드 검사
yarn format  # 코드 스타일 자동 정리
```

* ESLint → 코드 품질 검사 (미사용 변수, JSX 규칙 위반 등 탐지)

* Prettier → 코드 스타일 포맷팅 (들여쓰기, 세미콜론, 따옴표 등 자동 정리)

## 4. GitHub 반영

변경사항 확인
```bash
git status
```

커밋 & 푸시
```bash
git add .
git commit -m "커밋 메세지"
git push origin main
```

* 최종적으로 GitHub에 모든 설정 변경이 반영되었습니다.

## 5. 정리 및 배운 점

* App.tsx 오류는 코드 자체 문제가 아닌 IDE와 TypeScript 설정 충돌 때문이었음

* moduleResolution 옵션을 node로 바꾸어 IDE 호환성을 확보

* ESLint + Prettier 조합으로 코드 품질 관리와 포맷팅 자동화

* Cursor AI의 TS Server Restart 기능이 설정 반영에 중요

* GitHub 커밋 메시지는 설정 변경 시 보통 chore: prefix를 사용


> Lucky’s Tip

* IDE 오류 vs 런타임 에러 구분: 브라우저와 빌드는 정상인데 IDE에서만 에러가 보이면 대부분 TypeScript 설정 문제입니다.

* Prettier & ESLint 함께 사용: Prettier는 스타일, ESLint는 품질 검사 → 충돌 방지를 위해 eslint-config-prettier 사용을 권장합니다.

* 작업 기록 습관화: 설정 변경 후 GitHub에 바로 커밋/푸시 → 다른 환경에서도 동일한 세팅으로 작업 가능.

---

이번 과정을 통해 JSX 기초 문법에 대해 학습하고, ESLint와 Prettier 설정 방법을 익혔습니다.

Cursor AI의 TypeScript 지원 기능도 경험하며, 앞으로의 React + TypeScript 학습에 자신감을 얻었습니다.

다음은 React 컴포넌트에 대한 내용을 학습할 예정입니다.


---

참고 도서

- ["리액트를 다루는 기술 (개정판)" (길벗, 2019)](https://link.coupang.com/a/cR1vTu)

---

참고 사이트

- [Writing Markup with JSX](https://react.dev/learn/writing-markup-with-jsx)
- [Introducing JSX](https://legacy.reactjs.org/docs/introducing-jsx.html)
- [TypeScript 공식 문서: JSX](https://www.typescriptlang.org/docs/handbook/jsx.html)
- [React Reference Overview](https://react.dev/reference/react)

"이 포스팅은 쿠팡 파트너스 활동의 일환으로, 이에 따른 일정액의 수수료를 제공받습니다."
