MQTT Broker By Golang语言
============

MQTT Broker, 支持MQTT 版本 Version 3.1.1

Klink Mqtt Server by netty
基于 netty + redis + kafka 实现的MQTT服务broker

使用说明
功能说明
参考MQTT3.1.1规范实现
完整的QoS服务质量等级实现
遗嘱消息, 保留消息及消息分发重试
心跳机制
MQTT连接认证(可选择是否开启)，目前由clientId,username,password唯一确定一个有效的客户端连接
SSL方式连接(可选择是否开启)
主题过滤(支持单主题订阅如 test_topic /mqtt/test --不能以/结尾, 通配符订阅 # /mqtt/# --以#结尾)
集群功能(可选择是否开启)
Kafka消息转发功能(可选择是否开启)
编译执行
JDK1.8
项目根目录执行 mvn install
mqtt-broker 下执行 mvn clean package nutzboot:shade 进行打包
`java -jar mqtt-broker-xxx.jar
集群使用
多机环境集群:

klink.mqtt.broker.cluster-on=true
klink.mqtt.broker.kafka.bootstrap.servers=192.168.1.101:9092,192.168.1.102:9093
redis.mode=cluster
redis.nodes=192.168.1.103:16379,192.168.1.104:26379
单机环境集群:

klink.mqtt.broker.cluster-on=true
klink.mqtt.broker.kafka.bootstrap.servers=127.0.0.1:9092,127.0.0.1:9093
redis.mode=normal
redis.host=127.0.0.1
## Benchmark Tool

* https://github.com/inovex/mqtt-stresser
* https://github.com/krylovsk/mqtt-benchmark
