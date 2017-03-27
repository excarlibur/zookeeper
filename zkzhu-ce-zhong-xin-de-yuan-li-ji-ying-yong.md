zk注册中心的原理及应用

什么是zookeeper？

ZooKeeper is a high-performance coordination service for distributed applications. It exposes common services - such as naming, configuration management, synchronization, and group services - in a simple interface so you don't have to write them from scratch. You can use it off-the-shelf to implement consensus, group management, leader election, and presence protocols. And you can build on it for your own, specific needs.

ZooKeeper的数据模型

ZooKeeper拥有一个很像分布式文件系统的树型命名空间。两者间的唯一区别就是Zookeeper的节点可以有关联的数据孩子节点。

ZooKeeper Sessions

Zookeeper Watches

Consistency Guarantees

