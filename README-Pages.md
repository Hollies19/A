
# 一键上线到 GitHub Pages（无需本地环境）

这个模板已经包含 GitHub Actions 工作流。把本仓库推到 GitHub 后，会自动部署到 Pages。

## 使用步骤（只需 3 步）

1. **在 GitHub 新建仓库**（Public/Private 均可）。
2. **上传本模板全部文件**（或直接把本项目 `git push` 到 `main` 分支）。
3. 打开仓库 **Settings → Pages**，确认 Source 显示为 “GitHub Actions”。
   - 首次推送后，Actions 会自动运行并部署。几分钟后在同页即可看到你的访问链接。

> 默认部署网站根目录（本项目根目录）。你可以直接访问：
> - `index-cdn.html`（推荐：联网即可使用 Editor.md）
> - `index-local.html`（需要你自己在仓库里补齐 editor.md/ 与 jquery.min.js）
> - `preview-cdn.html`（纯预览示例）

## 自定义

- 如果你的站点不在根目录，想改成 `docs/` 等，请调整工作流中的 `path: "."`。
- 如果你使用自定义域名，添加 `CNAME` 文件到项目根目录即可。

## 常见问题

- **Actions 没触发？** 确保推送到 `main` 分支（或按需修改工作流触发分支）。
- **部署失败？** 在仓库的 “Actions” 页面查看日志。
- **访问 404？** Pages 首次部署需要几分钟；路径区分大小写。

祝你部署顺利！
