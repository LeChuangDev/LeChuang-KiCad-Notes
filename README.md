# LeChuang-KiCad-Notes
> 樂創 KiCad 完整学习笔记（Obsidian Markdown）

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)
[![main](https://img.shields.io/badge/branch-main-blue?style=flat-square)](https://github.com/LeChuangDev/LeChuang-KiCad-Notes/tree/main)

## 📌 仓库概述
本仓库为KiCad全套学习笔记，使用Obsidian Markdown编写。
覆盖KiCad基础配置、原理图绘制、PCB布局、元件库管理、Gerber制造输出、排错与自动化脚本。
可直接用Obsidian打开整个文件夹，支持内部双链；也可使用VS Code单独阅读Markdown文档。

> ⚠️ 说明：Obsidian本地配置文件夹 `.obsidian` 已加入忽略列表，不会上传个人插件、布局缓存。

## 📚 目录结构
```
LeChuang-KiCad-Notes/
├── 00-KiCad 总览 (MOC).md            # 知识库总览 MOC
├── 01 - 基础与配置 /                   # KiCad 安装、全局配置、偏好设置
├── 02 - 原理图设计 (Schematic)/       # 原理图绘制、ERC、BOM 导出
├── 03-PCB 设计 (Layout)/             # PCB 布局、布线、阻抗、DRC
├── 04 - 库管理 (Libraries)/           # 符号库、封装库、3D 模型管理
├── 05 - 制造与输出 (Fabrication)/      # Gerber、钻孔文件、生产文件输出
├── 06 - 疑难杂症 (Troubleshooting)/    # 常见报错、踩坑记录
├── 07 - 命令行与自动化 (CLI)/          # kicad-cli、脚本自动化
├── README.md
├── .gitignore
└── LICENSE
```

## 📖 使用说明
1. 全部文档为 Markdown 格式，**推荐 Obsidian 打开整个文件夹**，原生支持内部双链跳转。
2. 图片资源放在各章节子目录，笔记使用相对路径引用图片。

### Git提交规范（Conventional Commits）
- `feat`: 新增笔记章节
- `docs`: 补充内容、文字修改
- `fix`: 修正错误、勘误
- `refactor`: 调整目录结构

示例：
- `feat: 新增KiCad差分对布线笔记`
- `docs: 补充Gerber生产文件导出步骤`
- `fix: 修正ERC报错排查章节笔误`

## 📜 License
MIT License

笔记为个人学习总结，工程使用请以KiCad官方文档为准。

## 📫 About Author
LeChuang（樂創）
Hardware Engineering Student | Embedded & PCB Design Learner

