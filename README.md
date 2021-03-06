spamshot
========

Apple Script for automate procedures of iMessage spam reporting

iMessage 垃圾信息报告Apple Script自动化脚本

## 安装 ##

所有你需要的只有spamshot.applescript一个文件。

下载完成后把该文件放到`~/Library/Application Scripts/com.apple.iChat/`目录。

打开Mac上的`信息.app`，依次点击`信息`-`偏好设置`-`通用` 找到`AppleScript处理程序`，从下拉菜单选择`spamshot.applescript`.

![imsg_setup](http://ashfinal.qiniudn.com/20141226spamshot_imsgsetup.png)

## 使用方法 ##

**1.批量处理**

如果你需要扫描举报已有的垃圾信息(通常数量较多)，通过 `脚本编辑器.app`直接运行该脚本(快捷键为 `⌘+R`)。

你需要确认`脚本编辑器.app`已配置辅助控制权限。参照第2条进行查看/设置。

**2.逐条举报**

对想要举报的某条iMessage信息 回复 `spam report` 或者 `垃圾举报` 即可。

你需要添加`信息.app`的辅助控制权限：打开`系统偏好设置`-`安全性与隐私`-`隐私`-`辅助功能`，点加号手动添加`信息.app`。

![imsg_ctrl](http://ashfinal.qiniudn.com/20141226spamshot_imsgctrl.png)

如需更多自定义选项，请打开`spamshot.applescript`脚本文件参看详细设置。

## 可能存在的问题 ##

**1.Dropbox相关问题**

如果你在使用dropbox，可能会出现邮件截图缺失的情况。貌似dropbox会监控文件系统变化，把脚本运行过程产生在图片文件夹的临时截图给移走了。。。

因本人不使用dropbox，无法进行测试和进一步改进。使用dropbox仍想尝试正常运行，可以搜索`spamshot.applescript`文件里的`set picPath to (POSIX path of (path to pictures folder)) & "spamshot.png"`，将picPath更改为其它dropbox监控不到的目录(需更改6处)。

**2.非13寸MacBook相关问题**

相同操作系统版本在不同尺寸设备上的菜单竟然不同！这导致脚本模拟点击出错，会“清空”iMessage所有信息。(目前暂仅发现15寸设备上会有此问题)如果确实遇到此现象，请尝试将第299行处的`item 9`改为`item 11`。

![bug_patch](http://ashfinal.qiniudn.com/20141228spamshot_bugpatch.png)

## Thanks ##

Feel free to use and spread. Any contribution is welcome! ^_^
