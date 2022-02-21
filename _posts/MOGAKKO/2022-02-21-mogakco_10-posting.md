---
title:  "모각코 < Kotlin 기초편 > - 10일차"
excerpt: "모각코 <Kotlin 기초편>"

categories:
  - 모각코 Kotlin 기초편
tags:
  - [Blog, Github, Git, Kotlin, kotlin, 모각코, 모각코_코틀린기초편, 코뮤니티, androidstudio_linear_layout, Kotlin]

toc: true
toc_sticky: true

date: 2022-02-21
last_modified_at: 2022-02-21
---

## 🌈 모각코 < Kotlin 기초편 > - 10일차



## **✅ 오늘의 문제 : 비밀번호 입력 화면 레이아웃 구성하기**



⚡ **Text > TextView 컴포넌트**로 "비밀번호를 입력해주세요" 문구 추가

⚡ **Text > Password(Numeric) 컴포넌트** 추가

⚡ **버튼** 추가



너무 꽉 채우는 것보다 여백이 있는게 더 예쁜 것 같아서 양쪽 여백을 5~ 10씩 주었습니다!



##### **👀 xml 코드**

```kotlin
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="5dp"
        android:layout_marginTop="42dp"
        android:text="비밀번호를 입력해주세요."
        app:layout_constraintHorizontal_bias="0.061"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/editTextNumberPassword"
        android:layout_width="0dp"
        android:layout_height="44dp"
        android:layout_marginStart="10dp"
        android:layout_marginTop="23dp"
        android:layout_marginEnd="10dp"
        android:ems="10"
        android:inputType="numberPassword"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />

    <Button
        android:id="@+id/button"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:text="확인"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editTextNumberPassword" />

</androidx.constraintlayout.widget.ConstraintLayout>
```





##### **👀 실행결과**

![10result.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1645191621718/10result.png)



<https://codemate.kr/@guswlsdl04/모각코-코틀린-기초편-10일차> ◀ CLICK HERE!
