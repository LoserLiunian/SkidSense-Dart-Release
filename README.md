# SkidSense 手机端发布

SkidSense 手机端（Android）的安装包和自动更新源。源代码在私有仓库里，这里只放发布版本。电脑端在 [SkidSense-Release](https://github.com/LoserLiunian/SkidSense-Release)。

到 [Releases](https://github.com/LoserLiunian/SkidSense-Dart-Release/releases/latest) 下载对应的安装包：

| 手机 | 文件 |
|---|---|
| 大多数手机（arm64） | `SkidSense-<版本>-android-arm64.apk` |
| 较旧的 32 位手机 | `SkidSense-<版本>-android-arm.apk` |
| 模拟器（x86_64） | `SkidSense-<版本>-android-x64.apk` |
| 不确定是哪种 | `SkidSense-<版本>-android-universal.apk`（包含全部架构，体积较大） |

## 安装

1. 下载 APK，用浏览器或文件管理器打开。
2. 第一次安装时，系统会要求允许「安装未知应用」，允许你用来打开它的那个应用。
3. 之前装的是调试版（debug）的话，签名不同，需要先卸载一次再安装；之后的版本都能直接升级。

## 更新

应用启动时会检查新版本（最多每 6 小时一次），有新版本时在登录页和「电脑」页顶端提示。点「查看更新」→「下载并安装」，应用会下载适合这台手机的安装包，核对 SHA-256 后交给系统安装。第一次需要在系统设置里允许 SkidSense「安装未知应用」。

在「设置 → 应用更新」里可以手动检查，也可以打开「Beta 更新」，接收预发布版本。

## 校验

`update.release.json`（Beta 是 `update.beta.json`）列出了每个安装包的大小和 SHA-256，应用安装前会逐一核对。手动下载的也可以自己核对：

```sh
shasum -a 256 SkidSense-<版本>-android-arm64.apk
```
