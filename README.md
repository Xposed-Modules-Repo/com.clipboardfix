<div align="center">
<h1>澎湃OS剪贴板功能补全</h1>

<a href="https://github.com/Xposed-Modules-Repo/com.clipboardfix/releases"><img alt="GitHub all releases" src="https://img.shields.io/github/downloads/Xposed-Modules-Repo/com.clipboardfix/total?label=Downloads"></a>
<a href="https://github.com/Xposed-Modules-Repo/com.clipboardfix/releases/latest"><img alt="GitHub latest release" src="https://img.shields.io/github/v/release/Xposed-Modules-Repo/com.clipboardfix"></a>

<p>🛠️修复 HyperOS第三方输入法无法读取系统剪贴板历史内容的问题</p>

<p>
  <b>作者：</b>
  <b><a href="https://weibo.com/u/3725737792">李十六的日记本</a></b>&
  <b><a href="https://www.coolapk.com/u/3019478">江上晚</a></b>
  
</p>
</div>

---

## 📝模块说明

本模块主要修复HyperOS自动更新剪贴板和常用语V4.7.7后导致第三方输入法无法使用系统剪贴板的异常问题，由于小米在V4.7.7增加了严格的白名单验证，导致**第三方输入法**（微信输入法、豆包输入法 等）无法通过剪贴板面板查看系统剪贴板历史记录。

使用前应先解锁第三方输入法全面屏优化功能

## 📱本人已测且能正常使用的输入法

| 名称 |   版本号 |
|------|------------|
| 微信输入法 |   3.2.0   |
| 搜狗输入法 |   20.6.3   |
| 讯飞输入法 |   15.0.14   |
| QQ输入法 |   8.7.15  |

❌目前不支持百度输入法及最新版豆包输入法，百度输入法存在面板变形的情况，豆包输入法输入法会被抬高，这两个输入法目前无解

**测试都是基于以上版本进行测试的，理论可兼容所有版本，具体是否兼容请自行测试**

## 🤖使用方法

1. 安装本模块 APK
2. 在 LSPosed 中启用本模块
3. 作用域选择 **剪贴板和常用语**
4. 需要解锁第三方输入法全面屏优化功能请在Lsposed内勾选对应的输入法
5. 重启设备，必须重启手机，否则没有效果

## 💕特别提醒

使用过程中如果出现跨设备复制的内容不显示或者全面屏优化功能消失，请按照下面方法解决

1. 打开手机设置找到输入法设置，将输入法切换回内置的小爱输入法或搜狗输入法
2. 找个输入文本的界面让输入法弹出，然后点击系统的剪贴板界面，让剪贴板面板弹出
3. 返回桌面找到要使用的输入法长按进入软件应用信息界面后点击【结束运行】
4. 再次打开手机设置到输入法设置，将输入法切换回你要使用的输入法即可解决
5. 🤣为什么会这样我也不知道，你就这样做就行了🤣


## ❗注意事项

- 本模块仅修改剪贴板和常用语验证逻辑，不影响数据内容，请放心使用。
- 如果您的系统剪贴板功能正常请勿安装本模块！
- **本模块安装后需要重启手机才能生效，请确保您的设备已经安装了救砖模块**
- 无Root可以使用LSPatch(使用方式请自行到酷安寻找)
- 意见建议反馈请在 [酷安：江上晚](https://www.coolapk.com/u/3019478) [微博：李十六的日记本](https://weibo.com/u/3725737792)反馈

## 🔎相关链接

- 主仓库：[jiangshangwan/ClipboardFix](https://github.com/jiangshangwan/ClipboardFix)
