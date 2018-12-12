# boot-security


环境搭建说明
一、	Jdk要求1.8
代码里使用了1.8的lamdba表达式
二、	导入项目
1.	Eclipse导入
右键Import
 
点击next，浏览目录

点击完成，等待maven下载相关依赖jar包。
2.	idea导入maven项目
 
下一步，浏览，找到相应文件夹，
这里只是一个例子，具体路径根据您的情况自己选择
 
这里选择Maven
 
按下图进行勾选
 
 
点击Next
 

这里可以输入您的项目名
 

如果有报错，可以Rebuild Project试下 


三、	初始化表和配置修改
1.	初始化表和数据
数据库初始化脚本在文档和sql文件夹下，db文件夹下的boot_security.sql
创建数据库，库名我们设置为boot_security，可以用别的名（下一章的配置里库名改下即可），并执行sql，完成数据库基础表和数据的初始化。
 

2.	配置项目数据库信息
找到application.yml文件
 
 
根据自己的数据库信息进行配置，端口号、数据库名、用户名、密码。
3.	配置redis
 
如要配置密码
 别忘记冒号后加空格
不用redis也可以，看下02 框架及配置.docx 里的第四章 第三节切换到数据库存储



四、	启动
1.	启动redis服务
Windows版redis下载路径
https://github.com/MicrosoftArchive/redis/releases
 
下载免安装版的即可
 
双击及启动
2.	启动后台管理系统
 

右键Run A或者Debug As-> Java Application

启动成功
访问http://localhost:8080
 
管理员用户名和密码都是admin
3.	535错误
Idea启动后，可能会报出535错误代码，属于正常，因为没有在application.yml里配置正确的mail相关的配置，如没有发邮件的业务需求，请忽略该处。
如果要用发邮件模块的，请务必请您配置上您的邮箱信息，并且注释掉的两行配置，请打开，如下图
 

需要您开通smtp协议，如163邮箱：
http://help.163.com/10/0312/13/61J0LI3200752CLQ.html
270480546：授权码 nijjtvssqwpebibj


五、	打包
对着pom.xml或者项目右键，如图：
务必先停止运行项目，
 

初次编译打包，会弹出下图
 
输入Goals，选中Skip Tests，点击Run
以后直接右键Run As->Maven build即可

会自动一依次打包，下图打包成功
 

最终生成的可执行jar包在
 


六、	Jar部署运行
以boot-security-1.0.jar包在d:/test目录为例
打开cmd
D:
cd test
java -jar boot-security-1.0.jar
 
部署成功














 


