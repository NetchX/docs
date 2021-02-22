# 模式介绍

```
# Remark, Type, BypassChina
Rules
```

#### 引用，注释

```
# Discord and Steam, 0
// 注释
#include Discord.txt
// 模式引用
#include Steam.txt 
```

?> 模式可引用 **同类型的** 模式，**引用其他模式的模式不可被引用**

### `Remark`: string

模式名

### `Type`: int

?> Netch 界面模式类型数字加 1

模式类型, 默认为 0

* `0`: 进程代理
* `1`: TUN/TAP 代理规则 IP
* `2`: TUN/TAP 跳过规则 IP
* `3`: 网页代理
* `4`: 本地 Socks5 代理
* `5`: 本地 Socks5 和 HTTP 代理

### `BypassChina`: int

加密代理客户端应用路由规则, 默认为 0

TUN/TAP 模式无作用 

网页代理模式依靠此选项启用绕过大陆

* `0`: 禁用
* `1`: 启用

Shadowsocks, ShadowsocksR 通过 ACL 路由

VMess, VLESS 通过 routing 配置路由

Trojan C++ 无路由支持，使用 PAC 脚本路由

### `Rules`: string

规则

#### 进程代理模式

进程代理规则分为 代理规则 和 跳过规则

以 **!** 开头的规则为跳过规则, 其余为代理规则

规则需符合 C++ 正则表达式语法

程序的完整路径 如果匹配跳过规则, 则不被代理

如果不满足跳过规则并匹配代理规则, 则被代理

```
# 除了 Clash 全部代理, 0
.*
!clash\.exe
```

```
# Chrome 分流, 0, 1
chrome
```

#### TUN/TAP 模式

TUN/TAP 规则为 [IPv4 CIDR 块](https://zh.wikipedia.org/wiki/%E6%97%A0%E7%B1%BB%E5%88%AB%E5%9F%9F%E9%97%B4%E8%B7%AF%E7%94%B1#CIDR%E5%9D%97)

```
# 代理规则 IP , 1
8.8.8.8/32
1.1.1.1/32
```

```
# 规则 IP 除外被代理, 2
192.168.0.0/16
114.114.114.114/32
```

[提取加速器规则](https://github.com/FQrabbit/SSTap-Rule/blob/master/doc/UU-extract.md)

#### 其他模式

规则不适用
