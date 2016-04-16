#配置翻墙-影梭
　　本部分内容主要通过配置shadowsocksX来方便平时的浏览以及homebrew使用，至于shadowsocks的部署则不在其范围之内，请自行寻找教程学习。
##1. shadowscoksX的安装
###1.1 shadowsocksX的临时开启
　　shadowsocksX是一款图形界面的shadowsocks(影梭)客户端，安装简易，配置与其他平台相仿。  
　　首先其下载安装时需要翻墙的，于是最好在可以翻墙的环境[下载](https://sourceforge.net/projects/shadowsocksgui/files/latest/download?source=files)好，再通过U盘或邮件形式发送到本地，暂时不要安装，直接在dmg镜像中运行并配置。
###1.2 shadowsocksX的安装
　　开启你的终端翻墙(方法见[终端的配置](terminal.md#2-配置终端proxy))，可以用proxychains-ng也可以用dmg镜像里的影梭开全局。利用Homebrew-cask正式安装。

```sh
brew cask install shadowsocksx
```
　　然后就可以进行正常的配置使用了，dmg镜像中的临时影梭关闭，弹出dmg即可。
##2. 浏览器翻墙插件
* [SwitchyOmega](https://chrome.google.com/webstore/detail/proxy-switchyomega/padekgcemlokbadohgkifijomclgjgif) for Chrome  
* [Pan](https://addons.mozilla.org/zh-CN/firefox/addon/pan/) for firefox  

　　建议不要重点配置浏览器翻墙规则，我对浏览器插件的定位是，切换不同的翻墙模式，GFW-list以外的规则还是在user-rule里头写上比较好。
##3. 影梭用户规则
　　shadowsocksX菜单上就有编辑用户规则的选项，点选后`user-rule.txt`即用户规则。为了让用户规则同步，最好将其放到云存储中，再建立软链接，一劳永逸。
(以我的Dropbox为例，位于`~/Documents/Dropbox`)

```sh
mkdir -p ~/Documents/Dropbox/应用/shadowsocks
mv ~/.ShadowsocksX/user-rule.txt ~/Documents/Dropbox/应用/shadowsocks
ln -s ~/Documents/Dropbox/应用/shadowsocks/user-rule.txt ~/.ShadowsocksX
```
　　以下是我的用户规则内容，会不断更新

```
! Put user rules line by line in this file.
! See https://adblockplus.org/en/filter-cheatsheet

#国内电商
@@||taobao.com
@@||jd.com

#科研
@@||webofknowledge.com

#开发
||github.com
||raw.githubusercontent.com
||atom.io
||xda-developers.com

#云存储
||dropbox.com
||dropboxusercontent.com
||dropboxstatic.com

#翻墙
||digitalocean.com

#论坛
||v2ex.com

#edu
||dspace.mit.edu
```

##4. app的启动
　　如果有app需要翻墙启动，并且shadowsocks的全局模式不好使的话，需要这样利用proxychains-ng启动app,以Dropbox为例：

```sh
proxychains4 open /opt/homebrew-cask/Caskroom/dropbox/latest/Dropbox.app
```