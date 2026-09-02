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

在 HyperOS 3.0（Android 16）+上，系统应用「剪贴板与常用语V4.7.7」应用会阻止第三方输入法（如微信输入法等）访问剪贴板历史数据。官方内置输入法（搜狗小米定制版、讯飞小米定制版、百度小米定制版、小米智能输入法）不受影响。

此外，系统的「全面屏优化」默认只对官方定制输入法开放，第三方输入法不显示底部常用语 / 剪贴板入口。本模块一并解锁。

## 💡原理

**剪贴板修复**：「剪贴板与常用语V4.7.7」的 `InputProvider` 通过 `PackageManager.getNameForUid(callingUid)` 获取调用者包名，与白名单比对后决定是否允许访问。本模块 hook `PackageManager.getNameForUid()` 和 `getPackagesForUid()`，对非白名单的第三方输入法返回白名单包名，从而绕过验证。

**全面屏优化解锁**：在输入法进程内 hook `InputMethodServiceInjector`，将 `sIsImeSupport` 置位并让 `isImeSupport()` 恒返回 true 以跳过包名检查；在 system_server 内放行输入法权限校验，修复切换输入法列表被裁剪的问题。


## 📱本人已测且能正常使用的输入法

| 名称 |   版本号 |
|------|------------|
| 微信输入法 |   3.2.0   |
| 搜狗输入法 |   20.6.3   |
| 讯飞输入法 |   15.0.14   |
| QQ输入法 |   8.7.15  |

❌目前不支持百度输入法及最新版豆包输入法，百度输入法存在面板变形的情况，豆包输入法输入法会被抬高，这两个输入法目前无解

**测试都是基于以上版本进行测试的，理论可兼容所有版本，具体是否兼容请自行测试**

## 🤖安装说明

### 🌡️环境要求

- 已 Root 的小米 / 红米手机，HyperOS 3.0+
- 剪贴板和常用语 V4.7.7+
- **LSPosed 框架需支持 libxposed 新版模块 API（API 102）**，例如 Vector v2.2 及以上
  - 在 LSPosed 管理器首页「已激活」下方可以看到当前框架的 API 版本
  - 本模块基于新版 API 开发，与旧的 `de.robv.android.xposed` 不兼容

### ⌨操作步骤

1. 在 LSPosed 中启用本模块
2. 勾选作用域：
   - **剪贴板和常用语**（`com.miui.phrase`）—— 剪贴板修复必需
   - **当前使用的第三方输入法** —— 全面屏优化必需
   - **系统框架**（`system`）—— 用于放行输入法权限，建议一并勾选
3. 安装后请重启手机，否则不起作用

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
