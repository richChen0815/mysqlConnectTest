
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



### mysql-workbrench client(select workbrench)
