Mysql索引可以设置为btree或者hash如果使用的是memory存储引擎

区别：

{



}

show variables like "%pro%"

set profiling=1

show profiles

show profile all for query ${index}

Mysql存储引擎

​	blackhole

​	memory

​	myisam 

​		只支持表级锁

​		保存了条目数

​		堆表

​		不支持外键

​		.frm .myd .myi

​	innodb 

​		支持事务和行级锁

​		索引组织表

​		.frm .ibd(多表空间) .ibdata1-n(共享表空间)

外键控制数据库的完整性和一致性

CONSTRAINT `key` FOREIGN KEY (``*) REFERENCES `table` (``*)

索引优化查询，牺牲修改操作时的性能

​	show keys/index in ${database};

​	索引种类

​		主键

​		全文

​		普通

explain查看执行语句

profiles查看性能

profile查看具体执行细节

主从同步时可以通过blackhole来减轻主机压力和用过滤器选择同步数据

出现死锁怎么解决

共享锁 排他锁

JVM gc机制

树 可达性分析对象是否还存在引用

young  init eden_space from_space to_space 

old tenu

permanent permanent_space

调用system.gc() 建议JVM进行full gc

​	可禁用：-xx:+DisableExplicitGC

CMS GC

