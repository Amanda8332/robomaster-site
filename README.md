# 个人 RoboMaster 主页 — 使用说明

参照学术个人主页（Kevin Xu 风格的导航与项目页结构）+ 交龙战队的 RoboMaster 内容词汇构建。
纯静态站点：HTML + CSS + JS，**无需编译**，可直接用浏览器打开或部署到 GitHub Pages。

## 文件结构
```
site/
├── index.html              ← 主页（关于 / 数据 / 赛季时间线 / 项目 / 技能 / 联系）
├── css/style.css           ← 全部样式。顶部 :root 是“设计令牌”，改配色/字体只动这里
├── js/main.js              ← 移动端菜单、滚动动画
├── assets/
│   ├── img/                ← 放照片和项目图（me.jpg, proj1.jpg ...）
│   └── 你的简历.pdf         ← 简历放这里，改 index.html 里的链接
└── projects/
    ├── project-template.html    ← 新建项目时复制这个（空白骨架）
    ├── infantry-control.html     ← 步兵电控系统（已写满的完整范例，照着填）
    ├── gimbal-ballistics.html    ← 云台双环控制与弹道解算（骨架）
    ├── uav-flight-control.html   ← 无人机飞控与对地打击（骨架）
    └── power-comm.html           ← 功率控制与裁判系统通信（骨架）
```

> **从哪开始填**：先打开 `projects/infantry-control.html`，它每一节都写满了真实的步兵电控内容（麦轮解算、双环 PID、弹道、防卡弹、功率控制），你只要把 `【方括号】` 里的具体数字和经历换成自己的即可。其余三个骨架页结构相同，照着范例的写法补内容。

## 怎么改（按优先级）
1. **全局替换** `【你的名字】`、`【账号】`、`【your@email.com】` 等所有方括号占位符。
2. **主页 index.html**：改 hero 自我定位、stats 数字、timeline 赛季、projects 卡片、skills 列表、contact。
3. **项目详情页 projects/\*.html**：每页按“背景→职责→方案→问题与解决→成果”填写。**面试重点是“问题与解决”和量化成果**。
4. **配图**：把图片放进 `assets/img/`，替换页面里写着“封面图 / 主图”的占位 div（改成 `<img src="assets/img/xxx.jpg" alt="">`）。

## 换配色 / 字体
打开 `css/style.css` 最顶部的 `:root {}`：
- `--accent` 是强调橙、`--accent-2` 是电控蓝、`--bg` 是背景。
- 想要浅色主题：把 `--bg` 改亮、`--ink` 改暗即可。
- 字体改 `--font-display` / `--font-body`，并同步换 index.html 里的 Google Fonts 链接。

## 新增一个项目
1. 复制 `projects/project-template.html` 改名，如 `radar.html`。
2. 在 `index.html` 的项目网格里复制一张 `.proj-card`，把 `href` 指向新页面。

## 部署到 GitHub Pages（免费、有网址）
1. 新建仓库 `你的用户名.github.io`，把 site/ 里所有文件传到仓库根目录。
2. 仓库 Settings → Pages → Source 选 main 分支 → 保存。
3. 几分钟后访问 `https://你的用户名.github.io`。

> 注意：本环境无网络，Google Fonts 在你本地/线上打开时才会加载；离线预览时字体会回退到系统字体，不影响排版。
