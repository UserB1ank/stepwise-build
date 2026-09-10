# Stepwise Build

> Learn by building, one verified step at a time.

[中文](#中文) · [English](#english)

## 中文

Stepwise Build 是一个通用的 Agent Skill，用于带领用户渐进式构建软件项目。它不会一次性交付完整项目，而是将工作拆成小而可验证的步骤，让用户亲自编写、运行和理解代码。

### 它解决什么问题

- 一次只推进一个可运行、可验证的增量
- 在动手实现时讲清设计原则与工程取舍
- 根据用户水平调整讲解深度与推进速度
- 在每一步设置检查题和明确的验证标准
- 用户提交代码后，以教学为目标进行聚焦的代码审查
- 每 3–5 步进行一次里程碑复盘

### 适用场景

当用户希望：

- 边做项目边学习
- 自己写代码，而不是直接获得完整答案
- 从原型逐步成长到生产级实现
- 理解每一步背后的工程原则
- 获得循序渐进的代码审查和排错指导

如果用户明确要求直接完成整个项目，或者只需要查询、解释和一行修复，则不应启用此 skill。

### 安装

克隆仓库，并将仓库目录放入你的 Agent 所配置的 skills 目录：

```bash
git clone https://github.com/UserB1ank/stepwise-build.git
```

不同 Agent 的 skills 目录和加载方式可能不同，请以对应产品的配置说明为准。这个仓库不依赖特定 Agent 的专有元数据；入口只有标准的 [`SKILL.md`](./SKILL.md)。

### 使用示例

```text
请一步一步带我用 Go 构建一个任务管理 API。我想自己写代码，
每次只给我一个可以运行和验证的小步骤，并解释其中的设计原则。
```

```text
我已经完成了上一步。这是运行结果和我写的代码，请先检查，
确认没有问题后再告诉我下一步。
```

### 工作循环

```text
明确项目简报 → 给出一个小步骤 → 用户实现并运行
       ↑                              ↓
调整难度与节奏 ← 检查结果、答疑与代码审查
```

每一步都包含目标、学习点、具体任务、最小代码或命令、验证方法、检查题、排错提示和提交建议。只有用户反馈结果后，才会进入下一步。

## English

Stepwise Build is an agent-agnostic skill for guiding users through software projects incrementally. Instead of delivering an entire project at once, it turns the work into small, verifiable increments that the user writes, runs, and understands.

### What it does

- Advances through one runnable, verifiable increment at a time
- Explains engineering principles and trade-offs while building
- Adapts explanation depth and pace to the user's experience
- Defines a check question and observable success criteria for every step
- Reviews user-written code with a focused teaching goal
- Runs a milestone review every three to five steps

### When to use it

Use this skill when someone wants to learn by building, write the code themselves, progressively improve a project toward production quality, or understand the reasoning behind each change.

Do not activate it when the user explicitly wants the complete implementation immediately, or when the request is only a quick lookup, isolated explanation, or one-line fix.

### Installation

Clone the repository and place its directory in the skills location configured by your agent:

```bash
git clone https://github.com/UserB1ank/stepwise-build.git
```

Skill locations and loading mechanisms vary between agents. This repository avoids product-specific metadata and uses [`SKILL.md`](./SKILL.md) as its only entry point.

### Example prompt

```text
Guide me through building a task-management API in Go. I want to write
the code myself, one runnable and verifiable step at a time. Explain the
engineering principles behind each step and wait for my results.
```

### Core loop

```text
Capture the brief → Give one small step → User implements and runs it
        ↑                                      ↓
 Adapt pace and depth ← Review results, answer, and inspect the code
```

Every step includes a goal, learning points, concrete tasks, minimal code or commands, verification instructions, a check question, troubleshooting hints, and a suggested commit message. The next step starts only after the user reports the result.

## Repository contents

```text
.
├── SKILL.md    # Skill definition and operating instructions
├── README.md   # Overview, installation, and usage examples
└── LICENSE     # GNU General Public License v3.0
```
