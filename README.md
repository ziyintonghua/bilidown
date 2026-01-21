原版软件已恢复服务，此仓库永久存档。

复活「王子周棋洛」的B站视频下载器「Bilidown」。

使用： 仓库里的 app.asar 文件基于原版 v1.2.6 版本修改，因此下载后直接替换程序目录内对应文件即可。

对于 Retards & Resellers：我在 Releases 里上传了一份 Windows 便携版，自行取用。

发生了什么： 程序的主要逻辑仍然是请求 B 站 API ，并没有（也不应该）通过作者的服务器来进行；但作者也许预料到了自己的程序会被人倒卖，在执行搜索和登录操作前调用了supportCheck()函数，通过访问https://zhouql.vip/bilibili/support/support.json?t=${(new Date).getTime()}来控制程序是否可用。

解决方案也很简单，把实际操作前的检查逻辑删除即可。

经过测试，修改后的程序下载视频、音频、封面均正常。
