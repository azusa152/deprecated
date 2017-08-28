---
layout: post
title: WSN-for-IoT-Platform :Edison_Sensor_Gateway
subtitle   : "Edison_Sensor_Gateway"
date       : 2017-08-20 00:00:00
author     : "azusa"
comments   : true
signature  : true
---

WSN-for-IoT-Platform Edison_Sensor_Gateway
===================
在這一篇文章當中，我將介紹如何安裝我所開發的使用Intel EDISON的Sensor Gateway
程式碼於Github中:https://github.com/azusa152/WSN-for-IoT-Platform



組裝 Sensor_Gateway
-------------
首先我們將SD卡大小Intel Edison主體裝設至Edison Arduino kit上面，使他可以掛載通用Arduino的擴充版。之後我們將XBee晶片安裝在XBee Arduino 擴充版，最後再把此擴充版安裝到Edison Arduino kit上便完成我們的Sensor Gateway的組裝
![edison](https://drive.google.com/open?id=0BzxRHXHJhYfDbnB6cUpYbFotYkU)

PuTTY連線
-------------
我們將使用PuTTY與Intel Edison 進行溝通。首先我們將Intel Edison使用USB連線至電腦，並確認他連結到哪一個序列埠(Serial Port)，之後設定鮑率(Baud rate)後便可透過PuTTY連線至Intel Edison。這邊要注意的是Baud rate必須跟Intel Edison的鮑率必須是相同的才行。
![putty](https://drive.google.com/open?id=0BzxRHXHJhYfDT0d0MFZxNi1icDg)


