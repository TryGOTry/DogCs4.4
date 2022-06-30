# DogCs4.4
4.4修改版

压缩包内自带jdk11,客户端运行rundogcs.vbs即可.

服务端如果linux的话需要自己安装jdk11,相信对大家来说应该很容易吧.
# 解压密码

首发T00ls.net:https://www.t00ls.com/thread-66233-1-1.html

希望尽量别乱传.

仅限t00ls成员使用.

# Bug

1.默认64位木马运行的时候向c2请求payload返回404，但是32位木马是正常的，因为StagerUrl那块没写好,验证出了问题，但是可以利用profile文件自定义http-stager解决.

如:
```
http-stager {
    set uri_x86 "/XXXXn";
    set uri_x64 "/XXXXXX";
        }
```

![运行截图](https://github.com/TryHello/DogCs4.4/blob/main/1.png "运行截图")
