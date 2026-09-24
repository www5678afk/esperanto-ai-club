# Mi Estas · 世界语与人工智能社团

> 当普世语言遇见智能纪元。
> *Kiam la universala lingvo renkontas la epokon de artefarita intelekto.*

**Mi Estas**(中文别名「绿星社」)是一个以「世界语 × 人工智能」为母题的学生社团。本仓库托管社团招募季的官方单页网站源代码。

## 项目内容

- 单文件静态站点 `index.html`,内联 CSS 与脚本,无外部构建步骤。
- 包含八个段落:导航 / Hero / Marquee / 关于本会 / 三块基石 / 研究方向 / 学期活动 / 成员 / 纳新表单 / 资源 / 页脚。
- 设计基调:深墨色背景、衬线大标题、金色与翡翠色点缀,带轻微噪点纹理与滚动显现动效。
- 双语呈现:中文为工作语言,世界语作为「仪式语言」(开场、闭幕、暗号)。

## 本地预览

直接双击打开 `index.html` 即可在浏览器查看,或启动一个本地静态服务器:

```bash
# 任选其一
python -m http.server 8000
npx serve .
```

然后访问 <http://localhost:8000>。

## 文件结构

```
esperanto-ai-club/
├── index.html      # 站点全部内容、样式与脚本
├── README.md       # 你正在读的这份说明
└── .gitignore
```

## 部署建议

由于是纯静态文件,可直接托管在 GitHub Pages、Netlify、Cloudflare Pages、Vercel 等静态服务上。GitHub Pages 启用方式:Settings → Pages → Source 选择 `main` 分支根目录。

## 研究方向(四条主线)

1. **世界语语料与词表构建** *Corpus & Tokenization*
2. **多语种大模型对齐** *Cross-lingual Alignment*
3. **跨语种智能体协作** *Multilingual Agents*
4. **低资源语言与 AI 伦理** *Low-resource & Ethics*

## 社群原则(三块基石 / Tri Principoj)

- **普世语法** *Universal Grammar*
- **跨文化连接** *Cross-cultural Bridge*
- **智能平权** *AI for Linguistic Equality*

## 加入

打开页面后,直接滚动到「加入我们」段落填写表单即可。
申请门槛只有三条:好奇驱动、持续出席、愿意读/写一点点世界语。

---

*Anno · MMXXVI · Societo 第 I 期 · 接受纳新中*