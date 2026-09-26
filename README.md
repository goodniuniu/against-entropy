# against-entropy · 熵、热寂与意义

围绕三个追问的十五本书导读：

1. **热寂是所有生命的终点吗？宇宙本身呢？**
2. **生命存在的意义是和熵增对抗吗？**
3. **活着的意义是什么？**——以及变体：历史无用论是否也属于对"终极意义"的虚无判断？

线上地址：<https://goodniuniu.github.io/against-entropy/>

## 内容结构

```
against-entropy/
├── _config.yml            # Jekyll 配置（minima 主题）
├── index.md               # 首页：全书单总表 + 阅读路径入口
└── docs/
    ├── 01-entropy-physics/    # 物理与熵（5 篇导读 + 分类页）
    ├── 02-life-meaning/       # 生命与意义（5 篇导读 + 分类页）
    ├── 03-history-nihilism/   # 历史与虚无（5 篇导读 + 分类页）
    ├── paths/                 # 5 条主题阅读路径
    └── appendix/              # 2 篇附录：两场追问的讨论整理
```

## 快速开始（本地预览 / 发布）

本项目使用 GitHub Pages 原生支持的 Jekyll 站点形态，**无需本地构建即可发布**。

### 一、推送即发布

仓库已关联 GitHub Pages（`main` 分支根目录）。日常更新只需：

```bash
git add -A && git commit -m "更新内容" && git push
```

推送后等 1–3 分钟，GitHub Actions 会自动构建并部署。

### 二、首次搭建流程（存档备查）

1. 在 GitHub 创建仓库 `against-entropy`（Public）
2. 推送本地代码到 `main` 分支
3. 仓库 **Settings → Pages**：Source 选 **Deploy from a branch**，Branch 选 **main / (root)**，Save
4. 等待构建完成后访问 <https://goodniuniu.github.io/against-entropy/>

### 三、本地预览（可选）

需要 Ruby 与 Bundler 环境：

```bash
gem install bundler jekyll
jekyll serve
# 浏览器打开 http://127.0.0.1:4000/against-entropy/
```

### 四、构建失败排查

构建失败时优先查看仓库 **Actions** 日志，常见原因：

- 主题未在 `_config.yml` 声明（本站使用 `theme: minima`，内置无需声明版本）
- Markdown front matter 语法错误（`---` 必须顶格、成对）
- 相对链接大小写不一致（本站书名文件统一使用英文小写文件名，规避中文 URL 编码问题）

## 维护规范

新增书籍请严格遵循任务书第 4 节内容规范（模板七板块、诚实三档、追问落点），并同步更新：`index.md` 首页总表 → 所属路径（若适用）→ 分类页。
