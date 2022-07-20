# DogCs4.4
4.4修改版

压缩包内自带jdk11,客户端运行rundogcs.vbs即可.

服务端如果linux的话需要自己安装jdk11,相信对大家来说应该很容易吧.

有bug请提交lssues.
# 服务端也要用dogcs启动!!!
# 解压密码

首发T00ls.net:https://www.t00ls.com/thread-66233-1-1.html

个人博客:https://www.nctry.com/2630.html

希望尽量别乱传.（ps:用windows解压,mac解压有问题）

仅限t00ls成员使用.
# 修改说明

1.去除ListenerConfig中的特征水印

2.修改Stager Url校验算法

3.修改默认登录int长度48879,让网上的爆破脚本无法爆破

4.修改beacon配置信息的默认密钥,不会被默认的脚本获取到配置信息

5.修改原版的ua头

6.修复若干问题以及最新特征(url错误请求泄露信息特征)

7.bypass 360核晶模式:截图,Mimikatz,Hashdump(参考论坛一篇文章修改而成)

8.自带一个FindAv插件,集成git上的插件:https://github.com/thekingofsex/antiVirusCheck

注：需要用java11运行.
# 关于特征

今天有朋友和我说什么JARM指纹被加入规则库了？这里有几个解决方法：

1.用反向代理

2.修改java运行配置（找到java安装目录,打开conf/security/java.security 文件）

修改jdk.tls.disabledAlgorithms处的部分,大概736行，如图：

![JARM](https://github.com/TryHello/DogCs4.4/blob/main/jarm.png "JARM")

像图片那样新加一个TLSv1.3即可

# Bug

1.默认64位木马运行的时候向c2请求payload返回404，但是32位木马是正常的，因为StagerUrl那块没写好,验证出了问题，但是可以利用profile文件自定义http-stager解决.

如:
```
http-stager {
    set uri_x86 "/XXXXn";
    set uri_x64 "/XXXXXX";
        }
```
2.执行hashdump后beacon退出问题,新版本v1已更新.

![运行截图](https://github.com/TryHello/DogCs4.4/blob/main/1.png "运行截图")


![FindAv](https://github.com/TryHello/DogCs4.4/blob/main/FindAv.png "FindAv")


2022.07.19修复vnc执行退出bug
