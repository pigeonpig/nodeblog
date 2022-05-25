## 在Replit中自建监控网站


# 前言：

废话不多说，这篇文章胶凝在replit上白嫖一个网站监控，并设置企业微信通知。

本次一键部署资源可以在我的仓库Star获取：[valetzx starlist replit ](https://github.com/stars/valetzx/lists/replit)

# 准备：

注册 [Replit](https://replit.com/)，准备好教育仓库。

这里要用到nodejs监控，和Python企业微信通知

浏览仓库：[louislam/uptime-kuma](https://github.com/louislam/uptime-kuma) 监控主程序

浏览仓库：[easychen/wecomchan](https://github.com/easychen/wecomchan) 微信通知

# 开始：

转到仓库：[在replit自建uptime-kuma监控 (github.com)](https://github.com/valetzx/uptimekumaonreplit) 一键部署监控主程序。

注意！！！第一次运行成功后请注释掉 `main.sh` 文件中的 `git clone` 命令！！！

![image-20220423145822141](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444492287/gVpRHn9Au.png)

在教育仓库中新建Python项目，将uptimekumaonreplit仓库中的 `main.py` 粘贴至Python项目仓库中。在运行前执行 `pip install python-multipart` 指令。

-  `main.py` 来自 Zkeq [Github](https://github.com/zkeq) / [Blog](https://icodeq.com/)

![image-20220423143749287](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444496446/LBzSZdDDJ.png)

在补全企业微信相应信息后，点顶部绿色 Run，运行通知服务。

当Python通知程序成功运行后，复制你的 https://xxxx.xxxx.repl.co

![image-20220423144258748](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444500074/sOklNyD8J.png)

粘贴至一开始部署好的 监控主程序 仓库中的 `pushbullet.js` 文件中。

![image-20220423145120181](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444503844/vd1Z2Fkgz.png)

将你的 `pushbullet.js` 替换 `./uptime-kuma/server/notification-providers/pushbullet.js` 

![image-20220423145400484](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444507928/_3dTuGMRI.png)

最后 如果之前运行的没停就点Stop 反正就是重新跑一遍Run。

![image-20220423145632081](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444511637/OLNhVxeeM.png)

出现xxxxxx什么什么已拒绝连接是正常现象，uptime-kuma不允许跨域。

配置uptime-kuma通知：

![image-20220423150456630](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444516284/-V1TNk6xX.png)

打开你的 uptime-kuma 转到 `设置-通知` 设置通知。

![image-20220423150608163](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444521413/KRFS5Y_sa.png)

如果要设置企业微信应用程序通知就选择 `Pushbullet` 

![image-20220423150758369](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444525020/L3RESqCDI.png)

显示名称 随便写 Access Token 随便写 填好后点 测试按钮。当企业微信出现通知后保存。测试成功通知为：Uptime Kuma Alert Testing Successful.

![image-20220423151020723](https://cdn.hashnode.com/res/hashnode/image/upload/v1653444529316/fwDSfNLQ6.png)

文章备份：https://allblog.vercel.app/article/01VC3T5Y5OTPACA6C43NAKPYGKOCQNRRZV
