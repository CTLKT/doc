https://blog.csdn.net/vic868/article/details/44746737

【语法】RANK ( ) OVER ( [query_partition_clause] order_by_clause )
dense_RANK ( ) OVER ( [query_partition_clause] order_by_clause )

【功能】聚合函数RANK 和 dense_rank 主要的功能是计算一组数值中的排序值。

【参数】dense_rank与rank()用法相当，

<font color="red">【区别】</font> dence_rank在并列关系是，相关等级不会跳过。rank则跳过
rank()是跳跃排序，有两个第二名时接下来就是第四名（同样是在各个分组内）
dense_rank()l是连续排序，有两个第二名时仍然跟着第三名。