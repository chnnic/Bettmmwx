# 更新日志

## 2026-09-21 · 主题目录隔离与 Mini App 支持

- 各主题迁入 `themes/lumina/`、`themes/papermint/`，分别提供 `controller.css`、`tgbot.css` 与独立 README。
- 新增 Lumina / PaperMint TG Bot Mini App 主题，初始版本均为 `v2026.09.21-01`。
- Lumina 主控更新为 `v2026.09.21-03`，背景图片改用主题目录资源；旧资源直链保留兼容。
- PaperMint 主控样式仅移动路径，内容与 `v2026.09.21-03` 保持一致。
- 增加 `extensions/` 扩展约定，便于后续添加可选功能，不包含自动启用或安装逻辑。
- 按 Mini App 实际基础样式进行 48 组静态布局检查：两套主题、四组内置配色的深浅模式、320px / 390px / 1024px。检查无横向溢出、隐藏项保持隐藏、危险按钮保留红色、开关滑块可见。
- 验证范围仅为样式和静态布局；未修改线上 Bot 配置，未执行 Telegram 内的认证或业务操作。

## 2026-09-21 · 首次发布

- 发布 Lumina 白金 / 黑金与 PaperMint 薄荷纸境主题。
- 上传 Lumina 背景图片，提供安装和配置说明。
- LearnHub 更名为 PaperMint，主控 `--edu-*` 配置变量保持兼容。
