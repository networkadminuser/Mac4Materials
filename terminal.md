# 终端配置

　　本笔记的终端配置大体包括，安装iterm2+fish(或zsh)，用oh-my-fish(oh-my-zsh)配置美化。配置结束后能获得一个美观方便可翻墙的终端环境，然而，这些都并不是必须的，你可以用默认的终端默认的shell。

## 1. 修改主机名

>这一步真的没什么卵用，就是为了以后看着顺眼。

```sh
sudo scutil --set HostName yourhostname
```

## 2. 配置终端Proxy
　　终端的翻墙以本地有翻墙手段为前提，关于shadows的配置见本笔记的[配置翻墙-影梭](proxy-shaodowsocks.md)
### 2.1 安装Proxychains-ng

　　配置Proxychains-ng实现终端翻墙。  

```sh
brew install proxychains-ng  
```
### 2.2 关闭安全模式

　　但是，开机按住command+R，出现苹果后松开进入恢复模式。
恢复模式下，终端下执行：

```sh
csrutil enable --without debug
```
### 2.3 修改Proxychains设置
　　修改`/etc/proxychains.conf`使proxychains-ng走你的代理设置，以影梭为例，将该文件最后改为：

```
socks5 127.0.0.1 1080
```
## 3. 配置终端与shell
### 3.1 安装iTerm2

```sh
brew cask install iterm2-beta
```

### 3.2 安装fish/zsh
zsh的安装把相应的`fish`换为`zsh`即可。
```sh
brew install fish
```
　　用编辑器打开/etc/shells，比如

```sh
sudo vim /etc/shells
```
　　按 **i** 编辑，**shift+g** 跳到文件末尾，在末尾添加：

```sh
/usr/local/bin/fish
```
　　保存关闭，**Esc** 退出编辑模式，输入>`:wq`回车。  
　　在终端中执行：

```sh
chsh -s /usr/local/bin/fish
```
## 4. 安装oh-my-fish/oh-my-zsh
[oh-my-fish](https://github.com/oh-my-fish/oh-my-fish)
```sh
curl -L github.com/oh-my-fish/oh-my-fish/raw/master/bin/install | fish
```
[oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## 5. 设置语言环境变量
> 当系统环境为英语时很有必要

for fish `vim ~/.config/omf/init.fish`
```
set -g -x LANG en_GB.utf8
set -g -x  LC_ALL en_GB.UTF-8
```
for zsh `vim ~/.zshrc`
for bash `vim ~/.bash_profile`
```
export LANG=en_GB.utf8
export LC_ALL=en_GB.UTF-8
```
## 6. 启动loacte服务
　　终端下找文件命令，启用并重启后，locate '文件名'就能迅速找到文件。

```sh
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.locate.plist
```
