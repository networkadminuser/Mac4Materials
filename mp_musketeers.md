#MP三剑客的安装及FireWorks初始化
##1. Brew安装python
　　用brew安装python和python3

```sh
brew install python python3
```
　　在pip安装函数库之前，必须首先确定python路径  

```sh
which python
```
* 系统默认（错误）

```sh
/usr/bin/python
```
* brew安装（正确）

```
/usr/local/bin/python
```
　　当出现路径为系统默认时，请尝试以下命令后，重启终端软件，直到python路径显示正确。  

```sh
brew doctor
```
##2. Pip安装Materiasl Project三剑客
　　用pip安装pymatgen,custodian,FireWorks.

```sh
pip install pymatgen custodian fireworks
```
　　一般不会出什么问题，pip会自动安装依赖。当编程出现import失败的时候，利用pip安装相应的包就可以了，上述命令相当于最小安装。   
　　pip没有内置升级所有包的命令，可以使用以下命令升级全部：

```sh
pip freeze --local | grep -v '^\-e' | cut -d = -f 1  | xargs pip install -U
```
　　升级pip本身(注意顺序不可改)：

```sh
pip3 install --upgrade pip setuptools;
pip2 install --upgrade pip setuptools
```
##3. FireWorks数据库的初始化
