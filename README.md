# FlowDM 下载

FlowDM 是一个适用于 macOS 和 Windows 的下载管理器，支持 HTTP/HTTPS 多连接下载、磁力链接、浏览器下载接管、网页媒体检测，以及 HLS（`.m3u8`）和 DASH（`.mpd`）视频下载与合并。

## 下载

请前往 [FlowDM v0.4.0](https://github.com/zhangwenlv/FlowDM-Downloads/releases/tag/v0.4.0)，在 Assets 中按自己的系统下载：

| 系统 | 下载文件 | 说明 |
| --- | --- | --- |
| macOS | `FlowDM-0.4.0-macOS-Universal-friends.zip` | 同时支持 Apple Silicon 和 Intel Mac |
| Windows | `FlowDM-0.4.0-Windows-x64-friends.zip` | 支持 Windows 10/11 x64，包含 EXE 和 MSI |
| 浏览器插件 | `FlowDM-Browser-Extension-0.4.0.zip` | Chrome、Edge、Arc 可用；两个桌面包中也已包含 |

请不要下载 GitHub 自动生成的 **Source code** 压缩包。这个公开仓库只用于提供下载页面，自动生成的源码包不是可运行的 FlowDM 软件。

## 文件校验

- macOS Universal：`fcb017c08f02d2e61c9a9a61814cb6998d556752db8c91924428fec6055a2911`
- Windows x64：`1f41c4a3f1fe1c7735f74eae736200ced7c89937945cf61adc48970dd20c045a`
- 浏览器插件：`7ef2e561f0b159f166847e4544b12f63526af02849eb34fadc41f293fe0c54b1`

## macOS 安装

1. 下载并解压整个 macOS ZIP。
2. 按住 Control 点击 `install.command`，选择“打开”。
3. 根据提示输入当前 Mac 用户的管理员密码。
4. 安装脚本会把 FlowDM 复制到“应用程序”，并把浏览器插件复制到稳定目录。

这个朋友分享版没有提交 Apple 公证。若 macOS 提示无法验证开发者，请打开“系统设置 → 隐私与安全性”，找到被阻止的 FlowDM，然后点击“仍要打开”。

## Windows 安装

1. 下载并解压整个 Windows ZIP。
2. 打开 `Installers` 文件夹。
3. 优先运行名称中带 `setup` 的 EXE，也可以使用 MSI。
4. 双击 `install-browser-extension.cmd` 可把浏览器插件复制到稳定目录，并打开扩展管理页。

这个朋友分享版没有购买 Windows 代码签名证书。如果 SmartScreen 显示“未知发布者”，请先核对上面的 SHA-256，再点击“更多信息 → 仍要运行”。

## 浏览器插件

1. 安装并启动 FlowDM。
2. 打开 Chrome/Edge/Arc 的扩展管理页。
3. 打开“开发者模式”，点击“加载已解压的扩展程序”。
4. 选择桌面安装包脚本显示的 `Browser Extension` 稳定目录。

插件通过 `127.0.0.1:16888` 与本机 FlowDM 通信，不会把任务发送到云端。插件不会自动读取或发送 Cookie、Authorization 等登录凭证。

## 系统要求

- macOS 12 或更高版本，支持 Apple Silicon 和 Intel Mac
- Windows 10/11 x64；系统需要 Microsoft Edge WebView2 Runtime
- Chrome、Edge 或 Arc 浏览器可使用浏览器助手

## v0.4.0 功能

- HTTP/HTTPS 多连接下载、暂停、继续、取消和删除
- magnet 磁力链接下载和 DHT/Tracker 节点发现
- 浏览器普通下载接管和网页媒体资源检测
- 真正下载 HLS/DASH 分片并通过随应用提供的 FFmpeg 合并为 MP4
- macOS Universal 与 Windows x64 双平台支持
- 下载任务持久化、速度、进度、剩余时间和文件列表展示

## 使用范围

FlowDM 不支持 DRM、付费墙或绕过网站访问控制。请只下载你有权保存的内容。

桌面包中包含独立的 FFmpeg 9.0 命令行程序，其来源、对应源码地址和 GNU GPLv3 许可文本均随应用提供。
