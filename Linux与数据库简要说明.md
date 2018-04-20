
## Linux与数据库简要总结

## Linux

#### Linux内核最初只是由芬兰人李纳斯·托瓦兹（Linus Torvalds）在赫尔辛基大学上学时出于个人爱好而编写的。

#### Linux是一套免费使用和自由传播的类Unix操作系统，是一个基于POSIX和UNIX的多用户、多任务、支持多线程和多CPU的操作系统。

#### Linux能运行主要的UNIX工具软件、应用程序和网络协议。它支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。

#### Linux的发行版本有很多，我学习的是centos7版本，在学习之前已经购买阿里云服务器并且还安装的centos7的虚拟机；

#### 阿里云上的服务器只有命令行；而虚拟机可以选择安装可视化桌面，在桌面与命令行之间切换可以用ctrl+alt+f1和ctrl+alt+f2;

#### Nginx - HTTP server / wsgi
#### MySQL - Persestence/RDB 关系型数据库  SQL语言  持久化 方便、快速的存取 保证数据的有效性
#### Cluster 集群，N个服务器  + Nginx/Load Balance 负载均衡 + Keepalived 热备
#### Redis - High Speed Cache/NoSQL（= Not Only SQL）高速缓存服务

### linux 相关命令如下：

Nginx - HTTP server / wsgi
MySQL - Persestence/RDB 关系型数据库  SQL语言  持久化 方便、快速的存取 保证数据的有效性
Cluster 集群，N个服务器  + Nginx/Load Balance 负载均衡 + Keepalived 热备
Redis - High Speed Cache/NoSQL（= Not Only SQL）高速缓存服务



查看进程：ps                  - process state
新增用户：adduser
修改/新增密码：passwd + 用户名
切换用户：su                  - switch user

重启：reboot/init 6
关机：shutdown/init 0

显示连接用户：who/who am i/w
历史命令：history
执行历史命令：！+ 历史编号
查看当前工作路径：pwd         - print working directory
切换目录：cd - change directory
列出当前目录下的文件：ls      - list directory contents
列出当前目录下的文件（含隐藏文件）：ls -a
以长格式列出当前目录下的文件：ls -l 或 ll
以长格式列出当前目录下的文件（含隐藏文件）:ls -la 或ls -l -a
注：长格式中:‘r - read读  w - write写  x - execute执行’
查看内容前n行(不写-n，默认前10行)：head -n 文件名
查看内容后n行（不写-n，默认后10行）：tail -n 文件名

回到当前用户主目录：cd ~
以.开头的文件或文件夹为隐藏文件
查看文件里面的内容：cat + 文件名

查看命令手册（manual）：man + 命令
查看命令详细信息(information)：info + 命令
查看命令简略帮助信息：命令 + --help
（--help|less 或--help|more   一页页的显示）

创建空文件：touch +文件名
删除文件：rm + 文件名
强制删除文件：rm -f +文件名

创建文件夹： mkdir + 文件名
删除空文件夹： rmdir + 文件名
强制删除文件夹： rm -rf + 文件名

回声命令：echo
拷贝：cp +文件名 a/修改后文件名（不写则默认不改文件名）
剪切/改名字：mv +文件名 a/修改文件名（不写则默认不改文件名）
往文件内写入内容: echo '内容' > 文件名
比较两个文件内的内容，找出不同：diff A文件名 B文件名

字符统计，查出文件内字符数量：wc +文件名     
结果（行数，单词数，字符数（含末尾光标））
字符统计，查出文件内指定字符数量：grep -o 字符名 文件名|wc -l
检查文件类型：file + 文件名

联网：wget +域名
联网下载指定文件名：wget +域名  -O +文件名
查找文件内指定内容：cat +文件名|grep +内容
文件内容去重：uniq [-cdu][-f<栏位>][-s<字符位置>][-w<字符位置>][--help][--version][输入文件][输出文件]
	      uniq +文件名  去除文件内的重复内容
	      uniq -c 文件名 检查文件并删除文件中重复出现的行，并在行首显示该行重复出现的次数
文件内容排序：sort [-bcdfimMnr][-o<输出文件>][-t<分隔字符>][+<起始栏位>-<结束栏位>][--help][--verison][文件]
	      sort +文件名  文件内的排序

压缩：gzip +文件名
解压缩：gunzip +文件名
一起归档：tar -cvf 指定文件名  +需归档文件名(*.txt即所有的txt格式文件）
解档： tar -xvf 指定文件名

命令所在路径：which +命令
查看所有包含该命令所在路径：whereis +文件名
日历：cal +年份

录制脚本（记录操作）：script +文件名（默认为typescript）
（退出：exit）

同一Linux不同用户相互之间可以发信息：write +用户名
可以直接发送警告：wall +内容 （所有用户都可以收到） 

杀掉进程：kill +进程号
强制杀掉进程：kill -9 +进程号

新增/修改当前用户权限：chmod u+x +文件名
(x:执行；r:读；w：写)
去掉当前用户权限： chmod u-x +文件名
同组用户增加权限：chmod g+x +文件名
其他用户增加权限：chmod o+x +文件名

所有用户修改权限为可读可写可执行：chmod 777 +文件名
（-rwxrwxrwx    当前用户、同组用户、其他用户  二进制：111 111 111 也就是777）
执行文件：./文件名

python2中可读汉字（页首写）：#_*_ coding:utf-8 _*_

移除软件：remove
查进程：ps -aux 或ps -ef 
列出安装的软件：yum list installed

centos 7 防火墙：firewalld
查看防火墙状态：firewall-cmd --state
查看服务状态：systemctl status 服务名
停止防火墙：systemctl stop firewalld
系统控制(centos7): systemctl
重启防火墙：firewall-cmd --reload


那怎么开启一个端口呢
添加
firewall-cmd --zone=public --add-port=80/tcp --permanent    （--permanent永久生效，没有此参数重启后失效）
重新载入
firewall-cmd --reload
查看
firewall-cmd --zone= public --query-port=80/tcp
删除
firewall-cmd --zone= public --remove-port=80/tcp --permanent
（其它低版本：servies）

安装rpm文件：rpm -iv 文件名

查看端口状态：netstat -na|grep 端口号
查看端口号及其进程：netstat -nap|grep 端口号
将信息放入指定文件：netstat -nap > 文件名
将错误信息放入指定文件：netstat -nap 2> 文件名
停止nginx:nginx -s stop

远程连接到其他服务器：ssh 用户名@IP地址
网络拷贝
本地复制到远程：scp 地址及文件名 用户名@IP地址：下载到指定地址及文件名
远程复制到本地：scp 用户名@IP地址:地址及文件名 下载到指定地址及文件名
上传与下载前奏：sftp 用户名@IP地址
下载：get 文件名
上传：put 文件名


nat:网络地址转换
路由器端口映射：外网可以访问内网
找当前目录下文件：find -name 文件名
找内容(n为行号，R为递归的寻找，均可省略)：grep "字符" 文件名 -n -R
xargs
创建符号链接（硬链接。新建一个链接B指向A,AB都是打开同一文件）：ln 文件名A 文件名B 
注：此处A和B都指向文件源，删除一个，另一个不受影响，相当于不占用空间的情况下做了备份

软链接（相当于windws下的快捷方式,新建一个链接B,为A的快捷方式）：ln -s  文件名A 文件名B 

redis后台运行（多一个&）：redis-sever myredis.conf &
redis后台运行（重定向，输出到指定文件）：redis-server myredis.conf > 文件名 &
后台运行的任务放到前台（%后面的数字代表第几个任务）：fg %1
启动服务端：redis-cli
输密码：auth 密码

访问


计划任务定时执行：crontab
进入当前用户的工作表编辑：crontab -e
每行是一个命令：时间+动作 ==>  * * * * * 动作
*号分别代表：分（0-59）、时（0-23）、日（1-31）、月（1-12）、 周（0-6，0代表周日） ==> * * * * *
*取值范围内所有的数字
/每过多少个数字
-从X到Z
,散列数字
例：45 4 1,10,22 5 */ect/init.d/smb restart 
意思是：5月的1、10、22日的4点45重启smb


自己写的程序开机自启
方法一：
cd /etc
vi rc.local
添加要执行的程序地址：
例如：/home/xl/./hello.py
那么开机就会执行该python程序（前提hello.py改为可执行）

方法二、
可以利用crontab实现

方法三、
系统服务的启动就是通过“/etc/rc.d/init.d”中的脚本文件实现的。我们也可以写一个自己的脚本放在这里。
脚本文件的内容也很简单，类似于这个样子（例如起个名字叫做“hahad”）：
. /etc/init.d/functions
start() {
        echo "Starting my process "
        cd /opt
        ./haha.sh
}
stop() {
        killall haha.sh
        echo "Stoped"
}
写了脚本文件之后事情还没有完，继续完成以下几个步骤：
chmod +x hahad                    #增加执行权限
chkconfig --add hahad             #把hahad添加到系统服务列表
chkconfig hahad on                 #设定hahad的开关（on/off）
chkconfig --list hahad               #就可以看到已经注册了hahad的服务
 
这时候才完成了全部工作。



取得进程号并关闭
ps -aux|grep 进程名|awk '{print $2}'|xargs kill

在任意目录下都可以执行mycal ==>  ln -s /root/mycal /usr/bin/mycal
root文件夹下所有可执行程序在任意目录下都可执行：
cd ~
vi .bash_profile
在bin后加:/root

定义用户登录可执行的动作：
	vi .bash_profile
	export PASH 的下一行添加动作就可以了
	例如：
	echo Welcome to my world!

定义开机执行的动作：
	cd /etc
	vi rc.local
	最后一行添加动作就可以了
	例如：nginx

##### 注： 以上的命令肯定不能涵盖所有Linux命令，其余的命令在用的时候再查就好了。也可以通过'菜鸟教程'上去查询与学习。

### VI-VIM 

创建文件：vi +文件名（若有则打开该文件）
i
esc
在命令行时：
:set nu ：列号
:set nonu ：取消列号
:syntax on：高亮语法
:set ts=4 制表键改成4个空格
dd:删整行
dw:删一个单词
u：撤销
5dd:删5行
G：到最后一行
gg：到第一行
100G：到100行
/字符 查找字符
n 重复上一个搜寻

:1,$s/word1/word2/g ==>从第一行到最后一行寻找 word1 字符串，并将该字符串取代为 word2 ！(常用)【g全局搜索，gc为全局搜索且每次修改需确认  gice==> 全局，忽略大小写，修改需确认，不显示错误】

开始录制宏（宏的名字只能是abcd中的一个）：qa
结束录制：q
宏录制的内容重复执行n遍：n@a

用正则表达式需转义\

定义缩写书写方式，即短缩写代替长的代码，下次使用直接可以调出：
命令模式下：  ：abbr 字符 长字符
（退出后，下次进入就么没有了）

定义快捷键，命令模式下：
:map 快捷键 命令A

##### 注：当然，这些只是一些简单的命令，至于所有的快捷方式及命令，可以参见下图，这张图是从其他地方发现的，感觉特别有用，至于在哪儿发现额，我忘了，但是百度一下，你应该就会知道。

## 数据库

#### 数据库：数据库(Database)是按照数据结构来组织、存储和管理数据的仓库，它产生于距今六十多年前，随着信息技术和市场的发展，特别是二十世纪九十年代以后，数据管理不再仅仅是存储和管理数据，而转变成用户所需要的各种数据管理的方式。数据库有很多种类型，从最简单的存储有各种数据的表格到能够进行海量数据存储的大型数据库系统都在各个方面得到了广泛的应用。
#### 在信息化社会，充分有效地管理和利用各类信息资源，是进行科学研究和决策管理的前提条件。数据库技术是管理信息系统、办公自动化系统、决策支持系统等各类信息系统的核心部分，是进行科学研究和决策管理的重要技术手段。

### MySql 关系型数据库

#### Mysql是最流行的关系型数据库管理系统，在WEB应用方面MySQL是最好的RDBMS(Relational Database Management System：关系数据库管理系统)应用软件之一。

注:关系型数据库 ==> 关系代数 + 集合论
   用二维表组织数据
   SQL ==> 自己的编程语言 ==> 结构化查询语言




安装数据库客户端及服务器：yum install mariadb-server mariadb
启动数据库服务器：systemctl start mariadb
停止数据库服务器：systemctl stop mariadb
连接本地数据库服务器：mysql -u root -p
连接其他用户的数据库服务器：mysql -h ip地址 -u 用户名 -p
显示所有数据库：show databases;  （有分号哦）
要使用mysql数据库：use mysql

查看表内所有行所有列：select * from user;
查询用户名、连接方、密码：select user, host, password  from user;
修改连接方访问，远程连接（%为所有人）：update user set host='%' where host='xxx' and user='root';
查看网络端口是否正常：netstat -na|grep 端口号




数据库服务开机自启：systemctl enable mariadb
取消数据库服务开机自启：systemctl disable mariadb



-- SQL: Structured Query Language
-- DDL: create / drop / alter 
-- DML: insert / delete / update
-- DQL: select
-- DCL: grant / revoke



自增：auto_increment

通过主键id 与外键sid 将多个表格联系起来 进行查询（例如：学生，班级，信息三个表格）
select * from table1 t1, table t2, table3 t3
where name='' and t1.id=t2.sid and t3.sid=t2.id

倒序查询：select * from student order by (-id);

desc 看表的结构

函数返回表中的记录数：count（*）

根据一个或多个列对结果集进行分组: group by()

modify 修改类型：alter table 表格名称 modify  项目名称 改后的类型；
change 修改类型：alter table 表格名称 change 改前的项目名称 改后的名称 改后的类型；

关键字==>max,min,avg,求最大值，最小值，平均值: select 关键字 from student；


给表TbSC添加外键约束；
(on delete cascade -- 主键删除时此外键也删除)
（on update cascade -- 主键更新改变时外键也更新）
（on delete set null -- 主键删除时，外键值设置为null）
alter table TbSC add constraint fk_cid foreign key (sid) references bStudent(stuid) on delete cascade on update cascade;


where 里面不能写聚合函数直接判断，但是having可以：
	select * from A group by XX having avg(XXX)>=90;



表达式：IF( expr1 , expr2 , expr3 )
	expr1条件，条件为true，则值是expr2 ，false，值就是expr3 

IFNULL( expr1 , expr2 )
	在 expr1 的值不为 NULL的情况下都返回 expr1，否则返回 expr2

### sql语言

#### SQL 是用于访问和处理数据库的标准的计算机语言。

#### 如下，创建一个叫company的数据库，并进行增删改查的操作：

-- SQL (结构化查询语言-Structure Query Laguage)
-- DDL (数据定义语言）creat 创建/ drop 删除 /alter 修改
-- DML
-- DQL
-- DCL

-- 创建comany数据库
drop database if exists company;
create database company default charset utf8;

-- 关系型数据库用二维表组织数据
-- 关系型数据库有自己的编程语言

-- 切换到campany数据库
use company;

-- 创建部门表
-- 能够唯一确定一条记录的列可以设置为主键
-- 删表
drop table if exists tb_dept；  

create table tb_dept
(
deptno integer not null comment '部门编号',
dname varchar(20) not null comment '名称',
dloc varchar(10) comment '所在地',
primary key (deptno)
);

alter table tb_dept add ddate date not null comment '成立日期';

-- 向部门表添加数据
insert into tb_dept values (10, '财务部', '成都',now());
insert into tb_dept (deptno, dname) values (20, '研发部');
insert into tb_dept (deptno, dname) values (30, '销售1部'), (40, '销售2部'), (50, '后勤部');

-- 删除数据（注意：一定要带上条件）
delete from tb_dept where deptno=50;

update tb_dept set dloc='深圳', ddate='2018-4-1' where deptno=30;
update tb_dept set dloc='成都', ddate='2018-4-3' where deptno=20 or deptno=40;

-- 查所有行所有列
select * from tb_dept;
-- 投影
select deptno, dname from tb_dept;
-- 别名
select deptno as 部门编号, dname as 部门名称 from tb_dept;
-- 筛选
select deptno, dname from tb_dept where dloc='深圳';

### Redis

#### Redis 是完全开源免费的，遵守BSD协议，是一个高性能的key-value数据库。
#### Redis 与其他 key - value 缓存产品有以下三个特点：
#### Redis支持数据的持久化，可以将内存中的数据保存在磁盘中，重启的时候可以再次加载进行使用。
#### Redis不仅仅支持简单的key-value类型的数据，同时还提供list，set，zset，hash等数据结构的存储。
#### Redis支持数据的备份，即master-slave模式的数据备份

连接redis客户端并解决中文乱码问题：
	redis-cli --raw


redis五大类型：string类型 hash list set zset

set p 1 设置 p的值为1
get p	获取p的值
incr p  整数加1
decr p  整数减1

字符串(string)：
增：
1.设置新值并覆盖原有值：
	set 键 键值
2.设置值，取值同时进行（取到的值是设置之前的值）：
	getset 键 键值
3.设置值，并制定存在时间，在存在时间内才能取到该值：
	setex 键 时间 键值
4.只有在该键不存在时，为该键设置新值：
	setnx 键 键值
5.批量设置键：
	mset 键 键值 键 键值 ...

删：
1.删除已有键：
	del 键

改：
1.若键不存在则新建并返回值的长度，若键存在则追加在键值末尾并返回追加后值得长度：
	append 键 键值
2.若值不存在则新建并将值设为0并+1返回加后的值，若存在则值+1返回加后的值：
	incr 键 
  注：incrby 键 值 和上面的区别在于加的值不是1而是这里面的值
  注：decrby 键 值 和incrby相反，这里是减
      decr 键 和incr相反，这里是减

3.用指定的字符串覆盖给定 key 所储存的字符串值，覆盖的位置从偏移量 offset+1（offset为数字） 开始：
  注：如果offset比当前key对应string还要长，那这个string后面就补0以达到offset。不存在的key被认为是空字符串
	setrange 键 offset 指定字符


查：
1.判断该键是否存在，存在则返回1，不存在则返回0：
	exists 键
2.获取键对应的值：
	get 键
3.获取指定键的值的字符长度（空字符串返回0）：
	strlen 键
4.查看指定键的剩余存活时间（秒数），若键存在但未设置时间返回-1，若键不存在则返回-2：
	ttl 键

哈希（hash）：
新增与赋值：hset 哈希名 键 键值 
获取所有：hgetall 哈希名
获取所有键：hkeys 哈希名
获取所有值：hvals 哈希名
删除键：hdel 哈希名 键

列表(list)：
左插入：lpush 列表名 键值
右插入: rpush 列表名 键值
左删除：lpop 列表名 
右删除：rpop 列表名 
查：lrange 列表名 开始位置 结束位置

集合(set)：
新增和赋值：sadd 集合名称 键值
查长度：scard 集合名称
删除（随机删除）：spop 集合名称
查看集合：smembers 集合名称

有序集合(zset)：
新增和赋值：zadd 集合名称 键值 排序时返回的值K
获取键值：zscore 集合名称 排序时返回的值K
从小到大排序（返回的是K）：zrange 键
从大到小排序（返回的是K）：zrevrange 键


获取页面源码：
1.requests
2.beautifulsoup bs4
3.scrapy

## Git

#### Git是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。
#### Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件。
#### Git 与常用的版本控制工具 CVS, Subversion 等不同，它采用了分布式版本库的方式，不必服务器端软件支持。


```python
# ENTAC
# 验证用户名
# 版本控制：
# 1.Subversion  必须有中央服务器
# 2.Git         可以先在本地同步d
# git --version                            确认是否安装Git
# git init                                 加入版本控制
# git add.                                 添加
# git status                               查看状态
# git commit -m '项目的初始版本'             提交并写原因
# git log                                  查看日志
# git reset HEAD^                          回到上一版本
# git reset 版本号                          回到对应版本号的版本
# git remote add origin 网址                给远端仓库建立联系
# git pull 网址                             与服务器上代码同步
# git push origin master                   往服务器上传代码
# git clone 网址                            下载项目
# git rm 文件名                              删除文件
# git check out 文件名                       重新拿出文件
# git branch                                查看分支
# git branch 名称                            建立分支
# git checkout 名称                          切换至该名称的分支
# git merge 分支名称                          合并分支到主线

=============================04-20=================================
# git checkout -b 名称 						创建分支并切换至该分支
# git branch -d 名称                        删除本地分支
# git push origin --delete 分支名           删除远端分支
# git commit -am ''                         合并add和commit操作						
# git diff 分支1  分支2                     比较分支之间的不同  
# git merge                                 合并
# git tag -a 版本号 -m '注解'               打tag标签
# git push origin 版本号                    推送版本号
# git push origin --delete tag 版本号       删除上传的版本号
# git tag -d 版本号                         删除本地版本号
# git tag                                   查看标签
# git stash                                 加入缓存(修改才行，新建文件不行)
# git stash list                            查看缓存
# git stash apply  缓存号					释放缓存直当前目录


ctrl + insert 复制
shift + insert 粘贴
创建秘钥  ssh-keygen t rsa -C 用户名

```

## Python连接MySQL和Redis进行用户名密码核对操作。


```python
# 登陆（redis + mysql）
# 1. pip install redis
# 2. 连接mysql
# 3. 连接redis
# 		import redis
# 		redis.Redis()
# 4. python xxx.py argv1 argv2
# 		import sys
#		sys.argv[1]
# 5. 访问redis, 判断输入的姓名和密码和redis中保存的用户名和密码是否匹配
# 6. 和redis不匹配，则查询mysql, select操作
# 7. mysql有查询结果的话，则更新到redis中，反之则没该用户
import sys

import pymysql
import redis

def con_mysql(sql):
	db = pymysql.connect(
		host = '这里填服务器或虚拟机IP',
		user = '服务器或虚拟机登录名',
		passwd = '服务器或虚拟机登陆密码',
		port = 3306,
		db = '数据库名称',
		charset = 'utf8')
	cursor = db.cursor()
	cursor.execute(sql)
	data = cursor.fetchall()
	db.close()
	return data

def con_redis(name, passwd):
	r = redis.Redis(host = 这里填服务器或虚拟机IP', port = 6379, password = 'redis数据库密码')
	r_name = r.hget('user', 'nam')
	r_passwd = r.hget('user', 'passwd')
	# 类型转换，将类型转换为utf8
	r_name = r_name.decode('utf8')
	r_passwd = r_passwd.decode('utf8')
	# print(r_name, r_passwd)
	if name == r_name and passwd == r_passwd:
		return True, '欢迎回来, %s!' % name
	else:
		return False, '用户名或密码错误！'


def main():
	# print(con_mysql('select * from stu'))
	# print(con_redis())

	# 获取传入的姓名和密码参数
	name = sys.argv[1]
	passwd = sys.argv[2]
	#传入redis中， 进行校验
	result = con_redis(name, passwd)
	# result[0] 返回第一个False结果
	if not result[0]:
		# 查询mysql数据库
		sql = '''select * from stu where nam = '%s'
		and passwd = '%s' ''' % (name, passwd)
		data = con_mysql(sql)
		if data:
			r = redis.Redis(host = '这里填服务器或虚拟机IP', port = 6379, password = 'redis数据库密码')
			r.hset('user', 'nam', name)
			r.hset('user', 'passwd', passwd)
			print('刷新redis， 登陆成功！') 
		else:
			print('用户名和密码错误！') 
	else:
		print('redis中数据正确，登陆成功！') 


if __name__ == '__main__':
	main()
```

#### 总结：经过2周的Linux和数据库相关的学习，学会了命令行去写各种命令来操作系统执行各种操作，感觉以前不会的感觉高大上的通过敲命令来执行的动作，现在也发现不再神秘。学会Linux的操作，架设自己的网页，在手机或者别人电脑上访问自己的主页也是别有一番欣喜在其中的。虽然现在做的还简单，但是最起码有了自己的网页，有了自己的数据库，虽然还没有联系起来，但是我相信在接下来的Djangode学习当中，会做的越来越好的。。。。
