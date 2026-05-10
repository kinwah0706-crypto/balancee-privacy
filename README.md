# Grepu-Document

归朴 **Grepu** 在 **kanso.ltd** 上的静态站点与法务文案源码，仓库：[kinwah0706-crypto/Grepu-Document](https://github.com/kinwah0706-crypto/Grepu-Document)。

## 目录（发布结构）

| 路径 | 用途 |
|------|------|
| `privacy/` | 隐私政策（**URL 路径勿改**：与已上架 App 中 `Info.plist` 一致） |
| `terms/` | 使用条款：**`/terms/en/`**、**`/terms/zh/`**（与 `Info.plist` 中 `GREPU_TERMS_OF_USE_URL_*` 对齐） |
| `about/` | 品牌 / 关于页（如 `https://kanso.ltd/about`） |
| `legal/README.md` | 仅文档：说明「规划中的 legal 索引」与线上 URL 对应关系 |
| `CNAME` | GitHub Pages 自定义域：`kanso.ltd` |
| `index.html` | 根路径重定向至 `/privacy/en/` |

## App 与 App Store 使用的 URL

- 隐私政策（当前工程配置）：**`https://kanso.ltd/privacy/en/`**
- 使用条款（英文）：**`https://kanso.ltd/terms/en/`**
- 使用条款（中文）：**`https://kanso.ltd/terms/zh/`**

## GitHub Pages 部署（摘要）

1. 仓库 **Settings → Pages**：Source 选 `main` 分支、`/` root。  
2. Custom domain：`kanso.ltd`，建议启用 **Enforce HTTPS**。  
3. DNS：按 [GitHub Pages 自定义域文档](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site) 配置 `A` / `CNAME`。  

推送 `main` 后数分钟内站点会更新。

## 维护注意

- 修改 **`privacy/`、`terms/` 的 URL 路径或文件名** 前，须与 **iOS 工程 `Info.plist` 中 `GREPU_*_URL_*`** 及 **已提交审核版本** 对齐。  
- 正文中的 **App 名称**、**生效日期**、**联系邮箱** 请与 App 内嵌文案及上架材料保持一致（当前联系邮箱：**support@kanso.ltd**）。
