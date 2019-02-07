---
layout: post
title: WSN-for-IoT-Platform Edison_Sensor_Gateway
subtitle   : "Edison_Sensor_Gateway"
date       : 2017-08-20 00:00:00
author     : "azusa"
tags       : IntelEdison IoT
comments   : true
signature  : true
tags       : IoT,Intel Edison
---


組裝 Sensor_Gateway
-------------
首先我們將SD卡大小Intel Edison主體裝設至Edison Arduino kit上面，使他可以掛載通用Arduino的擴充版。之後我們將XBee晶片安裝在XBee Arduino 擴充版，最後再把此擴充版安裝到Edison Arduino kit上便完成我們的Sensor Gateway的組裝

<img  class="profile" src="/public/edison assemble.jpg" id="photo" >

PuTTY連線
-------------
我們將使用PuTTY與Intel Edison 進行溝通。首先我們將Intel Edison使用USB連線至電腦，並確認他連結到哪一個序列埠(Serial Port)，之後設定鮑率(Baud rate)後便可透過PuTTY連線至Intel Edison。

【注意】:Baud rate必須跟Intel Edison的鮑率必須是相同的才行。

<img height="100%" width="100%" class="profile" src="/public/putty.png" >

連線至Intel Edison後，我們可以輸入Intel Edison的帳號以及密碼登入至Intel Edison的系統並進行各項設定，如調整Wi-Fi設定 
> Configure_edison --wifi

<img height="100%" width="100%" class="profile" src="/public/edison login.png" >


Intel XDK 
-------------
Intel XDK 是 Edison 的主要開發環境，首先我們於Intel官網下載[Intel® XDK IoT Edition](https://software.intel.com/en-us/intel-xdk)以及[Bonjour Print Services](https://support.apple.com/kb/dl999?locale=zh_TW)。於Intel XDK中首先我們要尋找我們的Intel Edison的板子，發現到之後輸入Intel Edison的帳號及密碼，便可與Intel Edison建立起連線。之後我們便可上傳我們的程式專案至Intel Edison，並執行工作。

【注意】:Intel Edison的板子必須與主機連上同一個區域網路。

<img height="100%" width="100%" class="profile" src="/public/xdk.png" >

Serial test 專案
-------------
開啟XDK後，載入WSN-for-IoT-Platform/Edison/SerialTest/SerialTest/的專案，載入完成後按下-Select a Device- 按鍵尋找自己的板子之後按朝下的箭頭將此專案燒入至板子。之後按下綠色的RUN箭頭執行此程式。

【注意】此專案是測試序列溝通，也就是XBEE連線有沒有問題。若發現XBEE連線有問題時跑此專案後再跑原本的專案。

SensorGateway 專案
-------------
開啟XDK後，載入WSN-for-IoT-Platform/Edison/SensorGateway/SensorGateway/的專案，載入完成後有幾項參數需要調整，如下:
>**1.xbee setting**
>var xbeeAPI = new xbee_api.XBeeAPI({
    api_mode: 2
}); 確認API模式為2
var serialport = new SerialPort("/dev/ttyMFD1", {
    baudrate: 9600,
    parser: xbeeAPI.rawParser()
});確認鮑率與XBEE鮑率相同，且SerialPort為/dev/ttyMFD1

>**2.ip setting**
>gateway_ip :設定成此板子的IP位置
>ponte_ip:設定成架設PONTE的主機IP位置

>**3.使用協定**
>依據想使用的協定，將其他協定的部分註解
>共有三種協定，分別為HTTP,CoAP,MQTT 

之後按下-Select a Device- 按鍵尋找自己的板子之後確認PONTE伺服器有開，然後按朝下的箭頭將此專案燒入至板子。之後按下綠色的RUN箭頭執行此程式。

【注意】若出現找不到import的錯誤，可能是reset過edison，此時進入SSH Terminal的畫面，針對import一個一個下指令，如

> npm install dateformat


