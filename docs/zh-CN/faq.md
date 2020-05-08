# 常见问题
## 开启 TUN/TAP 模式后 CPU 占用高
![](resources/screenshots/FAQ/Q1.png)

这是因为 Netch 批量向路由表写入路由规则的原因，过一会就好了

## NAT 类型测试失败
换节点

## 网页代理模式启动失败
![](resources/screenshots/FAQ/Q3.png)

1. 一般都是依赖没装导致的
2. 检查是否被杀软拦截

## 关于如何让 UWP 软件走系统代理
https://kiritox.me/archives/setup-proxy-for-windows-apps.html

## Windows 7 不能正常启动
是因为您的 Windows 7 不是最新的，缺少一个 KB4503292 补丁

- [Download KB4503292 MSU for Windows 7 32-bit (x86)](http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/06/windows6.1-kb4503292-x86_932f3cccb6343fa2339648b391b80d28f8134870.msu)
- [Download KB4503292 MSU for Windows 7 64-bit (x64)](http://download.windowsupdate.com/d/msdownload/update/software/secu/2019/06/windows6.1-kb4503292-x64_a35bb4ea16d1d529fde9abfe8a0c16e9061f74cd.msu)

## 其他

![](resources/screenshots/FAQ/QN.png)