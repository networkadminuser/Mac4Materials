#Ssh本地转发(尚未自动)
##1. Expect脚本
pi\_ssh\_local\_forwarding.exp

```
#!/usr/bin/env expect -f
set localPort	your_local_port
set targetHost	target_server_ip
set targetPort	target_server_port
set transHost	transfer_server_ip
set transPort	transfer_server_port
set transUsr	transfer_server_username
set transPasswd	transfer_server_password
set timeout -1 
spawn ssh -L $localPort:$transHost:$target_server_port -p $transPort $transUsr@$
expect {
	"*yes/no" { send "yes\r"; exp_continue}
	"password:" { send "$transPasswd\r"}
}
interact
#expect eof
```
##2. plist

splist

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>Disabled</key>
	<false/>
	<key>KeepAlive</key>
	<true/>
	<key>Label</key>
	<string>com.onboot.sshd</string>
	<key>ProgramArguments</key>
	<array>
	<string>/usr/local/bin/sshd</string>
	</array>
	<key>RunAtLoad</key>
	<true/>
	<key>StandardOutPath</key>
	<string>/var/log/sshd-out.log</string>
	<key>StandardErrorPath</key>
	<string>/var/log/sshd-err.log</string>
</dict>
</plist>
```
