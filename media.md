# 影音工具
## 1. mpv
### 安装

```sh
pip install docutils
brew install mpv --with-bundle
```
找到mpv的安装位置  

```sh
locate mpv.app
```

如果想用spotlight打开的话：
>这意味着mpv.app占了两份空间，并且版本升级需要自行移除

```
sudo cp -a /usr/local/Cellar/mpv/0.16.0/mpv.app /Applications/mpv.app
```

## 2. you-get

### 安装

```sh
pip3 install git+https://github.com/soimort/you-get.git@develop
```

经测试，develop更加稳定，建议直接装开发版。

### 使用(播放在线视频)

```sh
you-get -p mpv http://www.bilibili.com/video/av2012631/index_59.html
```

更多使用方法请参考[Offical Repo](https://github.com/soimort/you-get/wiki/%E4%B8%AD%E6%96%87%E8%AF%B4%E6%98%8E).
