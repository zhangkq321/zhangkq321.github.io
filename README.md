# Keqin Zhang (张克钦) — academic homepage

个人学术主页，基于 [al-folio](https://github.com/alshedivat/al-folio) v1.x（Jekyll）。
线上地址：<https://zhangkq321.github.io>

## 怎么改内容

| 想改什么 | 改哪里 |
| --- | --- |
| 姓名、单位、简介、页脚、Google Scholar 高亮名 | `_config.yml` 顶部 + `scholar:` 段 |
| 首页自我介绍（中英双语）、教育经历、项目、获奖 | `_pages/about.md` |
| **论文列表** | `_bibliography/papers.bib` |
| 论文标签（abbr）的颜色 / 链接 | `_data/venues.yml` |
| 邮箱、GitHub、Scholar 等图标 | `_data/socials.yml` |
| 头像 | 放 `assets/img/prof_pic.jpg`，再把 `_pages/about.md` 里的 `profile.image` 改成 `prof_pic.jpg` |
| 新增页面（如 CV、中文独立页） | 在 `_pages/` 新建 `.md`，front matter 写 `nav: true` 和 `nav_order` |

BibTeX 可用字段（会渲染成按钮/徽标）：`abbr`、`bibtex_show`、`selected`（显示在首页精选）、
`annotation`（作者栏末尾的信息气泡，目前用来放 SCI 分区与影响因子）、`pdf`、`doi`、`arxiv`、`code`、`website`、`abstract`。

## 怎么发布

不需要在本机装 Ruby/Jekyll：推送到 `main` 分支后，GitHub Actions 会自动构建并发布。

```bash
git add .
git commit -m "update publications"
git push
```

首次使用请在 GitHub 仓库 Settings → Pages 里把 **Source** 设为 **GitHub Actions**。

仓库名必须是 `zhangkq321.github.io`，这样站点在根路径；`_config.yml` 的 `baseurl` 才保持为空。
如果换成别的仓库名，就要同时把 `baseurl` 改成 `/<仓库名>`，否则样式和链接会全部失效。

## 本地预览（可选）

想在本机看效果需要 Docker（本机目前没装）：

```bash
docker compose up -d      # http://127.0.0.1:8080/
docker compose down
```

## 文档

`docs/` 里保留了 al-folio 的官方说明，改主题时查 `docs/CUSTOMIZE.md`。
