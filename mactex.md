# LaTex的安装配置  
　　Mac下Latex的环境配置方法是很多的，宏包有Texlive和MacTex(专门为Mac配置)，MacTex除了默认的完整版，还有精简版(Basic)，至于Tex编辑器更是不胜枚举。网上比较多的配置方案是SublimeText3+ Mactex+ Perview/ Skim，以及更为强大的Emacs+ AUCTex+ Mactex。  
　　最终发现Atom编辑器方便稳定，虽然可能没有上述两个编辑器强大，但是绝对够用，此处留下AUCTex的安装供参考，本人实际方案见[Atom配置](atom.md)。

## 1. MacTex安装
```sh
brew cask install mactex
```
　　参考[官方文档](https://tug.org/mactex/UpdatingForElCapitan.pdf)修改各个软件path，第一次更新Tex Live Utility需要翻墙，建议更新在终端中进行：

```sh
sudo tlmgr update --self --all
```
　　本人第一次在Tex Live Utility中进行更新，未备份，一下占用30G，原因不明，而且卸载MacTex非常麻烦。

## 2. AUCTex安装
在~/.zshrc的$PATH后面追加MacTex的目录

```sh
export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Library/TeX/texbin"
```
重新载入.zshrc后，安装auctex

```sh
source ~/.zshrc;
brew install homebrew/tex/auctex
```
AUCTex的安装信息为：
>exmf files have been installed into:
  /usr/local/share/texmf

>You can add it to your TEXMFHOME using:
  sudo tlmgr conf texmf TEXMFHOME "~/Library/texmf:/usr/local/share/texmf"

>Emacs Lisp files have been installed to:
  /usr/local/share/emacs/site-lisp/auctex
