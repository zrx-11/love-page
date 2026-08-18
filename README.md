# Love Page 

<p align="center">
  <strong>为爱而生 · 记录你们的每一个重要时刻</strong><br>
  <sub>相恋时光 · 里程碑故事 · 纪念日倒计时 · 一键生成纪念卡</sub>
</p>

<p align="center">
  <a href="https://github.com/funnyzak/love-page/stargazers">
    <img src="https://img.shields.io/github/stars/funnyzak/love-page?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/funnyzak/love-page/network/members">
    <img src="https://img.shields.io/github/forks/funnyzak/love-page?style=social" alt="GitHub forks">
  </a>
</p>

<p align="center">
  <a href="https://github.com/funnyzak/love-page/releases">
    <img src="https://img.shields.io/github/v/release/funnyzak/love-page?include_prereleases" alt="Release">
  </a>
  <a href="https://github.com/funnyzak/love-page/issues">
    <img src="https://img.shields.io/github/issues/funnyzak/love-page" alt="Issues">
  </a>
  <a href="https://github.com/funnyzak/love-page/actions/workflows/deploy.yml">
    <img src="https://github.com/funnyzak/love-page/actions/workflows/deploy.yml/badge.svg" alt="Build">
  </a>
  <img src="https://img.shields.io/github/license/funnyzak/love-page" alt="License">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Astro-5.x-FF5D01?logo=astro" alt="Astro">
  <img src="https://img.shields.io/badge/Tailwind-4.x-06B6D4?logo=tailwindcss" alt="Tailwind CSS">
  <img src="https://img.shields.io/badge/TypeScript-strict-3178C6?logo=typescript" alt="TypeScript">
</p>

---

## 预览

<p align="center">
  <img src="https://github.com/user-attachments/assets/0c74a0b6-5a9f-484d-a92e-e89f36f1f496" alt="Love Page Preview" width="80%">
</p>

**中文站演示**: [love.gp.yycc.dev](https://love.gp.yycc.dev) · **English Demo**: [love-page-en.vercel.app](https://love-page-en.vercel.app/)

---

## 30秒部署你的专属页面

### 方式一：GitHub Pages（推荐）

```bash
# 1. Fork 本仓库
# 2. 设置 Secrets：Settings → Secrets → Actions → New secret
#    Name: LOVE_CONFIG_JSON
#    Value: {"boy":"你的名字","girl":"TA的名字","loveDate":"2020-01-01"}
# 3. 等待自动部署完成
```

### 方式二：Vercel / Netlify / Cloudflare

```bash
# 克隆项目
git clone https://github.com/funnyzak/love-page.git
cd love-page
npm install

# 配置并构建
VITE_LOVE_CONFIG_JSON='{"boy":"你的名字","girl":"TA的名字","loveDate":"2020-01-01"}' npm run build

# 部署到任意平台
npx vercel --prod          # Vercel
npx netlify deploy --prod  # Netlify
npx wrangler pages deploy dist  # Cloudflare
```

访问 `http://localhost:4321` 本地预览。

---

## 核心功能

| 功能 | 描述 |
|------|------|
| **今日摘要** | 首屏展示最近纪念日与常用入口 |
| **时光印记** | 实时显示在一起的年、天、时、分、秒 |
| **里程碑时间线** | 横向时间轴展示重要节点与故事 |
| **纪念日倒计时** | 临近提醒 + 当天全屏庆祝彩蛋 |
| **纪念卡生成** | 一键生成适合分享的竖版纪念卡 |
| **照片墙** | 大图预览、左右滑动浏览 |
| **背景音乐** | 自定义歌单，支持多种播放模式 |
| **主题切换** | 深色/浅色/跟随系统 |
| **多端适配** | 手机、平板、电脑都能舒适浏览 |
| **国际化** | 支持中文和英文 |
| **页面加密** | 可选密码保护，适合私密分享 |

---

## 快速配置

最小配置示例：

```json
{
  "boy": "你的名字",
  "girl": "TA的名字",
  "loveDate": "2020-01-01",
  "marriageDate": "2022-05-20",
  "milestones": [
    {"date": "2020-01-01", "label": "相恋", "icon": "💕", "story": "在一起的第一天"}
  ],
  "quotes": ["始于初见，止于终老"],
  "secretMessage": "感谢相遇，余生请多指教"
}
```

完整配置项请参考 [CONFIG.md](./CONFIG.md) 和 [config.example.json](./config.example.json)。

---

## 部署指南

### GitHub Pages

1. Fork 本仓库
2. **Settings** → **Pages** → Source 选择 **GitHub Actions**
3. **Settings** → **Secrets** → **Actions** → 添加 `LOVE_CONFIG_JSON`

### Cloudflare Pages

| 配置项 | 值 |
|--------|-----|
| Build command | `npm run build` |
| Build output | `dist` |
| Environment | `NODE_VERSION=22` |

### Vercel

| 配置项 | 值 |
|--------|-----|
| Framework | Astro |
| Build Command | `npm run build` |
| Output Directory | `dist` |

### Netlify

| 配置项 | 值 |
|--------|-----|
| Build command | `npm run build` |
| Publish directory | `dist` |

---

## 常见问题

<details>
<summary><strong>音乐无法自动播放？</strong></summary>
大多数浏览器禁止音频自动播放，需用户首次交互后才能播放。设置 `music.autoPlay: false` 让用户手动点击。
</details>

<details>
<summary><strong>如何更换字体？</strong></summary>

在 `src/layouts/BaseLayout.astro` 中修改 Google Fonts 链接，并在 CSS 中调整 `font-family`。
</details>

<details>
<summary><strong>如何关闭某个区块？</strong></summary>

通过 `sections` 配置关闭，例如：`{"sections":{"photoWall":false}}`。
</details>

<details>
<summary><strong>构建后样式异常？</strong></summary>

确保 `astro.config.mjs` 中的 `site` 与配置里的 `siteUrl` 一致。
</details>

---

## 开发指南

### 环境要求

- Node.js 18+（推荐 22）
- npm / pnpm / yarn

### 本地开发

```bash
npm install     # 安装依赖
npm run dev     # 启动开发服务器
npm run build   # 构建生产版本
npm run preview # 预览构建结果
npm run test    # 运行测试
```

### 目录结构

```
love-page/
├── src/
│   ├── config/          # 配置模块
│   ├── i18n/            # 国际化
│   ├── components/      # Astro 组件
│   ├── scripts/         # 前端脚本
│   ├── styles/          # 样式文件
│   └── pages/           # 页面路由
├── public/              # 静态资源
├── config.example.json  # 配置示例
└── CONFIG.md            # 配置文档
```

### 技术栈

- [Astro](https://astro.build) 5.x - 静态站点生成
- [TypeScript](https://www.typescriptlang.org) - 类型安全
- [Tailwind CSS](https://tailwindcss.com) v4 - 原子化 CSS
- Google Fonts - Dancing Script / Ma Shan Zheng / Noto Sans SC

### 国际化

项目支持中文（`zh-CN`）和英文（`en-US`），通过 `siteLocale` 配置切换。

**新增语言步骤：**

1. 在 `src/i18n/locales.ts` 添加语言标识符
2. 在 `src/i18n/messages/` 创建消息文件（如 `ja-JP.ts`）
3. 在 `astro.config.mjs` 的 `i18n.locales` 添加新语言
4. 更新 `src/i18n/utils.ts` 中的 `MESSAGES_MAP`

### 缓存策略

项目针对静态资源优化了缓存策略：

| 资源类型 | 缓存策略 |
|----------|----------|
| HTML 页面 | `max-age=0, must-revalidate` |
| 指纹资源 `/_astro/*` | `max-age=31536000, immutable` |
| 非指纹媒体 | `max-age=604800, must-revalidate` |

- **Vercel**: 使用 `vercel.json` 配置
- **Cloudflare Pages**: 使用 `public/_headers` 配置

---

## 贡献

欢迎提交 Issue 和 Pull Request！

```bash
# 开发流程
git checkout -b feature/amazing-feature
git commit -m "feat: add amazing feature"
git push origin feature/amazing-feature
# 提交 Pull Request
```

提交规范：`feat` / `fix` / `docs` / `style` / `refactor` / `perf` / `test` / `chore`

---

## 许可证

[GNU Affero General Public License v3.0](LICENSE)

---

## 致谢

- [Astro](https://astro.build) - 现代静态站点框架
- [Tailwind CSS](https://tailwindcss.com) - 原子化 CSS 框架
- [Google Fonts](https://fonts.google.com) - 优质字体服务

---

<p align="center">
  <a href="https://github.com/funnyzak/love-page/stargazers">
    <img src="https://api.star-history.com/svg?repos=funnyzak/love-page&type=Date" alt="Star History" width="80%">
  </a>
</p> 

<p align="center">
  如果这个项目对你有帮助，请给一个 ⭐️ 支持一下！
</p>
