查看mysql事务情况

```mysql
SELECT * FROM INFORMATION_SCHEMA.INNODB_TRX;
```
![img.png](img/img.png)

查看当前线程
```mysql
SHOW PROCESSLIST;
```
![img_1.png](img/img_1.png)
time表示耗时，info表示SQL语句

使用kill threadId
```mysql
kill 6
```
杀死对应的线程
