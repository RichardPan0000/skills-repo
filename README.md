# skills-repo
A repository for storing various skills.



## long-horizon-scaffold 技能总结与简短描述
### 简短描述（用于介绍）
The long-horizon-scaffold skill is used for complex tasks such as long-term projects, major modifications, and cross-file changes. It builds a unified task scaffold by creating a worklog task directory and three core files: spec.md, plan.md, and status.md, ensuring that tasks are traceable, recoverable, reviewable, and continuously promotable.
### 技能核心总结
该技能核心是为复杂任务（长周期开发、跨文件修改、需规划后实施等）提供标准化执行框架，核心流程与要求如下：
1. 触发时机：适用于多文件修改、需规划调研、跨回合/多天完成、涉及架构/接口调整等复杂任务，小改动无需使用（除非用户要求）。
2. 核心动作：先判断任务适配性，生成 kebab-case 格式任务标识，创建 worklog/<任务标识> 目录，初始化 spec.md（任务规范）、plan.md（执行计划）、status.md（任务状态）三个核心文件并规范其必备内容。
3. 执行要求：实施前需阅读理解三个核心文件，执行中持续更新文件（状态、计划、需求变化），任务结束后补全最终结果与遗留问题；禁止跳过初始化、直接改代码、覆盖已有文件等不规范操作。
4. 核心目标：通过标准化脚手架，实现复杂任务的可追踪、可恢复、可审查，确保任务有序推进。
