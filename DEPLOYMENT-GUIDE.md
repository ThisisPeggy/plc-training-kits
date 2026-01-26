# 🚀 部署指南 - 从 GitHub 到 Vercel

## 前置要求
- GitHub 账户
- Vercel 账户（免费）
- 域名已购买（例如：plc-training-kits.com）

---

## 📋 步骤 1：初始化 Git 仓库

```bash
cd /Users/peggy/Desktop/weibsite/Website

# 初始化 git
git init

# 添加所有文件
git add .

# 提交
git commit -m "Initial commit: PLC Training Kits Website"

# 添加远程仓库（替换 username 和 repo-name）
git remote add origin https://github.com/username/plc-training-kits.git

# 推送到 GitHub
git branch -M main
git push -u origin main
```

---

## 📋 步骤 2：在 Vercel 上部署

### 方法 A：使用 Vercel CLI（推荐）

```bash
# 安装 Vercel CLI
npm i -g vercel

# 在项目文件夹运行
vercel

# 按照提示完成：
# 1. 选择 "Create a new project"
# 2. 输入项目名称
# 3. 选择 GitHub（连接账户）
# 4. 部署完成！
```

### 方法 B：在 Vercel 网站连接 GitHub（更简单）

1. 访问 https://vercel.com
2. 点击 "New Project"
3. 选择 GitHub 仓库 (plc-training-kits)
4. 点击 "Import"
5. 保持默认设置，点击 "Deploy"
6. 等待部署完成（通常 1-2 分钟）

---

## 📋 步骤 3：配置自定义域名

### 在 Vercel 中添加域名：

1. 项目设置 → 域名
2. 点击 "Add Domain"
3. 输入你的域名：`plc-training-kits.tech`
4. 选择 DNS 提供商（GoDaddy、Namecheap 等）
5. 按照指示更新 DNS 记录

### DNS 记录配置：

如果域名在 GoDaddy/Namecheap，添加这些 DNS 记录：

```
Type: CNAME
Name: www
Value: cname.vercel-dns.com

Type: A
Name: @
Value: 76.76.19.131
```

---

## 📋 步骤 4：启用 HTTPS

Vercel 会自动为你的域名申请和启用 SSL 证书（免费）。

查看 "Domains" 标签，确保显示 "Valid Certificate"。

---

## 🔄 自动部署（持续集成）

一旦连接 GitHub，每当你 push 代码到 main 分支，Vercel 会自动：
1. 构建项目
2. 运行测试（如有）
3. 部署新版本

不需要任何手动操作！

---

## 📊 查看部署状态

- **Vercel 仪表板：** https://vercel.com/dashboard
- **实时日志：** 项目 → Deployments → 选择部署 → Logs
- **网站访问：** https://plc-training-kits.tech

---

## ⚠️ 常见问题

### Q1：404 错误
**A：** 确保文件路径正确。在本地测试：`python -m http.server 8000`

### Q2：图片不显示
**A：** 检查 `assets/` 文件夹是否被上传到 GitHub

### Q3：域名未生效
**A：** DNS 生效需要 24-48 小时，可以用 https://dns.google 检查

### Q4：想要回滚到上个版本
**A：** 在 Vercel → Deployments 中选择之前的版本，点击三个点 → Promote to Production

---

## 🎉 部署完成！

部署后访问：`https://plc-training-kits.tech`

所有更新会自动从 GitHub 同步。

---

**下一步：** 提交到 Google Search Console 和 Bing Webmaster Tools（见 SEO-提交指南.md）
