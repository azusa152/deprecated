---
layout: post
title: WSN-for-IoT-Platform Arduino_Sensor_Node
subtitle   : "Arduino_Sensor_Node"
date       : 2017-08-21 00:00:00
author     : "azusa"
comments   : true
signature  : true
tags       : IoT,Arduino
---

在這一篇文章當中，我將介紹如何安裝我所開發系統中XBEE的設定
程式碼於我的[Github倉庫](https://github.com/azusa152/WSN-for-IoT-Platform)中，歡迎大家使用。

組裝 Sensor node
-------------
本系統之感測節點是由Arduino打造，其接線圖如下:

<img height="100%" width="100%" class="profile" src="/public/sensornode.png" >

首先我們先將Arduino掛載XBee擴充版，並依據需要的功能外掛其他物品。如現在要做一個溫度與濕度的感測節點，則在上述的板子上外加溫溼度感測器以及蜂鳴器，並燒入溫度與濕度感測節點的程式 [WSN-for-IoT-Platform/Arduino/SensorNode/SensorNode/SensorNode.ino](https://github.com/azusa152/WSN-for-IoT-Platform/blob/master/Arduino/SensorNode/SensorNode/SensorNode.ino)。

Arduino Software IDE
-------------
Arduino Software IDE，是一套Arduino所提供的以Java編寫的跨平台應用軟體 ，具有括號匹配、語法突顯、自動縮排、將執行檔燒寫入Arduino硬體等的功能，並使用類似C及C++的程式語言做為開發用的語言。使用Arduino Software IDE編寫的程式被稱為「sketch」，在一般的sketch中含有的主要兩個的函式分別為:

> setup(): 用於初始設定，只會在程式開始執行時執行一次。
>loop(): 在Arduino電源關閉前會一直重複執行。

我們要將程式燒入時，首先要將Arduino用USB連接至電腦，並開啟Arduino Software IDE，並設定所使用的Arduino版本以及連接的序列埠後燒入程式碼即可。當Arduino燒入程式後，每次插上電源便會自動執行程式的動作，不需要透過Arduino Software IDE操作

<img height="100%" width="100%" class="profile" src="/public/sensornode.png" >



SensorNode.ino
-------------
這邊將介紹程式碼中的幾個可調整的參數

> ARDUINO CONFIG 
> const int kNodeType[]={1001,1002}; 數字為Arduino所接的感測器種類

>SLEEP CONFIG
>const int kWorkTime=5; 調整節點醒來時工作幾秒
>int sleep_time=1;  sleep_time*8秒為節點睡眠的時間
>const int kSmartSleepShort=1; //1 minute
>const int kSmartSleepMiddle=75; // 10minutes
>const int kSmartSleepLong=450; //1hour

>EMERGENCY CONFIG
>const int kEmergencyTime=3; //8*kEmergencyTime為緊急模式最少維持時間
