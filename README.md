# G318/G317 川藏大环线电子路书

> **理想L9 Livis · 30天 · 8,800公里 · G318进 G317出**

## 📚 简介

本项目是 G318/G317 川藏大环线的电子路书，详尽记录 30 天穿越 14 条国家高速和 5 条国家国道的自驾路线，覆盖 5 个阶段、32 个地点、6 个 5000m+ 垭口。

## ✨ 特色

- 📊 **交互式图表**：里程、海拔、道路分布可视化
- 🗺️ **路网拓扑图**：Mermaid 流程图清晰展示
- 🎨 **专业主题**：Material for MkDocs，响应式 + 明暗切换
- 📱 **移动友好**：手机/平板/电脑自适应
- 🔍 **全文搜索**：支持中文分词
- 🔗 **永久链接**：方便分享和引用

## 🛠️ 技术栈

- [MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [Mermaid](https://mermaid.js.org/) - 流程图
- [Vega-Lite](https://vega.github.io/vega-lite/) - 数据可视化

## 🚀 本地构建

### 1. 克隆仓库

```bash
git clone https://origin.cursor.com/git/soengyuchan/g318-g317-roadbook.git
cd g318-g317-roadbook
```

### 2. 安装依赖

```bash
pip install -r requirements.txt
```

### 3. 本地预览

```bash
mkdocs serve
```

浏览器打开 http://127.0.0.1:8000

### 4. 构建静态文件

```bash
mkdocs build
```

生成在 `site/` 目录。

## 📁 目录结构

```
.
├── mkdocs.yml          # MkDocs 配置
├── requirements.txt    # Python 依赖
├── README.md           # 项目说明
├── docs/               # Markdown 源文件
│   ├── index.md        # 首页
│   ├── overview.md     # 行程总览
│   ├── preparation.md  # 行前准备
│   ├── routes.md       # 路线与道路编号
│   ├── charging.md     # 充电站网络
│   ├── health.md       # 高反与健康
│   ├── stage-1-south.md   # 第一阶段
│   ├── stage-2-g318.md    # 第二阶段
│   ├── stage-3-lhasa.md   # 第三阶段
│   ├── stage-4-g317.md    # 第四阶段
│   ├── stage-5-return.md  # 第五阶段
│   ├── emergency.md    # 应急与救援
│   ├── gear.md         # 装备清单
│   ├── about.md        # 关于
│   ├── stylesheets/    # 自定义 CSS
│   └── javascripts/    # 自定义 JS
└── site/               # 构建产物（自动生成）
```

## 🗺️ 路线总览

| 阶段 | 天数 | 路线 | 里程 |
|------|------|------|------|
| 第一阶段 | 5 | 皇岗→桂林→贵阳→成都 | 1,940km |
| 第二阶段 | 9 | **G318** 成都→拉萨 | 2,150km |
| 第三阶段 | 5 | 拉萨+羊湖+珠峰 | 1,650km |
| 第四阶段 | 8 | **G317** 拉萨→成都 | 2,400km |
| 第五阶段 | 3 | 成都→重庆→皇岗 | 1,600km |

## ⚠️ 免责声明

本路书仅供参考。实际路况、天气、政策可能变化，出发前请核实最新信息。

## 📜 许可证

MIT License
