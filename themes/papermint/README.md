# PaperMint 薄荷纸境

圆角卡片、深色描边、偏移硬阴影与粉彩辅助色。

- [controller.css](controller.css)：主控完整样式，`v2026.09.23-01`。
- [tgbot.css](tgbot.css)：TG Bot Mini App 完整样式，`v2026.09.21-01`。

## 安装

主控文件放入「系统设置 → 外观 → 自定义 CSS」；TG Bot 文件放入「系统设置 → TG Bot → Mini App 自定义 CSS」。分别完整替换并保存，不要合并两端文件或与其他主题叠加。

保存 TG Bot 配置会随 Bot 重启生效，请只修改 CSS 字段，保留其他配置。安装后重新打开 Telegram 内的 Mini App。

## 主控参数

主控统一使用 `--paper-*` 变量，Mini App 使用 `--paper-mini-*`，不提供旧变量别名。更新时请完整替换对应 CSS；自行追加的配置也须使用新变量名。

- `--paper-content-max-width`：默认 `1440px`，`100%` 不限宽。
- `--paper-button-height-reduction`：默认 `4px`，`0px` 恢复原按钮高度。
- `--paper-effect-scale`：默认 `0.666667`，描边和阴影减少约三分之一。
- `--paper-premium-watermark-display`：`none` 关闭黑金水印，`block` 开启。
- `--paper-premium-accent-bg` / `--paper-premium-accent-fg`：黑金选中态配色。
- `--paper-premium-selection-bg`：黑金文字选区颜色。

新版节点管理的表格快捷操作保持单行，保留按钮尺寸与顺序；手机卡片布局不受影响。

## Mini App 参数

- `--paper-mini-content-max-width`：默认 `900px`，小屏自动适配。
- `--paper-mini-button-height`：普通按钮默认 `40px`，不缩放开关滑块。
- `--paper-mini-radius`：默认 `16px`。
- `--paper-mini-effect-scale`：默认 `0.666667`，控制描边和硬阴影。
- `--paper-mini-premium-accent`：黑金主题选中态的金色渐变。
- `--paper-mini-font`：本地字体栈，不额外请求在线字体。

Mini App 默认使用薄荷色；`theme-anime` 使用紫色、`theme-glass` 使用蓝色、`theme-premium` 使用金色。浅色与 `html.dark` 均支持；PaperMint 卡片始终关闭背景模糊和装饰纹理，保留自身纸感。

## 验证与边界

样式适配实际 Mini App 组件，使用静态样例检查深浅色、320px/390px/大屏、长文字、六项导航、危险按钮及开关左右滑块。不会修改开关状态、认证或业务配置；完整 Telegram 客户端流程仍需在安装后验证。

主控版的 Google Fonts 可能受网络影响，失败时使用系统字体；Mini App 版没有在线字体或背景图片依赖。TG Bot 主题不改变 Telegram 原生聊天气泡。
