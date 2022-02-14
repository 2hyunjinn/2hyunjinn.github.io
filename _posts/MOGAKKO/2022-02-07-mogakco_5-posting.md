---
title:  "모각코 < Kotlin 기초편 > - 5일차"
excerpt: "모각코 <Kotlin 기초편>"

categories:
  - 모각코 Kotlin 기초편
tags:
  - [Blog, Github, Git, Kotlin, kotlin, 모각코, 모각코_코틀린기초편, 코뮤니티, androidstudio_layout, Kotlin]

toc: true
toc_sticky: true

date: 2022-02-14
last_modified_at: 2022-02-14
---

## 🌈 모각코 <코틀린 기초편> -- 5일차

## ✅ Layout이란?

: 여러 컴포넌트(View)를 묶어주는 **뷰 그룹**

- Layout의 종류에 따라 컴포넌트들을 다르게 정렬할 수 있음





## ✅ Layout의 종류



### ⚡ **Linear Layout**

: 컴포넌트들을 차례대로 나열



👀 Linear Layout 의 orientation 속성

- vertical - 세로로 나열
- horizontal - 가로로 나열



![d5-1.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327555239/d5-1.png)![d5-2.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327583809/d5-2.png)



복잡한 레이아웃보다는 

**단순한 리스트** (상하 스크롤, 좌우 스크롤) 뷰일 때 **Linear Layout 을 사용!**





### ⚡ **Frame Layout**

: 액자 안에 그림을 끼우는 방식으로 컴포넌트 배치

- Frame Layout에 배치한 것 중에 가장 마지막 컴포넌트가 보임.
- 배치보다는 다른 용도(Web view 용 레이아웃 등)를 위한 레이아웃을 추가할 때 주로 사용





### ⚡ **Constraint Layout**

: 컴포넌트의 상하좌우에 필요한 제약을 추가하여 원하는 위치에 배치



👀 **Relative Layout** vs **Constraint Layout**



📛 구글에서는 Constraint Layout 을 권장

**why?**

1. Relative Layout 에 비해 Constraint Layout 이 더 최근에 만들어짐
2. Relative Layout + Linear Layout 의 장점 => Constraint Layout
3. Layout 여러 개가 중첩되었을 때 반응, 처리속도가 상대적으로 빠름



## ✅ Constraint Layout 사용방법



ex) 버튼을 아래의 화면처럼 우측 하단에 배치한 코드

![d5-3.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327639370/d5-3.png)



![d5-4.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327666576/d5-4.png)



**👀 13 ~ 14번 줄 집중!!**





#### **⚡ layout_constraintBottom_toBottomOf="parent"**

👀 컴포넌트의 bottom(하단)을 parent(부모 요소)의 bottom(하단)에 맞춘다 .



#### **⚡ layout_constraintEnd_toEndOf="parent"**

👀 컴포넌트의 end(오른쪽)을 parent(부모 요소)의 end(오른쪽)에 맞춘다.



Button의 부모 요소 = Constraint Layout

-> 화면의 가장 오른쪽과 하단에 배치됨



이런 식으로 배치하면 **레이아웃 에디터 툴의 디자인 모드에서**

**Constraint가 생긴 것**을 확인할 수 있음!



![d5-5.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327691331/d5-5.png)



#### **⚡ 만약 우측과 하단에 여백을 주고 싶다면?**

: 여백을 원하는 숫자로 바꾸면 됨.



![d5-6.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327710230/d5-6.png)



**👀 코드**



![d5-7.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327724353/d5-7.png)



#### **⚡** parent가 아닌 다른 요소와의 관계를 제약으로 만드는 방법은?



![d5-8.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640327742477/d5-8.png)



**👀 14번 줄 집중!**

" **layout_constraintBottom_toTopOf="@+id/button4 "**

=> 이것은 **컴포넌트의 하단(bottom)**을 

​      **button4**라는 아이디를 가진 **컴포넌트 위(top)로 배치**한다는 의미



**👀 19번 줄 집중!**

**android:id="@+id/button4" :** 바로 해당 컴포넌트의 id를 부여하는 코드



📛 프로젝트 안에 **고유한 id를 부여**하고 이를 통해 제약을 주는 것!

**< 프로젝트 안에서 id 이름은 겹치면 안됨 >**



**✔ 상 = top**

**✔ 하 = bottom**

**✔ 좌 = start (=left ; sdk 버전이 낮을 경우 left 사용)**

**✔ 우 = end (=right ; sdk 버전이 낮을 수록 right 사용)**



⚡ **layout_constraintTop_toBottomOf="A"**

👀 컴포넌트의 상단을 A 컴포넌트의 하단에 맞춘다.



⚡ **layout_constraintStart_toEndOf="A"**

👀 컴포넌트의 좌측을 A 컴포넌트의 우측에 맞춘다.

##  

## **✅ 오늘의 문제 : 버튼 만들기**



![5-1.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644570038999/5-1.png)![5-2.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644570058441/5-2.png)



[codemate_@guswlsdl04](https://codemate.kr/@guswlsdl04/%EB%AA%A8%EA%B0%81%EC%BD%94-%EC%BD%94%ED%8B%80%EB%A6%B0-%EA%B8%B0%EC%B4%88%ED%8E%B8-2%EC%9D%BC%EC%B0%A8) ◀ CLICK HERE!
