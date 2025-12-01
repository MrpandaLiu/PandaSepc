# PandaSepc

中文友好、支持敏捷开发的 Spec Driven AI 编程规则集

# Why PandaSepc?

已经有了 OpenSpec、SpecKit 这些工具，为什么还需要 PandaSpec：

- 🐼 更好的中文支持。不管是对话还是书写任何文档，都使用中文减少阅读压力
- 🚀 工作流优化。生成需求文档-技术文档和计划-生成代码，更符合个人日常需求开发习惯，取消冗杂的协同功能设计，更专注单一需求的实现，迭代更加敏捷
- 👊🏻 技术文档强化。对比其他 Spec 工具，在生成 `design.md` 中，更注重链路图、代码实现方案，可以作为你的需求技术方案使用
- 👋🏻 无关 AI Coding 工具。无需安装任何 cli，在任何主流 AI Coding 工具都可以直接复用到工作流中

# Usage

## Install

- 将 `commands` 目录复制到你的 AI Coding 工具指令目录下，比如使用 Claude Code 则在项目根目录的 `.claude`

- 将 `pandaspec` 目录复制到你的项目根目录

- 为你的 AI Coding 工具全局规则集添加 `AGENTS.md` 的内容，比如使用 Claude Code 则在 `CLAUDE.md` 文件中添加即可

## Usage

1. 需求澄清

使用 `/pandaspec:plan` 来为项目生成 `spec.plan.md` 文件，填写需求的详细描述

2. 技术方案生成

使用 `/pandaspec:design` 会消费前面创建的 `spec.plan.md` 文件生成技术方案，方案的地址位于 `pandaspec/features/<your-feature>` 目录下，包含 design.md 和 task.md。design.md 主要包含需求的背景、变更原因、架构链路图、变更代码等模块，task.md 顾名思义是要交给 AI Coding 工具执行的计划列表

3. 代码生成

使用 `/pandaspec:apply <your-feature>` 来生成具体变更代码
