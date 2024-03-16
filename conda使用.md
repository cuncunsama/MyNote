## 使用conda
```
~/.conda/envs  // 环境默认存储位置  
conda create -n myenv python=3.9  //创建环境  
conda create -n env-name [list of package]  
conda create --name myenv --prefix /path/to/myenv // 指定不同的位置  
conda create -n env-name --clone existing-env    // 通过克隆来复制一个环境  
conda activate myenv  // 激活conda环境		
conda deactivate  // 退出conda环境		 
conda remove --name myenv --all  // 删除conda环境		
conda env list  // 查看所有的conda环境及其路径 
conda list  // 列出conda环境中安装的所有包
conda info -s  
conda info -e // 等同于 conda env list
conda install package-name  // 安装包
conda remove package-name  // 卸载包
conda update package-name  // 更新包

```
### 查看conda安装包的位置
```
import module
print (module.__file__)
```

### 修改conda配置
```
conda配置文件： ~/condarc
conda config --set auto_activate_base false  // 取消自动进入base环境
conda config --show   // 查看conda的配置
conda config --show-sources    // 查看/home/suda401/.condarc
conda config --show channels   // 查看conda的channel
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/ //添加清华源  
conda config --remove channels channels 源名称或链接  
 
```
## 使用pip
```
pip list  
pip show packagename   // 可查看该包的位置
pip search packagename  // 搜索包  
pip install -e .    // 以可编辑模式安装package
pip install -r requirement.txt
```
### ~$ pip list --format=freeze  
```
package1==1.0.0
package2==2.0.0
package3==3.0.0
```
### 组合命令
~$ pip list --format=freeze | cut -d '=' -f 1 | xargs -I {} pip show {} | grep "Location"


## 使用Python
python -m site // 查看当前环境python搜索路径  
**sys.path**: 是一个环境变量，它包含了一系列目录名称，尝试导入一个模块时，python解释器会遍历sys.path的目录，直到找到相应的模块。  
**USER_BASE**
用户基础目录，存放用户级别的Python包的基本目录，用于存放通过pip install --user命令安装的包。  
这些包是特定于用户的，不需要管理员权限即可安装。  
**USER_SITE**
用户站点目录，这个用户基础目录下的一个子目录，用于存放用户级别的Python包。  
## 安装包的位置
**pip**  
~/.local/lib/python3.8/sit-packages/  // 基本环境  
~/.conda/envs/  // conda环境  
~/anaconda3/envs/    
**conda**  
~/anaconda3/lib/python3.11/site-packages/    
~/.envs/    
 
pip是python包的管理工具  
pip的镜像源： ~/.pip/pip.conf    
自定义pip的配置: pip config -v list    
查看包的信息：pip show pacagename    
查看已经安装的包：pip list  (Package Version Editable project location)    
以可编辑模式安装Python包：pip install -e /your/local/path    


















