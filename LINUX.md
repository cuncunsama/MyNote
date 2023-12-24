# LinuxCmd
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
### ubuntu访问windows的共享文件夹
```
smb://192.168.1.100
User: StrongYouYou
Passwd: '
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

#删除环境
conda remove -n envname --all 
```
/home/suda401/.condarc
### xdg-open filepath
```
xdg-open ./ 打开当前文件夹
```
### pip
~/.pip/pip.conf  
```
pip intall seaborn -i https://pypi.tuna.tsinghua.edu.cn/simple/
-i http://pypi.douban.com/simple --trusted-host pypi.douban.com
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

### du查看文件夹的占用空间
du -h --max-depth=0  
du -h --max-depth=1 文件名

### git使用
git status


### linux给edge设置代理
修改/usr/share/applications/microsoft-edge-dev.desktop  
```
Exec=/usr/bin/microsoft-edge-dev --proxy-server="127.0.0.1:7890"
```
### 防火墙ufw使用
查看防火墙状态  
```
sudo ufw status
```  
打开防火墙  
```
sudo ufw enable
```  
关闭防火墙  
```
sudo ufw disable
```
# Steps
### generative-models
```
cd generative-models/
source .pt2/bin/activate
PYTHONPATH=$PWD streamlit run scripts/demo/sampling.py --server.port 7860

```
- Put weights in /checkpoints/

### stable-webui
```
conda activate sdwebui
cd ~/Codebase/stable-diffusion-webui
./webui.sh
```

### FasterNet
```
cd ~/Codebase/FasterNet
conda activate fasternet

```

















