---
layout: post
title: WSN-for-IoT-Platform Edison_Sensor_Gateway
subtitle   : "Edison_Sensor_Gateway"
date       : 2017-08-20 00:00:00
author     : "azusa"
tags       : IntelEdison IoT
comments   : true
signature  : true
---

在這一篇文章當中，我將介紹如何安裝我所開發的使用Intel EDISON的Sensor Gateway
程式碼於Github中:https://github.com/azusa152/WSN-for-IoT-Platform



組裝 Sensor_Gateway
-------------
首先我們將SD卡大小Intel Edison主體裝設至Edison Arduino kit上面，使他可以掛載通用Arduino的擴充版。之後我們將XBee晶片安裝在XBee Arduino 擴充版，最後再把此擴充版安裝到Edison Arduino kit上便完成我們的Sensor Gateway的組裝

![edison](https://lh3.googleusercontent.com/-nl8f37SQYk4/WaPkFgaavRI/AAAAAAAAA5Y/5XV-i2VB4Wks-d-BFsu4GzKPAVqRWmZCgCLcBGAs/s0/edison+assemble.jpg "edison assemble.jpg")

PuTTY連線
-------------
我們將使用PuTTY與Intel Edison 進行溝通。首先我們將Intel Edison使用USB連線至電腦，並確認他連結到哪一個序列埠(Serial Port)，之後設定鮑率(Baud rate)後便可透過PuTTY連線至Intel Edison。這邊要注意的是Baud rate必須跟Intel Edison的鮑率必須是相同的才行。

![putty](https://lh3.googleusercontent.com/-mP-3XVfJMd4/WaPj79xbVqI/AAAAAAAAA5Q/TeMgwXyVZO8VnnFJS4_48bb-LMLTpiX2gCLcBGAs/s0/putty.png "putty.png")

連線至Intel Edison後，我們可以輸入Intel Edison的帳號以及密碼登入至Intel Edison的系統並進行各項設定，如調整Wi-Fi設定 
> Configure_edison --wifi

![edison login](https://lh3.googleusercontent.com/-hGCtrkhfEw8/WaPkbeQ4A6I/AAAAAAAAA5g/Zvh0MF5AvZsfREMkBA2Oxq1GzIfJ4hyGwCE0YBhgL/s0/edison+login.png "edison login.png")


Intel XDK 
-------------
Intel XDK 是 Edison 的主要開發環境，首先我們於Intel官網下載[Intel® XDK IoT Edition](https://software.intel.com/en-us/intel-xdk)以及[Bonjour Print Services](https://support.apple.com/kb/dl999?locale=zh_TW)。於Intel XDK中首先我們要尋找我們的Intel Edison的板子，發現到之後輸入Intel Edison的帳號及密碼，便可與Intel Edison建立起連線。之後我們便可上傳我們的程式專案至Intel Edison，並執行工作。

![xdk](https://lh3.googleusercontent.com/-LDsW3DOZVhs/WaPlm3lLyfI/AAAAAAAAA58/G0QyK3HUTlkqAbNculZxwN-prmsEIvvMQCE0YBhgL/s0/xdk.png "xdk.png")


