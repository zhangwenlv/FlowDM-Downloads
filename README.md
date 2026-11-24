# FlowDM 下载

FlowDM 是一个适用于 macOS 和 Windows 的下载管理器，支持 HTTP/HTTPS 多连接下载、磁力链接、浏览器下载接管、网页媒体检测，以及 HLS（`.m3u8`）和 DASH（`.mpd`）视频下载与合并。

## 下载

请前往 [FlowDM v0.8.0](https://github.com/zhangwenlv/FlowDM-Downloads/releases/tag/v0.8.0)，在 Assets 中按自己的系统下载：

| 系统 | 下载文件 | 说明 |
| --- | --- | --- |
| macOS | `FlowDM-0.8.0-macOS-Universal-friends.zip` | 同时支持 Apple Silicon 和 Intel Mac |
| Windows | `FlowDM-0.8.0-Windows-x64-friends.zip` | 支持 Windows 10/11 x64，包含 EXE 和 MSI |
| 浏览器插件 | `FlowDM-Browser-Extension-0.8.0.zip` | Chrome、Edge、Arc 可用；两个桌面包中也已包含 |

请不要下载 GitHub 自动生成的 **Source code** 压缩包。这个公开仓库只用于提供下载页面，自动生成的源码包不是可运行的 FlowDM 软件。

## 文件校验

- macOS Universal：`bb5cfe17a070f26388e2d13b4a55f81adcbff01b68980e0dfd04e964ea20bf9f`
- Windows x64：`1193cd466ffa8d9c688ecc0c89ba605253bcf743335c239747e8012044619a8c`
- 浏览器插件：`32e4e7677b643b25177a3a9bc78636e26a4952e351554d1f1955c244f8fcdbd9`

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

## 默认下载位置

1. 打开 FlowDM，点击左下角“设置”。
2. 在“默认下载位置”中选择文件夹并保存。
3. 浏览器任务和未单独选择目录的新任务都会保存到该位置。
4. 手动新建任务时仍可临时选择其他目录，只覆盖当前任务。

修改默认位置不会移动现有文件，也不会改变已有任务的保存路径；可以随时恢复为系统下载目录。

## 开机自启

1. 打开 FlowDM，点击左下角“设置”。
2. 打开“开机时自动启动 FlowDM”并保存。
3. macOS 会注册当前用户的登录启动项，Windows 会注册当前用户的启动项。
4. 再次关闭并保存会从系统启动列表移除，不影响任务记录和下载文件。

FlowDM 会读取系统中的真实自启状态；若系统启动项修改或设置保存失败，界面会显示明确错误并尽可能恢复原状态。

## 系统要求

- macOS 12 或更高版本，支持 Apple Silicon 和 Intel Mac
- Windows 10/11 x64；系统需要 Microsoft Edge WebView2 Runtime
- Chrome、Edge 或 Arc 浏览器可使用浏览器助手

## v0.8.0 功能

- 开机自启时静默进入后台，不再主动显示主界面
- 关闭主窗口时隐藏到系统托盘或 macOS 菜单栏，可从托盘重新显示或彻底退出
- 浏览器触发下载时主动弹出独立下载浮窗，即使主界面处于后台也能看到进度
- 下载浮窗实时显示进度、速度、已下载大小、总大小和剩余时间
- 下载浮窗支持暂停、继续、取消并保留数据、重试，以及完成后打开文件或所在文件夹
- 主窗口和各任务浮窗相互独立，关闭主窗口不会中断下载或关闭已有浮窗
- macOS 和 Windows 均可在应用设置中开启或关闭开机自启，并读取系统真实状态
- macOS 和 Windows 均可设置默认下载位置，浏览器接管任务不再固定保存到系统下载目录
- HTTP/HTTPS 动态分段下载，单任务从 8 个连接自适应提升至最多 32 个
- 遇到服务器连接限制时自动从 32 降至 16、8、4 或 1 个连接重试
- 最多同时运行 2 个任务，其余任务进入等待队列；全局最多使用 64 个 HTTP 连接
- 支持优先下载、动态拆分慢分片、断点续传，以及实时连接数、分片和重试指标
- 暂停、继续、取消并保留数据，以及删除任务和本地分片
- magnet 磁力链接下载和 DHT/Tracker 节点发现
- 浏览器普通下载接管和网页媒体资源检测
- 真正下载 HLS/DASH 分片并通过随应用提供的 FFmpeg 合并为 MP4
- macOS Universal 与 Windows x64 双平台支持
- 下载任务持久化、全局实时速度、进度、剩余时间和文件列表展示

## 使用范围

FlowDM 不支持 DRM、付费墙或绕过网站访问控制。请只下载你有权保存的内容。

桌面包中包含独立的 FFmpeg 9.0 命令行程序，其来源、对应源码地址和 GNU GPLv3 许可文本均随应用提供。
