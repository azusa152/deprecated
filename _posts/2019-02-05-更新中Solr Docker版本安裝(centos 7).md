---
layout: post
title: Solr Docker版本安裝(centos 7)
subtitle   : "Solr Docker"
date       : 2019-02-05 00:00:00
author     : "azusa"
comments   : true
signature  : true
tags       : IoT,Intel Edison
---


<更新中>Solr Docker版本安裝(centos 7)
---------------


1.Docker 安裝 

//安裝docker
yum install docker -y

//啟動docker並設定為自動啟動
service docker start 
chkconfig docker on

2.Solr 安裝

docker run --name my_solr -d -p 8983:8983 -t solr

docker images





https://philipzheng.gitbooks.io/docker_practice/content/install/centos.html
https://hub.docker.com/_/solr/
