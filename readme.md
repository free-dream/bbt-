# php类参考文档
## 一，环境搭建 
由于大多数同学都是第一次接触php，所以暂时只要求用php+mysql完成。另外，以下搭建只限于windows系统。

1. 直接到官网下载最新版

```
https://www.php.net/downloads.php  --选那个Zip标注的
https://dev.mysql.com/downloads/mysql/  --第一个就行
```

2. 安装mysql

   2.1 解压，进入bin文件夹，新建my.ini文件，将下面内容粘贴。

   * 有一处记得改为你的bin路径

   ```
   [client]
   # 设置mysql客户端默认字符集
   default-character-set=utf8
    
   [mysqld]
   # 设置3306端口
   port = 3306
   # 设置mysql的安装目录
   basedir=D:\Google\mysql-8.0.21-winx64\bin
   # 设置 mysql数据库的数据的存放目录，MySQL 8+ 不需要以下配置，系统自己生成即可，否则有可能报错
   # datadir=C:\\web\\sqldata
   # 允许最大连接数
   max_connections=20
   # 服务端使用的字符集默认为8比特编码的latin1字符集
   character-set-server=utf8
   # 创建新表时将使用的默认存储引擎
   default-storage-engine=INNODB
   ```

   2.2 切换目录

   用管理员模式打开cmd（或powershell皆可，以下皆称cmd），cd切换到bin目录。

   win10用户直接开始键+q打开搜索框，直接搜索，然后右键以管理员打开。

   ```shell
   >d:
   >cd google\mysql-8.0.21-winx64\bin  //替换成你自己的bin路径
   ```

   2.3 初始化

   直接照抄。

   ```shell
   >mysqld --initialize --console
   >mysqld install
   >net start mysql
   ```

   2.4 登录进入mysql命令行模式

   ```shell
   >mysql -uroot -p
   输入123456
   >exit //退出
   ```

   2.5 配置环境变量

   为方便使用mysql可以把bin目录加入系统环境变量，这样我们就不用每次都切换目录了，即以后可以直接在任意路径输入mysql连接命令打开mysql。

   方法是右键桌面的此电脑进入属性，然后点击高级系统设置-环境变量-系统变量（下面部分），找到path，双击然后新建即可。

3. 安装配置php

   3.1 解压，把php.exe所在目录写入系统环境变量

   3.2 根目录那里有php.ini-development，里面保存着大部分配置，以后有时间可以研究研究，ext里面存有大部分的扩展，开关都在ini里。

   3.3 搭建web服务器

   web服务器用于处理web请求并回应响应，这里搭建的web服务器仅仅是本地服务器，即只用于本地php文件的调试及本地的接口对接。

   ​	3.3.1 在其他地方建一个文件夹充当工作目录

   ​	3.3.2 cmd命令行切换至该目录

   ​	3.3.3 打开web服务器
   
   ```shell
   >php -S localhost:8000
   ```
   
      3.3.4 而后将文件存入根目录下，浏览器输入localhost:8000/文件全名即可

   ​	   3.3.5 更多方法详见

   ```
   https://www.php.net/manual/zh/features.commandline.webserver.php
   ```




## 二，基础知识

以下列出一些有用的网站，但是有些文章他们可能并非全对，或者与你的版本不对应，或者与你的环境不对应，总之，不要全信，多动脑筋。

1. 前端基础

   只要求简单会用HTML就行了

   ```
   https://www.runoob.com/html/html-tutorial.html
   ```

2. php基础

   以下的网站皆有系统的教学，不需要全学，可以边做边学，只学任务需要的。如果实在看不下去再去b站之类的找找视频吧。

   ```
   https://www.php.net/manual/zh/index.php -php官方文档
   https://www.runoob.com/php/php-tutorial.html  -菜鸟教程
   https://www.w3school.com.cn/php/index.asp  -w3school
   ```
3. mysql基础

   菜鸟和w3school也有系统的sql或mysql教学，暂时学会增删改查和命令行基本操作就行了。

   如果实在受不了命令行再去找些可视化辅助软件吧，如MySQL Workbench之类的。
