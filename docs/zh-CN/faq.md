# 常见问题

## 开启 TUN/TAP 模式后 CPU 占用高

![](resources/screenshots/faq/tuntap-high-cpu-usage.png)

这是因为 Netch 批量向路由表写入路由规则的原因，过一会就好了

## DNS(53) 端口被占用

在 设置-TUNTAP 中启用使用自定义 DNS （默认`1.1.1.1`）

## 网页代理模式 UWP 应用无法联网
https://github.com/Fndroid/clash_for_windows_pkg/wiki/UWP%E5%BA%94%E7%94%A8%E8%81%94%E7%BD%91#%E4%B8%BA%E4%BB%80%E4%B9%88cfw%E4%B8%8Buwp%E5%BA%94%E7%94%A8%E6%97%A0%E6%B3%95%E8%81%94%E7%BD%91

[enableloopbackutility.exe](https://telerik-fiddler.s3.amazonaws.com/fiddler/addons/enableloopbackutility.exe)

## Windows 7 使用进程模式注册驱动失败

[Download KB4503292 MSU for Windows 7 64-bit (x64)](http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/06/windows6.1-kb4503292-x64_a35bb4ea16d1d529fde9abfe8a0c16e9061f74cd.msu)

## 关于 NAT 测试

[网络地址转换-WIKIPEDIA](https://zh.wikipedia.org/wiki/%E7%BD%91%E7%BB%9C%E5%9C%B0%E5%9D%80%E8%BD%AC%E6%8D%A2)

!> NAT 开放程度会影响到以 GTAOL 为代表的 P2P 连接游戏匹配玩家的数量 和 种子下载寻找其他 peer 的效果

!> NAT 测试结果只能代表 UDP 转发效果，大部分在线竞技游戏使用 UDP 协议传输游戏数据。NAT 测试结果不能代表网页浏览等 TCP 协议使用场景的使用效果

NAT 测试结果为 `Fail` 或 `UdpBlocked` 可能是因为：

- 无法与服务器建立连接，这可能是因为 Netch 生成客户端配置错误或其他故障
- 服务器不支持 UDP 转发，请检查服务端配置
- 服务器无法建立与 STUN 服务器的连接，请在 Netch 设置内切换 STUN 服务器

NAT 测试结果 [*](https://github.com/NetchX/Netch/issues/504#issuecomment-766508605)：

`NAT1 → Full Cone NAT` 此类型可获得最佳游戏体验

`NAT2 → Address-Restricted Cone NAT`

`NAT3 → Port-Restricted Cone NAT`

`NAT4 → Symmetric NAT`

## TUN/TAP 启动失败，日志中有 CryptAcquireContext failed with error -2146893809

Win+R 输入 `%appdata%\Microsoft\Crypto` 后重命名 RSA 文件夹为 RSA_ 或直接删除。

## Netch 更新下载慢/失败

请启用 Netch 的`网页代理`后再更新。

## 其他

![](resources/screenshots/faq/Google.png)
