#影音工具
##安装mpv
安装mpv

```
pip install docutils
brew install mpv --with-bundle
```
找到mpv的安装位置  

```
locate mpv.app
```

如果想用spotlight打开的话：
>这意味着mpv.app占了两份空间，并且版本升级需要自行移除

```
sudo cp -a /usr/local/Cellar/mpv/0.16.0/mpv.app /Applications/mpv.app
```