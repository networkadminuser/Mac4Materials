# DigitalOcean影梭的配置

## 注册验证
注册DigitalOcean，至少充5美金激活，支持paypal不支持Alipay.

## 建立Droplet
小内存建议用32位系统，Debian兼容性更好。

## 安装Shadowsocks

```sh
apt-get update;
apt-get upgrade;
apt-get install python-pip vim;
pip install shadowsocks;
vim /etc/shadowsocks.json
```

设置配置文件

```json
{
  "server":"0.0.0.0",
  "server_port":443,
  "local_port":1080,
  "password":"yourpassword",
  "timeout":600,
  "method":"rc4-md5"
}
```

```vim
:wq #保存
```

配置shadowsocks自启动

```sh
vim /etc/rc.local
```
在`exit 0`之前添加

```
ssserver -c /etc/shadowsocks.json
```
