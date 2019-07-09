
### [download url](https://dev.mysql.com/downloads/file/?id=485812)

### mysql-server server(select Community)

## 安装步骤
 1.解压压缩包文件 </br>
 2.配置环境变量 server 的bin 目录配置到环境变量path中 </br>
 3.git bash here bin 
 
 ```
    (1)mysqld --install
    (2)mysqld --initialize 初始化
    (3)net stop mysql  net start mysql
 ```

 ![图片](https://github.com/richChen0815/mysqlConnectTest/blob/master/1562574879(1).jpg) 
 
 
## 问题 压缩包+命令行的方式 会有一个问题,会发现中间少了设置初始密码过程。如果没有密码怎么登陆呢？

   解决：
       找到mysql-server data 目录下.err文件，可以找到默认随机出来的密码。

       (1) mysql -u root -p -p 指的是密码
       (2) 输入随机分配密码
       (3) 重置密码
           5.7.6以及之后的版本修改密码的命令为： ALTER USER 'root'@'localhost' IDENTIFIED BY 'yourPass';
           5.7.6之前的修改密码的指令为： SET PASSWORD FOR 'root'@'localhost' = PASSWORD('yourPass');


  ![图片](https://github.com/richChen0815/mysqlConnectTest/blob/master/1562575813(1).jpg)
       
  ![图片](https://github.com/richChen0815/mysqlConnectTest/blob/master/1562576475(1).jpg)



### mysql-workbrench client(select workbrench)
 **workbrench --mysql图形化工具**
 1.创建数据库   右击 create new schema.
 2.切换active schema 
   (1)右击 set sa default active schema
   (2)use db_test;
   
**use command**
   一般生产环境不会安装客户端图形化界面,所以会使用到命令行开发。
   
   1.命令行登录mysql server
      ```
       mysql -u root -p
      ```
   2.显示有多少库
     show databases;
     

 
   
   
  
 student table 
   id
   name
   sex   M 男性 F 女性  boolearn(2) 
   class_id  Int 
   birth   timestamp (1970 到现在的时间戳)  | date  |  dateTime  
  

## 条件查询函数
```
   
   1. count(*) 查询数量      @example  select count(*) from t_class;
   2. min(column) 查最小值   @example  select min(number) from t_class;
   3. sum()  求和
   4. sqrt() 平方根
   5. rand() 随机数   rand()*3
   6. now()  当前函数  @example  select now();
   7. concat() 拼接字符串  @example  select concat(id,'用户姓名',name)  @result {}
```
   
## where 子条件查询

```
   1. 大于小于      @example select * from t_class where class_id > 1 and class_id < 5; </br>
   2.between and   @example select * from t_class where class_id between 1 and 5;</br>
   3.全匹配         @example select * from t_class where name ='一班';</br>
   4.like          @example select * from t_class where name like '%班';   '% 中间%' | '% 班'  |  '一 %'</br>
   5.排序 order by  desc(降序)| asc(正序); @example select * from t_student order by birth desc </br>
   6.关联查询       @example select t_student.id,t_class.name from t_student,t_class where t_student.class_id = t_class.class_id </br>
   7.left join on  @example select t_student.id,t_class.name from t_student left join t_class on t_student.class_id = t_class.class_id </br>
```
