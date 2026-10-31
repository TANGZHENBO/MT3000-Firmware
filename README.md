# GL-MT3000 · ImmortalWrt 25.12.2

面向 GL.iNet GL-MT3000（Beryl AX / MT7981B）的中文定制固件构建项目，使用 ImmortalWrt 25.12.2 官方 ImageBuilder。

## 预装功能

- 中文 LuCI 管理界面
- sing-box 核心 + HomeProxy 图形管理界面
- Adblock Fast 广告过滤（首次启动后需自行选择过滤列表并启用）
- Argon（默认）、Bootstrap、Material、OpenWrt 2020、OpenWrt classic 主题
- SmartDNS、DDNS、SQM、UPnP、流量统计、网络唤醒
- WireGuard、OpenVPN
- 不包含 Docker、PassWall、OpenClash，避免重复代理管理组件

## 自动编译

1. 打开仓库的 Actions 页面。
2. 选择 **Build ImmortalWrt 25.12.2 for GL-MT3000**。
3. 点击 **Run workflow** 启动编译。
4. 编译成功后，从 Actions Artifact 或 Releases 下载固件。

## 首次启动

1. 仅将 GL-MT3000 对应的 sysupgrade 固件刷入 GL-MT3000。
2. 登录 LuCI 后立即设置强 root 密码。
3. 在 **Services → HomeProxy** 导入自己的订阅或节点配置。
4. 在 **Services → Adblock Fast** 选择过滤列表，启用并应用。
5. 在 **System → Language and Style** 选择主题。

广告过滤默认不强制启用，避免意外影响 DNS 或代理。HomeProxy 已预装，但不包含任何节点或订阅。

## 注意事项

- 本仓库是固件构建配置，不代表已经生成可刷入固件；必须等待 Actions 编译成功。
- 不要将其他型号设备的固件刷入 GL-MT3000。
- 刷机前备份配置，并准备好官方恢复方式。不要将 LuCI 或 SSH 直接暴露到 WAN。