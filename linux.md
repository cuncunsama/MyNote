### ssh远程图形化界面
```
ssh -X user@IP
sudo xauth add $(xauth list $DISPLAY)
```
### grep使用
```
sudo grep -nir "xxx" ./*
```
-n 显示行数 -i 忽略大小写 -r 递归查找目录内文件
### 挂载共享文件夹
```
sudo mount -t cifs //192.168.1.100/Share ~/share -o username="StrongYouYou",password="'"
```
### docker使用
```
docker images
docker ps -a
docker start CONTAINERID
docker attach CONTAINERID
```
### conda使用
```
conda info -e
conda env list
conda activate env
conda deactivate
conda config --show-sources

```
/home/suda401/.condarc
### xdg-open filepath
```
xdg-open ./ 打开当前文件夹
```
### pip
```
pip intall seaborn -i https://pypi.tuna.tsinghua.edu.cn/simple/
```
### vim
- vim 显示行号  
  esc + :set number
### shell内快速指令


### chmod, chown, chgrp
chmod 修改权限  
u-用户所有者  g-组用户  o-其他用户  a-所有用户
```
sudo chmod a+x 1
sudo chmod a-x 1
sudo chmod o+x 1
sudo chmod 777 1
sudo chmod -R 777 /dir/
```
chown 修改用户
```
sudo chown root 1  将文件1的owner修改为root
sudo chown suda401:root 1	
```
chgrp 修改组
```
sudo chgrp -R suda401 /home/suda401/1
```
/etc/passwd  
/etc/group  
组名：口令：组标识号：组内用户列表

### du
du -h --max-depth=0  
du -h --max-depth=1 文件名























