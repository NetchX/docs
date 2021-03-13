# 使用技巧

- `读 TM 的手册`

- `不建议使用 Netch 作为日常浏览网页工具`，建议使用具有详细路由设置的软件（如 [clash](https://github.com/Dreamacro/clash/)）

- `不建议使用 Netch 网页代理模式以外的模式代理浏览器性质的软件（如 Chrome, Steam）`

- `不建议在 Netch 里使用无 UDP 转发的服务器`

## 主界面技巧

- `Ctrl+点击 测试图标` 测试选中服务器

- `Ctrl+点击 编辑模式图标` 使用默认程序打开选择模式对应文件（请在保存后重载模式）

- `Shift+点击 快速配置` 删除快速配置

- `点击 NAT 测试结果` 重新测试 NAT

## 设置技巧

- `检测心跳`设为 0 禁用自动测试全部服务器延迟

- 如果代理客户端无法解析代理服务器主机名，导致无法与代理服务器建立连接，请启用 `解析服务器主机名`，**此选项对 Trojan 服务器不生效**

- AioDNS 是一个本地 DNS 服务器，使用 TCP 查询 DNS，旨在解决未启用 UDP 转发的服务器无法转发 UDP DNS 查询。如果服务器启用了 UDP 转发，建议启用 `TUNTAP-使用自定义 DNS` 以禁用 AioDNS

- 替换 bin\tun2socks.exe 为支持 FakeDNS 的版本，TUNTAP-FakeDNS 设置将出现