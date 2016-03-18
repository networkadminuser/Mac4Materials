#终端配置

　　本笔记的终端配置大体包括，安装iterm2+zsh，用oh-my-zsh配置美化。配置结束后能获得一个美观方便可翻墙的终端环境，然而，这些都并不是必须的，你可以用默认的终端默认的shell，但是强烈建议你阅读以下注意事项再做决定。

* 关于zsh 

>　　zsh是一个极其强大的shell，无论是改变shell一成不变的配色，或者是丰富提示行内容，更不要说其卓越的纠错补全能力，都使得千万coder爱不释手。不过，最终使用与否在自己。  
　　如果没有安装zsh，那么笔记之后的内容与Mac默认的bash配置起来可能会有出入，因为之后的配置都是在zsh中进行的。  
　　假如安装了zsh却没配置，那么还不如不装。

* 关于iterm2

>　　iterm2是一个强大的终端，配色绚丽，多窗口...恕我玩得不转编不下去了。  
　　然而如果不iterm2的话——并没有什么影响。

* 关于翻墙 

>　　如果不翻墙，你懂的。  
　　如果当前Mac是EI Capitan之前的版本，那么终端翻墙根本不是什么事。  
　　但是EI Capitan（酋长石）的安全等级非常高，导致proxychains-ng都无法让终端翻墙，需要关闭一下Mac的安全设置。

##1. 修改主机名

　　这当然没什么卵用，请原谅我一生放荡不羁爱自由！

	sudo scutil --set HostName yourhostname

>　　这只是个在Linux和windows下形成的习(qiangpo)惯(zheng)，如果不改的话，Firefox浏览器的同步账户就会显示"[用户名]位于[主机名]的Firefox"，当主机名是一串意义不明朗或者不简洁的字母，便会令人心生不爽。

##2. 安装Homebrew
###2.1 Xcode Command Line Tools

　　安装苹果的基础开发环境，在终端输入一下指令，输入密码确认后，弹出图形化的界面提醒下载并安装，耐心等待安装完成即可。

	xcode-select --install
	
###2.2 Homebrew
　　EI Capitan（酋长石）默认终端是不能走系统代理的，因此，安装Homebrew（后简称brew）的前提，就是必须网络能够<font color="turquoise">**直接**</font>能连上其安装命令的网址。尝试在终端输入以下指令：

	ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

　　实际操作过程中网络可能碰到以下几种情形：  

*  可以连接github，没问题。   
*  不能连接github，试着安装brew，raw开头的网址未必连不上。
*  试完确实终端确实提示装不上，默哀一会，找个能连上的网。  

　　如果装不上brew，配置终端翻墙应该比找个网麻烦。

##3. 配置终端Proxy
###3.1 安装Proxychains-ng

　　配置Proxychains-ng实现终端翻墙。  

	brew install proxychains-ng  

###3.2 关闭安全模式

　　但是，开机按住command+R，出现苹果后松开进入恢复模式。
恢复模式下，终端下输入：

	csrutil enable --without debug

###3.3 修改Proxychains设置

##4. 配置终端与shell
###4.1 安装iTerm2

　　去iTerm2官网[Download](https://www.iterm2.com/downloads.html)上拖下test release,再拖到/应用程序即可。

###4.2 安装zsh

	brew install zsh

　　用编辑器打开/etc/shells，比如

	sudo vim /etc/shells

　　按<font color="orange"> **i** </font>编辑，<font color="orange">**shift+g** </font>跳到文件末尾，在末尾添加：

	/usr/local/bin/zsh

　　保存关闭，<font color="orange">**Esc** </font>退出编辑模式，输入<font color="orange">**:wq** </font>回车。  
　　在终端中执行以下命令：
##5. 启动loacte服务
　　终端下找文件命令，启用并重启后，locate '文件名'就能迅速找到文件。

	sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.locate.plist



