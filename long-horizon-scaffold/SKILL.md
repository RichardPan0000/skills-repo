---
name: long-horizon-scaffold
description: Use when a task spans multiple files or sessions, needs proposal, spec, design, and task decomposition before implementation, or requires resumable worklog, milestone tracking, and verification for a long-running change.

---

# Long Horizon Scaffold

## Overview

在长周期任务里，先建立可恢复的任务骨架，再进入实现。核心原则是把“为什么做、要满足什么、准备怎么做、接下来做什么、当前进展如何”拆开记录，避免把所有内容混进一个 `plan.md`。

## When to Use

满足任一条件时使用：

- 会修改多个文件或多个模块
- 预计跨多个回合或多天完成
- 需要先澄清目标、方案、范围，再开始实现
- 涉及架构、接口、数据流、部署或核心逻辑调整
- 需要中断后可恢复的任务记录
- 用户明确要求先做 proposal, spec, design, tasks, status 管理

不要用于单文件小修、小范围文案修改或一次即可完成的简单配置调整，除非用户明确要求留痕。

## Default Files

在 `worklog/<task-id-date>/` 下默认维护以下文件：

- `proposal.md`: 为什么值得做，本次变更解决什么问题，目标结果是什么
- `spec.md`: 需求、范围、非目标、约束、验收标准、与现状相比的变更点
- `design.md`: 技术方案、模块边界、数据流、权衡、风险、回退思路
- `tasks.md`: 可执行清单、顺序、验证点、完成勾选
- `status.md`: 当前状态、已完成、进行中、阻塞、最新决策、验证结果、下一步

`plan.md` 不再默认创建。若旧任务中已有 `plan.md`，保留它，但在继续大改前把其中内容拆分映射到 `design.md` 和 `tasks.md`。

## Workflow

1. 判断任务是否属于长周期任务；若不是，明确说明无需脚手架。
2. 生成简短的 kebab-case 任务标识，并创建或复用 `worklog/<task-id-date>/`。
3. 若目录已存在，先读取现有文件并续写，不要重建或覆盖。
4. 初始化缺失文件；任何正式实现前，先读完 `proposal.md`、`spec.md`、`design.md`、`tasks.md`、`status.md`。
5. 实施时按任务粒度维护 `tasks.md`，按里程碑维护 `status.md`。
6. 范围变了，先更新 `spec.md`；方案变了，先更新 `design.md`；目标理由变了，先更新 `proposal.md`。
7. 完成前执行必要验证，并把结果、剩余风险、建议下一步写入 `status.md`。
8. 若仓库存在长期基线文档，把最终决策同步回长期文档，再将任务标记为完成或 archived。

## Quick Reference

- `proposal.md` 回答: 为什么做
- `spec.md` 回答: 要满足什么
- `design.md` 回答: 准备怎么做
- `tasks.md` 回答: 现在按什么顺序做
- `status.md` 回答: 做到哪了，还差什么

## Common Mistakes

- 跳过 `proposal.md`，直接进入实现，导致“为何做”在中途漂移
- 把设计方案和执行清单继续混在一个 `plan.md`
- 只改代码不更新 `tasks.md` 或 `status.md`
- 目录已存在时重新初始化，覆盖旧上下文
- 完成后只口头汇报，不记录验证结果和遗留风险
