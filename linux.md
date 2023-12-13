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
























