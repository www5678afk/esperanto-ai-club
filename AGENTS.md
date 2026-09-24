# AGENTS.md

Mi Estas · 世界语与人工智能社团招募季官方单页站点。单文件静态站点，纯 HTML + 内联 CSS + 内联 JavaScript，无构建步骤。

> ⚠️ **多人协作项目** — 任何 Agent 在开始任何修改之前必须先完成下方「Pre-flight 同步检查」。

## Pre-flight 同步检查（强制）

本项目有多个协作者。**在任何修改（编辑文件、`git commit`、`git push`、创建分支、合并 PR 等）开始之前，必须先与远端同步。**

1. `git fetch origin` — 拉取远端最新引用
2. `git status` — 检查工作区是否有未提交的改动
   - 如果有未提交改动 → 先 `git stash` 或 commit，再继续
3. 比较 `HEAD` 与 `origin/<当前分支>`：
   - **远端领先（`origin/<branch>` 在 `HEAD` 之前）→ 立刻停止，不要盲改。** 把情况告诉用户，询问是 `git pull --rebase` 还是 `git merge`，或者让用户先决定如何处理。
   - **本地领先或平齐 → 可继续工作。** 推送前再 `git fetch` 一次确认仍然平齐。
4. **禁止 `git push --force` / `git push -f` 到 `main`**。任何需要重写历史的操作必须先与用户确认。
5. **禁止自动 rebase 别人的提交。** 如果 `pull --rebase` 会改写未属于自己的提交，先停下来询问。

理由：静默编辑会与队友推送产生冲突，悄无声息地覆盖他人工作。任何发现远端有更新的情况都必须显式上报。

## Setup commands

- 本地预览：直接双击 `index.html` 用浏览器打开，或运行任意静态服务器：
  - `python -m http.server 8000`
  - `npx serve .`
  - `npx http-server -p 8000`
- 没有 install / build / test / lint 步骤（无依赖、无框架、无打包器）

## Project layout

极简单文件项目：

- `index.html` — 站点全部 HTML、内联 `<style>`、内联 `<script>`
- `README.md` — 项目说明与本地预览指引
- `.gitignore` — OS / 编辑器产物
- 无 `src/` / `dist/` / `package.json` / 配置文件

## Code style

- HTML5 doctype，中文内容使用 UTF-8
- 全部样式写在 `index.html` 的 `<style>` 块内；设计令牌用 CSS 自定义属性集中定义在 `:root`
- 字体仅外链 Google Fonts（`Cormorant Garamond`、`Outfit`、`JetBrains Mono`、`Noto Serif SC`），不引入其他 CDN
- 类名采用 kebab-case，按区块前缀命名（`hero-` / `nav-` / `pillar-` / `research-` / `sched-` / `people-` / `join-` / `res-`）
- 配色与字体集中在 `:root` 的 design tokens 中；新增颜色/字号请优先扩展 tokens
- 保持现有响应式断点：`@media (max-width:900px)` 和 `@media (max-width:768px)`，移动端样式就近写在对应区块末尾
- 内联 `<script>` 仅做交互增强（滚动时导航栏样式切换、`IntersectionObserver` 触发 `.reveal`）；不要引入 jQuery / 框架

## Testing instructions

- 无自动化测试。改动后请用浏览器手动检查：
  - 桌面 1280px / 平板 900px / 手机 480px 三个宽度
  - 滚动导航栏渐变、`IntersectionObserver` 的渐显动效
  - Hero、Research、Pillars、Schedule、People、Join 表单各段落排版

## PR & commit conventions

- 默认分支：`main`
- 分支命名：`feat/<topic>` / `fix/<topic>` / `docs/<topic>`
- Commit 风格：conventional commits（`feat:` / `fix:` / `docs:` / `refactor:` / `style:` / `chore:`）
- 推送前确认 `git status` 无遗留临时文件
- 项目作者身份使用 noreply 邮箱：`239542272+www5678afk@users.noreply.github.com`

## Security

- 无 secrets、无后端、无表单后端处理；`Join` 段落的报名表单仅前端阻止默认提交并显示静态文案
- Google Fonts 外链为隐私面不收集用户数据
- 不要在 `index.html` 中加入跟踪脚本、外部统计、第三方 cookie