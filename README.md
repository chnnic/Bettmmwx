# Bettmmwx

MiaoMiaoWuX 的独立主题与界面扩展集合。每个主题单独维护主控 CSS、TG Bot Mini App CSS、使用说明和资源，不混用不同端的样式。

## 预览

> 截图使用模拟数据：节点与链路名称为演示用名称，IP 使用 RFC 5737 / RFC 3849 文档地址段，流量与延迟为随机数值，不含任何真实服务器信息。

### Lumina 白金 / 黑金

| 桌面 · 首页（浅色） | 桌面 · 首页（深色） |
| --- | --- |
| ![Lumina 白金 / 黑金 首页浅色](themes/lumina/screenshots/home-light.jpg) | ![Lumina 白金 / 黑金 首页深色](themes/lumina/screenshots/home-dark.jpg) |

![Lumina 白金 / 黑金 转发链画布与 iperf3 面板](themes/lumina/screenshots/forward-canvas.jpg)

<p><img src="themes/lumina/screenshots/servers-mobile.jpg" alt="Lumina 白金 / 黑金 手机服务管理" width="300"> <img src="themes/lumina/screenshots/forward-mobile.jpg" alt="Lumina 白金 / 黑金 手机转发链" width="300"></p>

### PaperMint 薄荷纸境

| 桌面 · 首页（浅色） | 桌面 · 首页（深色） |
| --- | --- |
| ![PaperMint 薄荷纸境 首页浅色](themes/papermint/screenshots/home-light.jpg) | ![PaperMint 薄荷纸境 首页深色](themes/papermint/screenshots/home-dark.jpg) |

![PaperMint 薄荷纸境 转发链画布与 iperf3 面板](themes/papermint/screenshots/forward-canvas.jpg)

<p><img src="themes/papermint/screenshots/servers-mobile.jpg" alt="PaperMint 薄荷纸境 手机服务管理" width="300"> <img src="themes/papermint/screenshots/forward-mobile.jpg" alt="PaperMint 薄荷纸境 手机转发链" width="300"></p>

### Claude Paper 陶纸

| 桌面 · 首页（浅色） | 桌面 · 首页（深色） |
| --- | --- |
| ![Claude Paper 陶纸 首页浅色](themes/claude-paper/screenshots/home-light.jpg) | ![Claude Paper 陶纸 首页深色](themes/claude-paper/screenshots/home-dark.jpg) |

![Claude Paper 陶纸 转发链画布与 iperf3 面板](themes/claude-paper/screenshots/forward-canvas.jpg)

<p><img src="themes/claude-paper/screenshots/servers-mobile.jpg" alt="Claude Paper 陶纸 手机服务管理" width="300"> <img src="themes/claude-paper/screenshots/forward-mobile.jpg" alt="Claude Paper 陶纸 手机转发链" width="300"></p>

## 主题

手机用户管理卡片：“复制订阅”与同区其他按钮统一为 36px 高、14px 字并撑满半宽，长套餐名省略显示（Lumina v2026.10.04-02，PaperMint / 陶纸 v2026.10.04-01）。

Lumina v2026.10.04-01：移除只在主控“液态玻璃”界面风格下生效的专用样式（Lumina 已全局关闭背景模糊，玻璃效果早已不可见）；普通外观（含 PRO）显示不变，文件减至 61,247 字节。

本版 v2026.10.03-05：关闭全站动画与过渡（IP 滚动字幕、彩虹进度条、弹跳 / 脉冲图标、弹窗与菜单进出场、悬停渐变、平滑滚动），仅保留加载转圈，减轻手机卡顿；弹窗与菜单直接显示和关闭。CSS 末尾“减少动画”一段删除即可恢复。首页图表的脚本绘制动画不受 CSS 控制。

v2026.10.03-04：手机转发链卡片中新增的“画布编排”入口与编辑、服务器、删除按钮统一为 32×36px；Lumina 深度精简至 63,731 字节（等价写法与常量复用），逐元素计算样式比对 16 个页面快照、浅色 / 深色均无差异。

v2026.10.03-03：转发链“延迟探测”的逐跳结果、端到端路径和“iperf3 测速”历史结果中，长链路名称改为自动换行完整显示，不再省略；“最优 / #N”徽标保持横排。

v2026.10.03-02 改进桌面与手机易用性：手机图标按钮放大到 34px，复选框、开关、“解锁”图标和“点击…”文字按钮扩大触控范围；覆盖主控 PRO 模式缩小的顶部导航（13px）和首页卡片说明（12px）字号，10px 小字提到 11px；浅色模式加深证书“有效”徽标及绿色、琥珀、青色小字，Lumina、PaperMint 金色小标签改用深金色。按钮外观与业务操作不变；iPhone 真机仍需复测。

v2026.10.03-01：改进手机转发链画布：画布高度随屏幕计算，常见手机首屏可同时看到服务器池、整条链和缩放按钮；画布底部新增“按住此栏拖动画布”平移栏，空白画布仍用于滑动页面。连接点与“移出该组”按钮扩大触控范围，缩放按钮跟随深浅色主题，转发链列表标题在窄屏不再竖排。顶部 `--*-mobile-canvas-pan-strip` 为 `flex` 显示平移栏（默认），`none` 隐藏。桌面布局不变；iPhone 真机仍需复测，双指缩放画布需要主控前端支持。

v2026.10.03-02：手机转发画布改为上下三块，默认在空白画布上滑动页面可到达下方设置；节点拖动、编辑和缩放保留。顶部 `--*-mobile-canvas-pan-pointer-events` 默认为 `none`，改为 `auto` 恢复空白画布拖动。手机服务管理四个辅助按钮恢复两列两行，适配新版按钮包装层。桌面布局不变；本次只更新三套主控 CSS，TG Bot 文件不变。

手机转发链页面宽度与节点管理一致：767px 以下移除内层容器多余的两侧留白，保留卡片内边距和链路横向滚动；桌面布局不变。

转发链入口域名行与 IPv6 前缀行保留至少 88px 前缀输入宽度，长域名在右侧省略显示，下拉菜单保留完整选项；不修改实际域名或转发配置。

手机转发链表单中，名称全宽单独一行，端口范围与转发引擎并排下一行；桌面沿用原有布局。

| 主题 | 主控 CSS | TG Bot Mini App CSS | 说明 |
| --- | --- | --- | --- |
| Lumina 白金 / 黑金 | [controller.css](themes/lumina/controller.css) · v2026.10.04-02 | [tgbot.css](themes/lumina/tgbot.css) · v2026.09.21-02 | [安装与配置](themes/lumina/README.md) |
| PaperMint 薄荷纸境 | [controller.css](themes/papermint/controller.css) · v2026.10.04-01 | [tgbot.css](themes/papermint/tgbot.css) · v2026.09.21-01 | [安装与配置](themes/papermint/README.md) |
| Claude Paper 陶纸 | [controller.css](themes/claude-paper/controller.css) · v2026.10.04-01 | [tgbot.css](themes/claude-paper/tgbot.css) · v2026.10.01-01 | [安装与配置](themes/claude-paper/README.md) |

三套主控样式已合并服务卡片的“模式 / WS”外观，并让信息行保持单行。模式防误触开关继续有效，未修改连接模式、真实状态或菜单选项。

Lumina 使用暖金强调色和可选壁纸；PaperMint 使用圆角、描边、偏移硬阴影和粉彩辅助色；Claude Paper 是受 Claude 界面启发的非官方暖纸色主题，使用陶土橙和衬线标题。各主题兼容浅色与深色。

## 目录结构

```text
themes/
├── README.md                  # 新主题的目录与维护约定
├── lumina/
│   ├── README.md
│   ├── controller.css         # 主控
│   ├── tgbot.css              # Telegram Mini App
│   ├── screenshots/           # 模拟数据截图
│   └── assets/wallpaper.jpg
├── papermint/
│   ├── README.md
│   ├── controller.css
│   └── tgbot.css
└── claude-paper/
    ├── README.md
    ├── controller.css
    └── tgbot.css
extensions/
└── README.md                  # 未来可选功能的扩展约定
assets/
└── lumina-wallpaper.jpg       # 旧壁纸直链兼容副本
```

## 安装

主控自定义 CSS 上限为 65,536 个 UTF-8 字节（包含中文注释、换行和空格），不是字符数。三套主控文件已保留顶部配置格式并压缩其余正文：陶纸 53,822 字节、Lumina 61,537 字节、PaperMint 57,029 字节。后续修改建议控制在 65,000 字节以内；可用 `wc -c themes/*/controller.css` 检查。

先备份对应输入框里的旧 CSS，再打开需要的文件，点击 GitHub **Raw**，复制完整内容。

- **主控**：把 `controller.css` 粘贴到「系统设置 → 外观 → 自定义 CSS」并保存、刷新。
- **TG Bot Mini App**：把 `tgbot.css` 粘贴到「系统设置 → TG Bot → Mini App 自定义 CSS」并保存，然后重新打开 Telegram 内的 Mini App。该页提示保存会随 Bot 重启生效，请选择合适的时间操作，不要改动 Token、管理员 ID 等其他配置。

每个输入框只使用一套主题。不要把 `controller.css` 和 `tgbot.css` 合并，也不要叠加不同主题。可以只安装其中一端；尚未提供对应端的主题不能跨端混用。

这里的 TG Bot 主题只作用于机器人打开的 **Mini App 网页**，不会改变 Telegram 原生聊天气泡或 Bot 消息配色；两个入口的 CSS 相互独立。

主控自定义 CSS 的授权及版本要求见 [官方 CSS 文档](https://miaomiaowux.com/docs/custom-css/)，Mini App 的打开与认证方式见 [官方 TG Bot 文档](https://miaomiaowux.com/docs/tool-mmwx-tgbot/)。

## 配置与适配

每个 CSS 文件开头的第一个 `:root` 集中放置可调参数，主题目录的 README 逐项说明。PaperMint 主控使用 `--paper-*`，Mini App 使用 `--paper-mini-*`，不提供旧变量别名；更新时请完整替换对应 CSS，并同步自行追加的配置变量名。

- 主控：限宽、壁纸、描边、阴影、按钮高度、黑金水印及选中色。
- Mini App：独立的内容限宽、按钮高度、圆角；Lumina 可设置壁纸和模糊，PaperMint 可设置描边/阴影比例，Claude Paper 使用独立的 `--claude-mini-*` 深浅色与本地字体配置。
- 保留在线、警告、危险操作的语义颜色；开关保留可辨识的左右滑块。
- 服务卡片“自动”等模式菜单默认禁止鼠标/触屏点击；各主题首个 `:root` 中的 `--*-server-mode-pointer-events` 改为 `auto` 可恢复。不修改服务器配置，键盘仍可操作。
- 服务管理分组筛选框与相邻状态按钮等高；PaperMint 跟随自己的按钮减高配置与手机断点。
- 主控已包含套餐编辑、Xray 配置窄屏、探针说明挤压等布局修复。
- 转发链名称和操作按钮独占首行，链路使用下一整行；套餐节点、日志正文/事件表及代码预览区域重新分配显示空间。
- 手机二级窗口适配 URI 筛选、多列输入表单、套餐标签/节点列表、模板预览/代码与转发链滚动区域；手机规则不改变桌面布局。
- 三套主控主题均兼容新版管理页的页面级 `div.container`，中等窗口充分利用可用宽度，大屏仍遵守各主题的最大宽度配置。
- 手机/触屏轻量模式减少卡片阴影与常用控件过渡，保留加载反馈和内容；只针对 CSS 绘制开销，尚待浏览器与真机性能复测。

样式基于主控的组件属性与 Mini App 的实际 `.card`、`.btn`、`.xsw` 等钩子。主控升级后若组件结构变更，可能需要同步适配。建议使用支持 `:has()`、`color-mix()` 等语法的现代浏览器。

## 添加主题或功能

- 新主题添加到 `themes/<theme-id>/`，按 [主题约定](themes/README.md) 独立提供各端文件和说明。
- 未来跨主题可选功能添加到 `extensions/<feature-id>/`，按 [扩展约定](extensions/README.md) 声明作用端、依赖、加载顺序和回退方式。当前尚无功能扩展包。
- 主题默认应能独立使用；不要依赖其他主题的 CSS，也不要用远程 `@import` 拼接必须的功能文件。
- CSS 修改需更新头部版本与日期，格式为 `vYYYY.MM.DD-NN`。

## 路径迁移

原根目录的 `mmwx-lumina-platinum-gold.css`、`mmwx-papermint.css` 已分别迁入 `themes/lumina/controller.css`、`themes/papermint/controller.css`。更新收藏或下载链接即可，主控中已粘贴的 CSS 不受文件移动影响。

新 Lumina 使用主题目录内的壁纸直链，并锁定图片所在的提交版本，避免以后改分支或目录影响已安装的背景；旧 `assets/lumina-wallpaper.jpg` 保留兼容。更新图片时请同步更新 CSS 中的资源版本。

## 安全与验证边界

仓库仅包含样式、图片与说明，不包含主控地址、Bot Token、账号配置或许可证数据。不会自动安装、重启 Bot 或改变任何业务配置。

Mini App 样式依据实际页面的内置样式和组件钩子制作；使用无业务操作的静态样例验证布局，不代表已完成 Telegram 客户端中的登录与业务流程测试。不要为了预览样式而开启生产环境的开发调试认证选项。

Lumina 壁纸通过 GitHub Raw 加载，访问速度取决于网络；PaperMint 主控使用 Google Fonts，加载失败时回退系统字体，Mini App 版不依赖在线字体。替换图片或字体时请确保有使用权限。
