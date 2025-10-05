
# Editor.md 入门示例（按官方介绍）

本包提供 **最小可用示例**，分别包含：
- `index-local.html`：本地引入 Editor.md（需要你已下载 editor.md 源码并按官方结构放置）
- `index-cdn.html`：使用 CDN 引入（联网可直接打开）
- `preview-local.html`：Markdown → HTML 预览（本地文件）
- `preview-cdn.html`：Markdown → HTML 预览（CDN）

---

## 1) 安装方式（三选一）

### A. 直接下载（GitHub Download）
1. 下载 Editor.md 压缩包并解压到你的项目目录，例如：`./editor.md/`
2. 确认目录结构包含：`editormd.min.js`、`css/`、`lib/` 等。

### B. NPM 安装
```bash
npm install editor.md
```
安装后，`node_modules/editor.md/` 即为根目录，其中包含 `editormd.min.js`、`lib/`、`css/`。

### C. Bower 安装（已过时，不推荐）
```bash
bower install editor.md
```

> 无论哪种方式，**关键是能访问到 `editor.md/lib/`**，因为编辑器会按 `path` 自动加载依赖。

---

## 2) 目录结构（本地引用时）

建议项目结构：
```
your-project/
├─ index-local.html
├─ preview-local.html
├─ jquery.min.js
└─ editor.md/
   ├─ editormd.min.js
   ├─ css/
   └─ lib/
```

> 如果你是 npm 安装，也可以把 `node_modules/editor.md/` 复制或软链为本地的 `./editor.md/`，或调整 HTML 中的路径。

---

## 3) 运行

- 方式 1：**直接双击** `index-cdn.html`（联网即可看到编辑器）
- 方式 2：准备好本地文件后，**双击** `index-local.html`
- 方式 3：本地起服务（可避免某些浏览器对 `file://` 的限制）：
  ```bash
  # Python 3
  python -m http.server 8000
  # 打开 http://localhost:8000/index-cdn.html 或 index-local.html
  ```

---

## 4) 常见问题

- **编辑器不显示 / 控制台报错“Cannot load ...js”**  
  多半是 `path : "editor.md/lib/"` 的路径不对；请确保该目录存在且相对路径正确。

- **jQuery 未定义**  
  确保在 `editormd.min.js` 之前引入了 `jquery.min.js`。

- **GitHub Pages 无法加载**  
  检查静态路径是否区分大小写；等待几分钟生效。

---

## 5) 示例文件说明

- `index-*.html`：创建一个 Markdown 编辑器（所见即所得，左写右看）
- `preview-*.html`：把 Markdown 转换为 HTML 的纯展示页（无编辑功能）

> Editor.md 目前不支持 **HTML → Markdown** 反向解析。如需该功能，可使用 `turndown` 等第三方库。
