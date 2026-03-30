# 操作指南 / Operation Guide

## 第一步：部署到 GitHub Pages（5 分钟）

### 1. 创建仓库

1. 登录 [github.com](https://github.com)，点击右上角 **+** → **New repository**
2. 仓库名填写 **`你的用户名.github.io`**（例如 `yanbinxu.github.io`）
3. 选择 **Public**
4. 不要勾选 "Add a README file"（我们已经有了）
5. 点击 **Create repository**

### 2. 上传文件

**方法 A：网页上传（最简单）**

1. 在新建的仓库页面点击 **"uploading an existing file"**
2. 把下载的 zip 解压后的 **所有文件和文件夹** 拖进去
3. 点击 **Commit changes**

**方法 B：命令行（推荐，方便后续更新）**

```bash
# 克隆空仓库
git clone https://github.com/你的用户名/你的用户名.github.io.git
cd 你的用户名.github.io

# 把解压后的所有文件复制到这个目录
# 确保 _config.yml、index.html 等在根目录

git add .
git commit -m "init: academic homepage"
git push origin main
```

### 3. 开启 GitHub Pages

1. 进入仓库 → **Settings** → 左侧菜单 **Pages**
2. Source 选择 **Deploy from a branch**
3. Branch 选择 **main**，目录选 **/ (root)**
4. 点 **Save**
5. 等待 1-3 分钟，访问 `https://你的用户名.github.io` 即可

---

## 第二步：个性化修改

### 需要替换的内容

| 文件 | 需要改的地方 | 说明 |
|------|-------------|------|
| `index.html` | `许彦斌` | 替换为你的中文名 |
| `index.html` | Google Scholar / GitHub 链接 | 换成你自己的链接 |
| `index.html` | 论文作者列表 | 补充完整的共同一作等信息 |
| `_config.yml` | `url` 字段 | 填入 `https://你的用户名.github.io` |
| `assets/` | 添加 `photo.jpg` | 你的个人照片 |

### 添加照片

1. 准备一张证件照或学术照（建议宽高比 4:5）
2. 命名为 `photo.jpg`，放到 `assets/` 目录下
3. 打开 `index.html`，找到：
   ```html
   <!-- Replace with your photo: <img src="assets/photo.jpg" alt="Yanbin Xu"> -->
   <div class="avatar-placeholder">Y</div>
   ```
4. 改为：
   ```html
   <img src="assets/photo.jpg" alt="Yanbin Xu">
   ```

---

## 第三步：每天更新科研日志（核心工作流）

### 写一篇新日志

在 `_posts/` 文件夹里创建新文件，文件名格式 **必须** 是：

```
YYYY-MM-DD-english-title.md
```

例如：`2026-04-01-ablation-study-results.md`

### 文件内容模板

```markdown
---
layout: post
title: "你的标题（支持中英文）"
tags: [experiment, deep-learning]
---

正文从这里开始，用 Markdown 写。

## 小标题

- 列表项
- **加粗** 和 *斜体*
- `代码片段`

> 引用文字

用三个反引号写代码块：

​```python
model = DeepRDR(config)
​```
```

### 发布日志

**方法 A：GitHub 网页操作（手机也行）**

1. 打开你的仓库 → 进入 `_posts` 文件夹
2. 点击 **Add file** → **Create new file**
3. 文件名输入 `2026-04-01-your-title.md`
4. 粘贴上面的模板，写入内容
5. 点击 **Commit new file**
6. 等待约 1 分钟，页面自动更新

**方法 B：本地编辑 + Git 推送**

```bash
# 写完后
git add _posts/2026-04-01-your-title.md
git commit -m "log: ablation study results"
git push
```

### 日志自动展示

首页会自动显示最新 5 篇日志，点击 "Research Log" 可以看到全部。不需要修改任何 HTML。

---

## 项目结构说明

```
你的用户名.github.io/
├── _config.yml              ← Jekyll 配置（改 URL）
├── _layouts/
│   ├── default.html         ← 全局布局（导航栏、页脚、语言切换）
│   └── post.html            ← 日志文章布局
├── _posts/                  ← ★ 科研日志放这里 ★
│   ├── 2026-03-29-xxx.md
│   └── 2026-03-30-xxx.md
├── assets/
│   ├── style.css            ← 样式表
│   └── photo.jpg            ← 你的照片（需要自己添加）
├── blog.html                ← 日志列表页
├── index.html               ← 首页
├── GUIDE.md                 ← 本操作指南
└── README.md
```

---

## 常用操作速查

| 我想…… | 怎么做 |
|--------|--------|
| 发一篇科研日志 | 在 `_posts/` 新建 `YYYY-MM-DD-title.md`，push |
| 更新论文状态（被接收了） | 编辑 `index.html`，把 `review` 改为 `accepted` |
| 添加新论文 | 在 `index.html` 的 `pub-list` 里复制一个 `pub-item`，修改内容 |
| 添加教育/实习经历 | 在 `index.html` 的 `timeline` 里添加一个 `<li>` |
| 换照片 | 替换 `assets/photo.jpg` |
| 修改研究方向标签 | 编辑 `index.html` 里的 `interest-tag` |
| 绑定自定义域名 | 仓库 Settings → Pages → Custom domain，填入你的域名 |

---

## 进阶：绑定自定义域名（可选）

如果你购买了域名（如 `yanbinxu.com`）：

1. 在域名服务商那里添加 DNS 记录：
   - 类型 `CNAME`，主机记录 `@` 或 `www`，值 `你的用户名.github.io`
2. 在仓库 Settings → Pages → Custom domain 填入域名
3. 勾选 **Enforce HTTPS**
4. 在仓库根目录创建一个 `CNAME` 文件，内容就是你的域名

---

## 常见问题

**Q: Push 之后页面没更新？**
A: GitHub Pages 构建需要 1-3 分钟。可以去仓库的 Actions 标签页查看构建状态。

**Q: 样式显示不正常？**
A: 检查 `_config.yml` 里的 `baseurl` 是否为空字符串 `""`。

**Q: 能不能在手机上更新？**
A: 可以！直接在 GitHub 手机端网页或 GitHub App 里编辑 `_posts/` 文件夹。

**Q: 想改颜色或字体？**
A: 编辑 `assets/style.css` 文件顶部的 CSS 变量（`:root { ... }`）。
