# Hexo Blog Template (Ready-to-edit)

这是一个开箱即用的 Hexo 博客源码模版（轻量版），包含：
- 基本站点配置 `_config.yml`
- `package.json`（包含 Hexo 构建依赖）
- 示例文章 `source/_posts/hello-world.md`
- 关于页面 `source/about/index.md`
- `scaffolds/post.md`
- 占位的 `themes/next` 目录（请按下述步骤获取官方 NexT 主题）
- GitHub Actions 工作流 `.github/workflows/deploy.yml`（自动构建并部署到 Pages 仓库）
- sitemap 配置与 SEO 基础设置

## 使用说明（下载后按顺序执行）
1. 解压并进入目录：
   ```bash
   unzip my-hexo-template.zip
   cd my-hexo-template
   ```
2. 安装依赖：
   ```bash
   npm ci
   ```
3. 获取官方 NexT 主题（两种方式任选其一）：
   - 推荐（使用 Git clone，将主题放到 `themes/next`）：
     ```bash
     git clone https://github.com/theme-next/hexo-theme-next themes/next
     ```
     > 如果上面的 repo 地址无效，请访问 NexT 官方仓库并替换为正确地址（通常为 `theme-next/hexo-theme-next`）。
   - 或者在 `themes/` 下创建一个名为 `next` 的主题目录，并把 NexT 源码放入。

4. 修改站点配置 `_config.yml`：
   - 改 `url` 为 `https://yourname.github.io`（或你的自定义域）
   - 改 `deploy.repo` 为你的 Pages 仓库地址 `https://github.com/yourname/yourname.github.io.git`
   - 在 `themes/next/_config.yml` 中配置评论（Twikoo、Valine 等）与 Google Analytics ID

5. 本地预览：
   ```bash
   npx hexo server
   # 或者
   ./node_modules/.bin/hexo server
   ```
   打开 http://localhost:4000

6. 发布到 GitHub Pages：
   - 方法一（本地部署到 Pages 仓库）：
     ```bash
     npx hexo clean && npx hexo generate && npx hexo deploy
     ```
   - 方法二（使用本仓库内置的 GitHub Actions，配置好 `yourname/yourname.github.io` 仓库并在 Actions 中启用）：
     - 将本仓库（源码）推到 `yourname/my-blog`（或任意 repo）
     - 在 GitHub 上创建空的 Pages 仓库 `yourname/yourname.github.io`
     - 修改 `.github/workflows/deploy.yml` 中的 `external_repository` 为 `yourname/yourname.github.io`
     - Push 到 `main` 分支，Actions 会自动构建并把 `public/` 推送到你的 Pages 仓库

---
如果你希望我直接把官方 NexT 主题也一起打包（这会显著增加 zip 大小），或者替你把主题完整配置好并直接上线到你的 GitHub 仓库，请告诉我你的 GitHub 用户名与你希望的风格（极简 / 卡片 / 杂志），我可以进一步把主题文件并自动配置好。
