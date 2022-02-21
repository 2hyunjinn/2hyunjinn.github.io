---
title:  "모각코 < Kotlin 기초편 > - 9일차"
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

## 🌈 모각코 < Kotlin 기초편 > - 9일차

## ✅ 아이콘 만들기



**👇링크 클릭**

[Launcher Icon Generator](https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html#foreground.type=clipart&foreground.clipart=android&foreground.space.trim=1&foreground.space.pad=0.25&foreColor=rgba(96%2C 125%2C 139%2C 0)&backColor=rgb(68%2C 138%2C 255)&crop=0&backgroundShape=square&effects=none&name=ic_launcher)



![ICONMAKE.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1645027041243/ICONMAKE.png)



1. 이미지, 아이콘, 텍스트 지정
2. 색상을 조정하여 원하는 아이콘 생성
3. 우측 상단의 '다운로드 버튼' 클릭!



## ✅ 앱에서 아이콘 변경하기



**⚡** **ic_launcher** 라는 문구가 들어간 파일은 모두 아이콘과 관련된 파일!



![and9-3.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677012021/and9-3.png)





#### 1️⃣ **New > Image Asset 클릭**



![and9-4.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677031315/and9-4.png)





#### 2️⃣ **Configure Image Asset > Name**

Name 값 변경 ❌



![and9-5.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677051386/and9-5.png)



👀 **Foreground Layer** : 아이콘 이미지 설정

👀 **Background Layer :** 아이콘 이미지의 배경색 설정





#### 3️⃣ **Foreground Layer > 폴더버튼 클릭**

아까 다운 받았던 파일 이름.png 선택!



![and9-7.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677083939/and9-7.png)





#### 4️⃣ **Background Layer > Color 설정**

아이콘 배경색과 동일하게 변경



![and9-8.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677105247/and9-8.png)





#### 5️⃣ **Foreground Layer > Scaling 조정**

원하는 크기로 변경



![and9-9.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677125915/and9-9.png)

👀 Finish 버튼 클릭!







## ✅ 앱 이름 변경하기



##### ⚡ app > manifests > AndroidManifest.xml

![and9-12.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/COMU/post/1640677185017/and9-12.png)



```kotlin
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.lotto">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Lotto">
        <activity
            android:name=".MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```



##### ⚡ a**ndroid:label="@string/app_name"**

**app_name**이라는 이름으로 선언된 string 값 = '앱의 이름'



##### ⚡ app_name 설정

**res > values > strings.xml** 

: 원하는 이름으로 변경



![string.xml.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1645027637461/string.xml.png)

저는 간단하게 'Lotto'로 설정했습니다!

##  

## **✅ 오늘의 문제 : 앱 아이콘, 앱 이름 변경하기**



**👀 실행 결과**



![9result.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1645026796443/9result.png)



<https://codemate.kr/@guswlsdl04/모각코-코틀린-기초편-9일차> ◀ CLICK HERE!
