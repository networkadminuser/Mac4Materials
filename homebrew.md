#软件管理器
##1.Homebrew的安装
###1.1 Xcode Command Line Tools

　　安装苹果的基础开发环境，在终端输入一下指令，输入密码确认后，弹出图形化的界面提醒下载并安装，耐心等待安装完成即可。

```sh
xcode-select --install
```
###1.2 Homebrew
　　EI Capitan（酋长石）默认终端是不能走系统代理的，因此，安装Homebrew（的前提，就是必须网络能够<font color="turquoise">**直接**</font>能连上其安装命令的网址。尝试在终端输入以下指令：

```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
　　如果确实无法连接，建议更换网络环境。
##2. Homebrew的常用指令
```sh
brew install 		安装
brew uninstall 		卸载
brew update			升级brew
brew upgrade		升级软件包
brew search			寻找软件包(包含caks等)
brew list			显示已装软件包(不包含cask等)
brew info			显示安装包信息
brew doctor			修复系统使homebrew正常工作
brew cask install	cask安装软件包
brew cask remove	cask卸载软件包
brew cask list		显示cask软件包
brew cask cleanup	清理cask下载的临时文件
```
##3. Homebrew-cask常用软件
　　由于Homebrew本身安装的软件大多需要配置，如emacs或者mpv等，会单独列出，而Homebrew-cask装的软件大多无需配置，因此将本人现在cask软件列在下方，如需要配置，也会在后面单独列出。

```
#系统必备
alfred				#神器不解释
iterm2-beta			#强大终端
mounty				#挂载ntfs格式U盘、硬盘
cleanmymac			#卸载软件，清理垃圾
flash				#浏览器flash插件

#翻墙浏览
shadowsocksx		#影梭客户端
google-chrome-dev	#chrome浏览器
xmarks-safari		#多浏览器书签同步

#编辑阅读
microsoft-office	#微软office
mactex				#mac下Latex宏包
macdown				#markdown编辑器，支持语法高亮
skim				#pdf阅读器
diffmerge			#比较文件夹、文件内容

#同步云盘
dropbox				#dropbox客户端 
baiducloud			#国产毒瘤，没有bcould,实属无奈 

#其他
steam				#放弃解释
zotero				#文献管理
sogouinput			#比百度输入法好，知乎水军骗我
```