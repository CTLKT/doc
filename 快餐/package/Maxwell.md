####  Maxwell
它会实时监控MySQL数据库的数据变更操作（包括insert、update、delete），并将变更数据以 JSON 格式发送给 Kafka，<font color="red" >通过监听mysql的binlog</font>

#### 1、Maxwell输出数据格式
![Snipaste_2024-05-06_12-22-40.png](..\img%2FSnipaste_2024-05-06_12-22-40.png)

#### 2、Mysql 主从复制
##### 主从复制的应用场景如下
（1）做数据库的热备：主数据库服务器故障后，可切换到从数据库继续工作。

（2）读写分离：主数据库只负责业务数据的写入操作，而多个从数据库只负责业务数据的查询工作，在读多写少场景下，可以提高数据库工作效率。
##### 主从复制的工作原理如下
（1）Master主库将数据变更记录，写到二进制日志（binary log）中

（2）Slave从库向mysql master发送dump协议，将master主库的binary log events拷贝到它的中继日志（relay log）

（3）Slave从库读取并回放中继日志中的事件，将改变的数据同步到自己的数据库
##### 3、Maxwell原理
很简单，就是将自己伪装成slave，并遵循MySQL主从复制的协议，从master同步数据。
