---
layout: post
category: "Git"
title:  "Git笔记"
tags: [Git]
---

##Git笔记
###一、git基础知识
####1.Git系统与其它系统的区别：
	(1)直接记录快照，而非差异比较: git只关心文件数据的整体是否发生变化，而大多数其他系统则只关心文件内容的具体差异。
	(2)近乎所有操作都是本地执行: 在git中的绝大多数操作都只需要访问本地文件和资源，不用联网。
	(3)时刻保持数据完整性：git在保存之前，进行校验和计算，并将结果作为数据的唯一标识。
	(3)多数操作仅添加数据：常用的git操作大多属于添加操作。在 Git 里，一旦提交快照之后就完全不用担心丢失数据。

####2.Git系统文件的三种状态：
	(1)已提交表示该文件已经被安全地保存在本地数据库中了；
	(2)已修改表示修改了某个文件，但还没有提交保存；
	(3)已暂存表示把已修改的文件放在下次提交时要保存的清单中。

####3.	
我们可以从文件所处的位置来判断状态：如果是 Git 目录中保存着的
特定版本文件，就属于已提交状态；如果作了修改并已放入暂存区域，就属于已暂存状态；如果自上次取出后，作了修改但还没有放到暂存区域，就是已修改状态。
####4.	Git的安装。
####5.	初次运行git前的配置：
三个工作环境变量：
a./etc/gitconfig(系统目录下):使用git config时，加--system;

b.~/.gitconfig（用户目录下）:使用git config时，加--global;

c.当前项目的git目录中的配置文件（.git/config），.git/config中的目录会覆盖/etc/gitconfig中的目录。

d.配置用户信息 ：$git config --global user.name “用户名”；
				 $git config --global user.email 邮箱名。
e.设置默认的文本编辑器：$git config --global core.editor 文本编辑器名（emacs、vi、vim）。

f.设置合并冲突时使用的差异分析工具：
	$git config --global merge.tool 差异分析工具名（eg.vimdiff）.

g.查看配置信息：$git config --list
查看不同用户名的配置：$git config user.name 用户名

h.获取各式工具的帮助：$git help <verb>

					  $git <verb> --help
					  $man git-<verb>
	还可以到FreenodeIRC（irc.freenode.net）服务器上的#git或#github寻求帮助。

##二、git的基本操作
###1.取得项目中的git仓库：

方法一：在工作目录中初始化新仓库：到此项目所在的目录 执行$git init

方法二：从已有的git仓库中拷贝一个新的镜像仓库：$git clone [url] [新的工程名](eg. $git clone git://github.com/schacon/grit.git)。
	
注：git://表示git协议，也可以用http(s)://或user@server:/path.git(表示SSH传输协议)。
###2.记录每次更新到仓库：
	未完待续…

