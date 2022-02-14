---
title:  "모각코 < Kotlin 기초편 > - 4일차"
excerpt: "모각코 <Kotlin 기초편>"

categories:
  - 모각코 Kotlin 기초편
tags:
  - [Blog, Github, Git, Kotlin, kotlin, 모각코, 모각코_코틀린기초편, 코뮤니티, androidstudio, 에뮬레이터, 에뮬레이터 설치, Kotlin]

toc: true
toc_sticky: true

date: 2022-02-14
last_modified_at: 2022-02-14
---

## 🌈 모각코 <코틀린 기초편> -- 4일차

*이 게시물의 맨 마지막 과제를 제외한 사진은 아래 링크의 사진을 첨부하였습니다.

https://codemate.kr/project/안드로이드-APP-메이트-코틀린-기초편



## ✅ 구조 파악하기

![d4-2.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640326944531/d4-2.png)

1.  **프로젝트 창 : 프로젝트에 포함된 폴더와 파일들을 볼 수 있는 창**
2. **에디터 창 : 파일을 수정할 수 있는 창 (레이아웃/코드)**
3. **도구 창**



## ✅ 프로젝트 창

: 여러 가지 방식으로 폴더와 파일을 볼 수 있음



![d4-3.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640326975839/d4-3.png)

가장 많이 쓰이는 것 : **Project** & **Android**



### ⚡ **프로젝트 모드** 

: 모든 폴더와 파일을 폴더 구조 그대로 볼 수 있는 모드



![d4-4.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640326994046/d4-4.png)



### ⚡ **안드로이드 모드**

: 안드로이드 **개발용으로 최적화**한 폴더/파일 구조



![d4-5.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327016562/d4-5.png)

개발할 때는 보통 안드로이드 모드를 사용!



👀 **AndroidManifest.xml**

: 앱의 전체 구성 정보를 담고 있는 파일 (**매니페스트** 라고 말하면 이 파일을 말함!)

* 액티비티의 개수, 앱의 첫 화면을 담당할 액티비티, 권한 허용 등의 코드가 들어있음.





👀 **MainActivity.kt, activity_main.xml**

: 화면을 구성하는 파일

- **.xml** 파일 : 레이아웃 담당
- **.kt** 파일 : 화면에 대한 코드(코틀린) 작성



📛보통 이름을 지을 때 파일 이름이 OOOActivity 라면?

=> activity_OOO 라고 레이아웃 파일명을 정함





👀 **build.gradle (프로젝트 수준, 모듈 수준)**

: 빌드를 위해 필요한 설정을 작성하는 곳



📛 **빌드란?** 프로젝트를 설치 할 수 있는 앱으로 만들기 위한 과정

📛 프로젝트 수준의 **build.gradle** 파일 VS 모듈 수준의 **build.gradle** 파일

: 외부의 라이브러리를 가져올 때 프로젝트 수준인지, 모듈 수준인지 확인 필수!

##  

## ✅ **레이아웃 에디터 창**

: 레이아웃 에디터 창은 Code, Split, Design 총 3가지 모드!



### ⚡ **코드 모드 : 코드로 레이아웃을 수정 및 확인**



![d4-6.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327078796/d4-6.png)



### ⚡ **스플릿 모드 : 코드와 디자인 모드 반반**



![d4-7.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327091773/d4-7.png)



### ⚡ **디자인 모드 : 그래픽 UI로 xml 파일을 수정**



![d4-8.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327123678/d4-8.png)



👀 팔레트(Palette), 컴포넌트 트리(Component Tree), 속성( Attributes )창,

그리고 화면이 표시되는 창으로 구분됨.





👀 **팔레트(Palette)**

: 디자인에 추가할 수 있는 컴포넌트들을 모아놓은 부분

(드래그 앱 드롭을 통해 원하는 컴포넌트 추가)



![d4-9.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327147768/d4-9.png)



👀 **컴포넌트 트리 (Component Tree)**

: 현재 화면 내에 들어있는 컴포넌트들을 트리 구조로 보여줌.



![d4-10.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327167680/d4-10.png)



## ✅ 오늘의 문제 : 실행 인증하기!

![4.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644504559339/4.png)



[codemate_@guswlsdl04](https://codemate.kr/@guswlsdl04/%EB%AA%A8%EA%B0%81%EC%BD%94-%EC%BD%94%ED%8B%80%EB%A6%B0-%EA%B8%B0%EC%B4%88%ED%8E%B8-2%EC%9D%BC%EC%B0%A8) ◀ CLICK HERE!
