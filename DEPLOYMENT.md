# 部署指南

本指南将帮助你把个人学术网站部署到 GitHub Pages。

---

## 快速开始

### 本地预览网站

在开始部署之前，先本地预览网站效果：

```bash
# 进入项目目录
cd Laurence-Li-official-homepage

# 安装 Quarto（如果还没有安装）
# 访问 https://quarto.org/docs/get-started/

# 本地预览
quarto preview
```

打开浏览器访问 `http://localhost:4200` 查看网站。

### 构建网站

```bash
quarto render
```

这会在 `_site` 目录下生成静态网站文件。

---

## GitHub Pages 已配置

你的仓库已经配置好了 GitHub Actions 部署工作流。每次你 push 到 main 分支，网站会自动部署。

### 启用 GitHub Pages

1. 在 GitHub 仓库页面，点击 **Settings**（设置）
2. 左侧菜单找到 **Pages**
3. 在 **Build and deployment** 部分，确认 Source 是 **GitHub Actions**
4. 等待 1-2 分钟，你的网站将出现在 `https://YukunLi-lab.github.io/Laurence-Li-official-homepage/`

---

## 后续更新

### 更新网站内容

1. 修改 `*.qmd` 文件中的内容
2. 提交并推送：
   ```bash
   git add .
   git commit -m "更新: [描述你做了什么修改]"
   git push
   ```

3. GitHub Actions 会自动检测到推送并重新部署

4. 等待 1-2 分钟，网站会自动更新

### 查看部署状态

1. 在 GitHub 仓库页面，点击 **Actions** 标签
2. 可以看到部署进度和历史记录
3. 点击具体的 workflow run 可以查看详细日志

---

## 文件结构说明

```
Laurence-Li-official-homepage/
├── _quarto.yml          # Quarto 配置文件
├── index.qmd            # 主页
├── about.qmd            # 关于我
├── education.qmd        # 教育背景
├── research.qmd        # 科研经历
├── projects.qmd         # 项目展示
├── publications.qmd     # 研究成果
├── skills.qmd           # 技能
├── honors.qmd           # 荣誉奖项
├── contact.qmd          # 联系方式
├── styles/
│   └── styles.css       # 自定义样式
├── images/
│   └── profile/         # 头像目录
├── assets/
│   └── cv.pdf          # 简历 PDF
├── .github/
│   └── workflows/
│       └── deploy.yml   # GitHub Actions 部署配置
└── CLAUDE.md           # 工作流规则
```

---

## 替换占位符

在浏览器中打开网站后，你需要替换以下占位符：

### 必须替换

- `您的姓名` → Laurence Li（你的真实姓名）
- `your.email@student.sysu.edu.cn` → 你的真实邮箱
- 头像占位符 → 替换为真实头像 (命名 `headshot.png`，放在 `images/profile/` 目录)
- `assets/cv.pdf` → 替换为你的简历 PDF

### 根据情况替换

- `[您的专业]` → 你的专业（如：计算机科学与技术）
- `[研究兴趣领域]` → 你的研究方向
- GPA、课程、项目、获奖等具体信息

---

## 常见问题

### 部署失败

1. 检查 **Actions** 标签页的错误日志
2. 确保仓库是 **Public**
3. 确认 `.github/workflows/deploy.yml` 文件存在

### 图片不显示

1. 检查图片路径是否正确
2. 图片应放在 `images/` 目录下
3. 在 Markdown 中引用时使用正确路径

### 样式不对

1. 清除浏览器缓存
2. 确认 `styles.css` 路径在 `_quarto.yml` 中正确配置
3. 本地运行 `quarto render` 重新生成

---

## 获取帮助

- [Quarto 文档](https://quarto.org/docs/reference/)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [GitHub Actions 文档](https://docs.github.com/en/actions)

---

*最后更新：2025年3月*
