#MP三剑客的安装及FireWorks初始化
##1. Brew安装python
　　用brew安装python和python3

	brew install python python3

　　在pip安装函数库之前，必须首先确定python路径  

	which python

* 系统默认（错误）

		/usr/bin/python

* brew安装（正确）

		/usr/local/bin/python

　　当出现路径为系统默认时，请尝试以下命令后，重启终端软件，直到python路径显示正确。  

	brew doctor

##2. Pip安装Materiasl Project三剑客
　　用pip安装pymatgen,custodian,FireWorks.

	pip install pymatgen custodian fireworks

　　一般不会出什么问题，pip会自动安装依赖。当编程出现import失败的时候，利用pip安装相应的包就可以了，上述命令相当于最小安装。   
　　pip没有内置升级所有包的命令，可以使用以下命令升级全部：

	pip freeze --local | grep -v '^\-e' | cut -d = -f 1  | xargs pip install -U

　　一般刚刚装好的pip都不是最新版的，提示你升级pip不要管，升级了反而容易出问题。

##3. FireWorks数据库的初始化
