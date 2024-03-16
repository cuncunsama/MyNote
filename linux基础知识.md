# linux基础
## 环境变量文件
**系统级别，对所有用户有效**   
**/etc/profile**	会调用 /etc/bash.bashrc, 系统全局环境变量设定，修改后需要重新登录或者source   
**/etc/bash.bashrc** 重新打开一个shell就可生效  

**用户私有环境变量设定，只对当前用户有效**  
**/home/user/.profile** 	  for logn shells，会调用 ~/.bashrc 需要重新登录才能生效  
**/home/user/.bashrc**	   for non-login shells 每次打开新的shell时，会执行该文件  

## source 和 . 和 ./ 和 sh 执行文件时的区别 
1. source 和 . 执行文件是在当前shell中进行，会影响到当前shell的环境  
2. sh 执行文件是在子shell中进行的，如果脚本中设置了环境变量，即使PATH改变了也不会反应到当前环境中  
3. ./ 是执行所有可执行程序的一种方式，./的执行也是在当前shell的子shel中运行，同样不会影响当前shell的环境  

当启动一个**交互式非登录shell**时，Bash会读取并执行```/etc/bashrc```和```~/bashrc```。每次打开一个新的终端或启动一个新的子shell时，都会执行这两个文件中的命令。  
```/etc/bash.bashrc``` **系统级别**  
```/.bashrc```	**用户级别**  

$0 脚本的名字  
$1 传入脚本的第一个参数  
$2 传入脚本的第二个参数  
$# 传入脚本的参数个数

自定义~/.bashrc文件  
	google-p = google-chrome-stable --proxy-server="127.0.0.1:7890"  
	edge-p = microsoft-edge-dev --proxy-server="127.0.0.1:7890"  

## 查看电脑和系统信息


## 查找文件
### find  
```
指定目录，名中带cuda
~$ find / -type d -name cuda 
指定文件，名中带cuda
~$ find / -type f -name cuda
```
### grep
查找文件内容中包含固定字符串的文件    
```
~$ grep "搜索内容" "搜索路径"
~$ grep "固定字符串" /path/to/directory/*
递归在所有子目录中搜索，并且只输出文件名
~$ grep -rl "String" /path/to/dir
只看文本文件，使用-I排除二进制文件
~$ grep -rIl "String" /path/to/dir
```
```
ls | grep -v "\.png$" 屏蔽输出中 .png 结尾的文件 \. 表示 . ，\ 是反义符号
```
### locate
在数据库中搜索，所以速度很快，添加或删除文件后使用```updatedb```更新数据库后在进行搜索

### which
查看可执行文件的位置，在```PATH```变量指定的路径中搜索，返回第一个搜索结果  
```
~$ which ls
```

### whereis
用于定位二进制文件、源代码文件和手册页面的路径 /bin /sbin /usr/bin /usr/sbin /usr/local/bin /usr/local/sbin















