#Golang语言版本 K-link MQTT Broker 

## 介绍

支持 MQTT Broker 3.1.1 协议版本

## 运行

```
$ go run main.go
```

## 参数

```
参数:

全局 :
    -w,  --worker <number>            用于处理消息Worker的数量. (默认数量是 1024)
    -p,  --port <port>                端口号 (默认端口: 1883)
         --host <host>                主机IP. (默认IP： "0.0.0.0")
    -ws, --wsport <port>              websocket监听端口
    -c,  --config <file>              配置文件

日志 ：
    -d, --debug <bool>                启用调试输出(默认关闭)
    -D                                调试启用

集群:
    -r,  --router  <rurl>             维护集群信息的路由表
 
命令:
    -h, --help                        帮助
```

### .config

```
{
	"workerNum": 4096,
	"port": "1883",
	"host": "0.0.0.0",
	"cluster": {
		"host": "0.0.0.0",
		"port": "1993"
	},
	"router": "127.0.0.1:9888",
	"wsPort": "1888",
	"wsPath": "/ws",
	"wsTLS": true,
	"tlsPort": "8883",
	"tlsHost": "0.0.0.0",
	"tlsInfo": {
		"verify": true,
		"caFile": "tls/ca/cacert.pem",
		"certFile": "tls/server/cert.pem",
		"keyFile": "tls/server/key.pem"
	},
	"plugins": {
		"auth": "authhttp",
		"bridge": "kafka"
	}
}
```

### 支持的功能列表：

- 支持 QOS 0 and 1
- 容器化部署
- 支持保留消息
- 支持遗嘱消息
- 支持Websocket
- 支持TLS/SSL 
- 支持Auth 
  - Auth Connect
  - Auth ACL
  - 支持Cache 
  - 支持Kafka 

### 在线/离线 提醒

## 性能

- 支持高吞吐
- 支持高并发
- 低内存和CPU
## 压测工具

- https://github.com/inovex/mqtt-stresser
- https://github.com/krylovsk/mqtt-benchmark
