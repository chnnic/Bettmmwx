# Claude Paper · 陶纸

受 Claude 界面启发的非官方主控与 TG Bot Mini App 主题。暖米白背景、陶土橙强调色、衬线标题与细边线；深色模式使用暖炭灰。不是 Anthropic 官方产品，不替换主控标识。

- [controller.css](controller.css)：主控完整样式，`v2026.09.29-02`。
- [tgbot.css](tgbot.css)：TG Bot Mini App 完整样式，`v2026.10.01-01`；不要与主控文件混用。
- 独立文件，不依赖 Lumina、PaperMint、远程字体、图片或 JavaScript。

## 安装

备份对应字段的旧 CSS，每个输入框只完整粘贴一套主题，不要叠加。

- 主控：将 `controller.css` 完整替换到「系统设置 → 外观 → 自定义 CSS」，保存后刷新。
- TG Bot Mini App：将 `tgbot.css` 完整替换到「系统设置 → TG Bot → Mini App 自定义 CSS」，保存后重新打开 Telegram 内的 Mini App。保存可能触发 Bot 热重启，请选择合适时机；不要改动 Token、管理员 ID 等其他配置。

两端样式分别保存，更新主控 CSS 不会自动更新 Mini App。Mini App 主题不改变 Telegram 原生聊天气泡或 Bot 消息配色。

跟随主控的浅色 / 深色切换；无须切换主控基底主题。内置风格的配色统一为陶纸，但危险、警告等状态仍保留语义色。

## 主控顶部配置

可调参数集中在第一个 `:root`，均以 `--claude-*` 命名。

| 参数 | 默认值 / 用途 |
| --- | --- |
| `--claude-content-max-width` | `1440px`；`100%` 不限宽 |
| `--claude-card-radius` | `16px`，卡片和弹窗圆角 |
| `--claude-control-radius` | `9px`，按钮和输入框圆角 |
| `--claude-light-page` / `--claude-dark-page` | 深浅模式页面底色 |
| `--claude-light-surface` / `--claude-dark-surface` | 深浅模式面板底色 |
| `--claude-light-ink` / `--claude-dark-ink` | 深浅模式正文颜色 |
| `--claude-light-accent` / `--claude-dark-accent` | 深浅模式主按钮与强调色 |
| `--claude-body-font` | 本地无衬线字体，负责表格、正文和操作区 |
| `--claude-heading-font` | 本地衬线字体，负责页面和弹窗标题；可改为 `var(--claude-body-font)` |

卡片与控件不使用背景模糊、背景图片、悬停位移或偏移硬阴影。保留轻阴影、键盘焦点轮廓、禁用态、开关滑块以及主控原生按钮高度。

顶栏“更多”折叠菜单采用无底色菜单项，悬停与键盘选中使用中性色，不套用陶土橙主按钮背景。

## Mini App 顶部配置

参数集中在 `tgbot.css` 第一个 `:root`，使用独立的 `--claude-mini-*`，不依赖主控变量。

| 参数 | 默认值 / 用途 |
| --- | --- |
| `--claude-mini-content-max-width` | `900px`；`100%` 不限宽 |
| `--claude-mini-button-height` | `40px`，普通按钮最小高度，不改变开关尺寸 |
| `--claude-mini-card-radius` / `--claude-mini-control-radius` | `16px` / `9px` |
| `--claude-mini-light-page` / `--claude-mini-dark-page` | 深浅页面底色 |
| `--claude-mini-light-surface` / `--claude-mini-dark-surface` | 深浅卡片、输入框及导航底色 |
| `--claude-mini-light-ink` / `--claude-mini-dark-ink` | 深浅正文颜色 |
| `--claude-mini-light-accent` / `--claude-mini-dark-accent` | 深浅强调色 |
| `--claude-mini-light-accent-text` / `--claude-mini-dark-accent-text` | 强调色按钮的文字颜色，修改强调色时一起核对对比度 |
| `--claude-mini-body-font` / `--claude-mini-heading-font` | 本地正文字体 / 统计数字衬线字体 |

Mini App 使用实色纸面，不加载壁纸、在线字体或背景模糊；底部选中导航采用浅强调色，不使用整块高饱和主按钮背景。开关保留白色滑块，在线状态仍为绿色，危险操作与提示仍为红色，未知状态保持中性。保留 `.hide`、禁用态、键盘焦点和底部安全区域。

## 适配范围

包含已有的节点操作单行、手机节点名称、用户续期按钮、探针说明布局、套餐双栏、Xray 窄屏以及二级窗口内部留白修复。标签过多时保留滚动，不强制显示原本隐藏的组件，不改变业务表单或权限。

主控升级可能改变组件结构；样式使用 `:has()`、`color-mix()` 等现代 CSS。不同系统的本地衬线字体会略有差异；不加载第三方字体来强求一致。

## 本版验证

已在独立浏览器标签中临时预览首页、节点管理与系统开关，检查五种内置基底的深浅纸面、390px 首页及节点名称。120 项选择器通过当前浏览器的语法支持检查；浅色主按钮文字对比度约 4.71:1，深色约 7.04:1。未执行业务写操作，未验证全部业务弹窗或登录流程。

已部署主控并刷新核对：保存字段、页面下发样式与本文件一致，其他外观字段和开关未变；原 CSS 已备份。

Mini App 版依据 2026-10-01 实际 `/tg-app` 的原生样式钩子制作，使用原生底层 CSS 与无业务数据的静态样例验证。320 / 390 / 768 / 1200px、默认 / anime / glass / premium 基底的深浅色共 32 组检查无横向溢出，六项导航、限宽、隐藏态、禁用态、开关滑块和焦点正常；浏览器选择器语法检查、高对比度和减少动态效果检查通过。未在 Telegram 客户端中验证认证、兑换、订阅或服务器控制流程，不开启调试认证选项。

Mini App 文件发布与生产部署分开；本次未保存生产配置或重启 Bot，安装时需单独更新 Mini App 自定义 CSS。
