# DogCs4.4
4.4修改版

压缩包内自带jdk11,客户端运行rundogcs.vbs即可.

服务端如果linux的话需要自己安装jdk11,相信对大家来说应该很容易吧.

有bug请提交lssues.
# 解压密码

首发T00ls.net:https://www.t00ls.com/thread-66233-1-1.html

希望尽量别乱传.

仅限t00ls成员使用.
# 修改说明
1.去除ListenerConfig中的特征水印
2.修改Stager Url校验算法
3.修改默认登录int长度48879,让网上的爆破脚本无法爆破
4.修改beacon配置信息的默认密钥,不会被默认的脚本获取到配置信息
5.修改原版的ua头
6.修复若干问题以及最新特征(url错误请求泄露信息特征)
7.bypass 360核晶模式:截图,Mimikatz,Hashdump(参考论坛一篇文章修改而成)
8.自带一个FindAv插件
注：需要用java11运行.
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
