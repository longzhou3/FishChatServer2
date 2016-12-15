# FishChatServer2

1 说明
======
吸取了第一版的经验以及我们商业版的探索. 第二版我更多的思考在不要过多的实现轮子, 这个版本将很多业务无关的代码去掉, 并且尽量靠拢`微服务`.
部署方式可以支持：
> * 普通部署
> * 容器部署 


2 架构
======

![](./doc/architecture.png)


3 协议
======
在`protocol`目录下

* external 是对外的协议，采用`protobuf`实现
* rpc 是服务内部的调用，采用`grpc`


4 服务说明
======
进入server目录下

```shell
access
gateway
logic
manager
register
```

5 依赖
======
```shell
etcd
redis
mongodb
kafka
ElasticSearch(可选)
```


6 部署
======

### 6.1 普通部署

为了方便, 我们在单机上进行部署

#### 6.1.1 依赖安装

* kafka安装 : http://kafka.apache.org/quickstart (默认启动即可)

* redis安装 : 采用默认安装即可

* mongodb安装 : 采用默认安装即可

* etcd安装 : 需要3.0以上版本, 采用默认安装即可

#### 6.1.2 服务安装
进入server目录 运行 `go build`, 然后启动服务即可(因为服务做了`服务发现`, 所以对启动顺序没有要求)



### 6.2 容器部署(暂不可用)

部署完全采用`Kubernetes + Docker`

所以第一步需要搭建`Kubernetes`和`Docker`, 幸运的是现在网络上已经有大量的资料了, 这块我就不多写了.

7 测试
======


8 监控
======