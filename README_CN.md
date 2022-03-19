<h1 align="center">
  <img src="https://github.com/Dreamacro/clash/raw/master/docs/logo.png" alt="Clash" width="200">
  <br>ShellClash<br>
</h1>


  <p align="center">
	<a target="_blank" href="https://github.com/Dreamacro/clash/releases">
    <img src="https://img.shields.io/github/release/Dreamacro/Clash.svg?style=flat-square&label=Clash">
  </a>
  <a target="_blank" href="https://github.com/juewuy/ShellClash/releases">
    <img src="https://img.shields.io/github/release/juewuy/ShellClash.svg?style=flat-square&label=ShellClash&colorB=green">
  </a>
</p>

中文 | [English](README.md) 

功能简介：
--

~通过管理脚本在Shell环境下便捷使用[Clash](https://github.com/Dreamacro/clash)<br>
~支持在Shell环境下管理[Clash各种功能](https://lancellc.gitbook.io/clash)<br>
~支持在线导入[Clash](https://github.com/Dreamacro/clash)支持的分享、订阅及配置链接<br>~支持配置定时任务，支持配置文件定时更新<br>~支持在线安装及使用本地网页面板管理内置规则<br>
~支持路由模式、本机模式等多种模式切换<br>~支持在线更新<br>

设备支持：
--

~支持各种基于OpenWrt或使用OpenWrt二次定制开发的路由器设备<br>
~支持各种运行标准Linux系统（如Debian/CenOS/Armbian等）的设备<br>~兼容Padavan固件（保守模式）、潘多拉固件以及华硕/梅林固件<br>~兼容各类使用Linux内核定制开发的各类型设备<br>

——————————<br>
~更多设备支持，请提issue或前往TG群反馈（需提供设备名称及运行uname -a返回的设备核心信息）<br>

使用方式：
--
~确认路由器设备已经开启SSH并获取root权限（带GUI桌面的Linux设备可使用自带终端安装）<br>
~使用SSH连接工具（如putty，JuiceSSH，系统自带终端等）路由器或Linux设备的SSH管理界面或终端界面，并切换到root用户<br>
~确认设备已经安装curl或者wget下载工具。**如未安装**，LInux设备请[参考此处](https://www.howtoing.com/install-curl-in-linux)安装curl，基于OpenWrt（小米官方系统、潘多拉、高恪等）的设备请使用如下命令安装curl：<br>

```shell
opkg update && opkg install curl #如已安装请忽略
```

~之后在SSH界面执行如下安装命令，并按照后续提示完成安装<br>

~**使用curl安装**：<br>

```Shell
#by fastgit.org
export url='https://raw.fastgit.org/juewuy/ShellClash/master' && sh -c "$(curl -kfsSl $url/install.sh)" && source /etc/profile &> /dev/null
#ghproxy.com加速
export url='https://ghproxy.com/https://raw.githubusercontent.com/juewuy/ShellClash/master' && sh -c "$(curl -kfsSl $url/install.sh)" && source /etc/profile &> /dev/null
#github-CDN源
export url='https://raw.githubusercontent.com/juewuy/ShellClash/master' && sh -c "$(curl -kfsSl $url/install.sh)" && source /etc/profile &> /dev/null
#jsdelivrCDN源
export url='https://cdn.jsdelivr.net/gh/juewuy/ShellClash@master' && sh -c "$(curl -kfsSl $url/install.sh)" && source /etc/profile &> /dev/null
```

~**使用wget安装**：<br>

```sh
#jsdelivrCDN源
export url='https://cdn.jsdelivr.net/gh/juewuy/ShellClash@master' && wget -q --no-check-certificate -O /tmp/install.sh $url/install.sh  && sh /tmp/install.sh && source /etc/profile &> /dev/null
```

~**使用低版本wget（提示不支持https）安装**：<br>

```sh
#作者私人http源
export url='http://shellclash.ga/' && wget -q -O /tmp/install.sh $url/install.sh  && sh /tmp/install.sh && source /etc/profile &> /dev/null
```

~**非root用户安装后**请额外执行以下命令以读取环境变量：<br>

```shell
source ~/.bashrc &> /dev/null
```

~安装完成管理脚本后，执行如下命令以**运行管理脚本**<br>

```Shell
clash #正常模式运行
clash -h #脚本帮助及说明
clash -u #卸载脚本
clash -t #测试模式运行
```

~**DOCKER环境下安装：**<br>

请参考https://github.com/echvoyager/shellclash_docker

~**运行时的额外依赖**：<br>

`大部分的设备/系统都已经预装了以下的大部分依赖，使用时如无影响可以无视之`

```sh
bash/ash		必须		全部缺少时无法安装及运行脚本
curl/wget		必须		全部缺少时无法在线安装及更新，无法使用节点保存功能
iptables		重要		缺少时只能使用纯净模式
systemd/rc.common	一般		全部缺少时只能使用保守模式
iptables-mod-nat	一般		缺少时无法使用redir模式，混合模式
ip6tables-mod-nat	较低		缺少时影响redir模式，混合模式对ipv6的支持
crontab			较低		缺少时无法启用定时任务功能
net-tools		极低		缺少时无法正常检测端口占用
ubus/iproute-doc	极低		缺少时无法正常获取本机host地址
```



更新日志：
--

### [点击查看](https://github.com/juewuy/ShellClash/releases)

交流反馈：
--
### [TG讨论组](https://t.me/clashfm) 

相关Q&A：
--

### [详见博客](https://juewuy.github.io)

## 请喝杯茶：

​		支付宝										微信

##### <img src="http://juewuy.github.io/post-images/1604390977172.png" style="zoom:50%;" /><img src="http://juewuy.github.io/post-images/1604391042406.png" style="zoom:50%;" />

友情推广：
--
### [顶级8K专线机场-墙洞](https://dler.best/auth/register?affid=89698)
