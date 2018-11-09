
# [OS-Q 垂直系统](https://github.com/OS-Q/OS-Q) 

虚拟系统Q，构建于传统系统之上，垂直整合的数据生态链，更好的执行数据的采集-传输-分析-存储的过程

[![sites](docs/os-q.png)](http://www.os-q.com)

## 简介

以云端为指挥中心，所有的数据通过云端导流到指定的设备上，降低对云端的处理性能需求，Q系统的核心思想就是强化边缘设备的作用

建立一种星型网络关联，所有的设备通过和中心平台对接，然后查询到自己最佳的配对方

---

## 项目结构

#### 物理环境

构建于Linux上的各种物理系统和驱动：

https://github.com/OS-Q/linux.git

#### 功能调用

基于Q系统对外提供的各种功能接口：

https://github.com/OS-Q/FaaS.git

#### 边缘设备

无固定地址的嵌入式设备边缘设备：

https://github.com/OS-Q/edge-Q.git

#### 信息发布

网络信息平台管理和控制调度相关设备：

https://github.com/OS-Q/web-Q.git

#### Q数据库

对原始素材数据和制成数据的归档存储：

https://github.com/OS-Q/DB-Q.git

---

## 节点连接

####  Q1

针对边缘控制节点：

https://github.com/OS-Q/Q1.git

通过私有传输协议将数据收集传递

####  Q2

针对边缘网络节点：

https://github.com/OS-Q/Q2.git

通过轻量级网络通信将数据送达网络

####  Q3

针对边缘计算节点：

https://github.com/OS-Q/Q3.git

无效数据的消耗，有效数据的精炼


####  Q4

针对云端数据分发平台：

https://github.com/OS-Q/Q4.git

将分布的数据信息进行汇集和导流

---

##  www.OS-Q.com
