将项目上传至GitHub:
git init
git add .
git commit -m "注释语句"
git config --global user.email "hushunjian950420@163.com"
git config --global user.name "hushunjian"
git remote add origin https://github.com/hushunjian/hushunjian
git pull origin master
git push -u origin master



Linux环境下安装jdk:
yum install java-1.8.0-openjdk* -y 


Linux环境下安装Git:
yum install -y git


Linux环境下安装rz:
yum provides */rz
yum install -y lrzsz


Linux环境下安装mysql:
yum install mysql
yum install mysql-server
yum install mysql-devel


设置密码
set password for 'root'@'localhost' =password('password');

设置所有ip都可以访问数据库
grant all privileges on *.* to root@'%'identified by 'mysql'
参考网址:http://www.cnblogs.com/starof/p/4680083.html



Linux环境下查看网络端口信息:
netstat -ntpl


查看防火墙状态:
iptables -vnL


清除防火墙中链的规则
iptables -F


使用navicat连接远程linux的mysql中文显示乱码的问题:
右键->连接属性->高级->去掉使用mysql字符集，编码选择(65001)utf-8


GitHub删除target文件夹:
git pull origin master 
dir
git rm -r --cached target
git commit -m '删除target文件夹'
git push -u origin master



启动，停止mysql服务
service mysqld start
service mysqld stop
service mysqld restart


linux命令行登录mysql
mysql --user=root -p


mysql常用命令
show databases
use mysql
show tables
create database apps
drop database apps
show variables like '%character%'



Linux查看系统语言
echo $LANG


查看安装的语言包
locale

安装中文语言包
yum groupinstall chinese-support


修改mysql字符编码
[client]
default-character-set=utf8
[mysql]
default-character-set=utf8
[mysqld]
default-character-set=utf8
参考网址：http://blog.csdn.net/xlgen157387/article/details/52781632



重启虚拟机
reboot


安装中文输入法
yum install "@Chinese Support"



打包，解压缩命令
unzip 压缩包 解压含有多个压缩文件



Linux下安装Nginx
检查常用必备支持库  rpm -qa | grep gcc
安装g++,gcc  yum install gcc-c++
参考网址:https://www.linuxidc.com/Linux/2016-08/134110.htm


Linux下安装redis
$ wget http://download.redis.io/releases/redis-4.0.8.tar.gz
$ tar xzf redis-4.0.8.tar.gz
$ cd redis-4.0.8
$ make
切换到src目录下使用make install
启动redis服务
redis-server /usr/local/redis/etc/redis.conf
参考页面http://www.jb51.net/article/79096.htm
netstat -tunpl|grep 6379
ps -ef|grep redis
开启redis远程访问
注释bind 127.0.0.1
设置protected-mode no
参考网页https://www.cnblogs.com/liusxg/p/5712493.html


安装本地jar包至本地仓库中：
mvn install:install-file -Dfile=D:\***.jar -DgroupId=*** -DartifactId=*** -Dversion=*** -Dpackaging=jar



@PathVariable和@RequestParam的区别:
	@RequestParam用来获得静态的URL请求参数
	@PathVariable用来获得动态的URL请求入参



swagger的使用
@ApiModelProperty(value="",required=true) 注解使用


mybatis中使用PageInterceptor插件进行分页
<plugins>
	<plugin interceptor="com.github.pagehelper.PageInterceptor">
		<property name="offsetAsPageNum" value="false" />
		<property name="rowBoundsWithCount" value="true" />
		<property name="pageSizeZero" value="true" />
		<property name="reasonable" value="false" />
		<property name="supportMethodsArguments" value="false" />
		<property name="returnPageInfo" value="none" />
	</plugin>
</plugins>

创建rowBounds对象
PageRowBounds pb = new PageRowBounds((pageNumber-1)*pageSize,pageSize);

mybatis中打印sql语句
<setting name="logImpl" value="STDOUT_LOGGING" />


