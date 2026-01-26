# 📊 Google Analytics 4 设置指南

Google Analytics 4 (GA4) 可以追踪网站访客数据。这是完全免费的！

---

## 📋 步骤 1：创建 Google Analytics 账户

1. 访问 https://analytics.google.com
2. 点击 "Start measuring"（或登录已有账户）
3. 点击 "Create"

---

## 📋 步骤 2：设置 GA4 属性

### 账户名称
- 输入：`PLC Training Kits` 或 `Automation Trainer`
- 这是账户级别，用于组织管理

### 属性名称
- 输入：`plc-training-kits.tech`
- 这是网站属性名称

### 时区和货币
- 时区：选择你所在地区（中国选 UTC+8 或 Asia/Shanghai）
- 货币：USD（美元，因为产品面向全球）
- 点击 "Create"

---

## 📋 步骤 3：添加数据流（Web Stream）

1. 选择平台：**Web**
2. 输入网站 URL：`https://plc-training-kits.tech`
3. 流名称：`plc-training-kits.tech`
4. 点击 "Create stream"

---

## 📋 步骤 4：获取测量 ID

页面会显示你的 **Google Analytics ID**，格式是 `G-XXXXXXXXXX`

**复制这个 ID，非常重要！**

---

## 📋 步骤 5：集成到网站

打开 `index.html` 文件，找到这一行（已经在代码中）：

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
```

将 `G-XXXXXXXXXX` 替换为你的实际 GA4 ID。

例如，如果你的 ID 是 `G-ABC123DEF45`，改为：

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-ABC123DEF45"></script>
```

同时下面的配置代码也要改：

```javascript
gtag('config', 'G-ABC123DEF45', {
    'page_title': document.title,
    'page_location': window.location.href
});
```

---

## 📋 步骤 6：验证跟踪是否工作

1. 保存修改后的 index.html
2. 上传到 GitHub
3. 等待 Vercel 自动部署（通常 1-2 分钟）
4. 访问你的网站：https://plc-training-kits.tech
5. 回到 Google Analytics，点击 "Realtime"
6. 如果显示你正在访问，说明跟踪成功！✅

---

## 📊 主要指标解释

### 用户相关
- **Users（用户）** - 独立访客数
- **New Users（新用户）** - 首次访问的用户
- **Sessions（会话）** - 用户访问次数
- **Session Duration（会话时长）** - 用户停留时间

### 行为相关
- **Pages/Session（每个会话的页面数）** - 用户浏览多少个页面
- **Bounce Rate（跳出率）** - 用户来了就走的比例（低越好）
- **Scroll（滚动）** - 用户是否向下滚动看内容

### 地理相关
- **Countries（国家）** - 用户来自哪些国家
- **Cities（城市）** - 用户来自哪些城市
- **Language（语言）** - 用户使用什么语言

### 设备相关
- **Device Category（设备类型）** - Desktop / Mobile / Tablet
- **Platform（平台）** - Windows / Mac / Android / iOS

---

## 🎯 自定义事件追踪（可选）

如果你想追踪特定的用户行为，可以添加自定义事件。例如：

### 追踪 WhatsApp 点击

在 HTML 中，WhatsApp 按钮代码添加 JavaScript：

```html
<a href="https://wa.me/8617612051841" class="btn btn-whatsapp"
   onclick="gtag('event', 'contact_whatsapp');">
   ...
</a>
```

### 追踪邮箱复制

```javascript
link.addEventListener('click', (e) => {
    // ... 复制代码 ...
    gtag('event', 'copy_email');
});
```

这样在 GA4 中就能看到有多少人点击了 WhatsApp 或复制了邮箱。

---

## 📋 检查清单

部署后：

- [ ] 申请了 Google Analytics 4
- [ ] 获得了 GA4 ID（G-XXXXXXX）
- [ ] 将 GA4 ID 替换到 index.html 中
- [ ] 上传代码到 GitHub
- [ ] Vercel 已部署
- [ ] 访问网站后，GA4 Realtime 显示"1 users"

---

## 📊 定期查看报告

登录 Google Analytics，定期查看：

### 每周
- Realtime 报告（当前访问者）
- 昨天的流量数据

### 每月
- 完整月度报告
- 用户来源（哪里来的流量）
- 用户地理位置
- 最受欢迎的页面

### 每季度
- 年度对比
- 趋势分析
- ROI 分析（WhatsApp 点击与访问者数）

---

## 💡 优化建议

### 如果跳出率太高（>50%）
- 优化页面加载速度
- 改进页面设计
- 增加相关内容链接

### 如果移动端用户比例高
- 确保移动端显示效果好
- 优化移动端按钮大小
- 加快移动端加载速度

### 如果 WhatsApp 点击率低
- 调整按钮位置和大小
- 改进 CTA 文案
- 测试不同的颜色

---

## 🚀 高级功能（稍后可考虑）

- **Goals / Conversions** - 设置转化目标（如 WhatsApp 联系）
- **Audiences** - 根据行为创建用户段
- **Custom Reports** - 创建自定义报告
- **Data Studio** - 创建可视化仪表板

---

**现在就去申请 GA4，获得你的 GA4 ID，然后告诉我！** 📊
