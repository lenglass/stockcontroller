- Docker command

sudo docker run -it -d -p 58058:8080 --name tomcat-container tomcat:9.0.12-jre11-slim
docker run -it -d -p 18080:8080 -v /files:/opt/apache-tomcat-9.0.12/webapp --name tomcat tomcat:1

docker build -t tomcat:1 .

cd d:/Master/Documents/stockcontroller/Dockerfile
docker-compose up -d
docker exec -it tomcat-container ash
cd /opt/tomcat/webapps

英語に抵抗ある？
IntelliJ を日本語化するかどうか迷ってるんだけど。

日本語化は Pleiades 使えば簡単だよ。
