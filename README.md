[![sites](docs/os-q.png)](http://www.os-q.com)

# OS-Q（www.OS-Q.com）


[虚拟]系统Q，试图以一种构建于传统系统之上的同一封装，构建统一的数据生态链，更好的执行数据的采集传输加工处理和存档问题


## 简介

我试图通过构建一个连接边缘和云端的一体化系统，将所有数据无缝对接

通过设备虚拟层，让每个节点都是系统的一个设备外设，如果SOC的寄存器一般可以自由操作

将人和物统一在这个系统中，人和物都是数据的生产者和消费者



---

## 组成

#### 物理环境

系统主要构建于Linux上，包括各种物理驱动，相应的物理环境参见：

https://github.com/OS-Q/linux.git

#### 容器环境

在Linux系统之上，是由容器构建的基础环境：

https://github.com/OS-Q/docker.git


#### 功能调用

在基础环境中可能调用各种函数功能：

https://github.com/OS-Q/FaaS.git

#### 数据库

对数据的归档处理单独封装：

https://github.com/OS-Q/DB.git

#### 边缘节点

针对嵌入式设备的边缘节点：

https://github.com/OS-Q/edge.git



---

## 为锻造最美之器

