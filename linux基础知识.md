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


