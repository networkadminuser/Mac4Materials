#Mpenv安装配置

>本笔记基于Mpenv的sjtu分支，仅适合用于在sjtu的Pi上进行MPenv的安装配置。

##第一部分 在Pi上安装管理员环境(admin_env)并申请个人环境名称
>注意：一个账户(也就是一个用户名下)只需新建一次管理员环境，在该用户名下，可以新建很多个人环境。安装前请咨询hongzhu老师，来确认你的账户下是否已经安装完成管理员环境。如果已经安装完毕，请直接进行第一部分最后一步，向hongzhu老师申请环境名。

###1. ssh登陆Pi
###2. 加载必要modules
```
unset MODULEPATH
module use /lustre/usr/modulefiles/pi
module load anaconda/2
```
###3. 建立管理员虚拟环境并下载安装所需文件
####3.1 建立管理员虚拟环境(admin_env)
```
cd ~
mkdir admin_env
conda create --name admin_env numpy scipy matplotlib
source activate admin_env
```
####3.2 克隆Mpenv的sjtu分支
```
cd admin_env
git clone https://github.com/materialsproject/MPenv.git
cd MPenv
git checkout sjtu
git pull
```
>**注意:**  
>当这一步完成后，如退出登陆，重新登陆在以后步骤前，应运行如下命令：  

>```
>unset MODULEPATH
>module use /lustre/usr/modulefiles/pi
>module load anaconda/2
>source activate admin_env
>```

####3.3 复制VASP二进制文件

```
cd ~
mkdir VASP
cd VASP
mkdir vasp.5.4.1.05Feb16
scp -r umjzhh@202.120.58.229:/lustre/home/umjzhh/keliu/VASP_unpacked/vasp.5.4.1.05Feb16/bin/ ~/VASP/vasp.5.4.1.05Feb16/bin/
```
###4. 修改Mpenv源码并安装
```
vim ~/admin_env/MPenv/MPenv/mpenv_static/BASH_template.txt
```
将第13行改为：  

```
export PATH=$HOME/VASP/vasp.5.4.1.05Feb16/bin:$PATH
```
保存 BASH\_template.txt。  
安装Mpenv:

```
cd ~/admin_env/MPenv/
python setup.py develop
```
###5. 向hongzhu申请你个人用的环境名
#第二部分 在Pi上安装自己的虚拟环境

##1. 上传并解压压缩包
当你收到名为“环境名_files.tar.gz”的压缩包，即可在本地通过`scp`命令将其传至你在Pi的`$HOME`目录。

```
scp ~/Downloads/压缩包名 Pi用户名@Pi主机IP:~
```
登陆Pi，解压：

```
tar -xvzf 环境名_files.tar.gz
```
##2. 加载必要modules并激活管理员环境(admin_env)
```
unset MODULEPATH
module use /lustre/usr/modulefiles/pi
module load anaconda/2
source activate admin_env
```
##3. 安装你自己的环境
>注意1:  
>环境名与压缩包名称相对应，压缩包名为“环境名_files.tar.gz”。  
>注意2:  
>如果你的用户的`$HOME`下没有 `.bashrc.ext`, 那么就在该处新建`.bashrc.ext`空文件。

```
mpenv --conda --https 环境名
```
>注意3:  
>安装期间，因各种原因终止，则删除`~/环境名`文件夹，并清空`.bashrc.ext`你环境名所对应的内容，并重新尝试。

等待成功，之后激活你的环境以测试：

```
source activate 环境名/virtenv_环境名
```
或者，你可以通过修改`.bashrc.ext`来使得`usr_环境名`命令回复正常。

`use_none`退出虚拟环境。

#第三部分
复制VASP\_PSP文件夹，加到`.bashrc.ext`的最后

```
scp -r umjzhh@202.120.58.229:/lustre/home/umjzhh/VASP_PSP ~/
```