---
layout: post
title: "Package & Import"
description: Package & Import란?
headline:
modified: 2019-08-16
category: Java
tags: [Java]
imagefeature:
mathjax:
chart:
comments: true
featured: true
---
## Package란?

자바에서는 클래스를 만들때 비슷한 클래스끼리 모아서 저장한다.
그래야 관리하기가 더욱 수월하기 때문이다.
논리적으로 비슷하거나 서로 의존을 하는 클래스끼리 묶어두는게 보통이다.
패키지를 만들면 default package말고 밑에 새로운 패키지가 형성된다.
디폴트 패키지라는것은 우리가 패키지를 만들지 않았을때 자동으로 인식하는 패키지이다.

### 과일장수가 상인에게 사과를 사고 팔아서 현재 잔액과 사과개수를 알 수 있는 프로그램을 만들어보자

###### 1. 먼저 오렌지를 사는 buyer를 나타내기 위해 **orange.buyer**이라는 package를 만들자
<img src="{{ site.url }}/images/java1.png"> 
import을 사용하려면 class FruitBuyer 앞에 public을 **꼭** 붙여야한다!
**그럼 import란 무엇일까?**
아래 글에서 알아보자

###### 2. 오렌지를 파는 seller를 나타내기 위해 **orange.seller**이라는 package를 만들자
<img src="{{ site.url }}/images/java2.png"> 
buyApple 매소드를 호출하는데는 제약이 없다 -> **public**때문

## Import란?
소스코드를 작성할 때 다른 패키지의 클래스를 사용할 때는 패키지명이 포함된 이름을 사용해야한다. 하지만, 매번 패키지명을 붙여서 작성하기란 여간 불편한 일이 아닐 것이다. 
    클래스의 코드를 작성하기 전에 import문으로 사용하고자 하는 클래스의 패키지를 미리 명시해주면 소스코드에 사용되는 클래스이름에서 패키지명은 생략할 수 있다. 
    import문을 선언하는 방법은 다음과 같다. 
>import 패키지명.클래스명; (해당 클래스만 명시적 사용)
또는 
import 패키지명.*; (모든 클래스를 명시적으로 사용)


키워드import와 패키지명을 생략하고자 하는 클래스의 이름을 패키지명과 함께 써주면 된다. 같은 패키지에서 여러 개의 클래스가 사용될 때, 
**import문을 여러 번 사용하는 대신 '패키지명.*'을 이용해서 지정된 패키지에 속하는 모든 클래스를 패키지명 없이 사용할 수 있다.**

###### 3. 두명의 판매자(seller1,2)을 설정하고 각 판매자의 돈,사과개수,사과한개당 가격을 설정한다.
<img src="{{ site.url }}/images/java3.png"> 
메인 클래스 & 결과


######출처 : [package와 import1](https://kamang-it.tistory.com/entry/Java-13package%EC%99%80-import)
######출처 : [package와 import2](http://egloos.zum.com/rustymind/v/2679757)
