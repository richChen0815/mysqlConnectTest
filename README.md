
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

       (1) mysql -u root -p
       (2) 输入随机分配密码
       (3) 重置密码
           5.7.6以及之后的版本修改密码的命令为： ALTER USER 'root'@'localhost' IDENTIFIED BY 'yourPass';
           5.7.6之前的修改密码的指令为： SET PASSWORD FOR 'root'@'localhost' = PASSWORD('yourPass');


  ![图片](https://github.com/richChen0815/mysqlConnectTest/blob/master/1562575813(1).jpg)
       
  ![图片](https://github.com/richChen0815/mysqlConnectTest/blob/master/1562576475(1).jpg)



### mysql-workbrench client(select workbrench)
