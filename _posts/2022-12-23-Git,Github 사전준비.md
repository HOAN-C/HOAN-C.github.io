---
layout: single
title: "💾 Git, Github 사전준비"
categories:
  - github
---

## 사전준비

### 1. Github 가입하기

[https://github.com](https://github.com/)

Github에서 계정을 하나 생성하자.

이메일, 비밀번호, 이름만 뚝딱뚝딱하면 된다.

---

### 2. Git 다운로드 받기

[https://git-scm.com/downloads](https://git-scm.com/downloads)

Git을 자신의 운영체제에 맞춰 다운로드 받으면 끝난다.

next 클릭클릭클릭클릭

---

## 초기설정

설치가 완료됐으면 Git bash 프로그램을 실행시켜보자.

시커먼 터미널 창이 나온다.

겁먹지 말고 아래 코드들을 따라 지면 된다.

### 사용자 이름 설정

```
git config --global user.name "사용자 이름"
```

### 사용자 이메일 설정

```
git config --global user.email "사용자 이메일"
```

### 설정 확인

```
git config --list
```

![Untitled](/assets/img/2022-12-23-1-1.png)

위처럼 출력이 되는데, [user.name](http://user.name) 과 [user.email](http://user.email) 에 자기가 기입한 정보가 잘 들어갔는지 확인하면 된다.

터미널에서 작업을 하고 있는 경우

```jsx
:q
```

명령어를 입력하면 나올 수 있다.

이제 직접 사용해보자.
