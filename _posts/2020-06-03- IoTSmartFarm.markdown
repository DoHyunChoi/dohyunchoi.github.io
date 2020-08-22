---
layout: post
title: "IoT 작물 모니터링","[인턴십 프로젝트]"     
description: 
headline:
modified: 2020-06-03
category: JAVA
tags: [Project]
imagefeature:
mathjax:
chart: true
comments: true
featured: true
---

## 1. 서비스 개요(Smart Farm)   
- 사물인터넷(IoT) 기술.<br>
- IT와 BT를 결합하여 농산물 대량 생산<br>
- 이산화탄소, 온도, 습도를 실시간 모니터링
- 사용장비 : Ardunio mega 2560보드wifi shield, 아두이노 온습도센서, CO2센서, 서브모터, 안드로이드 휴대폰기기
<br>

###### 유사 서비스(K사의 ICT 스마트팜)    
<img src="{{ site.url }}/images/KT_smartfarm.jpg">  
<br>
- ICT 기반 식물공장 통합 운영 플랫폼 및 모니터링 시스템 개발   
- 식물공장 시스템 녹색기술 인증 및 녹색기술 제품 인증<br>

## 2. 개발방법  

<img src="{{ site.url }}/images/SmartFarm_method.jpg">  
<br>

- 1. 온습도 센서를 아두이노와 연결하여 서버로 전송     
- 2. Mqtt 서버를 통해 받은 센서 값을 DB에 저장    
- 3. Mqtt dashboard를 이용하여 시간별 센서 값을 그래프로 변환   
- 4. 안드로이드 어플리케이션을 통해 유저인터페이스 제공, 모니터링   
<br>

## 3. 새로 알게된점(ThingSpeak)
<img src="{{ site.url }}/images/IoT_Thingspeak.jpg">  
<br>

- 온습도 센서를 아두이노와 연결하여 서버로 전송     
- Thingspeak 클라우드 서버를 통해 받은 센서 값을 DB에 저장    
- <span style="color:blue"> **Thingspeak 자체 DB플랫폼 이용하여 시간별 센서 값을 그래프로 변환 **</span>  
- 안드로이드 어플리케이션을 통해 유저인터페이스 제공, 모니터링   
<br>

#### 3-1. ThingSpeak란

- IoT 관점에서 클라우드 컴퓨팅 기술 동향 중 IoT 생태계 형성을 위한 서비스/개발 클라우드 플랫폼   
- 클라우드 서비스란 별도의 사비를 사용하면서 개인 서버를 사용하지 않고 IoT 구현 가능   
<br>
  
## 4. 실행 결과
#### 안드로이드 어플리케이션(회원가입, 모니터링)
<img src="{{ site.url }}/images/SmartFarm_android.jpg">  
<br>
<img src="{{ site.url }}/images/SmartFarm_android2.jpg">  
<br>

#### 4-1 MQTTT 서버 사용(Mqtt.fx, 센서 데이터&그래프)
<img src="{{ site.url }}/images/SmartFarm_mqtt1.jpg">  
<br>
<img src="{{ site.url }}/images/SmartFarm_mqtt2.jpg">  
<br>

###### Mqtt 핵심코드

```
//Setting Network
char ssid[] = "CNM_D";      // network SSID (name)
char pass[] = "cnm1205!";   // network password

if ( mqttClient->connect(CLIENT_ID) )
                {
                   
                    Serial.println("\nConnected to MQTT broker!!!");

                   
                    // Publish
                    if (mqttClient->publish("CNM/ROTICS/TEST/Ajou", "Hi~~~")) {
                        Serial.println("Publish ok");


                        mqttClient->publish("Humidity_DOHYUN(%)",ChrBufferRfsrH);
                        mqttClient->publish("Temperature_DOHYUN(C)",ChrBufferRfsrT);
                        mqttClient->publish("Co2_DOHYUN(ppm)",ChrBufferRfsrC);

                  	else {
                        Serial.println("Publish failed");
                    }
                   
                    if (mqttClient->subscribe("CNM/ROTICS/TEST/Ajou")) {
                        Serial.println("Subscribe ok");

                        mqttClient->subscribe("Humidity_DOHYUN(%)",ChrBufferRfsrH);
                        mqttClient->subscribe("Temperature_DOHYUN(C)",ChrBufferRfsrT);
                        mqttClient->subscribe("Co2_DOHYUN(ppm)",ChrBufferRfsrC);
           
                        Serial.println("Humidity done ");
                        Serial.println("Temperature done");
                        Serial.println("CO2 done ");
                    }
                    else {
                        Serial.println("Subscribe failed");
                    }


```
#### 4-2 ThingSpeak Cloud 사용(ThingView, 센서 데이터&그래프)
<img src="{{ site.url }}/images/SmartFarm_ts4.jpg">  
<img src="{{ site.url }}/images/SmartFarm_ts2.jpg">  
<img src="{{ site.url }}/images/SmartFarm_ts3.jpg">  
<br>

###### ThingSpeak 핵심코드

```
//Setting Network
char ssid[] = "CNM_D";      // network SSID (name)
char pass[] = "cnm1205!";   // network password

// ThingSpeak Settings
char thingSpeakAddress[] = "api.thingspeak.com";
String writeAPIKey = "Q25GXGJRBQPTH9GU";	//my channel ID APIkey

//Update data to ThingSpeak
void updateThingSpeak(float co2, float temp, float humid) {

 if (client.connect(thingSpeakAddress, 80) > 0){       

      String tsData = "1="+String(co2,DEC)+"&2="+String(temp, DEC)+"&3=" +String(humid,DEC);
    }
}

```
<br>
## 5. 보완   
- CO2 센서가 부정확하여 결과값의 차이가 매우 컸다.  
- 무료 MQTT 서버와 Broker를 통한 지속적인 아두이노 데이터 교환이 어려웠다. 사용자가 많아 서버가 원활하지 못했기 때문이다.   
<br>
## 6. 결론   
- MQTT뿐만 아니라 Node.js, Node-RED, Apache등 기초적인 서버 구축.
- MQTT,  Mosquitto등 IoT에 자주 쓰이는 프로토콜과 브로커에 대한 학습
- JAVA를 기반으로한 ThingSpeak 언어에 대한 학습
- 기초적인 아두이노  회로뿐만 아니라 와이파이 쉴드를 이용한 고급예제까지 다루어 아두이노에 대한 전문 지식 함양
- https://github.com/DoHyunChoi/CNM_ROBOTICS_Android https://github.com/DoHyunChoi/CNM_ROBOTICS 에 업로드

<br>

## 7. 동계인턴십발표 포스터   
<img src="{{ site.url }}/images/internship_poster.jpg">  
<br>
