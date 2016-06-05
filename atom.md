# Atom的安装配置

## 1. 安装Atom
```sh
brew cask install atom
```

## 2. 配置
### 2.1 设置tab长度为4
`⌘,`进入配置    
`Tab的长度`或`Tab Length`设置为4

### 2.2 Markdown不自动删行末空格
```sh
atom ~/.atom/config.cson
```

在`".md.text":`后添加：

```sh
whitespace:
  removeTrailingWhitespace: false
```

保存。

## 3. 插件&主题

```
# run script
script

# python
autocomplete python

# latex
latex
language latex
pdf-view

# julia
language julia

# git
git-plus

# markdown
language markdwon
markdown writer

# 汉化
simplified-chinese-menu

# 主题
seti-ui
```
