spamshot
========

Apple Script for automate procedures of iMessage spam reporting

iMessage 垃圾信息报告Apple Script自动化脚本

![spamshot_screenshot](http://ashfinal.qiniudn.com/20141226spamshot_00.png)

## 安装 ##

所有你需要的只有spamshot.applescript一个文件。

下载完成后把该文件放到`~/Library/Application Scripts/com.apple.iChat/`目录。

打开Mac上的`信息.app`，依次点击`信息`-`偏好设置`-`通用` 找到`AppleScript处理程序`，从下拉菜单选择`spamshot.applescript`.

![imsg_setup](http://ashfinal.qiniudn.com/20141226spamshot_imsgsetup.png)

## 使用方法 ##

**1.批量处理模式**

如果你需要扫描举报已有的垃圾信息(通常数量较多的情况下)，通过 `脚本编辑器.app`直接运行该脚本(快捷键为 `⌘+R`)。

你需要确认`脚本编辑器.app`已配置辅助控制权限。具体可以参照下文加粗部分进行查看/设置。

**2.自动处理模式**

不需要主动运行。配置完辅助控制权限后，每当收到疑似垃圾信息时，会弹出对话框询问是否举报，选OK则自动完成操作。

**3.逐条举报模式**

你可以对想要举报的某条iMessage 回复 `spam report` 或者 `垃圾举报` 即可实现自动化举报。

**第2、3种模式你需要添加`信息.app`的辅助控制权限：打开`系统偏好设置`-`安全性与隐私`-`隐私`-`辅助功能`，点加号手动添加`信息.app`。**

![imsg_ctrl](http://ashfinal.qiniudn.com/20141226spamshot_imsgctrl.png)

如需更多自定义选项，请打开`spamshot.applescript`脚本文件参看详细设置。

## 已知问题 ##

如果你在使用dropbox，可能会出现邮件截图缺失的情况。貌似dropbox会监控文件系统变化，把脚本运行过程产生在桌面的临时截图给移走了。。。

因本人不使用dropbox，无法进行测试和进一步改进。使用dropbox仍想尝试正常运行，可以搜索`spamshot.applescript`文件里的`set picPath to (POSIX path of (path to desktop)) & "spamshot.png"`，将picPath更改为其它dropbox监控不到的目录(需更改6处)。
