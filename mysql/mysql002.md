### 数据库为什么要分库分表

连接数

处理能力

存储数量







sql优化

索引

分区

主从：高可用

集群：容错，所有时间数据一样，是同步的，不是异步的



什么时候考虑切分：

根据业务现状考虑。

数据量过大： 物理文件超过2g,条数载500w-1000w

数据增长过快

对某些字段进行切分

处于安全性和可用性的考虑：不用业务放在不同的数据库上，防止数据丢失都丢了



分库分表：

垂直切分：根据业务进行不同的切分。

​	根据访问频率进行切分，

水平切分：

​	同一个库建多张相同的表

​	

## 数据切分的问题和解决方案：

事物一致性的问题

跨节点join查询问题

​	全局表

​	字段冗余

​	er分片（业务相关联数据分布在一个节点上）

​	数据组装

跨节点分页，排序问题

​	结果汇总做二次计算

全局主键

​	

数据迁移，扩容问题

​	

## 通过mycat来处理

提供各种策略



全局表：

​	有关系

​	数据不经常更新

​	数据量不大

​	