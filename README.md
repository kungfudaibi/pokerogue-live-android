# PokéRogue 安卓在线版

这是给 [PokéRogue](https://github.com/pagefaultgames/pokerogue) 做的一个安卓入口：用 WebView 打开官网游戏，并适配全屏、文件选择和下载。游戏仍从 `pokerogue.net` 加载，官网更新后，这里通常也能直接玩到新版。

## 和离线直装版有什么不同？

想离线玩可以看看 [1596941391qq/pokerogue-android](https://github.com/1596941391qq/pokerogue-android) 的[安装包](https://github.com/1596941391qq/pokerogue-android/releases)。它把游戏内容做进 APK；这个版本则打开官网。两个项目独立，存档不会自动互通。

| | 这个在线版 | 离线直装版 |
| --- | --- | --- |
| 游戏内容 | 从官网加载，需要联网 | 随 APK 安装，游戏主体可离线运行 |
| 更新 | 跟随官网网页 | 下载并安装作者打包的新版 |
| 存档 | 官网账号和在线存档 | APK 自己的本地数据 |

手机浏览器和这个 App 的登录状态也是分开的，第一次打开需要重新登录。横屏会稍微拉宽游戏画面来减少两侧留白；网页生成的 `blob:` 文件暂时不能导出。

## 下载与构建

APK 在 [Releases](https://github.com/kungfudaibi/pokerogue-live-android/releases)。自己构建需要 JDK 17+、Android SDK 36 和 Build Tools 36.0.0，设置好 `JAVA_HOME`、`ANDROID_HOME` 后运行：

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\build.ps1
```

输出在 `build/pokerogue-live.apk`。`signing/dev.keystore` 是本机生成的签名文件；想让自己构建的下一版覆盖安装，记得保留它。

## 许可

这个 Android 外壳的源码按 [AGPL-3.0](LICENSE) 发布，与 [PokéRogue 源码的许可](https://github.com/pagefaultgames/pokerogue#licensing)保持一致。官网游戏和素材仍按各自的许可使用。本项目不是官方应用。
