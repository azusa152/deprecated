---
layout: post
title: WSN-for-IoT-Platform Xbee_Setting
subtitle   : "Xbee_Setting"
date       : 2017-08-19 00:00:00
author     : "azusa"
tags       : Zigbee IoT
comments   : true
signature  : true
---


在這一篇文章當中，我將介紹如何安裝我所開發系統中XBEE的設定
程式碼於我的[Github倉庫](https://github.com/azusa152/WSN-for-IoT-Platform)中，歡迎大家使用。



XCTU
-------------
XCTU是DIGI公司提供的免費GUI介面軟體，可以在Windows, MacOS 以及Linux系統上執行，並設定XBee晶片。關於XBee的晶片設定，首先我們將XBee晶片接在含有FT232RL晶片的USB轉TTL串口模組上面(若沒有用FT232RL晶片的話可能會造成晶片韌體永久損壞)，之後把電壓切換至3.3V供應，並把板載調到高電平，最後接USB線至電腦上便完成。之後開啟XCTU軟體，進行設定。

![enter image description here](https://lh3.googleusercontent.com/-pUywudNuYJw/WaUD3gMDjUI/AAAAAAAAA60/ZwNRFBEbQS4UUzs18veo33xC7PvhBTh1wCE0YBhgL/s0/XCTU.png "XCTU.png")

進入至XCTU軟體畫面後，首先我們要尋找我們XBee晶片所連接的序列埠，之後便可進入設定畫面。首先我們先把XBee晶片的韌體更新至最新版本，之後依據此XBee晶片要擔任Coordinator 或 Router而燒入不同韌體。重要的參數如下:

> ID :為PAN的ID，要在同一個PAN的XBee節點才會互相溝通。
> 
> DH :為目標位置的高位，通常同一家DIGI公司所生產的XBee晶片皆為0013A200，若是想要廣播或連接到不同家公司的晶片可設為0。
>
> DL: 為目標位置的低位，DIGI公司所生產的XBee晶片通常為生產時的流水號，若設定特定值代表只往那顆節點傳送訊息，若設定為FFFF的話會廣播訊息至所有節點。
> 
> NI:節點的名稱。
>
> AP:是否為API模式，API模式時所傳送的訊息皆包裝成一個訊息框後才傳送，若是AT模式的話是一個字一個字的傳送。於本系統我們需要調為2使訊息框可以包含跳脫字元(Escape character)。

【注意】:API(Api mode)須設定為2。


ZigBee Config 
-------------
於本系統中所設定的參數請參考 WSN-for-IoT-Platform/zigbeeConfig .txt 的檔案。
目前系統有設定兩群的ZigBee網路



第一個如下:
>網路參數:
>
>ID :987
> 
>SC :10
>
>SD :3

>晶片序號
>
>COR:
0013A200
40C8D191
>
>Router1:
13A200
40C8D185
>
>ROUTER3:
13A200
40694FA0

第二個如下:
>網路參數:
>
> ID 319
>
>SC 10
>
>SD 3

>晶片序號
>
>COR2_HC:
13A200
40F1EC3E
>
>ROUTER1_HC:
13A200
4071F80D
>
>ROUTER2_HC:
13A200
4071F744
