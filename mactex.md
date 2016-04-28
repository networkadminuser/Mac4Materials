#Mac环境下Latex的安装配置
　　Mac下Latex的环境配置方法是很多的，宏包有Texlive和MacTex(专门为Mac配置)，MacTex除了默认的完整版，还有精简版(Basic)，至于Tex编辑器更是不胜枚举。网上比较多的配置方案是SublimeText3+ Mactex+ Perview/ Skim，但是此处只介绍我自己试验过的emacs+ auctex+ Mactex +?，以及Atom+内置插件。  
　　相对而言，Atom+插件的较为简单且短暂试用并未发现什么问题，建议新手使用。
##1. MacTex+AUCTex+emacs
```sh
brew cask install mactex
```
　　参考[官方文档](https://tug.org/mactex/UpdatingForElCapitan.pdf)修改各个软件path，第一次更新Tex Live Utility需要翻墙，建议更新在终端中进行：

```sh
sudo tlmgr update --self --all
```
　　本人第一次在Tex Live Utility中进行更新，未备份，一下占用30G，原因不明，而且卸载MacTex非常麻烦。
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