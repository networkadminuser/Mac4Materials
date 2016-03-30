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

>这一步真的没什么卵用，就是为了以后看着顺眼。

```sh
sudo scutil --set HostName yourhostname
```

##2. 配置终端Proxy
　　终端的翻墙以本地有翻墙手段为前提，关于shadows的配置见本笔记的[配置翻墙-影梭](proxy-shaodowsocks.md)
###2.1 安装Proxychains-ng

　　配置Proxychains-ng实现终端翻墙。  

```sh
brew install proxychains-ng  
```
###2.2 关闭安全模式

　　但是，开机按住command+R，出现苹果后松开进入恢复模式。
恢复模式下，终端下执行：

```sh
csrutil enable --without debug
```
###2.3 修改Proxychains设置
　　修改`/etc/proxychains.conf`使proxychains-ng走你的代理设置，以影梭为例，将该文件最后改为：

```
socks5 127.0.0.1 1080
```
##3. 配置终端与shell
###3.1 安装iTerm2

```sh
brew cask install iterm2-beta
```

###3.2 安装zsh
```sh
brew install zsh
```
　　用编辑器打开/etc/shells，比如

```sh
sudo vim /etc/shells
```
　　按<font color="orange"> **i** </font>编辑，<font color="orange">**shift+g** </font>跳到文件末尾，在末尾添加：

```sh
/usr/local/bin/zsh
```
　　保存关闭，<font color="orange">**Esc** </font>退出编辑模式，输入<font color="orange">**:wq** </font>回车。  
　　在终端中执行：

```sh
chsh -s /usr/local/bin/zsh
```
##4. 安装oh-my-zsh

##5. 启动loacte服务
　　终端下找文件命令，启用并重启后，locate '文件名'就能迅速找到文件。

```sh
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.locate.plist
```


