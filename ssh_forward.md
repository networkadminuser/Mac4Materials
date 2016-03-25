#Ssh本地转发(尚未自动)
##1. Expect脚本
pi_ftp_local_forwarding.exp

	#!/usr/bin/env expect
	set timeout 10
	spawn ssh -L 8891:202.120.1.119:21 -p 222 zhuh@202.120.1.119
	expect {
	    "*yes/no" { send "yes\r"; exp_continue}
	    "password:" { send "Zhyme2@2015\r"}
	}
	interact {
	timeout 600 { send " "}
	}

##2. plist

splist

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
