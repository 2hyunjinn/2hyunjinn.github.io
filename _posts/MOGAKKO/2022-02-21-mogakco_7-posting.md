---
title:  "모각코 < Kotlin 기초편 > - 7일차"
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

## 🌈 모각코 < Kotlin 기초편 > - 7일차

## ✅ 버튼이 눌렸는지 감지하기 - 로그로 확인하기



1️⃣ 버튼의 id 설정 ***\*id는 프로젝트 안에서 고유(unique)해야 함!\***



버튼의 id가 **runButton** 이라고 가정

```kotlin
class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        
				findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
            Log.d("로또앱", "버튼 누름")
        }
    }
}
```



위의 코드를 실행하기 위해 총 4가지 import가 필요함!

```kotlin
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.util.Log
import com.google.android.material.floatingactionbutton.FloatingActionButton
```



안드로이드 스튜디오에서는 자동으로 import 해주지만,

**자동으로 인식이 되지 않는다면?**

1. 직접 import 코드 작성
2. alt + enter 를 눌러 import하기





**👀 코드 해석**

```kotlin
findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
    Log.d("로또앱", "버튼 누름")
}
```



##### 1️⃣ **findViewById<FloatingActionButton>(R.id.runButton)**

: 프로젝트 안에 있는 컴포넌트 중에서 id가 **runButton**인 **FloatingActionButton** 을 찾는다.



##### 2️⃣ **~~~.setOnClickListener { ..... }**

**: '.'** 앞에 있는 컴포넌트가 클릭 되었을 때 중괄호({}) 안의 코드를 실행한다.



##### 3️⃣ **Log.d("로또앱", "버튼 누름")**

**:** **로또앱**이라는 태그로 **버튼 누름**을 Logcat에 출력한다.



따라서 빌드 후 runButton 클릭하면

-> Logcat에 "버튼 누름" 이라는 로그가 출력됨



Logcat의 검색창에 로또앱 이라는 텍스트를 검색하면 로또앱이 태그인 로그만 확인 가능

![d8-2.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640654055108/d8-2.png)





## ✅ 버튼이 눌렸는지 감지하기 - 텍스트 바꾸기



##### **👀 간단하게 버튼을 눌렀을 때 텍스트를 변경**

```kotlin
findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
    findViewById<Button>(R.id.lottoNum1).text = "45"
}
```



**Log.d("로또앱", "버튼 누름")**이라는 코드 대신

**findViewById<Button>(R.id.lottoNum1).text = "45"** 코드 추가



- id가 lottoNum1인 Button 컴포넌트의 text 속성을 "45"로 지정하라는 뜻
- 이때 text는 숫자가 아닌 문자 or 문장이어야 함 (문장은 "" 로 표현)





## ✅ 버튼이 눌렸는지 감지하기 - 배경색 바꾸기

 

##### **👀 배경색을 바꾸는 코드 추가**

```kotlin
findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
    findViewById<Button>(R.id.lottoNum1).text = "45"
    findViewById<Button>(R.id.lottoNum1).backgroundTintList = ColorStateList.valueOf(Color.rgb(255,0,0))
}
```

**setOnClickListener** 중괄호 안에 원하는 코드 추가





##### **👀 배경색을 바꾸는 코드**

```kotlin
findViewById<Button>(R.id.lottoNum1).backgroundTintList = ColorStateList.valueOf(Color.rgb(255,0,0))
```



**backgroundTintList 속성을 ColorStateList.valueOf(Color.rgb(r값, g값, b값)) 으로 설정**

-> 원하는 r, g, b 컬러로 배경색 변경 가능





## ✅ 컴포넌트를 변수로 지정하기



**변수란?**

- 데이터를 저장해놓는 공간
- 숫자, 문자, 컴포넌트 등을 저장, 사용 가능
- 중간에 다른 데이터로 덮어씌워 저장 가능



코틀린에서는 보통 컴포넌트를 변수로 지정해두고 사용함.

```kotlin
val num1 = findViewById<Button>(R.id.lottoNum1)
findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
    num1.text = "45"
    num1.backgroundTintList = ColorStateList.valueOf(Color.rgb(255,0,0))
}
```



```kotlin
findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
    findViewById<Button>(R.id.lottoNum1).text = "45"
    findViewById<Button>(R.id.lottoNum1).backgroundTintList = ColorStateList.valueOf(Color.rgb(255,0,0))
}
```



위와 아래의 실행 결과는 같음!

**다른 점은?** 

위의 코드에서는 **findViewById<Button>(R.id.lottoNum1)**로 찾은 컴포넌트를

**num1**이라는 변수에 저장해두고 반복되는 코드를 줄였음

**=> 이렇게 변수로 저장해두고 사용하는 것을 권장**





#### ✅ **심화내용**

코틀린에서 val은 변하지 않는 변수! (상수와는 또 다른 개념)

따라서, 아무렇게나 변할 수 있는 변수는 var로 선언!!

# ﻿

## ✅ 오늘의 문제 : 6개 버튼 텍스트, 색깔 변경하기



##### **👀 activity_main.xml**



```kotlin
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/floatingActionButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="41dp"
        android:clickable="true"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:srcCompat="@android:drawable/ic_menu_rotate" />

    <LinearLayout
        android:layout_width="408dp"
        android:layout_height="730dp"
        android:gravity="center"
        android:orientation="vertical"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent">

        <Button
            android:id="@+id/lottoNum1"
            android:layout_width="70dp"
            android:layout_height="80dp"
            android:backgroundTint="#E0E0E0"
            app:cornerRadius="80dp" />

        <Button
            android:id="@+id/lottoNum2"
            android:layout_width="70dp"
            android:layout_height="80dp"
            android:backgroundTint="#E0E0E0"
            app:cornerRadius="80dp" />

        <Button
            android:id="@+id/lottoNum3"
            android:layout_width="70dp"
            android:layout_height="80dp"
            android:backgroundTint="#E0E0E0"
            app:cornerRadius="80dp" />

        <Button
            android:id="@+id/lottoNum4"
            android:layout_width="70dp"
            android:layout_height="80dp"
            android:backgroundTint="#E0E0E0"
            app:cornerRadius="80dp" />

        <Button
            android:id="@+id/lottoNum5"
            android:layout_width="70dp"
            android:layout_height="80dp"
            android:backgroundTint="#E0E0E0"
            app:cornerRadius="80dp" />

        <Button
            android:id="@+id/lottoNum6"
            android:layout_width="70dp"
            android:layout_height="80dp"
            android:backgroundTint="#E0E0E0"
            app:cornerRadius="80dp" />
    </LinearLayout>

</androidx.constraintlayout.widget.ConstraintLayout>
```





##### **👀 MainActivity.kt**



```kotlin
package com.example.lotto

import android.content.res.ColorStateList
import android.graphics.Color
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import com.google.android.material.floatingactionbutton.FloatingActionButton

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val num1 = findViewById<Button>(R.id.lottoNum1)
        val num2 = findViewById<Button>(R.id.lottoNum2)
        val num3 = findViewById<Button>(R.id.lottoNum3)
        val num4 = findViewById<Button>(R.id.lottoNum4)
        val num5 = findViewById<Button>(R.id.lottoNum5)
        val num6 = findViewById<Button>(R.id.lottoNum6)

        findViewById<FloatingActionButton>(R.id.floatingActionButton).setOnClickListener{
            num1.text="43"
            num1.backgroundTintList=ColorStateList.valueOf(Color.rgb(255,0,0))

            num2.text="44"
            num2.backgroundTintList=ColorStateList.valueOf(Color.rgb(255,128,0))

            num3.text="25"
            num3.backgroundTintList=ColorStateList.valueOf(Color.rgb(255,255,0))

            num4.text="11"
            num4.backgroundTintList=ColorStateList.valueOf(Color.rgb(0,255,0))

            num5.text="8"
            num5.backgroundTintList=ColorStateList.valueOf(Color.rgb(0,0,255))

            num6.text="17"
            num6.backgroundTintList=ColorStateList.valueOf(Color.rgb(127,0,255))

        }
    }
}
```



##### **👀 실행결과**



![7result.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644939126293/7result.png)



<https://codemate.kr/@guswlsdl04/모각코-코틀린-기초편-7일차> CLICK HERE!



