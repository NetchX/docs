# 常见问题

## 更新 v2rayN 格式订阅报错

Netch 1.8.0 将 JSON 库迁移到了 System.Text.Json，并依据 [v2rayN 分享链接格式](https://github.com/2dust/v2rayN/wiki/%E5%88%86%E4%BA%AB%E9%93%BE%E6%8E%A5%E6%A0%BC%E5%BC%8F%E8%AF%B4%E6%98%8E(ver-2)) 规范化导入分享连接。

但是被大量使用的 SSPanel-Uim 因为 v2rayN 使用的 Newtonsoft.Json 库允许将 Number 反序列化为字符串，所以未注意规范，[现已规范化](https://github.com/Anankke/SSPanel-Uim/commit/4ccec3c9132c4cba498ce588653aa44302efe55c)，请寻找相关人员提醒更新面板。

## 开启 TUN/TAP 模式后 Windows 服务 CPU 利用率高

TUN/TAP 模式启动时 Netch 向路由表写入路由规则，规则条目越多利用率越高，并且会向日志文件写入内容 [*](https://github.com/NetchX/Netch/issues/320)

SSTap 和 商业加速器虚拟网卡模式 都能观察到此问题

原因未知，建议少使用具有大量数量的规则。

## DNS(53) 端口被占用

- [停用 Hyper-V](https://developer.android.com/studio/run/emulator-acceleration#disable-hyper-v)

- 启用`设置-TUNTAP-使用自定义 DNS`（默认`1.1.1.1`）

## 网页代理模式 UWP 应用无法联网
[Clash For Windows Wiki - UWP 应用联网](https://github.com/Fndroid/clash_for_windows_pkg/wiki/UWP%E5%BA%94%E7%94%A8%E8%81%94%E7%BD%91#%E4%B8%BA%E4%BB%80%E4%B9%88cfw%E4%B8%8Buwp%E5%BA%94%E7%94%A8%E6%97%A0%E6%B3%95%E8%81%94%E7%BD%91)

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

## Netch 更新下载慢/失败

请启用 Netch 的`网页代理`后再更新。

## TUN/TAP 启动失败，日志中有 CryptAcquireContext failed with error -2146893809

Win+R 输入 `%appdata%\Microsoft\Crypto` 后重命名 RSA 文件夹为 RSA_ 或直接删除。
