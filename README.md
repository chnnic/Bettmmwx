# Bettmmwx

为 MiaoMiaoWuX 主控提供两套独立、可直接粘贴使用的自定义 CSS 主题：**Lumina** 与 **LearnHub**。

这是社区样式项目，不是主控程序，也不是独立探针项目。仅调整页面外观和布局，不修改节点、服务器、用户或 Xray 业务配置。

## 选择主题

- [Lumina 白金 / 黑金](./mmwx-lumina-platinum-gold.css) — `v2026.09.21-02`
  暖金强调色、浅色与深色适配、可选壁纸，以及对主控液态玻璃外观的专项适配。
- [LearnHub](./mmwx-learnhub.css) — `v2026.09.21-02`
  圆角控件、深色描边、偏移硬阴影和粉彩辅助色；选中颜色跟随主控当前主题。

两套 CSS **二选一，不要叠加**。切换时完整替换自定义 CSS 输入框中的内容。

## 安装与更新

1. 先备份主控当前的自定义 CSS。
2. 打开上方任意一个 CSS 文件，点击 GitHub 的 **Raw**，复制完整内容。
3. 在主控进入 **系统设置 → 外观 → 自定义 CSS**。
4. 粘贴全部内容，点击该 CSS 配置区域的 **保存**。
5. 刷新页面检查效果；更新时按同样步骤完整替换。

若主控没有自定义 CSS 入口或样式未生效，请先确认使用的主控版本与许可证支持该功能。使用说明以 [MiaoMiaoWuX 官方文档](https://miaomiaowux.com/docs/custom-css/) 为准。

## 常用配置

配置项集中在每个文件开头的第一个 `:root` 中，直接修改变量即可。

### Lumina

- `--lumina-content-max-width: 1440px`：页面最大宽度，可改为 `1600px` 或 `100%`。
- `--lumina-wallpaper`：默认使用本仓库 [背景图片](./assets/lumina-wallpaper.jpg) 的 GitHub 原始文件直链；改为 `none` 关闭图片背景，或自行填写 `url("你的图片地址")`。
- `--lumina-background-attachment: fixed`：背景固定；改为 `scroll` 可随页面滚动。
- `--lumina-card-hover-stripes: 0`：关闭卡片斜纹；`1` 开启。
- `--lumina-premium-watermark-display: none`：关闭 Premium 水印；`block` 开启。

### LearnHub

- `--edu-content-max-width: 1440px`：页面最大宽度；`100%` 不限宽。
- `--edu-button-height-reduction: 4px`：按钮减高 4px；`0px` 恢复。
- `--edu-effect-scale: 0.666667`：描边和阴影减少约三分之一；`1` 恢复原强度。
- `--edu-premium-watermark-display: none`：关闭黑金水印；`block` 开启。
- `--edu-premium-accent-bg` / `--edu-premium-accent-fg`：黑金选中控件的背景和文字颜色。
- `--edu-premium-selection-bg`：黑金文字选区颜色；原生文字选区使用实色，不使用渐变。

## 已包含的布局修复

- 大型套餐编辑窗口不再在中等宽度下被限制到 512px。
- Xray 配置窗口自适应宽度，手机抽屉保持完整可用宽度。
- Xray 长版本信息和服务控制按钮组在窄屏换行。
- 伪装探针说明与表单在空间不足时上下排列，避免文字被挤成细长列。
- 节点表格操作图标与名称及附加信息整体居中。
- LearnHub 的开关滑块、紧凑国旗按钮、续费按钮排列和手机节点卡片适配。

## 注意事项

- 建议使用支持 `:has()`、`color-mix()` 和现代 CSS 布局的浏览器。
- 部分样式依赖主控的 `data-slot` 和组件类名；主控升级后若布局变化，可能需要同步调整选择器。
- LearnHub 使用 Google Fonts 在线字体；无法加载时会使用系统字体。
- 仓库不包含主控地址、账户配置、令牌或许可证信息。
- Lumina 背景图片随仓库一起维护，不再依赖个人图床。图片使用 GitHub Raw 直链，加载情况取决于访问 GitHub 的网络；自行替换图片时请确保有使用权限。
- 修改 CSS 后，请同步更新文件头部的版本号与日期，格式为 `vYYYY.MM.DD-NN`。
