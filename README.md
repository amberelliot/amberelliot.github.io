# kunpeng-gao.github.io — 个人学术主页

## 创建流程

1. **提取简历内容** — 使用 `pdfminer.six` 从 PDF 简历中提取中英文信息。
2. **设计页面** — 单页滚动式布局，白底 + 藏蓝配色，纯 HTML + CSS，无需任何框架。
3. **创建 GitHub 仓库** — 仓库名必须为 `amberelliot.github.io`，Public 可见。
4. **配置 GitHub Pages** — Settings → Pages → Branch 选 `main` → Save。
5. **推送代码** — 将 `index.html`、`style.css` 推送到仓库。
6. **验证上线** — 等待 1-2 分钟，访问 `https://amberelliot.github.io` 即可。

### 本地命令速查

```bash
cd "项目目录"
git add index.html style.css
git commit -m "更新内容"
git push
```

---

## 踩坑记录

| 问题 | 原因 | 解决 |
|------|------|------|
| pip 安装包超时 | 清华镜像源被代理拦截 | 使用官方源 `-i https://pypi.org/simple/ --trusted-host pypi.org --trusted-host files.pythonhosted.org` |
| PDF 中文乱码 | `pypdf` 无法解码 xdvipdfmx 生成的中文字体 | 换用 `pdfminer.six` 提取 |
| GitHub Pages 404 | 初期推了 `master` 分支，但 Pages 默认需要 `main` | `git branch -m master main` 重命名后重新推送，Settings → Pages 切换分支 |
| 找不到 Pages 设置 | 误入 Branch protection 页面 | 在 Settings 左侧菜单的 "Code and automation" 下找 "Pages" |

---

## 改进建议

### 内容层面
- 论文被接收后，更新 AdaptMMBench 的发表信息（会议名、DOI 链接）。
- 自演化智能体项目有产出后，补充论文或博客链接。
- 可以加一个 **"News"** 区块，展示最新动态（论文接收、获奖等）。
- 添加 GitHub 图标链接到你的 GitHub 主页。

### 技术层面
- 把自己的真实头像替换 Hero 区域的占位，用 `<img>` 标签加在名字上方。
- 如果需要多页面，可以引入简单的静态站点生成器（如 Jekyll，GitHub Pages 原生支持）。
- 添加 Google Analytics 统计访问量（`gtag.js`）。
- 启用 HTTPS 强制跳转（Settings → Pages → Enforce HTTPS）。

### 部署层面
- 建议在本地改好、浏览器确认没问题后，再 `git push`，避免反复提交。
- 重大改动前，可以先用 `git branch` 创建分支测试，确认后合并到 `main`。

---

## 文件结构

```
├── index.html      # 主页面
├── style.css       # 样式
├── README.md       # 本文件
└── .gitignore      # 排除 venv/ 等临时文件
```
