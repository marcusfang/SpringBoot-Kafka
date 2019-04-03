# springboot整合kafka
1. 确保自己成功搭建了kafka服务端，并且版本号为：kafka_2.12-1.0.0，可以从“https://archive.apache.org/dist/kafka/1.0.0/kafka_2.12-1.0.0.tgz”下载到！

2. kafka的安装极为简单，就是把kafka_2.12-1.0.0.tgz解压后，修改config/server.xml中的两处：
     listeners = PLAINTEXT://10.168.1.33:9092
     zookeeper.connect=10.168.1.39:2181
而后直接启动它即可，启动命令为：bin/kafka-server-start.sh config/server.properties

3. 修改本项目的配置文件application.yml中的spring.kafka.bootstrap-servers的连接信息为你搭建的Kafka连接地址。

4. 启动本项目，并访问http://localhost:8080/kafka/send，
观察com.xiaour.spring.boot.kafka.producer.Producer
和com.xiaour.spring.boot.kafka.consumer.Consumer
的动向；

![comsumer](https://github.com/marcusfang/SpringBoot-Kafka/blob/master/src/main/resources/static/comsumer.png)