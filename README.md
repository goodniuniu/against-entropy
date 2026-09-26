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
├── _includes/             # 覆写 minima 模板（页头 / 页脚 / head）
├── _layouts/page.html     # 覆写 minima 页面布局（眉题 + 徽章，正文标题由布局渲染）
├── assets/css/entropy.css # 视觉主题「深空纸墨」（见下节）
└── docs/
    ├── 01-entropy-physics/    # 物理与熵（5 篇导读 + 分类页）
    ├── 02-life-meaning/       # 生命与意义（5 篇导读 + 分类页）
    ├── 03-history-nihilism/   # 历史与虚无（5 篇导读 + 分类页）
    ├── paths/                 # 5 条主题阅读路径 + 总览索引页（/paths/）
    └── appendix/              # 2 篇附录讨论 + 总览索引页（/appendix/）
```

## 视觉定制：「深空纸墨」主题

站点外观由两层组成：GitHub Pages 内置的 **minima** 主题负责骨架，本仓库的覆写文件负责视觉。核心思路——夜空底色之上，生长宋体排版的秩序（有序在无序中借流成序）：

| 文件 | 作用 |
|---|---|
| `assets/css/entropy.css` | 全部视觉规则：深空底色 + 星空点缀、宋体正文 + 无衬线界面文字、表格圆角面板、金色章节装饰、确定性徽章、移动端适配 |
| `_includes/head.html` | 主题色 meta、星形 favicon、加载 entropy.css |
| `_includes/header.html` | 固定页头：站名 + 六项导航（当前项金色高亮，移动端折叠为汉堡菜单） |
| `_includes/footer.html` | 页脚：站名、标语与「距热寂还有约 10^100 年」一行 |
| `_layouts/page.html` | 文章页头：标题由布局渲染（正文不再写一级标题），附眉题与「分类 / 难度」徽章 |

内容侧的两条配套约定：

- **各级页面不再在正文写 `# 一级标题`**，标题统一来自 front matter `title`（书籍页 `《书名》 · 导读` 会自动拆为主标题 + 眉题）；
- 附录中的确定性标记写作 `<span class="ct ct-fact">事实</span>`（`ct-hypo` / `ct-stance` 同理），渲染为三色徽章，对应项目第一红线「区分三档确定性」。

调色改 `entropy.css` 顶部 `:root` 变量即可；正文行长、卡片、表格等排版参数均在该文件内有注释分组。

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
