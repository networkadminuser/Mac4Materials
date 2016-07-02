# 软件管理器
## 1.Homebrew的安装
### 1.1 Xcode Command Line Tools

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
brew cleanup		brew清理
brew cask install	cask安装软件包
brew cask remove	cask卸载软件包
brew cask list		显示cask软件包
brew cask cleanup	清理cask下载的临时文件
brew cask list | xargs brew cask install --force
					升级cask软件
```
##3. Homebrew-cask常用软件
　　由于Homebrew本身安装的软件大多需要配置，如emacs或者mpv等，会单独列出，而Homebrew-cask装的软件大多无需配置，因此将本人现在cask软件列在下方，如需要配置，也会在后面单独列出。

```
# 系统必备
alfred				# 神器不解释
iterm2-beta			# 强大终端
squirrel			# 鼠须管，神级输入法
mounty				# 挂载ntfs格式U盘、硬盘
cleanmymac			# 卸载软件，清理垃圾
flash				# 浏览器flash插件


# Mac Plus
rcdefaultapp		# 设定文件/链接默认打开方式
dictunifier			# 转化其他词典为Mac内置格式
scroll-reverser		# 可以设置鼠标滚轮反向
qlcolorcode			# 预览(preview)高亮支持
qlmarkdown			# preview markdown支持
quicklook-csv		# preview csv支持
quicklook-json		# preview json支持

# 开发工具
atom				# 神编辑器不解释
beyond-compare		# 代码比较
robomongo			# MongoDB客户端
filezilla			# FTP免费客户端
xquartz				# X11支持
mactex				# mac下Latex宏包
detexify			# Latex神器，手画匹配latex代码

# 翻墙浏览
shadowsocksx		# 影梭客户端
google-chrome-dev	# chrome浏览器

# 编辑阅读
microsoft-office	# 微软office
skim				# pdf阅读器
calibre				# 转格式, kindle好帮手

# 同步云盘
dropbox				# dropbox客户端 

# 其他
steam				# 放弃解释
zotero				# 文献管理
upeditor			# 中银safari插件

# 中国特色
thunder				# 下不动，你就开会员
aliwangwang			# 剁手初段
```
## 4.Homebrew-cask 重新安装

```sh
brew uninstall --force brew-cask; brew untap phinze/cask; brew update; brew cleanup; brew cask cleanup
```
