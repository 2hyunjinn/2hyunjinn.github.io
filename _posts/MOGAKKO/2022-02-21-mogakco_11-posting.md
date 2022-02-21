---
title:  "모각코 < Kotlin 기초편 > - 11일차"
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

## 🌈 모각코 < Kotlin 기초편 > - 11일차

## **✅ 오늘 배울 내용**

1. **EditText 에 입력된 텍스트 가져오기**
2. **비밀번호 체크하는 조건문 만들기**



## **✅ EditText에 입력된 텍스트 가져오기**

##### **📛 주의 📛**

Edit Text 컴포넌트의 text를 불러올 때는 뒤에 꼭 **.toString()**을 붙여야 함!



```kotlin
// EditText 컴포넌트를 찾아서 editText 변수에 저장한다.
val editText = findViewById<EditText>(R.id.아이디)

// editText 에서 사용자가 입력한 텍스트를 불러와 passwordText 에 저장한다.
val passwordText = editText.text.toString()
```

**EditText는?** 

일반 TextView ❌ 사용자가 입력할 수 있는 컴포넌트 ⭕

text 속성이 일반 textView와 달리 EditText 만의 형태로 설정됨.



따라서 그 안에 입력된 텍스트를 가져오려면 **toString()** 을 붙여야 함!!





## **✅ 비밀번호 체크하는 조건문 만들기**



조건문을 이용해 우리가 원하는 텍스트(비밀번호)가 맞는지 체크하기!



**📛** **== 연산자**?

왼쪽과 오른쪽이 같은지 비교하는 연산자

**=> if (조건문) 에서 조건문의 결과가 참인지 거짓인지 판단하여 조건문 실행**



```kotlin
if ( passwordText == "12345678" ) 
    // 참이라면(입력한 passwordText 와 "12345678"이 같다면) 이곳의 명령 실행
} else {
   // 거짓이라면(다르다면) 이곳의 명령 실행
}
```

##  

## **✅ 오늘의 문제 : 비밀번호 체크하기**



⚡ 사용자가 입력한 비밀번호를 passwordText 변수에 저장

⚡ **passwordText** 를 체크하여 원하는 비밀번호가 맞을 경우

Logcat에 "**통과"**를 출력하고, 아닐 경우 "**틀렸어요.**"를 출력



## **✅ [선택] 오늘의 심화 문제 : 아이디(이메일), 비밀번호 체크하기**



⚡ 이메일 입력 창 추가

⚡ 이메일이 틀렸을 경우 **"이메일이 틀렸어요"** 출력

- 이메일이 맞지만 비밀번호가 틀렸을 때는 **"비밀번호가 틀렸어요."** 출력
- 이메일과 비밀번호가 맞을 경우 **"통과"** 출력



##### **👀 xml**



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
        android:layout_marginTop="40dp"
        android:text="아이디와 비밀번호를 입력해주세요."
        app:layout_constraintHorizontal_bias="0.024"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="5dp"
        android:layout_marginTop="88dp"
        android:text="이메일"
        app:layout_constraintHorizontal_bias="0.013"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="5dp"
        android:layout_marginTop="180dp"
        android:text="비밀번호"
        app:layout_constraintHorizontal_bias="0.013"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <EditText
        android:id="@+id/editTextEmail"
        android:layout_width="0dp"
        android:layout_height="44dp"
        android:layout_marginStart="10dp"
        android:layout_marginTop="48dp"
        android:layout_marginEnd="10dp"
        android:ems="10"
        android:inputType="textEmailAddress"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/textView" />

    <EditText
        android:id="@+id/editTextNumberPassword2"
        android:layout_width="0dp"
        android:layout_height="44dp"
        android:layout_marginStart="10dp"
        android:layout_marginTop="140dp"
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
        android:layout_marginTop="21dp"
        android:layout_marginEnd="10dp"
        android:text="확인"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editTextNumberPassword2" />

</androidx.constraintlayout.widget.ConstraintLayout>
```





##### **👀 kt**

```kotlin
package com.comu.android.secretmemo

import android.os.Bundle
import android.util.Log
import android.widget.Button
import android.widget.EditText
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        findViewById<Button>(R.id.button).setOnClickListener{
            // EditText 컴포넌트를 찾아서 editText 변수에 저장한다.
            val editEmail = findViewById<EditText>(R.id.editTextEmail)
            val emailText = editEmail.text.toString()

            // editText 에서 사용자가 입력한 텍스트를 불러와 passwordText 에 저장한다.
            val editText=findViewById<EditText>(R.id.editTextNumberPassword2)
            val pwText=editText.text.toString()

            if(emailText == "guswlsdl04@naver.com"){
                if(pwText == "123456"){
                    Log.d("SecretMemo", "통과")
                }
                else{
                    Log.d("SecretMemo","비밀번호 오류")
                }
            }
            else Log.d("SecretMemo", "이메일 오류")
        }
    }
}
```



##### **👀 실행결과 1**

![11result1.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1645430515199/11result1.png)





##### **👀 실행결과 2**

![11result2.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1645430533529/11result2.png)



<https://codemate.kr/@guswlsdl04/모각코-코틀린-기초편-11일차> ◀ CLICK HERE!
