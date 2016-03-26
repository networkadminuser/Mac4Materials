#Mac下LaTex
##1. 安装配置MacTex
```sh
brew cask install mactex
```
##2. 安装auctex
在~/.zshrc的$PATH后面追加MacTex的目录

```sh
export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Library/TeX/texbin"
```
重新载入.zshrc后，安装auctex

```sh
source ~/.zshrc;
brew install homebrew/tex/auctex
```
auctex的安装信息为：
>exmf files have been installed into:
  /usr/local/share/texmf

>You can add it to your TEXMFHOME using:
  sudo tlmgr conf texmf TEXMFHOME "~/Library/texmf:/usr/local/share/texmf"

>Emacs Lisp files have been installed to:
  /usr/local/share/emacs/site-lisp/auctex