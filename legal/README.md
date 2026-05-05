# `legal/` — 内容索引（规划用）

本目录**不参与** GitHub Pages 的默认站点根路径映射。对外可见的 URL 由仓库**根目录下**的文件夹名称决定（部署到 **kanso.ltd** 后路径一致）。

| 对外 URL（示例） | 仓库内发布路径 | 说明 |
|------------------|----------------|------|
| `https://kanso.ltd/privacy/en/` | `privacy/en/index.html` | 英文隐私政策（App / App Store 英文区） |
| `https://kanso.ltd/privacy/` | `privacy/index.html` | 当前重定向至 `/privacy/en/` |
| `https://kanso.ltd/terms/en/` | `terms/en/index.html` | 英文使用条款 |
| `https://kanso.ltd/terms/` | `terms/index.html` | 重定向至 `/terms/en/` |

后续若增加中文静态页，可采用 `privacy/zh/index.html`、`terms/zh/index.html`，并在不破坏已提审 URL 的前提下更新根目录 `privacy/`、`terms/` 的跳转逻辑。

若要在此目录放 **Markdown 源稿** 再生成 `privacy/`、`terms/` 下的 HTML，可单独加构建脚本（本仓库当前为手写静态 HTML）。
