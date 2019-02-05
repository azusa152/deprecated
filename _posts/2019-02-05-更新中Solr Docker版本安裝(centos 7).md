
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
<img class="profile" src="/public/13055127_1089114864479810_6006379361949457218_o.jpg" alt="profile-image">