# [OS-Q](https://github.com/OS-Q/OS-Q) 
####  qitas@qitas.cn
[![sites](OS-Q/OS-Q.png)](http://www.OS-Q.com)

## [简介](https://github.com/OS-Q/OS-Q/wiki) 

Q系统核心思想是强化边缘设备的作用，以云端为指挥中心，所有的数据通过云端导流到指定的设备上，降低对云端的处理性能需求，通过通过丰富的边缘端设备实现丰富的功能

是一个有应用层软件构成的大系统工程，通过积木组合实现任意的业务逻辑。


Q系统的核心宗旨：角色分配，功能增强，裂变增生

- 对于系统初始状态具有完备性，设备的角色可以有多重延伸，而每种“进化的方向”取决于现有群体的需求

- 对于角色完备的群体，可以通过数量补足或提高短板性能，所有的取向宗旨是最高能效提高群体的效率

- 每个个体都可以自动复制部署相同的设备或则需要的设备，从而实现在更大范围和视角下的群体效应


## [系统构成](https://github.com/OS-Q/OS-Q/wiki) 

#### 通信组件：[MQ-Q](https://github.com/OS-Q/MQ-Q)

Q系统的消息中间件，提供给各个边缘设备使用

#### 数据存储：[DB-Q](https://github.com/OS-Q/DB-Q)

本地化数据归档，组成分布的数据网络

#### 数据呈现：[UI-Q](https://github.com/OS-Q/UI-Q)

系统在不同维度上的数据呈现和交互控制，面向使用者

#### 功能服务：[QaaS](https://github.com/OS-Q/QaaS)

QaaS对外提供各种服务接口，面向业务调用

#### 边缘设备：[Edge-Q](https://github.com/OS-Q/Edge-Q)

大量边缘设备完成Q系统主体功能，包括丰富的产品形态和功能服务

### [底层系统](OS-Q/)

#### [RTOS](https://github.com/OS-Q/RTOS)

最边缘端的控制和感知底层系统，通过底层系统实现更上层应用的归一化

#### [Linux](https://github.com/OS-Q/Linux)

普遍的计算和通信设备底层系统，通过Linux平台集成相应的工具和资源

#### [Docker](https://github.com/OS-Q/Docker)

弹性云端或高性能端的底层技术，通过容器实现自下而上的环境搭建

---

###  [OS-Q: operation system for edge device cluster](http://www.OS-Q.com)
####  2019-3-20