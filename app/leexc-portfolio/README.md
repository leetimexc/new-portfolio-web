# Rico Portfolio - Designer Portfolio Website

> [中文文档](README-zh.md) | English

该项目是基于 Astro 构建的高性能设计师作品集模板，采用复古蓝配色、精心打磨的动效与响应式结构，以提供沉浸的浏览体验。

![Astro](https://img.shields.io/badge/Astro-5.15.4-FF5D01?logo=astro&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.1.14-38B2AC?logo=tailwind-css&logoColor=white)
![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)

## ✨ 主要特性

- 🚀 **Astro 构建** - 轻量、高效的静态站点生成器
- 🎨 **复古蓝风格** - 深浅色模式切换，统一视觉语言
- 📱 **响应式布局** - 覆盖从桌面到移动的所有设备
- 🎭 **流畅动效** - 结合 AOS 与定制动画提升层次感
- 📝 **博客系统** - 原生支持 MDX 博客内容
- 🎯 **作品集展示** - 精致卡片与过渡，突出案例故事
- 🔍 **SEO 优化** - 自动生成 SEO 与社交媒体标签
- ⚡ **性能优化** - 图片压缩、代码拆分与按需加载
- 🌐 **多语言友好** - 易扩展的 i18n 支持

## 🛠️ 技术栈

- **框架**：[Astro](https://astro.build) 5.15.4（兼容 v6）
- **样式**：[Tailwind CSS](https://tailwindcss.com) 4.1.14
- **动效**：[AOS](https://michalsnik.github.io/aos/)
- **物理引擎**：[Matter.js](https://brm.io/matter-js/)
- **内容管理**：MDX
- **类型检查**：TypeScript

## 📦 安装

### 通过包管理器安装依赖

```bash
# 推荐 pnpm
pnpm install

# npm 用户
npm install

# yarn 用户
yarn install
```

### 环境变量配置

复制示例文件 `.env.example` 为 `.env` 并填写：

```bash
cp .env.example .env
```

编辑 `.env` 并配置：

```env
# 网站地址（可选，默认 https://your-domain.com）
PUBLIC_SITE_URL=https://your-domain.com

# 可选分析工具 ID
PUBLIC_GA4_ID=your-google-analytics-id
PUBLIC_UMAMI_ID=your-umami-id
```

> **提示**：若未设置 `PUBLIC_SITE_URL`，会使用默认 `https://your-domain.com`。部署后建议补充真实域名，以确保站点地图、RSS 与 SEO 元数据一致。

## 🚀 开发

```bash
# 启动开发服务器
npm run dev
# 或
pnpm dev

# 访问 http://localhost:4321
```

## 📦 打包

```bash
# 生产构建
npm run build

# 预览产物
npm run preview
```

## 📁 项目结构

```
├── public/              # 静态资源
│   ├── assets/         # 图片、视频等
│   └── favicon.png     # 网站图标
├── src/
│   ├── assets/         # 源素材
│   ├── collections/    # 数据集合（作品、经历等）
│   ├── components/     # Astro 组件
│   │   ├── cards/      # 卡片组件
│   │   ├── sections/   # 区块组件
│   │   ├── ui/         # UI 组件
│   │   └── widgets/    # 小组件
│   ├── config/         # 配置文件
│   ├── content/        # MDX 博客内容
│   ├── layouts/        # 布局组件
│   ├── pages/          # 页面路由
│   ├── scripts/        # 脚本文件
│   └── styles/         # 样式文件
├── astro.config.mjs    # Astro 配置
├── tailwind.config.mjs # Tailwind 配置
└── package.json        # 依赖声明
```

## 🎨 定制指南

### 修改站点信息

在 `src/config/site.js` 中调整基础信息：

```javascript
export const siteConfig = {
  title: "Your Portfolio",
  author: "Your Name",
  url: "https://your-domain.com",
  // 其他配置项
};
```

### 修改主题色

在 `src/styles/global.css` 里定义 CSS 变量：

```css
@theme {
  --color-primary: #2d6dc3;
  --color-primary-dark: #3b7bd9;
  /* 更多颜色变量 */
}
```

### 添加作品

在 `src/collections/works.json` 中补充作品数据。

### 添加博客

在 `src/content/post/` 下创建新的 MDX 文件。本模板采用 Astro v5 的 Content Layer API，与 v6 兼容：

- ✅ 使用新版 Content Layer API（`glob` 加载器）
- ✅ 以 `entry.id` 替代旧的 `entry.slug`
- ✅ 使用 `render(entry)` 取代旧的 `entry.render()`
- ✅ 通过 `import.meta.env` 而非 `process.env`
- ✅ 使用 `import.meta.glob()` 替代废弃的 `Astro.glob()`
- ✅ 所有 `getStaticPaths()` 参数均为字符串（v6 要求）

## Figma 资源

- **Programming Sticker**：[Figma rogramming-sticker-1-0](https://www.figma.com/community/file/1392100849031958853/programming-sticker-1-0)
- **Bento Cards**：[Figma Bento Cards](https://www.figma.com/community/file/1231184483170475120)
- **Social Cards**：[Figma Bento 2.5d](https://www.figma.com/community/file/1232620929235403629/bento-2-5d-widgets)

## 💡 致谢

- [Astro](https://astro.build) - 提供静态站点生成能力
- [Tailwind CSS](https://tailwindcss.com) - 项目全局样式工具
- [Matter.js](https://brm.io/matter-js/) - 增强交互体验的物理引擎
- [AOS](https://michalsnik.github.io/aos/) - 负责滚动动画

## 💜 支持项目

如果这个模板对你有帮助，欢迎通过星标、提交问题或贡献来支持它持续进化。

## 📝 更新日志

### 最新更新（2024）

- **升级至 Astro 5.15.4** - 完全符合 v5.15 标准并兼容 v6
- **内容集合升级** - 全面使用新版 Content Layer API，移除所有过时接口
- **API 现代化** - 将所有废弃 API 更新至最新写法
- **性能优化** - 构建与运行时性能稳步提升

⭐ 如果该项目帮到你，请顺手点个 Star！
