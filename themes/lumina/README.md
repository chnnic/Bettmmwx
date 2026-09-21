# Lumina 白金 / 黑金

暖金强调色、白金浅色与黑金深色，搭配独立壁纸和轻薄边线。

- [controller.css](controller.css)：主控完整样式，`v2026.09.21-04`。
- [tgbot.css](tgbot.css)：TG Bot Mini App 完整样式，`v2026.09.21-02`。
- [assets/wallpaper.jpg](assets/wallpaper.jpg)：两端共用的背景图。

## 安装

主控文件放入「系统设置 → 外观 → 自定义 CSS」；TG Bot 文件放入「系统设置 → TG Bot → Mini App 自定义 CSS」。分别完整替换并保存，不要把两端文件合并。

保存 TG Bot 配置会随 Bot 重启生效。只修改 CSS 字段，保留原有 Token、管理员 ID 和开关。安装后重新打开 Telegram 内的 Mini App。

## 主控参数

- `--lumina-wallpaper`：默认使用本目录壁纸的固定提交版本 GitHub Raw 直链，改为 `none` 关闭；换图时同步更新资源版本。
- `--lumina-content-max-width`：默认 `1440px`，可设置 `1600px` 或 `100%`。
- `--lumina-background-attachment`：`fixed` 固定背景，`scroll` 随页面滚动。
- `--lumina-card-hover-stripes`：`0` 关闭悬停斜纹，`1` 开启。
- `--lumina-premium-watermark-display`：`none` 关闭黑金水印，`block` 开启。

## Mini App 参数

- `--lumina-mini-wallpaper`：默认使用相同背景图，`none` 关闭图片。
- `--lumina-mini-background-attachment`：默认 `scroll`，减少手机固定背景重绘。
- `--lumina-mini-content-max-width`：默认 `900px`，只限制大屏，小屏仍使用可用宽度。
- `--lumina-mini-button-height`：默认 `40px`，开关不受普通按钮高度影响。
- `--lumina-mini-radius`：卡片圆角，默认 `14px`。
- `--lumina-mini-blur`：默认 `0px`，可设 `14px`；频繁更新的卡片建议关闭模糊。
- `--lumina-mini-accent` / `--lumina-mini-accent-text`：金色渐变与其文字颜色。
- `--lumina-mini-selection`：文字选区的实金色。

Mini App 依据 `html.dark` 切换深浅色，覆盖内置主题的表面配色；保留在线、危险按钮和未知状态的语义色。底部导航、分段选中、进度条与开关开启态使用金色。

## 验证与边界

样式适配真实 Mini App 的组件结构，并用静态样例检查手机/大屏、深浅色、长链接、六项管理员导航、开关滑块和危险按钮。不修改认证或业务逻辑；完整 Telegram 客户端流程仍需在安装后验证。

旧版根目录壁纸保留兼容副本，新版本统一引用主题目录资源。TG Bot 主题只改变 Mini App 网页，不改变 Telegram 原生聊天界面。
