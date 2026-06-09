# LogScope Studio

<div align="center">


**面向安全分析与运维排查的桌面日志分析工具**

作者：**tongnian951-stack**  
主页：[https://github.com/tongnian951-stack](https://github.com/tongnian951-stack)

</div>

---

## 项目简介

LogScope Studio 是一款基于 Wails、Go、Vue 3 和 TypeScript 构建的桌面日志分析工具。它面向本地日志审计、异常排查、攻防溯源和日常运维分析场景，提供日志打开、检索、过滤、高亮、统计分析、时间线标记和报告导出等能力。

项目适合处理 SSH、Nginx、MySQL、系统日志、Web 访问日志、错误日志等文本型日志文件。

## 界面预览

![分析视图](./assets/image-20250726123621237.png)

## 核心能力

### 日志查看

- 支持本地日志文件打开与快速浏览
- 支持大文件分片处理，降低一次性加载压力
- 支持多文件分析和最近文件记录
- 支持行号、关键字段和上下文信息展示

### 检索过滤

- 支持普通文本检索
- 支持正则表达式匹配
- 支持大小写敏感、全词匹配等检索条件
- 支持多过滤窗口，便于拆分不同分析方向
- 支持基于选中文本快速创建过滤条件

### 高亮标记

- 支持自定义高亮词
- 支持不同颜色标记不同类型的证据
- 适合标记 IP、账号、URL、状态码、异常关键字和攻击特征

### 统计分析

- 支持 IP、URL、状态码、事件类型等维度统计
- 支持图表展示分析结果
- 支持时间线视图，便于还原事件演变过程
- 支持将关键证据沉淀为分析结果

### 辅助工具

- 文件分片
- 过滤结果导出
- 分析报告导出
- Mermaid 流程图展示
- 内置 CyberChef 辅助分析页面

## 功能截图

### 文件与日志视图



![日志视图](./assets/image-20250726123621237.png)

## 技术栈

| 模块     | 技术              |
| -------- | ----------------- |
| 桌面框架 | Wails v2          |
| 后端     | Go                |
| 前端     | Vue 3、TypeScript |
| 状态管理 | Pinia             |
| UI       | Element Plus      |
| 图表     | ECharts、Mermaid  |
| 构建     | Vite              |

## 目录结构

```text
.
├── backend/                 # 后端模型与服务
├── frontend/                # 前端界面
├── assets/                  # README 截图资源
├── 日志分析/                # 示例日志与分析素材
├── CyberChef_v11.0.0/       # 本地辅助分析工具
├── app.go                   # Wails 应用入口
├── main.go                  # 程序启动入口
├── wails.json               # Wails 配置
└── README.md                # 项目说明
```

## 环境要求

- Windows 10+、macOS 或 Linux
- Go 1.22+
- Node.js 16+
- Wails CLI

安装 Wails CLI：

```bash
go install github.com/wailsapp/wails/v2/cmd/wails@latest
```

## 开发运行

安装前端依赖：

```bash
cd frontend
npm install
cd ..
```

启动开发模式：

```bash
wails dev
```

仅启动前端调试页面：

```bash
cd frontend
npm run dev -- --host 127.0.0.1
```

## 构建

Windows：

```bash
.\build.bat win
```

清理构建产物：

```bash
.\build.bat clean
```

说明：Wails 的 Linux 和 macOS 构建通常需要在对应系统环境中完成。

## 使用流程

```text
选择日志文件
  ↓
浏览原始日志
  ↓
设置检索、过滤和高亮规则
  ↓
查看命中结果与上下文
  ↓
统计关键字段
  ↓
整理时间线和证据
  ↓
导出结果或报告
```

## 适用场景

- SSH 登录异常分析
- Web 访问日志排查
- Nginx 错误日志定位
- MySQL 查询日志审计
- 系统安全事件梳理
- CTF / 应急响应日志题分析

## 项目信息

- 项目名称：LogScope Studio
- 作者：tongnian951-stack
- 项目主页：[https://github.com/tongnian951-stack](https://github.com/tongnian951-stack)
- 版本：1.0.0

## License

本项目遵循仓库内 `LICENSE` 文件声明。
