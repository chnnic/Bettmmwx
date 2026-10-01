# PaperMint 薄荷纸境

圆角卡片、深色描边、偏移硬阴影与粉彩辅助色。

- [controller.css](controller.css)：主控完整样式，`v2026.10.01-04`。
- [tgbot.css](tgbot.css)：TG Bot Mini App 完整样式，`v2026.09.21-01`。

## 安装

主控文件放入「系统设置 → 外观 → 自定义 CSS」；TG Bot 文件放入「系统设置 → TG Bot → Mini App 自定义 CSS」。分别完整替换并保存，不要合并两端文件或与其他主题叠加。

保存 TG Bot 配置会随 Bot 重启生效，请只修改 CSS 字段，保留其他配置。安装后重新打开 Telegram 内的 Mini App。

## 主控参数

主控统一使用 `--paper-*` 变量，Mini App 使用 `--paper-mini-*`，不提供旧变量别名。更新时请完整替换对应 CSS；自行追加的配置也须使用新变量名。

- `--paper-content-max-width`：默认 `1440px`，`100%` 不限宽。
- `--paper-content-gutter`：默认 `24px`，控制 640px 及以上的页面两侧内边距。
- `--paper-button-height-reduction`：默认 `4px`，`0px` 恢复原按钮高度。
- `--paper-effect-scale`：默认 `0.666667`，描边和阴影减少约三分之一。
- `--paper-premium-watermark-display`：`none` 关闭黑金水印，`block` 开启。
- `--paper-premium-accent-bg` / `--paper-premium-accent-fg`：黑金选中态配色。
- `--paper-premium-selection-bg`：黑金文字选区颜色。

内容限宽兼容新版管理页的页面级 `div.container`，不再被断点缩成窄列。窗口宽度达到 `640px` 时，两侧内边距由 `--paper-content-gutter` 控制，默认各 `24px`；手机保留主控原生间距。最大宽度配置不变，弹窗与嵌套容器不受这条适配影响。

新版节点管理的表格快捷操作保持单行，保留按钮尺寸与顺序；手机卡片布局不受影响。

探针设置的说明与表单在宽屏均分两列，窄屏自动上下排列；兼容新版响应式布局及开关外层的 `label` / `div` 结构，不改变开关或域名配置。

套餐编辑弹窗为右栏和底部按钮留出阴影及焦点安全边距；中等宽度下右栏按可用空间收缩，标签较多时可滚动，避免“全选”“取消”“保存”被裁切。

同样为 Xray / 网站管理分页、入站向导、节点导入和模板预览补齐安全留白；保留原按钮尺寸、硬阴影与滚动裁切。节点导入的标签过多时可整体滚动，列表保留最小可操作高度。

## 手机轻量模式

服务管理分组框与在线/离线按钮等高：默认桌面 38px、手机 40px，跟随 `--paper-button-height-reduction`，不低于相邻按钮原生高度。服务卡片的“自动”等模式菜单默认防误触：第一个 `:root` 中 `--paper-server-mode-pointer-events: none` 禁止鼠标/触屏点击，`auto` 恢复。不修改服务器模式，不影响 Agent / Xray 配置；不是原生 disabled，键盘仍可操作。

宽度不超过 `767px`，或设备为无悬停的粗指针触屏时启用：

- `--paper-mobile-motion-duration: 0s`：卡片、常用控件、开关与进度条的过渡时长；可改为 `120ms` 恢复短过渡。
- `--paper-mobile-card-shadow`：手机卡片阴影，可在第一个 `:root` 中调整。
- 停止卡片本体的装饰动画；加载 SVG、弹窗/抽屉开合、焦点和禁用状态仍保留，不隐藏列表内容。

手机卡片改用不透明底色与单层硬阴影，关闭常见面板的背景模糊，纸面背景随页面滚动；卡片、按钮与侧栏的位移/滤镜悬停效果仅对可悬停的精确指针设备生效。

这是 CSS 绘制效果的减负，不降低主控数据刷新频率，也不优化业务脚本。已完成语法与规则范围检查；手机渲染、滚动与真机帧率尚待验证，不承诺具体提速比例。

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
