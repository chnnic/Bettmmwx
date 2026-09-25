# Bettmmwx

MiaoMiaoWuX 的独立主题与界面扩展集合。每个主题单独维护主控 CSS、TG Bot Mini App CSS、使用说明和资源，不混用不同端的样式。

## 主题

| 主题 | 主控 CSS | TG Bot Mini App CSS | 说明 |
| --- | --- | --- | --- |
| Lumina 白金 / 黑金 | [controller.css](themes/lumina/controller.css) · v2026.09.25-01 | [tgbot.css](themes/lumina/tgbot.css) · v2026.09.21-02 | [安装与配置](themes/lumina/README.md) |
| PaperMint 薄荷纸境 | [controller.css](themes/papermint/controller.css) · v2026.09.25-01 | [tgbot.css](themes/papermint/tgbot.css) · v2026.09.21-01 | [安装与配置](themes/papermint/README.md) |

Lumina 使用暖金强调色和可选壁纸；PaperMint 使用圆角、描边、偏移硬阴影和粉彩辅助色。两套主题均兼容浅色与深色。

## 目录结构

```text
themes/
├── README.md                  # 新主题的目录与维护约定
├── lumina/
│   ├── README.md
│   ├── controller.css         # 主控
│   ├── tgbot.css              # Telegram Mini App
│   └── assets/wallpaper.jpg
└── papermint/
    ├── README.md
    ├── controller.css
    └── tgbot.css
extensions/
└── README.md                  # 未来可选功能的扩展约定
assets/
└── lumina-wallpaper.jpg       # 旧壁纸直链兼容副本
```

## 安装

先备份对应输入框里的旧 CSS，再打开需要的文件，点击 GitHub **Raw**，复制完整内容。

- **主控**：把 `controller.css` 粘贴到「系统设置 → 外观 → 自定义 CSS」并保存、刷新。
- **TG Bot Mini App**：把 `tgbot.css` 粘贴到「系统设置 → TG Bot → Mini App 自定义 CSS」并保存，然后重新打开 Telegram 内的 Mini App。该页提示保存会随 Bot 重启生效，请选择合适的时间操作，不要改动 Token、管理员 ID 等其他配置。

每个输入框只使用一套主题。不要把 `controller.css` 和 `tgbot.css` 合并，也不要叠加 Lumina 与 PaperMint。可以只安装其中一端。

这里的 TG Bot 主题只作用于机器人打开的 **Mini App 网页**，不会改变 Telegram 原生聊天气泡或 Bot 消息配色；两个入口的 CSS 相互独立。

主控自定义 CSS 的授权及版本要求见 [官方 CSS 文档](https://miaomiaowux.com/docs/custom-css/)，Mini App 的打开与认证方式见 [官方 TG Bot 文档](https://miaomiaowux.com/docs/tool-mmwx-tgbot/)。

## 配置与适配

每个 CSS 文件开头的第一个 `:root` 集中放置可调参数，主题目录的 README 逐项说明。PaperMint 主控使用 `--paper-*`，Mini App 使用 `--paper-mini-*`，不提供旧变量别名；更新时请完整替换对应 CSS，并同步自行追加的配置变量名。

- 主控：限宽、壁纸、描边、阴影、按钮高度、黑金水印及选中色。
- Mini App：独立的内容限宽、按钮高度、圆角；Lumina 可设置壁纸和模糊，PaperMint 可设置描边/阴影比例。
- 保留在线、警告、危险操作的语义颜色；开关保留可辨识的左右滑块。
- 主控已包含套餐编辑、Xray 配置窄屏、探针说明挤压等布局修复。

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
