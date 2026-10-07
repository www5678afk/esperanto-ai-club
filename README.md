# Mi Estas · 英语学院世界语专业俱乐部

吉林外国语大学英语学院下的一个小社团——英语学院世界语专业俱乐部 Mi Estas。学世界语，也聊 AI 工具。

## 文件结构

```
.
├── index.html   # 单页全部内容（HTML + CSS + JS）
├── qr.png       # 【你需要提供】微信群聊二维码图片
└── README.md
```

## 如何替换成真实的微信群聊二维码

页面加载时会自动尝试 `qr.png`。两种情况：

1. **`qr.png` 存在**：弹窗里直接显示真实二维码
2. **`qr.png` 不存在**：自动回退到 JS 生成的占位图案（带「VS · MMXXVI」徽章的伪 QR）

替换步骤：

1. 把你拿到的微信群聊二维码图片保存为 `qr.png`（PNG / JPG 均可，建议 ≥ 400×400 像素）
2. 把 `qr.png` 放到和 `index.html` **同一个目录**
3. 刷新页面，点击「加入群聊」即可看到真实二维码

如需更改文件名或路径，编辑 `index.html` 中下面这一行即可：

```html
<img src="qr.png" alt="微信群聊二维码" class="qr-img" id="qrImg" ...>
```

## 本地预览

直接用浏览器打开 `index.html` 即可；也可以起一个本地静态服务：

```bash
# Python 3
python -m http.server 8000

# Node.js (需要 npx)
npx serve .
```

打开 `http://localhost:8000`。

## 部署

任何支持静态网站的平台都可：GitHub Pages、Netlify、Vercel、Cloudflare Pages、自建 Nginx 等。

### GitHub Pages（推荐）

```bash
git init
git add index.html README.md
git commit -m "Initial commit"
gh repo create mi-estas --public --source=. --remote=origin --push
gh repo edit --enable-pages --pages-source-branch=main --pages-source-path=/
```

部署完成后访问 `https://<username>.github.io/mi-estas`。

## 设计说明

- **风格延续**：暗色 + 暖金 + 翡翠绿；Cormorant Garamond 衬线斜体 + Noto Serif SC 中文 + JetBrains Mono 标签；世界语与中文混排
- **海报式单页**：所有内容压缩进一屏到底的一页，**只有一个 CTA 入口**通向群聊
- **可替换 QR**：见上文「如何替换成真实的微信群聊二维码」
- **占位图案**：当无 `qr.png` 时显示，避免页面破图
