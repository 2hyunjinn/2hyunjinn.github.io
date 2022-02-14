---
title:  "모각코 < Kotlin 기초편 > - 6일차"
excerpt: "모각코 <Kotlin 기초편>"

categories:
  - 모각코 Kotlin 기초편
tags:
  - [Blog, Github, Git, Kotlin, kotlin, 모각코, 모각코_코틀린기초편, 코뮤니티, androidstudio_linear_layout, Kotlin]

toc: true
toc_sticky: true

date: 2022-02-14
last_modified_at: 2022-02-14
---

## 🌈 모각코 < Kotlin 기초편 > - 6일차

## **✅ Layout 중첩하기 (Linear Layout)**

###  

## ⚡ 레이아웃 추가하기



#### **👀 Palette 창**

1. Layouts 클릭
2. LinearLayout(vertical) 드래그 -> 화면에 끌어다 놓음





#### **👀 Linear Layout의 constraint 추가**

1. 상, 하, 좌, 우 여백 0으로 바꾸기 (=> 이 부분에서 잘 안돼서 xml코드를 통해 직접 수정함 ㅠㅠ)





#### **👀 Linear Layout 안에 버튼 추가**

1. Palette > Common 클릭
2. Common > Button 클릭
3. Button을 드래그하여 Component Tree > Linear Layout에 추가



#### **👀 버튼의 속성 수정**

1. id를 buttonNum1로 수정
2. 수정 후 다른 곳을 클릭하면 아래와 같은 창이 뜸 (이때 Refactor 버튼 클릭)
3. layout_width : 70dp
4. layout_height : 80dp
5. text 문구 삭제 (밑으로 내리면 있음)



**📛 dp를 안붙여서 계속 오류떴으니 주의! 꼭 dp 붙이기**



**⚡ 여기서 dp란?**

**안드로이드 위젯의 크기를 지정할 때 사용되는 단위**로,

위젯의 크기는 "wrap_content", "match_parent", dp단위를 사용하는 것이 좋다!

(텍스트의 크기는 sp단위 사용이 권고됨)



**⚡ 단위의 종류**

in : 인치 기반의 물리적 스크린 크기

mm : 밀리미터 기반의 물리적 스크린 크기

px : 스크린상의 실제 픽셀에 대응하는 단위 (화면 밀도가 큰 스크린에서는 작게 보여지게 됨)



**📛 dp : 밀도 독립적 픽셀 (160dpi 화면의 물리적 픽셀 하나)**

- 사용 중인 화면의 실제 밀도에 따라 시스템이 dp의 단위의 모든 확대/축소를 처리함
- px = dp * (dpi / 160)
- **다른 밀도의 화면에서도 UI가 적절히 표시되도록 하기 위해 dp 단위 사용**



sp : 배율 독립적 픽셀  (텍스트의 경우)

- dp와 동일하게 크기 확대/축소 



#### **👀 버튼의 radius 속성 추가**

1. 속성 창의 돋보기 버튼 클릭
2. radius 검색
3. cornerRadius 값을 80dp로 설정



#### **👀 Linear layout 안에 있는 컴포넌트들이 중앙에 배치되도록 설정**

1. Linear Layout 클릭
2. 돋보기 버튼 클릭
3. gravity 검색
4. gravity > center 속성 클릭
5. true로 바꿔주기



#### **👀 원의 색깔 설정**

1. 돋보기 버튼 클릭
2. backgroundTint 검색
3. 원하는 색깔로 바꾸기 (전 99C8C2C2로 바꿨습니다!)







## **✅ 오늘의 문제 : 앱 레이아웃 만들기**



**👀 실행 결과 화면!**



![6result.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644832779849/6result.png)



![6code1.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644833057114/6code1.png)



![6code2.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644833061982/6code2.png)



![6code3.png](https://s3.ap-northeast-2.amazonaws.com/images.codemate.kr/images/guswlsdl04/post/1644833066722/6code3.png)



[codemate_@guswlsdl04](https://codemate.kr/@guswlsdl04/%EB%AA%A8%EA%B0%81%EC%BD%94-%EC%BD%94%ED%8B%80%EB%A6%B0-%EA%B8%B0%EC%B4%88%ED%8E%B8-2%EC%9D%BC%EC%B0%A8) ◀ CLICK HERE!
