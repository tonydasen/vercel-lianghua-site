# QuantWiki - 量化交易知识库

一个简洁、深色调的量化交易知识分享网站，纯静态页面，可直接部署到 Vercel。

## 项目结构

```
quant-wiki/
├── index.html          # 首页（热门文章 + 分类筛选）
├── articles.html       # 全部文章列表
├── strategies.html     # 策略库（默认筛选策略类）
├── tools.html          # 工具框架（默认筛选工具类）
├── article.html        # 文章详情页
├── admin/
│   └── index.html      # 后台管理（发布/编辑/删除文章）
├── data/
│   └── articles.json   # 文章数据库（JSON格式）
└── README.md
```

## 部署到 Vercel

### 方法一：Git 仓库部署（推荐）

1. 在 GitHub 创建新仓库，上传本项目文件
2. 登录 [Vercel](https://vercel.com)，点击 "Add New Project"
3. 选择你的 GitHub 仓库，点击 "Deploy"
4. 等待部署完成，获得域名如 `https://your-project.vercel.app`

### 方法二：Vercel CLI 部署

```bash
# 安装 Vercel CLI
npm i -g vercel

# 进入项目目录
cd quant-wiki

# 登录并部署
vercel login
vercel --prod
```

### 方法三：直接上传

1. 登录 [Vercel](https://vercel.com)
2. 点击 "Add New Project" → "Import Git Repository" 旁边的箭头 → "Upload"
3. 上传项目 zip 文件
4. 点击 Deploy

## 发布新文章流程

### 方式一：通过后台管理页面

1. 访问 `https://your-project.vercel.app/admin/`
2. 输入密码：`quantwiki2026`（可在后台修改）
3. 点击 "发布文章"，填写表单
4. 点击 "生成JSON"，复制生成的 JSON 数据
5. 将 JSON 粘贴到 `data/articles.json` 文件中
6. 提交到 Git 仓库，Vercel 自动重新部署

### 方式二：直接编辑 JSON 文件

1. 打开 `data/articles.json`
2. 在数组末尾添加新的文章对象
3. 确保 JSON 格式正确
4. 提交到 Git 仓库

## 文章数据格式

```json
{
  "id": "16",
  "title": "文章标题",
  "category": "strategy",
  "subcategory": "趋势跟踪",
  "difficulty": 2,
  "tag": "策略",
  "tagClass": "tag-strategy",
  "tagIcon": "fa-chess",
  "description": "文章简短描述",
  "content": "<h3>章节标题</h3><p>正文内容...</p>",
  "author": "作者名",
  "date": "2026-05-02",
  "views": 0,
  "readTime": "15分钟",
  "codePreview": "可选的代码预览",
  "featured": false
}
```

### 分类对应表

| category | tag | tagClass | tagIcon |
|----------|-----|----------|---------|
| strategy | 策略 | tag-strategy | fa-chess |
| theory | 理论 | tag-theory | fa-graduation-cap |
| data | 数据 | tag-data | fa-database |
| ml | ML | tag-ml | fa-brain |
| risk | 风控 | tag-risk | fa-shield-halved |
| tool | 工具 | tag-tool | fa-toolbox |

### 难度等级

- `1` = 入门（1个蓝点）
- `2` = 进阶（2个蓝点）
- `3` = 高级（3个蓝点）

## 广告位说明

网站右侧边栏预留了 4 个广告位，分别在以下位置：

1. **顶部大横幅** - `index.html` / `articles.html` 右侧第一个 `.ad-banner`
2. **工具推荐卡片** - `.ad-card` 包含 QuantConnect
3. **数据服务卡片** - `.ad-card` 包含 Tushare
4. **底部推广卡片** - 最后一个 `.ad-card` 包含 Pro 会员

修改广告内容只需编辑对应 HTML 文件中的广告区块即可。

## 自定义配置

### 修改网站名称/Logo

编辑各 HTML 文件中的 `.logo-text` 内容。

### 修改配色

在各 HTML 文件的 `:root` CSS 变量中修改颜色值。

### 修改管理密码

访问后台 → 系统设置 → 输入新密码 → 保存。

## 技术栈

- 纯 HTML + CSS + JavaScript（无框架依赖）
- JSON 文件作为轻量数据库
- Font Awesome 图标
- Google Fonts (Inter + JetBrains Mono)

## 浏览器兼容性

- Chrome / Edge / Firefox / Safari 最新版
- 响应式设计，支持移动端

## License

MIT
