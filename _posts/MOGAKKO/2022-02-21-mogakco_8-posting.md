---
title:  "모각코 < Kotlin 기초편 > - 8일차"
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

## 🌈 모각코 < Kotlin 기초편 > - 8일차

## ✅ 코틀린 간단하게 문법 배우기

### **⚡ 코틀린에서 함수 사용하기**

**함수란?**

- 특정 입력 값에 대한 결과 값을 반환
- 코틀린에서의 함수는 아래의 형태로 사용



```kotlin
fun 함수이름(입력값) {
  함수 내용
	return 반환값
}
```

return 이 반환한다는 뜻!







### **⚡ 코틀린에서 조건문 사용하기**

**조건문이란?**

- 특정 조건일 때 코드가 실행되도록 설정하는 것



if(조건문){



} 



조건문이 참이라면 해당 {} 안의 명령을 실행!



```kotlin
if ( n <= 10 ) { 
	A 
} else if ( n <= 20  ) {
  B
} else {
  C
}
```

##### **👀 코드 해석**

- n이 10보다 작거나 같을 때 A 코드 실행 (n이 10 이하일 때)
- 그게 아니라 n이 20보다 작거나 같을 때 B 실행 (n이 10 초과 20 이하일 때)
- 그게 아니라면 C 실행 (n이 20 초과)

##  



### **⚡ 코틀린에서 배열 사용하기**

```kotlin
// 정수 데이터를 저장할 빈 배열 만들기
val numbers = arrayListOf<Int>() 

// array에 숫자(num) 추가
numbers.add(num)

// array의 모든 숫자 삭제
numbers.clear()

// array 안에 숫자(num)가 있는지 없는지 체크하기
numbers.contains(num) // 있으면 True, 없으면 False 
```







### **⚡ 코틀린에서 반복문 사용하기**

```kotlin
// 조건이 참일 경우 A 부분 실행
while ( 조건 ) { 
  A 
}

// 무한 반복이되, if 안의 조건이 참일 경우 반복문을 빠져나온다.
while (true) {
	if ( 조건 ) {
	  break
	}
}
```





## ✅ 함수를 이용하여 랜덤 숫자 뽑기

##### **👀 코드**

```kotlin
class MainActivity : AppCompatActivity() {
    val random = Random() // 랜덤값을 사용할 수 있도록 선언

	override fun onCreate(savedInstanceState: Bundle?) {
	    super.onCreate(savedInstanceState)
	    setContentView(R.layout.activity_main)
	
        // 6개의 번호 변수 선언
	    val num1 = findViewById<Button>(R.id.lottoNum1)
	    val num2 = findViewById<Button>(R.id.lottoNum2)
	    val num3 = findViewById<Button>(R.id.lottoNum3)
	    val num4 = findViewById<Button>(R.id.lottoNum4)
	    val num5 = findViewById<Button>(R.id.lottoNum5)
	    val num6 = findViewById<Button>(R.id.lottoNum6)

	    findViewById<FloatingActionButton>(R.id.runButton).setOnClickListener {
	        setLottoNum(num1)
	        setLottoNum(num2)
	        setLottoNum(num3)
	        setLottoNum(num4)
	        setLottoNum(num5)
	        setLottoNum(num6)
	    }
	}
	
	fun setLottoNum(lottoNum: Button) {
	    lottoNum.text = "${random.nextInt(45) + 1}"
	    lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(86, 88, 88))
	}
}
```



##### 👀 **결과 보기**



![Animation6.gif](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640676370475/Animation6.gif)



##### **⚡ 코드 해석**



1️⃣ **private val random = Random()**

- 랜덤값을 사용할 수 있도록 미리 변수 선언
- random.nextInt(숫자) 로 랜덤 값 받기
- **ex) random.nextInt(5) -> 0~4 사이의 무작위 정수 반환**



로또 번호는 1부터 45까지의 랜덤한 정수이므로

**random.nextInt(45)** 코드로 0~44 사이의 정수를 받은 후 

+1 해주어 1~45 사이의 랜덤한 숫자를 얻을 수 있음!





2️⃣ **setLottoNum()**

- setLottoNum 이라는 이름의 함수 호출
- 이때 반드시 Button 컴포넌트를 괄호 안에 담아야 함
- num1 ~ num6 의 버튼 컴포넌트를 순차적으로 담아 함수 호출





3️⃣ **fun setLottoNum(lottoNum: Button) { }**

- setLottoNum 이라는 이름의 함수 생성
- 입력 값 : Button 컴포넌트 - 입력받은 컴포넌트에 lottoNum이라는 이름 설정





4️⃣ **lottoNum.text="${random.nextInt(45) + 1}"**

- lottoNum의 텍스트 값을 ${random.nextInt(45) + 1}로 설정
- But, 텍스트 속성에는 숫자를 넣을 수 없음!
- **따라서, ${ ... } 를 통해 문자처럼 만들어 텍스트 값을 설정**





5️⃣ **lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(88,88,88))**

- 입력받은 컴포넌트 lottoNum의 배경색을 rgb(88,88,88)로 바꿉니다.





## ✅ 문제점 발생!



**⚡ 배경색이 바뀌지 않음**

로또는 숫자의 범위에 따라 색깔이 바뀌어야 하는데 바뀌질 않음



👀 로또 번호 색깔

1~10은 노란색, 

11~20은 파란색, 

21~30은 빨간색,

31~40은 회색, 

41~45는 초록색



**=> 조건문을 이용하여 해결**



**⚡ 숫자가 겹칠 수 있음**

로또 번호는 모두 다른 숫자이기 때문에 숫자가 겹치면 안됨



**=> 배열과 반복문을 통해 해결**



![Untitled.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640676472505/Untitled.png)

##  

## ✅ 오늘의 문제 : 로또번호추첨앱 기능 완성하기



우측 하단의 버튼을 누를 때마다 랜덤한(겹치지 않는) 숫자 6개가 표시되고,

해당 숫자에 맞는 배경색으로 바뀌도록 변경하기

![Animation8.gif](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640676551484/Animation8.gif)







##### **👀 MainActivity.kt**

```kotlin
package com.example.lotto

import android.content.res.ColorStateList
import android.graphics.Color
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.widget.Button
import com.google.android.material.floatingactionbutton.FloatingActionButton
import kotlin.random.Random

class MainActivity : AppCompatActivity() {
    private val random = Random(45) // 랜덤값을 사용할 수 있도록 선언
    private val numbers = arrayListOf<Int>() // 번호를 저장할 배열 생성
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val num1 = findViewById<Button>(R.id.lottoNum1)
        val num2 = findViewById<Button>(R.id.lottoNum2)
        val num3 = findViewById<Button>(R.id.lottoNum3)
        val num4 = findViewById<Button>(R.id.lottoNum4)
        val num5 = findViewById<Button>(R.id.lottoNum5)
        val num6 = findViewById<Button>(R.id.lottoNum6)

        findViewById<FloatingActionButton>(R.id.floatingActionButton).setOnClickListener {
            numbers.clear() // 모든 숫자 삭제하고 시작

            setLottoNum(num1)
            setLottoNum(num2)
            setLottoNum(num3)
            setLottoNum(num4)
            setLottoNum(num5)
            setLottoNum(num6)
        }
    }
    private fun setLottoNum(lottoNum: Button) {
        var num = 0
        while (true) {
            num = random.nextInt(45) + 1 // 0~44이기 때문에 1~45로 변경
            if ( !numbers.contains(num) ) {  // 만약 이전에 나온 번호와 겹치지 않는다면
                numbers.add(num) // 번호 추가
                break
            }
        }

        lottoNum.text = "${num}" // 숫자를 문자로 바꿔주기

        if ( num <= 10 ) { // 10보다 작거나 같으면
            lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(255,194,0))
        } else if (num <= 20) { // 10보다는 크고 20보다 작거나 같으면
            lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(0,0,255))
        } else if (num <= 30) { // 20보다는 크고 30보다 작거나 같으면
            lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(245,33,34))
        } else if (num <= 40 ) { // 30보다는 크고 40보다 작거나 같으면
            lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(128,128,128))
        } else { // 40보다도 크다면
            lottoNum.backgroundTintList = ColorStateList.valueOf(Color.rgb(129,193,71))
        }
    }
}
```



##### **👀 실행결과**



![8result.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644940903845/8result.png)



<https://codemate.kr/@guswlsdl04/모각코-코틀린-기초편-8일차> ◀ CLICK HERE!
