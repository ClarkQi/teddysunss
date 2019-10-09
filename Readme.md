![Shadowsocks](https://github.com/teddysun/shadowsocks_install/raw/master/shadowsocks.png)
# Auto install Shadowsocks Server

shadowsocks.sh
===============
- Description: Auto Install Shadowsocks(Python) Server for CentOS/Debian/Ubuntu
- Intro: https://teddysun.com/342.html

shadowsocks-libev.sh
===============
- Description: Auto Install Shadowsocks(libev) Server for CentOS
- Intro: https://teddysun.com/357.html

shadowsocks-libev-debian.sh
===============
- Description: Auto Install Shadowsocks(libev) Server for Debian/Ubuntu
- Intro: https://teddysun.com/358.html

shadowsocks-go.sh
===============
- Description: Auto Install Shadowsocks(Go) Server for CentOS/Debian/Ubuntu
- Intro: https://teddysun.com/392.html

shadowsocks-crond.sh
===============
- Description: Check Shadowsocks(All version) Server is running or not, and start it if not running
- Intro: https://shadowsocks.be/6.html

shadowsocksR.sh
===============
- Description: Auto Install ShadowsocksR Server for CentOS/Debian/Ubuntu
- Intro: https://shadowsocks.be/9.html

shadowsocks-all.sh
==================
- Description: Auto Install Shadowsocks Server (all version) for CentOS/Debian/Ubuntu
- Intro: https://teddysun.com/486.html

haproxy.sh
===============
- Description: Auto Install haproxy for Shadowsocks Server
- Intro: https://shadowsocks.be/10.html

Copyright (C) 2014-2017 Teddysun

安装方法
===============
- wget --no-check-certificate -O shadowsocks-go.sh https://raw.githubusercontent.com/ClarkQi/teddysunss/master/shadowsocks-go.sh
- chmod +x shadowsocks-go.sh
- ./shadowsocks-go.sh 2>&1 | tee shadowsocks-go.log

安装完成后，脚本提示如下
====================
- Congratulations, your_shadowsocks_version install completed!
- Your Server IP        :your_server_ip
- Your Server Port      :your_server_port
- Your Password         :your_password
- Your Encryption Method:your_encryption_method

- Your QR Code: (For Shadowsocks Windows, OSX, Android and iOS clients)
-  ss://your_encryption_method:your_password@your_server_ip:your_server_port
- Your QR Code has been saved as a PNG file path:
-  your_path.png

- Welcome to visit:https://teddysun.com/486.html
- Enjoy it!

卸载方法
====================
- 若已安装多个版本，则卸载时也需多次运行（每次卸载一种）

- 使用root用户登录，运行以下命令：

- ./shadowsocks-go.sh uninstall

启动脚本
====================
- 启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。

- Shadowsocks-Python 版：
- /etc/init.d/shadowsocks-python start | stop | restart | status

- ShadowsocksR 版：
- /etc/init.d/shadowsocks-r start | stop | restart | status

- Shadowsocks-Go 版：
- /etc/init.d/shadowsocks-go start | stop | restart | status

- Shadowsocks-libev 版：
- /etc/init.d/shadowsocks-libev start | stop | restart | status

各版本默认配置文件
====================
- Shadowsocks-Python 版：
- /etc/shadowsocks-python/config.json

- ShadowsocksR 版：
- /etc/shadowsocks-r/config.json

- Shadowsocks-Go 版：
- /etc/shadowsocks-go/config.json
- /etc/shadowsocks/config.json

- Shadowsocks-libev 版：
- /etc/shadowsocks-libev/config.json

BBR一键安装 解除电信限速
=====================

文章摘自：https://www.thevultr.org/vultr_su_du_tai_man_zen_me_ban_an_zhuang_bbr_ti_su_ruan_jian_su_du_fei_qi_lai/

BBR一键安装包来自秋水逸冰（https://teddysun.com/489.html）。个人建议使用一台全新的vps安装比较好。在这里我用的vultr的纯净系统，未安装任何程序

打开你的putty，连上你的vultr的vps，输入下面三行代码：

    wget –no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
    chmod +x bbr.sh
    ./bbr.sh

一键安装安装BBR工具方法

之后点击任意按键，本一键包会自动更换内核和安装部署TCP BBR工具，大约二十分钟就可以了。

安装完成后，我们会看到”Info: The system needs to be restart. Do you want to reboot? [y/n]”，然后输入y回车，重启服务器。

参照以上办法基本没有问题。

如果一旦出现问题也可以使用下面代码检查

    uname -r

输入命令，查看是否有内核4.9.0内核，有就说明更换内核了。

或者输入这个：

    sysctl net.ipv4.tcp_available_congestion_control

输入命令，然后看是否有返回”net.ipv4.tcp_available_congestion_control = bbr cubic reno”

输入：

    lsmod | grep bbr

输入命令，是否看到BBR字样

这里我们是安装成功的。
