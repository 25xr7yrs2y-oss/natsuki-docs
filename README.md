# 📚 natsuki-wiki — EU 海关法规知识库

基于 [Quartz v4](https://quartz.jzhao.xyz/) 构建的个人 Wiki，部署于 **Cloudflare Pages**。

在线地址：**[https://natsuki.uk/wiki/](https://natsuki.uk/wiki/)**

---

## 📝 如何添加/编辑内容

### 在线编辑（推荐）

1. 打开 `content/` 目录
2. 进入对应子目录（`sources/`、`syntheses/`、`concepts/`）
3. 点击 **Add file → Create new file** 或点击已有文件编辑
4. 使用 Markdown + [[wikilinks]] 语法编写
5. 提交后等待 Cloudflare Pages 自动构建部署（约 2-3 分钟）

### 本地编辑

```bash
git clone https://github.com/25xr7yrs2y-oss/natsuki-wiki.git
cd natsuki-wiki
npm install

# 在 content/ 目录下编辑 Markdown 文件

npx quartz build     # 构建
npx quartz build --serve  # 构建 + 本地预览 http://localhost:8080

git add . && git commit -m "更新内容" && git push
```

### 部署

推送后需手动触发部署：

```bash
npx wrangler pages deploy public --project-name=natsuki-wiki --commit-dirty=true
```

或在 Cloudflare Dashboard → Pages → natsuki-wiki → 手动触发部署。

---

## 📂 内容结构

```
content/
├── index.md                         # Wiki 首页
├── sources/                         # 资料来源
│   ├── eu-customs-legal-index.md    # 法规索引
│   ├── eu-customs-research-report.md # 研究报告
│   └── eu-customs-source-portals.md # 官方查询入口
├── syntheses/                       # 综合分析
│   └── eu-customs-legal-knowledge-base.md
└── concepts/                        # 核心概念
```

## 🛠️ 技术栈

- **引擎**: [Quartz v4](https://quartz.jzhao.xyz/) — Obsidian 兼容的静态 Wiki 生成器
- **部署**: Cloudflare Pages
- **特性**: [[wikilinks]] 双向链接 · Backlinks · Graph View · 全文搜索 · 暗色模式

## 📄 License

MIT

<!-- auto-deploy-test: 2026-06-07 -->
