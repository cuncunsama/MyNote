# linux基础
## 环境变量文件
在Linux系统中，这些配置文件的执行顺序如下：

1. **`/etc/profile`**：
    - 位于系统级别，适用于所有用户。
    - 在用户登录时执行，用于设置全局环境变量和系统范围的配置。
    - 通常包含一些路径设置、全局环境变量和系统级别的别名。
    - 只在登录时执行一次。

2. **`~/.bash_profile`、`~/.bash_login`、`~/.profile`**：
    - 位于用户级别，适用于单个用户。
    - 在每次登录时执行其中一个，按照以下顺序：
        - `~/.bash_profile`
        - `~/.bash_login`
        - `~/.profile`
    - 主要用于定义与用户相关的环境变量和个人级别的配置。
    - 如果存在 `~/.bash_profile` 文件，一般还会执行 `~/.bashrc` 文件。

3. **`~/.bashrc`**：
    - 位于用户级别，适用于单个用户。
    - 在每次启动新的子shell（例如打开终端）时执行。
    - 主要用于定义与交互式命令行相关的配置，例如命令提示符、编辑器变量和用户级别的别名。
    - 不应该输出任何内容，以避免干扰非交互式的操作。

4. **`/etc/bash.bashrc`**：
    - 为每一个运行Bash shell的用户执行此文件。
    - 当Bash shell被打开时，该文件被读取。
    - 在Debian系统中，`/etc/bash.bashrc` 会在执行 `~/.bashrc` 之前被读取。

当启动一个**交互式非登录shell**时，Bash会读取并执行```/etc/bashrc```和```~/bashrc```。每次打开一个新的终端或启动一个新的子shell时，都会执行这两个文件中的命令。  
**系统级别**```/etc/bash.bashrc```   ```/etc/lprofile```  
**用户级别**```/.bashrc```  ```/.profile```
需要注意的是，/etc/bash.bashrc 在Debian系统中有一些特殊的行为。在Debian中，Bash被编译时使用了 -DSYS_BASHRC 选项，使得Bash在执行交互式非登录shell时会先读取 /etc/bash.bashrc，然后再读取 ~/.bashrc。因此，在Debian系统中，/etc/bash.bashrc 的作用类似于 /etc/profile 对于 ~/.bash_profile 的作用 。  

**ssh远程登录**  
/etc/bash.bashrc  
/etc/profile  
~/.bashrc  
~/.profile  
**ctrl+alt+t**  
/etc/bash.bashrc  
~/.bashrc  
**ctrl+alt+f1**  



当按下 `Ctrl+Alt+F1` 进入TTY1终端模式时，进入了一个**登录shell**。在TTY1中，你需要输入用户名和密码来登录系统。这是一个交互式登录shell，用于实时与用户交互，并从启动文件中读取命令和设置环境变量。

如果你在TTY1中执行命令，它会立即执行并返回结果。当你退出TTY1时，这个shell也会终止。

请注意，TTY1是一个文本控制台，不包含图形界面。如果你想返回到图形界面（X会话），可以按下 `Ctrl+Alt+F7`。




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















