---
layout: page
permalink: /about/index.html
title: Who am I?
tags: [DoHyun, Canada, English]
imagefeature: 04.jpg
chart: true
---

<figure>
	<img src="{{ site.url }}/images/08.png" alt="To Introduce me..">
	<figcaption>To Introduce me..</figcaption>
</figure>

{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}

<!--
This is my personal blog. It currently has {{ site.posts | size }} posts in {{ site.categories | size }} categories which combinedly have {{ total_words }} words, which will take an average reader ({{ site.wpm }} WPM) approximately <span class="time">{{ total_readtime }}</span> minutes to read. {% if featuredcount != 0 %}There are <a href="{{ site.url }}/featured">{{ featuredcount }} featured posts</a>, you should definitely check those out.{% endif %} The most recent post is {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Read more about {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %} which was published on {% for post in site.posts limit:1 %}{% assign modifiedtime = post.modified | date: "%Y%m%d" %}{% assign posttime = post.date | date: "%Y%m%d" %}<time datetime="{{ post.date | date_to_xmlschema }}" class="post-time">{{ post.date | date: "%d %b %Y" }}</time>{% if post.modified %}{% if modifiedtime != posttime %} and last modified on <time datetime="{{ post.modified | date: "%Y-%m-%d" }}" itemprop="dateModified">{{ post.modified | date: "%d %b %Y" }}</time>{% endif %}{% endif %}{% endfor %}. The last commit was on {{ site.time | date: "%A, %d %b %Y" }} at {{ site.time | date: "%I:%M %p" }} [UTC](http://en.wikipedia.org/wiki/Coordinated_Universal_Time "Temps Universel Coordonné").
-->

<h1 align="center">
<a href="https://docs.google.com/document/d/1yD5WR35FCXlvAgM1NlSH4OImQr-NazU-QyheRkeTYgU/edit?usp=sharing"> DoHyun_Resume </a>  
</h1>

<figure>
  <img src="{{ site.url }}/images/dohyun.jpg" alt="DoHyun Choi">
  <figcaption>DoHyun Choi</figcaption>
</figure>

<!--## [INTRODUCTION]() 링크 만드는법 -->
### INTRODUCTION

저의 목표는 모든 개인에게 맞춘 세상을 만드는 것입니다. 예를 들어 사람마다 소설이나 시 등의 글이나 여러 음악에는 어느 정도 양의 한계가 존재합니다. 자신이 좋아하는 작가의 글을 다 읽고 다음 글이 나올 때까지 몇 년 이상이 걸리는 경우도 있습니다. 우리는 같은 것을 계속해서 보는 것이 아닌 새로운 것을 보길 원합니다. 음악도 같습니다. 이는 작업 시간의 한계로 어쩔 수 없습니다. 이를 해결하기 위해 기존에 있는 글이나 음악을 DNN으로 사용자의 취향에 맞는 새로운 글이나 음악을 자체 생성을 해주며 더욱 개인화된 경험을 제공해주는 등 획일화된 서비스가 아닌 각각의 개인에게 맞춘 서비스를 제공하고 싶습니다.

## EXPERIENCE

### 집에 혼자 있는 아이들의 TV 시청을 통제할 수 있는 시스템 구현  - *Team project*
<sub>2018.08.07 - 11.20, [Github](https://github.com/dohyunchoi/), [Report](https://drive.google.com/file/d/13G662Hwn3H2UbMD0tupZN2hIXEp2DHCx/view?ths=true)</sub>
· 집에 혼자 있는 아이들의 TV 시청을 통제할 수 있는 시스템
· 미연령대 TV 프로그램 시청 방지,  시청시 카메라 모듈 사용, TV on/off, 모바일로                    
  셋탑박스 제어를 연구
· 송도 모 셋탑박스 업체와 협력하여 카메라 모듈 연동, TV프로그램 정보 조회 합동
  구현
- Server, Android Application 개발 총괄

### 집에 혼자 있는 아이들의 TV 시청을 통제할 수 있는 시스템 구현  - *Team project*
<sub>2016.09.04 - 12.20, [Github](https://github.com/dohyunchoi/), [Report](https://docs.google.com/document/d/1R6VHGJOkyxnUBbDqYo-D69sheJ-ucjB4tPCfiQwUpfs/edit)</sub>
· 학생들에게 실시간으로 사용가능한 강의실을 보여주고 예약할 수 있는 시스템
· Use Case Diagram, Non-functional Requirements, Domain Model 등 
  S/W 설계에 필요한 분석적이고 체계적인 설계방식 구현

### SKills
Server, Android Application

### Language
Android, Java, C

### Framework - 타 github 인용
Pandas, NumPy, scikit-learn, KoNLPy, Spark, [PyTorch](https://github.com/newhiwoong/PyTorch), [TensorFlow](https://github.com/newhiwoong/TensorFlow), [Keras](https://github.com/newhiwoong/Keras-Applications)

### AI / ML
오일석의 '[패턴인식](http://www.yes24.com/24/goods/3315437?scode=032&OzSrank=1)', 마이클 네그네빗스키의 ‘[인공지능 개론](http://www.yes24.com/24/Goods/9386454?Acode=101)’ 독학으로 전통적인 ML 분야 학습, Vision + NLP + Sequence Models - [Coursera 강의](https://www.coursera.org/learn/nlp-sequence-models) 수료 및 각종 프로젝트 진행, [강화학습](https://event-us.kr/modu/event/2016) + [Deep Generative](https://event-us.kr/modu/event/4648) 스터디를 통하여 학습 및 실습


<h2>Connect</h2>
✉️ [dohyen94@gmail.com]()  
🌐 [https://github.com/DoHyunChoi](https://github.com/DoHyunChoi)
