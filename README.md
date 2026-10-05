# PokéRogue 官网版 Android 外壳

打开官方站点 https://pokerogue.net/ 的轻量 WebView 应用。网页内容由官网实时提供，需要联网和官网账号；它与离线 APK 的本地存档不共享。

使用 `powershell -ExecutionPolicy Bypass -File .\build.ps1` 构建。输出为 `build/pokerogue-live.apk`。首次构建会在 `signing/` 生成仅供本机测试的签名密钥；保留该文件才能覆盖安装后续版本。

当前支持沉浸式全屏、官网页面浏览、文件选择与普通 HTTPS 下载链接。网页生成的 blob 文件导出暂不支持。游戏画布自身的宽高比由官网控制，手机屏幕比例不同可能仍有留白。
