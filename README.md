# OpenClaw 自我进化技能包

让 OpenClaw 具备自我学习、记忆和持续改进能力。

## 功能特性

- ✅ **自动记忆** — 记录用户偏好、习惯
- ✅ **错误追踪** — 自动记录失败和错误
- ✅ **教训记录** — 记录学习到的经验教训
- ✅ **功能需求追踪** — 记录想要但未实现的功能
- ✅ **Hook 自动提醒** — 每次启动时自动提醒反思

## 快速安装

### 一键安装

```bash
git clone https://github.com/lintong1111/openclaw-self-improvement.git
cd openclaw-self-improvement
chmod +x install.sh && ./install.sh
```

### 手动安装

```bash
# 创建目录
mkdir -p ~/.openclaw/workspace/.learnings
mkdir -p ~/.openclaw/hooks/self-improvement

# 复制学习记录模板
cp -r .learnings/* ~/.openclaw/workspace/.learnings/

# 复制 Hook 配置
cp -r hooks/openclaw/* ~/.openclaw/hooks/self-improvement/

# 启用 Hook
openclaw hooks enable self-improvement
```

### 验证安装

```bash
openclaw hooks list
ls ~/.openclaw/workspace/.learnings/
```

## 文件结构

```
.
├── README.md
├── install.sh
├── .learnings/                    # 学习记录目录（workspace 级别）
│   ├── LEARNINGS.md              # 教训记录
│   ├── ERRORS.md                 # 错误记录
│   └── FEATURE_REQUESTS.md       # 功能需求
└── hooks/
    └── openclaw/                 # OpenClaw Hook
        ├── HOOK.md
        ├── handler.js
        └── handler.ts
```

## 学习记录格式

### LEARNINGS.md — 教训记录

```markdown
## 2026-03-31 tool-gotcha: 错误描述

**问题：** 简述问题
**原因：** 根本原因
**解决：** 解决方案
**Pattern：** 抽象出的模式
```

### ERRORS.md — 错误记录

```markdown
## 2026-03-31 integration: 服务名

**错误：** 错误信息
**影响：** 影响范围
**修复：** 修复方法
**预防：** 预防措施
```

### FEATURE_REQUESTS.md — 功能需求

```markdown
## 功能名称

**描述：** 功能说明
**场景：** 使用场景
**优先级：** 高/中/低
```

## 使用场景

| 情况 | 记录位置 |
|------|---------|
| 用户纠正你 | `.learnings/LEARNINGS.md` |
| 命令执行失败 | `.learnings/ERRORS.md` |
| 用户想要新功能 | `.learnings/FEATURE_REQUESTS.md` |
| 发现更好的方法 | `.learnings/LEARNINGS.md` |
| 重要教训 | 升级到 `MEMORY.md` |

## 重要教训升级规则

| 内容类型 | 升级目标 |
|---------|---------|
| 行为模式 | `SOUL.md` |
| 工作流改进 | `AGENTS.md` |
| 工具技巧 | `TOOLS.md` |

## 卸载

```bash
openclaw hooks disable self-improvement
rm -rf ~/.openclaw/hooks/self-improvement
```

## 更新日志

- 2026-03-31：优化文档结构，修正安装路径

## 许可证

MIT
