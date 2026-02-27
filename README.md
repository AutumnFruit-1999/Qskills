# Qskills - 技能仓库

本仓库包含用于 Cursor/Claude Agent 的技能（Skills），用于增强 AI 助手的专业能力。

## 技能列表

| 技能名称 | 目录 | 优先级 | 描述 |
|---------|------|--------|------|
| **mcp-skills-logger** | `mcp-skills-logger/` | 最高 | 调用任何工具前必须先输出完整的调用记录。要求按"问题→调用工具→执行工具→工具返回"的严格顺序输出记录。 |
| **source-citation** | `source-citation/` | 必需 | 为信息、反馈、解释和摘要提供引用、参考和来源。在使用工具获取信息时自动包含 URL、截图、文件路径、引用或时间戳。 |

## 技能详细信息

### mcp-skills-logger
- **用途**: 强制记录所有工具调用链条
- **触发条件**: 调用任何工具、Skill、MCP 或子代理之前
- **核心规则**: 先记录，后执行，再返回
- **优先级**: 最高（【强制执行 | 绝对禁止跳过】）

### source-citation
- **用途**: 提供信息来源引用和参考
- **触发条件**: 
  - 使用 WebSearch、WebFetch、Read 等工具获取信息
  - 用户需要搜索结果摘要
  - 用户询问事实性问题
  - 用户要求提供来源/引用/参考
- **优先级**: 必需（【必须读取】）

## 目录结构

```
Qskills/
├── README.md                           # 本文件
├── mcp-skills-logger/                  # 工具记录器技能
│   └── SKILL.md
└── source-citation/                    # 来源引用技能
    └── SKILL.md
```

## Git 提交历史

| 提交 | 说明 |
|------|------|
| `b5c935e` | Add README.md: Summary table of all skills in the repository |
| `d944b64` | Add source-citation skill: Provide citations and references for information |
| `d9acfb7` | Update mcp-skills-logger: Add priority indicator to description |
| `915eff3` | Rename mcp-logger to mcp-skills-logger |
| `9ed6068` | Initial commit: Add mcp-logger skill |
