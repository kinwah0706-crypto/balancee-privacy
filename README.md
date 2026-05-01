# Balancee 隐私政策站点 (kanso.ltd)

本目录为 Balancee 应用隐私政策的静态站点，用于部署到 **kanso.ltd**，供 App Store 及应用内「隐私政策」链接使用。

**不熟悉 Git / 部署？** 请直接看 **[零基础部署指南.md](./零基础部署指南.md)**，按步骤操作即可；也可使用目录下的 **deploy.sh** 一键推送。

## 部署方式一：GitHub Pages（推荐）

### 1. 创建 GitHub 仓库

- 新建一个**公开**仓库，例如 `balancee-privacy` 或 `balancee-website`。
- 不要勾选「Add a README」，保持空仓库（若已有内容也可直接推送）。

### 2. 只推送本目录内容

在本地执行（将 `YOUR_USERNAME` 和 `balancee-privacy` 换成你的用户名和仓库名）：

```bash
cd /Users/aimo/Documents/Cursor/Kanso/website
git init
git add index.html privacy/ CNAME README.md
git commit -m "Add privacy policy page for kanso.ltd"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/balancee-privacy.git
git push -u origin main
```

### 3. 开启 GitHub Pages 并绑定域名

1. 仓库内：**Settings → Pages**。
2. **Source** 选 **Deploy from a branch**。
3. **Branch** 选 `main`，目录选 **/ (root)**，保存。
4. 若 **Custom domain** 未自动出现：在 Pages 设置里找到 **Custom domain**，填写 `kanso.ltd`，保存。
5. 建议勾选 **Enforce HTTPS**（证书由 GitHub 自动签发）。

### 4. 在域名商处配置 DNS

在购买 **kanso.ltd** 的域名服务商控制台（如阿里云、腾讯云、Cloudflare、Namecheap 等）添加解析：

| 类型  | 主机记录 | 记录值 |
|-------|----------|--------|
| **A** | `@`      | `185.199.108.153` |
| **A** | `@`      | `185.199.109.153` |
| **A** | `@`      | `185.199.110.153` |
| **A** | `@`      | `185.199.111.153` |
| **CNAME** | `www` | `YOUR_USERNAME.github.io` |

（`YOUR_USERNAME` 换成你的 GitHub 用户名；若只用根域名 `kanso.ltd`，可只配 4 条 A 记录。）

保存后等待几分钟到几十分钟生效。隐私政策页地址见下方 URL。

---

## 部署方式二：Vercel

1. 注册 [Vercel](https://vercel.com)，安装 Vercel CLI 或使用网页导入。
2. 在项目根目录或 `website` 目录执行 `vercel`，按提示部署。
3. 在 Vercel 项目 **Settings → Domains** 添加 `kanso.ltd`。
4. 按 Vercel 提示在域名商处添加 **A** 或 **CNAME** 记录。

---

## 上架前请在本页完成替换

在 `privacy/index.html`（中文）和 `privacy/en/index.html`（英文）中请替换以下占位内容：

- **生效日期**：如 `2025 年 3 月 1 日`
- **提供方**：公司/团队/开发者名称
- **联系邮箱**：在「五、联系我们」中的邮箱地址

替换后重新提交并推送，GitHub Pages 会自动更新。

---

## 在 App 与 App Store 中使用的 URL

- **中文（中国区等）隐私政策**：`https://kanso.ltd/privacy` 或 `https://kanso.ltd/privacy/`
- **英文（海外上架）隐私政策**：`https://kanso.ltd/privacy/en` 或 `https://kanso.ltd/privacy/en/`

根路径 `https://kanso.ltd` 会自动跳转到 `https://kanso.ltd/privacy/`。在 App Store Connect 的「App 信息」中按地区填写对应 URL；应用内设置/关于页可提供同一链接，或根据系统语言跳转中/英页面。
