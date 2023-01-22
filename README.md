<p align="center"><img src="https://i.loli.net/2020/03/06/Q8dyDxz63OKbZml.png"></p>

## About Kinss
Kinss is a minimalist feed reader for kindle.

## CHANGELOG
- 2023-01-22 更新了库依赖。不知会有多少人还坚持用kindle来阅读。过了一两年才发现项目完全跑不动了。刚好前几个月把古董KPW3拿出来越个狱，有点怀念初中时每天只有kindle陪伴的日子了。谁能想到在7、8年前kindle还能上百度贴吧回帖，现在估计是不能了。

## Quickstart
1. `pip install -r requirements.txt`
2. 运行`app.py`，默认 ip 是 `0.0.0.0` & 端口 `5000`。

## Docker 部署
### 安装
运行下面的命令下载 kinss 镜像

`$ docker pull intemd/kinss`

然后运行 kinss 即可

`$ docker run -d --name kinss -p 5000:5000 intemd/kinss`

在浏览器中打开 http://0.0.0.0:5000/ ，enjoy it! ✅

您可以使用下面的命令来关闭 kinss

`$ docker stop kinss`
### 更新
删除旧容器

`$ docker stop kinss`

`$ docker rm kinss`

然后重复安装步骤

## Aggregator
此程序依赖**feverapi**，任何集成了此api的服务理论上都能运行。以下是几个大佬提供的公开服务，我稍微进行了测试。体验地址：[kinss](https://kinss.2333332.xyz)，当然，由于网络线路等原因，当读取文章列表时，一次响应**可能高达10秒**。建议自建。

|Aggregator|Fever UesrName|Fever Password|Fever API endpoint|thanks to|
|  ----  | ----  |--------|  ----  | ----  |
|FreshRSS|kinss|kinsses|https://rss.othing.xyz/api/fever.php|@yzqzss|

## 通过链接方式登录
现已支持通过Get请求的方式进行登录（即通过访问如https://domain/login?name=FeverUsername&psd=FeverPassword&endpoint=FeverAPIendpoint 的链接的形式直接登录），该方式对咪咕版Kindle等设备更为友好。例如上面的例子：

https://kinss.2333332.xyz/login?name=kinss&psd=kinsses&endpoint=https://rss.othing.xyz/api/fever.php

对于没有浏览器的设备，理论上可能的操作参考：
 https://zhuanlan.zhihu.com/p/143457808

由于本人没有类似设备，故无法测试。

***实际使用中请将等号后的参数替换为自己的参数使用。***

**由于Get请求的安全性较Post方式弱，使用该方式登录时请妥善保管好登录链接，不要外泄。**

## Features
- [x] 已读/未读
- [x] 星标
- [x] 二维码
- [x] 多账户

## Read On KPW3
![](assets/1.png)
![](assets/2.png)
![](assets/5.png)

## License
Kinss is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
