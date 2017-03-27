。zk注册中心的原理及应用

什么是zookeeper？

ZooKeeper is a high-performance coordination service for distributed applications. It exposes common services - such as naming, configuration management, synchronization, and group services - in a simple interface so you don't have to write them from scratch. You can use it off-the-shelf to implement consensus, group management, leader election, and presence protocols. And you can build on it for your own, specific needs.

ZooKeeper的数据模型

ZooKeeper拥有一个很像分布式文件系统的树型命名空间。两者间的唯一区别就是Zookeeper的节点可以有关联的数据孩子节点。 Paths to nodes are always expressed as canonical, absolute, slash-separated paths。任何字符都能用于路径，只要遵守以下几条规则:

The null character \(\u0000\) cannot be part of a path name. \(This causes problems with the C binding.\)

* The following characters can't be used because they don't display well, or render in confusing ways: \u0001 - \u0019 and \u007F - \u009F.

* The following characters are not allowed: \ud800 -uF8FFF, \uFFF0 - uFFFF.

* The "." character can be used as part of another name, but "." and ".." cannot alone be used to indicate a node along a path, because ZooKeeper doesn't use relative paths. The following would be invalid: "/a/b/./c" or "/a/b/../c".

* The token "zookeeper" is reserved.

ZNodes

在Zookeeper树上的结点，一般称之为znode. Znodes保持了一个包含数据变化版本号和时间戳数据结构\(Stat Structure\)及访问控制列表变化。版本号和时间戳让Zookeeper可以验证缓存以及协调更新。每当某个znode的数据变化，它的数据版本号也将增加。

znodes的特征:Watches,Data Access,Ephemeral Nodes,Sequence 

Time in ZooKeeper

Nodes

ZooKeeper Sessions

Zookeeper Watches

Consistency Guarantees

