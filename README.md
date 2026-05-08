<div align="center">
<h1>澎湃OS剪贴板功能补全</h1>

<a href="https://github.com/Xposed-Modules-Repo/com.clipboardfix/releases"><img alt="GitHub all releases" src="https://img.shields.io/github/downloads/Xposed-Modules-Repo/com.clipboardfix/total?label=Downloads"></a>
<a href="https://github.com/Xposed-Modules-Repo/com.clipboardfix/releases/latest"><img alt="GitHub latest release" src="https://img.shields.io/github/v/release/Xposed-Modules-Repo/com.clipboardfix"></a>

<p>🛠️修复 HyperOS 3.0第三方输入法无法读取系统剪贴板历史内容的问题</p>

<p>
  <b>作者：</b>
  <b><a href="https://weibo.com/u/3725737792">李十六的日记本</a></b>&
  <b><a href="https://www.coolapk.com/u/3019478">江上晚</a></b>
  
</p>
</div>

---

## 📝模块说明

本模块主要修复HyperOS 3.0自动更新剪贴板和常用语V4.7.7后导致第三方输入法无法使用系统剪贴板的异常问题，由于小米在V4.7.7增加了严格的白名单验证，导致**第三方输入法**（微信输入法、豆包输入法 等）无法通过剪贴板面板查看系统剪贴板历史记录。

## 📱已测应用

| 名称 |   版本号 |
|------|------------|
| 微信输入法 |   3.2.0   |
| 豆包输入法 |   1.3.6   |

## 🤖使用方法

1. 安装本模块 APK
2. 在 LSPosed 中启用本模块
3. 作用域选择 **剪贴板和常用语**
4. 重启设备，必须重启手机，否则没有效果

## ❗注意事项

- 本模块仅修改剪贴板和常用语验证逻辑，不影响数据内容，请放心使用。
- 如果您的系统剪贴板功能正常请勿安装本模块！
- **本模块安装后需要重启手机才能生效，请确保您的设备已经安装了救砖模块**
- 意见建议反馈请在 [酷安：江上晚](https://www.coolapk.com/u/3019478) [微博：李十六的日记本](https://weibo.com/u/3725737792)反馈

## 🔎相关链接

- 主仓库：[jiangshangwan/ClipboardFix](https://github.com/jiangshangwan/ClipboardFix)
