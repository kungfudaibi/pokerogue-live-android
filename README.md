# PokéRogue 实时网页版 Android 客户端（非官方）

本项目针对 [Pagefault Games 的 PokéRogue 仓库](https://github.com/pagefaultgames/pokerogue)所提供的网页游戏，**没有修改、复制或离线打包游戏源码**；我们新增了一个独立的 Android WebView 外壳，让手机直接打开官方站点 `https://pokerogue.net/`，并处理沉浸式显示、文件选择、普通下载与宽屏适配。游戏内容、账号、联机和更新仍由官网提供。本项目与官方团队无关。

## 与离线直装版的区别

另一个项目：[1596941391qq/pokerogue-android 的离线直装版](https://github.com/1596941391qq/pokerogue-android)（[下载页面](https://github.com/1596941391qq/pokerogue-android/releases)）。那是**不同作者、不同安装包**；本仓库没有使用它的代码或离线游戏资源，也不代表它的后续版本。

| | 本项目：实时网页版 | 上述离线直装版 |
| --- | --- | --- |
| 游戏来源 | 启动时加载 `pokerogue.net` | APK 内打包的游戏内容，版本以其发布包为准 |
| 网络 | 需要连接官网 | 游戏主体可离线运行；具体功能以该项目说明为准 |
| 更新 | 官网更新后通常随网页生效 | 需要作者重新打包并安装新版 |
| 账号与存档 | 使用官网账号及在线存档 | 使用该 APK 的本地数据；两者不会自动互通 |
| 安装关系 | 包名 `net.pokerogue.livewrapper` | 独立项目，请以其发布说明为准 |

## 功能与限制

- 运行时加载官网网页；支持全屏、文件选择、普通 HTTPS 下载。
- 横屏时会横向拉伸官网固定比例的游戏画布来减少留白，因此图像可能比官网原比例略宽。
- WebView 登录状态与手机浏览器分开保存。网页生成的 `blob:` 文件导出尚未实现。
- 不保证官网脚本、网络或账号服务变更后仍能正常工作；这是个人试用版。

## 构建

需要 JDK 17+、Android SDK（包含 Android 36 平台和 Build Tools 36.0.0）。设置 `JAVA_HOME`、`ANDROID_HOME` 后运行：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\build.ps1
```

输出为 `build/pokerogue-live.apk`。首次构建会在 `signing/dev.keystore` 生成本地测试签名密钥。该私钥**不会上传到 GitHub**；若要覆盖安装后续自建版本，请妥善保存自己的密钥。发布页的 APK 由本仓库源码构建。

## 许可与来源

本仓库新增的 Android 外壳源码以 [AGPL-3.0-only](LICENSE) 发布，以贴近 [PokéRogue 源码的 AGPL-3.0-only 许可](https://github.com/pagefaultgames/pokerogue#licensing)。官网运行时提供的游戏代码、文档、音画素材有各自的许可与权利声明；本仓库的许可不改变它们。应用图标是本项目的改作图案，PokéRogue 名称、标识和相关角色权利仍归各自权利人所有。本项目未取得官方认可。
