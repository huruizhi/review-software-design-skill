# Review Software Design Skill

一个轻量的 Codex 软件设计评审 Skill，基于《软件设计的哲学》的复杂度管理思想，并针对 AI 辅助开发增加了可验证性、非确定性隔离和小批量变更等检查。

## 适用阶段

- **设计阶段（主要）**：比较方案，确定模块、接口、接缝、错误语义和验证方式。
- **Code Review 阶段（辅助）**：检查实现是否出现浅模块、信息泄漏、无效抽象和设计漂移。

## 核心能力

- 用变更放大、认知负担和未知影响评估复杂度。
- 识别深模块、浅模块和纯转发层。
- 检查信息隐藏、局部性和接缝位置。
- 将真实故障与不必要的错误分类区分开。
- 对重要决策执行“设计两次”。
- 用类型、Schema、契约测试、可观测性和可回滚变更约束 AI 生成代码。

## 安装

```bash
git clone git@github.com:huruizhi/review-software-design-skill.git
cp -R review-software-design-skill/skills/review-software-design ~/.codex/skills/
```

`dist/review-software-design.skill` 是可分发的 Skill 压缩包。

## 使用

设计阶段：

```text
使用 $review-software-design 评审这份设计方案，比较两种模块和接口设计。
```

Code Review 阶段：

```text
使用 $review-software-design 检查这个 PR 是否出现设计漂移、浅模块或信息泄漏。
```

Skill 会以 **Keep**、**Deepen** 或 **Redesign** 开头，然后给出证据、推荐设计、验证方式和主要取舍。

## 仓库结构

```text
.
├── README.md
├── dist/
│   └── review-software-design.skill
└── skills/
    └── review-software-design/
        ├── SKILL.md
        └── agents/openai.yaml
```
