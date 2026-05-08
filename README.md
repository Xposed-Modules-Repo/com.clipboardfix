<div align="center">
<h1>澎湃OS剪贴板补全</h1>

<a href="https://github.com/Xposed-Modules-Repo/com.clipboardfix/releases"><img alt="GitHub all releases" src="https://img.shields.io/github/downloads/Xposed-Modules-Repo/com.clipboardfix/total?label=Downloads"></a>
<a href="https://github.com/Xposed-Modules-Repo/com.clipboardfix/releases/latest"><img alt="GitHub latest release" src="https://img.shields.io/github/v/release/Xposed-Modules-Repo/com.clipboardfix"></a>

<p>修复 HyperOS 3.0（澎湃OS）第三方输入法无法使用系统剪贴板历史的问题</p>

<p>
  <b>支持框架</b>：
  <b><a href="https://github.com/LSPosed/LSPosed">LSPosed</a></b>
</p>
</div>

---

## 功能说明

在 HyperOS 3.0（Android 15/16）上，小米对剪贴板内容提供者（com.miui.phrase）增加了严格的 UID 包名白名单验证，导致**第三方输入法**（微信键盘、Gboard 等）无法通过剪贴板面板查看系统剪贴板历史记录。

本模块通过 Xposed Hook 绕过以下限制：

- **包名白名单验证**：让第三方输入法被识别为已授权的系统输入法
- **CTA（隐私合规）检查**：移除跨设备剪贴板数据的访问限制
- **图片缩略图格式兼容**：将 WebP 格式的缩略图自动转换为 PNG，解决第三方面板无法渲染图片的问题
- **数据丢失保护**：防止系统服务覆盖用户剪贴板数据

## 兼容性

| 项目 | 要求 |
|------|------|
| 系统 | HyperOS 3.0（澎湃OS）/ Android 15+ |
| 框架 | LSPosed |
| 目标应用 | com.miui.phrase（系统剪贴板服务） |

## 安装

1. 安装本模块 APK
2. 在 LSPosed 中启用模块
3. 作用域选择 **系统框架**（或保持默认）
4. 重启设备

## 注意事项

- 本模块仅修改剪贴板内容提供者的验证逻辑，不影响数据内容
- 长按粘贴功能不受影响（走系统 ClipboardManager，不经过本 provider）
- 如遇到问题，请在 [Issues](https://github.com/Xposed-Modules-Repo/com.clipboardfix/issues) 反馈

## 相关项目

- 主仓库：[jiangshangwan/ClipboardFix](https://github.com/jiangshangwan/ClipboardFix)