一个简洁风格的个人作品集静态网站，用于展示个人项目作品、技能方向与联系方式。纯原生 HTML / CSS / JavaScript 构建，零依赖、零构建工具，开箱即用。

## 项目介绍

网站采用经典的「左侧固定侧边栏 + 右侧主内容」双栏布局，共 5 个页面：

| 页面 | 说明 |
| --- | --- |
| `index.html` | 首页，包含项目作品、关于我、联系方式三个区块 |
| `skill-python.html` | Python 技能详情页（相关项目：课语通） |
| `skill-java.html` | Java 技能详情页（相关项目：二手集市） |
| `skill-typescript.html` | TypeScript 技能详情页（相关项目：轻记账、城市脉搏与体征） |
| `skill-htmlcss.html` | HTML/CSS 技能详情页（相关项目：城市脉搏与体征） |

首页展示 4 个项目作品，采用多种排版形式（Hero 大图、图左文右、图右文左）：

- **轻记账** —— 极简记账微信小程序（TypeScript / 微信云开发 / ECharts）
- **二手集市** —— 校园二手交易平台（Java / Spring Boot / MySQL / Vue）
- **城市脉搏与体征** —— 城市交通与天气数据可视化大屏（Canvas / SVG / ECharts）
- **课语通** —— 基于大语言模型的课程问答助手（Python / FastAPI / RAG）

## 功能说明

- **深色 / 浅色主题切换**
  - 右上角固定主题切换按钮，一键切换全站配色（背景、文字、边框同步变化）
  - 深色模式经过对比度调校，保证文字清晰可读
  - 通过 `localStorage` 持久化用户选择，刷新或重新打开网站后保持上一次主题
  - 切换带 0.35s 平滑过渡动画，页面加载时通过 head 内联脚本预应用主题，避免闪烁
- **响应式布局**
  - 桌面端：左侧固定侧边栏 + 右侧滚动内容
  - 移动端（≤768px）：侧边栏变为顶部粘性导航栏，配合汉堡菜单按钮展开/收起
- **导航高亮**：基于 `IntersectionObserver` 监听滚动位置，自动高亮当前所在区块对应的导航项
- **技能详情页**：每个技能页展示技能描述与相关项目、技术栈标签，并可返回首页

## 技术栈

- **HTML5**：语义化标签（`aside` / `main` / `section` / `article` / `nav`）
- **CSS3**：
  - CSS 自定义属性（CSS Variables）实现主题系统，`html.dark` 类一键切换深浅配色
  - Flexbox 弹性布局、媒体查询响应式设计
  - `transition` 过渡动画
- **JavaScript（原生 ES6，无框架无依赖）**：
  - `localStorage` 实现主题持久化
  - `IntersectionObserver` 实现滚动导航高亮
  - DOM 动态注入主题切换按钮

> 项目图片与头像使用在线生成接口提供，无需本地资源即可运行。

## 部署方式

### 1. 本地运行

纯静态站点，直接双击 `index.html` 即可在浏览器中打开。

推荐使用本地服务器（避免部分浏览器对 `file://` 协议的限制）：

```bash
# Python 3
python3 -m http.server 8080

# 或 Node.js
npx serve .
```

然后访问 `http://localhost:8080`。

### 2. GitHub Pages

1. 将代码推送到 GitHub 仓库：

```bash
git init
git add .
git commit -m "feat: 个人作品集网站"
git branch -M main
git remote add origin git@github.com:<你的用户名>/<仓库名>.git
git push -u origin main
```

2. 在仓库页面进入 **Settings → Pages**，将 Source 设置为 `main` 分支 / `(root)` 目录，保存即可。

3. 稍等片刻后访问 `https://<你的用户名>.github.io/<仓库名>/`。

### 3. 其他静态托管

Vercel、Netlify、Cloudflare Pages 等平台均可直接部署：导入 GitHub 仓库后无需任何构建配置，部署根目录即可（无构建命令，输出目录为 `/`）。

## 目录结构

```
lab04/
├── index.html              # 首页
├── skill-python.html       # Python 技能详情页
├── skill-java.html         # Java 技能详情页
├── skill-typescript.html   # TypeScript 技能详情页
├── skill-htmlcss.html      # HTML/CSS 技能详情页
├── css/
│   └── style.css           # 全站样式（主题变量 / 布局 / 响应式 / 动画）
├── js/
│   └── main.js             # 主题切换 / 移动端菜单 / 滚动导航高亮
└── .gitignore
```

## 联系方式

- Email: xiaoliang@example.com
- GitHub: [github.com/xiaohe-dev](https://github.com/xiaohe-dev)
- 个人主页: [xiaoliang.dev](https://xiaoliang.dev)
