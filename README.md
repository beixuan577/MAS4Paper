# MAS4Paper - Multi-Agent System for Academic Paper Generation

<div align="center">

[English](#english) | [中文](#中文)

</div>

---

<a name="中文"></a>
## 📝 中文介绍

### 概述

**MAS4Paper** 是一套面向经济学与交叉学科研究的**多智能体协作学术论文生成系统**。系统能够从选题、数据采集、处理、理论建模、实证分析、图表绘制、论文写作、独立审稿、修改迭代到最终排版，**全流程自主完成一篇学术论文的生成**。

### ✨ 核心特性

- 🤖 **11个专业智能体** - 分工明确，协同工作
- 🔄 **全流程自动化** - 从选题到排版，无需人工干预
- 📊 **可复现性保障** - 所有中间数据、代码、过程完整记录
- 🎯 **标准化接口** - 智能体间通过共享知识库协作
- 📚 **多学科支持** - 经济学与交叉学科研究

### 🏗️ 系统架构

```
┌─────────────────────────────────────────────────────────────┐
│                    编排层 (Orchestrator)                      │
│                  任务调度 + 流程控制 + 冲突解决                   │
└─────────────────────────────────────────────────────────────┘
                              │
       ┌──────────────────────┼──────────────────────┐
       ▼                      ▼                      ▼
┌─────────────┐      ┌─────────────┐      ┌─────────────┐
│   研究层    │      │   写作层    │      │   质控层    │
│  Agent 1-5  │      │  Agent 6-8  │      │  Agent 9-11 │
└─────────────┘      └─────────────┘      └─────────────┘
```

### 🤖 11个专业智能体

| 层级 | Agent | 名称 | 职责 |
|------|-------|------|------|
| 研究层 | Agent 1 | 选题策划Agent | 分析研究前沿，确定选题方向 |
| 研究层 | Agent 2 | 数据采集Agent | 数据收集、清洗、标注 |
| 研究层 | Agent 3 | 理论建模Agent | 理论框架构建、假设推导 |
| 研究层 | Agent 4 | 实证分析Agent | 统计分析、回归、因果推断 |
| 研究层 | Agent 5 | 图表绘制Agent | 可视化图表生成 |
| 写作层 | Agent 6 | 结构规划Agent | 论文结构设计、章节安排 |
| 写作层 | Agent 7 | 内容撰写Agent | 各章节内容撰写 |
| 写作层 | Agent 8 | 排版格式Agent | 格式调整、参考文献、排版 |
| 质控层 | Agent 9 | 独立审稿Agent | 同行评审模拟、问题发现 |
| 质控层 | Agent 10 | 修改迭代Agent | 根据审稿意见修改 |
| 质控层 | Agent 11 | 质量检验Agent | 最终质量检查、复现性验证 |

### 📅 工作流程

```
阶段一（Day 1-3）: 研究准备
  → 选题策划 + 数据采集 + 理论建模

阶段二（Day 4-6）: 实证分析
  → 实证分析 + 图表绘制

阶段三（Day 7-10）: 论文撰写
  → 结构规划 + 内容撰写 + 排版格式

阶段四（Day 11-14）: 质量迭代
  → 独立审稿 + 修改迭代 + 质量检验
```

### 🚀 快速开始

#### 安装方式

1. 下载 `mas4paper.skill` 文件
2. 在 OpenClaw/QClaw 中导入技能

#### 使用方式

```
用户: 用MAS4Paper生成一篇关于人工智能对就业影响的论文
AI: [启动多智能体协作系统]
    Agent 1: 选题策划...
    Agent 2: 数据采集...
    Agent 3: 理论建模...
    ...
    [输出完整论文 + 可复现包]
```

### 📦 输出内容

```
/output/
├── paper_final.docx        # 最终论文
├── paper_final.pdf         # PDF版本
├── figures/                # 所有图表
├── data/                   # 数据集 + 数据字典
├── code/                   # 完整代码
├── logs/                   # 执行日志
└── reproducibility/        # 可复现包
```

### 🔬 可复现性保障

- ✅ 全过程记录（输入、输出、时间戳）
- ✅ 数据清洗规范（缺失值、异常值处理记录）
- ✅ 代码版本控制（完整运行环境配置）
- ✅ 随机种子固定（确保结果可复现）

---

<a name="english"></a>
## 📝 English Introduction

### Overview

**MAS4Paper** is a **Multi-Agent System for Academic Paper Generation** designed for economics and interdisciplinary research. The system can autonomously complete the entire process of generating an academic paper: from topic selection, data collection, processing, theoretical modeling, empirical analysis, figure generation, paper writing, independent review, revision iteration to final formatting.

### ✨ Key Features

- 🤖 **11 Specialized Agents** - Clear division of labor, collaborative work
- 🔄 **Full Process Automation** - From topic selection to formatting
- 📊 **Reproducibility Guarantee** - Complete recording of all intermediate data, code, and processes
- 🎯 **Standardized Interfaces** - Agents collaborate through shared knowledge base
- 📚 **Multi-disciplinary Support** - Economics and interdisciplinary research

### 📥 Installation

1. Download the `mas4paper.skill` file
2. Import the skill in OpenClaw/QClaw

### 💬 Usage

Simply say: "Use MAS4Paper to generate a paper about [your research topic]"

### 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

## 📁 Repository Structure

```
mas4paper/
├── SKILL.md                          # Main skill documentation
├── README.md                         # This file
├── LICENSE                           # MIT License
├── scripts/
│   └── run_mas4paper.py              # Main control script
├── references/
│   ├── agent_configs.md              # Agent configuration reference
│   ├── code_standards.md             # Code standards
│   ├── data_sources.md               # Data source list
│   └── journal_templates.md          # Journal format templates
└── assets/
    └── config.yaml                   # Configuration example
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📮 Contact

- Issues: [GitHub Issues](https://github.com/your-repo/mas4paper/issues)
- Discussions: [GitHub Discussions](https://github.com/your-repo/mas4paper/discussions)

## 🙏 Acknowledgments

This skill is inspired by the paper "A Reproducible and Scalable Intelligent Research Paradigm" and aims to provide a practical implementation path for AI-assisted academic research.

---

<div align="center">

**Star ⭐ this repo if you find it helpful!**

Made with ❤️ by the MAS4Paper Team

</div>
