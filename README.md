# Mac4MaterilsReserach
用于第一性原理材料研究的Mac的配置笔记

　　入手的第一台MacBook,主要用于Materials Project的配置和使用，随时记下自己安装配置的中的遇到的问题以及解决方案，以防忘记。鉴于本人半路出家，水平泛泛，如大家有更好的方案，敬请不吝斧正。

## 终端配置  
　　对于需要用终端完成许多工作的系统来说，配置好用的终端是十分酸爽的。相比终端的重要性而言，这部分内容还显得十分单薄，后续会随着本人的使用和熟悉继续补充。  
　　终端配置采用zsh+iterm2，zsh的配置采用oh-my-zsh。  
　　由于主要计算完成于学校的服务器，Ip限制导致ssh及ftp的连接较为麻烦，所以设置了本地ssh端口转发，现尚未完全实现自动化。

* [终端的配置](terminal.md)
* [本地ssh转发](ssh_forward.md)

　　To do list

- iterm2快捷键  
- 双层ssh服务器，ftp的实现(成熟后，合并到ssh转发种)
- alias设置

## MP环境  
　　Materials Project是一个在超级计算机上实现第一性原理的半自动计算的开源项目（当然，个人认为这个半自动是谦词，我就想问一句啥叫全自动，全自动洗衣机不用放衣服么？）。它包含了[一系列python函数库](https://github.com/materialsproject)，和一套[Web App](https://materialsproject.org/)。  
　　本笔记中主要涉及本地python函数库的配置。  

* [MP三剑客的安装及FireWorks初始化](mp_musketeers.md)
* pymatgen
* [Mpenv安装配置](mpenv.md)

　　To do list

* VASP(还没来得及安装)

## 编辑工具  
　　所谓工欲善其事，必先利其器，毕竟面对代码的时间应该更在终端之上，如果担心自己眼瘸手残，为何不上编辑器！  
　　本笔记暂时只涉及emacs的基本配置，或许慢慢会换成atom了，MacTex的配置也是刚刚开了个头。  
　　现在Org-ref模式还根本不会使，不然也就不用Markdown来写这个笔记了，毕竟Markdown的学习成本近乎没有。在Org-ref弄懂了马上加上，它和Markdown一样语法简单，但是还能引用参考文献，我看了视频感觉，基本可以代替Latex应付常规的期刊（不过话说过来期刊也是要求tex文件啊，暂时还没有要org文件的）。  
　　接下来准备想办法把Materials Project里头的函数加到python的自动补全里头，还没有预估难度和时间。  
　　再进一步，我想能不能给Dash里加上Materials Project的 documentation，我觉得我应该是想多了！

* [emacs](emacs.md)  
* MacTex

　　To do list

- emacs-org-ref
- emacs-Materials_Project
- Dash-Materials_Project

## 影音工具
　　[mpv](media.md)