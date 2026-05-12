# 三点焊计算器

## 项目简介

三点焊计算器是一款基于 Web 的环形槽焊点标注与 CNC 加工程序生成工具。通过直观的象限分区和参数化配置，快速在圆形工件上布置焊点，并自动生成对应的 G 代码加工程序。支持 P/Q 面镜像反转和顺时针/逆时针路径切换。

## 主要功能

### 1. 图形化焊点标注

- 圆周四象限分区（左上、右上、右下、左下）
- 实时 Canvas 绘图显示焊点位置和标签
- 中心点、起点标识，程序顺序编号
- 自适应画布尺寸，深色/浅色主题跟随系统

### 2. 参数化配置

- **基本几何**：圆直径、起点 C 角度、起点 XY 坐标
- **加工参数**：安全高度、切削深度、退刀距离、暂停时间
- **进给参数**：进给速度 F、接近进给 F2、主轴转速 S2、刀号 T
- **起点偏移**：X 轴自动计算（半径 + 偏移量）

### 3. 角度规则

- 0° ~ 45°：显示为正角度（顺时针区域）
- 45° ~ 90°：自动转换为负角度标注（逆时针区域）
- 示例：输入 80° 自动显示为 -10°，输入 49° 显示为 -41°

### 4. 反转功能

- **反转顺序**：一键切换顺时针 / 逆时针焊点连接顺序
- **反转 PQ 面**：镜像调换左右象限焊点，适配双面加工场景

### 5. CNC 程序生成

- 自动生成 G87 环形槽加工程序
- 绝对坐标输出（相对起点的角度偏移量）
- 实时程序预览，支持复制到剪贴板和导出 TXT 文件

## 技术特点

### 前端技术

- 纯 HTML/CSS/JavaScript 实现，无需后端依赖
- Canvas 2D 绘图，高性能图形渲染
- CSS 变量实现深色/浅色主题切换
- 响应式设计，桌面端和移动端均可使用

### 交互特性

- 实时参数更新和图形重绘
- 象限快捷角度按钮
- 自动字母标签分配（A-Z）
- 自定义颜色选择器

## 使用说明

### 快速开始

1. 打开 `index.html` 文件或部署到 GitHub Pages
2. 在基本几何中设置圆直径和起点位置
3. 配置加工参数（安全高度、切削深度等）
4. 在四个象限中添加焊点，输入 0° ~ 90° 角度
5. 查看图形预览确认焊点位置
6. 复制或导出生成的加工程序

### 添加焊点

- 选择目标象限（左上 / 右上 / 右下 / 左下）
- 输入角度值（0 ~ 90），系统自动转换显示
- 选择标签字母或使用自动分配
- 点击"添加"按钮

### 快捷操作

- 点击预设角度按钮快速填充角度值
- 点击"示例焊点"一键加载演示数据
- 点击"清除全部"清空所有焊点
- 使用"反转顺序"和"反转 PQ 面"切换加工模式

### 程序导出

1. 点击"复制程序"将代码复制到剪贴板
2. 点击"导出文件"下载为 TXT 文本文件

## 开发信息

### 开发者

- **主要开发者**：鱼
- **AI 协作**：DeepSeek AI
- **开发时间**：2026 年 5 月

### 技术栈

- 原生 JavaScript (ES6+)
- HTML5 Canvas API
- CSS3 (Grid、Flexbox、CSS 变量)
- 响应式 Web 设计

### 项目特点

1. **无依赖**：不依赖任何外部库或框架
2. **离线使用**：所有功能在浏览器本地运行
3. **跨平台**：支持桌面和移动设备
4. **易部署**：单 HTML 文件即可运行

## 注意事项

1. **单位系统**：所有尺寸单位为毫米（mm），角度单位为度（°）
2. **坐标系统**：遵循数控机床坐标系约定
3. **程序格式**：生成的是 G87 环形槽加工循环代码
4. **精度**：角度计算精度为一位小数
5. **在实际加工前，请务必在仿真软件中验证生成的程序，确保加工安全。**

## 更新日志

### v1.0 (2026-05)

- 初始版本发布
- 四象限焊点标注功能
- 角度自动转换规则 (0-45°/45-90°)
- 反转顺序和反转 PQ 面功能
- G87 程序生成和导出
- 深色模式支持
- 响应式设计

## 在线使用

https://xiaowuyu273637.github.io/Three-Point-Welding-Calculator/

## 贡献指南

欢迎提交 Issue 和 Pull Request 来改进这个项目。

## 许可证

本项目遵循 MIT 许可证。

---

# Three-Point Welding Calculator

## Project Introduction

The Three-Point Welding Calculator is a web-based tool for annular groove weld point marking and CNC machining program generation. Through intuitive quadrant partitioning and parametric configuration, quickly arrange weld points on circular workpieces and automatically generate corresponding G-code machining programs. Supports P/Q face mirror reversal and clockwise/counterclockwise path switching.

## Main Features

### 1. Graphical Weld Point Marking

- Four-quadrant circular partitioning (Top-Left, Top-Right, Bottom-Right, Bottom-Left)
- Real-time Canvas drawing showing weld point positions and labels
- Center point, start point markers, and program sequence numbering
- Adaptive canvas sizing, dark/light theme follows system

### 2. Parametric Configuration

- **Basic Geometry**: Circle diameter, start C angle, start XY coordinates
- **Machining Parameters**: Safe Z height, cutting depth, retract distance, dwell time
- **Feed Parameters**: Feed rate F, approach feed F2, spindle speed S2, tool number T
- **Start Offset**: X-axis auto-calculation (radius + offset)

### 3. Angle Rules

- 0° ~ 45°: Displayed as positive angle (clockwise region)
- 45° ~ 90°: Automatically converted to negative angle (counterclockwise region)
- Example: Input 80° auto-displays as -10°, input 49° displays as -41°

### 4. Reversal Functions

- **Reverse Order**: One-click toggle between clockwise / counterclockwise weld point connection
- **Reverse P/Q Face**: Mirror swap left/right quadrant weld points for dual-face machining

### 5. CNC Program Generation

- Auto-generates G87 annular groove machining programs
- Absolute coordinate output (angle offset relative to start point)
- Real-time program preview, copy to clipboard and export as TXT file

## Technical Features

### Frontend Technology

- Pure HTML/CSS/JavaScript implementation, no backend dependencies
- Canvas 2D drawing, high-performance graphics rendering
- CSS variables for dark/light theme switching
- Responsive design, works on desktop and mobile

### Interactive Features

- Real-time parameter updates and graphic redrawing
- Quadrant quick-angle buttons
- Automatic letter label assignment (A-Z)
- Custom color picker

## Usage Instructions

### Quick Start

1. Open `index.html` or deploy to GitHub Pages
2. Set circle diameter and start position in basic geometry
3. Configure machining parameters (safe height, cutting depth, etc.)
4. Add weld points in four quadrants, input 0° ~ 90° angles
5. Check graphic preview to confirm weld point positions
6. Copy or export the generated machining program

### Adding Weld Points

- Select target quadrant (Top-Left / Top-Right / Bottom-Right / Bottom-Left)
- Enter angle value (0 ~ 90), system auto-converts display
- Select label letter or use auto-assign
- Click "Add" button

### Quick Operations

- Click preset angle buttons to quickly fill values
- Click "Example" to load demo data
- Click "Clear All" to remove all weld points
- Use "Reverse Order" and "Reverse P/Q Face" to toggle machining modes

### Program Export

1. Click "Copy Program" to copy code to clipboard
2. Click "Export File" to download as TXT text file

## Development Information

### Developer

- **Main Developer**: Yu (Fish)
- **AI Collaboration**: DeepSeek AI
- **Development Date**: May 2026

### Technology Stack

- Native JavaScript (ES6+)
- HTML5 Canvas API
- CSS3 (Grid, Flexbox, CSS Variables)
- Responsive Web Design

### Project Highlights

1. **No Dependencies**: Does not rely on any external libraries or frameworks
2. **Offline Use**: All functions run locally in the browser
3. **Cross-Platform**: Supports desktop and mobile devices
4. **Easy Deployment**: Runs with a single HTML file

## Important Notes

1. **Unit System**: All dimensional units in millimeters (mm), angles in degrees (°)
2. **Coordinate System**: Follows CNC machine tool coordinate conventions
3. **Program Format**: Generates G87 annular groove machining cycle code
4. **Precision**: Angle calculation precision to one decimal place
5. **Always verify the generated program in simulation software before actual machining.**

## Update Log

### v1.0 (2026-05)

- Initial version release
- Four-quadrant weld point marking
- Auto angle conversion rules (0-45°/45-90°)
- Reverse order and reverse P/Q face functions
- G87 program generation and export
- Dark mode support
- Responsive design

## Live Demo

https://xiaowuyu273637.github.io/Three-Point-Welding-Calculator/

## Contribution Guidelines

Issues and Pull Requests to improve this project are welcome.

## License

This project follows the MIT License.

---

本工具由 鱼 与 DeepSeek AI 共同开发 | Developed by Yu (Fish) in collaboration with DeepSeek AI