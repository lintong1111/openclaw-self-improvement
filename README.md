# OpenClaw 自我进化技能包

让 OpenClaw 具备自我学习、记忆和持续改进能力。

## 功能特性

- ✅ **自动记忆** - 记录用户偏好、习惯
- ✅ **错误追踪** - 自动记录失败和错误
- ✅ **教训记录** - 记录学习到的经验教训
- ✅ **功能需求追踪** - 记录想要但未实现的功能
- ✅ **Hook 自动提醒** - 每次启动时自动提醒反思

## 快速安装

### 一键安装脚本

```bash
# 1. 克隆仓库
cd ~
git clone https://github.com/lintong1111/openclaw-self-improvement.git

# 2. 进入目录
cd openclaw-self-improvement

# 3. 运行安装脚本
chmod +x install.sh && ./install.sh
```

### 手动安装

如果一键脚本失败，按以下步骤手动安装：

#### 1. 创建必要的目录

```bash
mkdir -p ~/.openclaw/workspace/.learnings
mkdir -p ~/.openclaw/hooks
```

#### 2. 复制文件

```bash
# 复制 learnimgs 模板
cp -r .learnings/* ~/.openclaw/workspace/.learnings/

# 复制 Hook 配置
cp -r hooks/openclaw ~/.openclaw/hooks/self-improvement
```

#### 3. 启用 Hook

```bash
openclaw hooks enable self-improvement
```

#### 4. 验证安装

```bash
# 检查文件是否存在
ls -la ~/.openclaw/workspace/.learnings/
ls -la ~/.openclaw/hooks/self-improvement/

# 检查 Hook 状态
openclaw hooks list
```

## 文件说明

```
.
├── README.md                    # 本说明文件
├── install.sh                   # 一键安装脚本
├── .learnings/                  # 学习记录目录
│   ├── LEARNINGS.md            # 教训记录模板
│   ├── ERRORS.md               # 错误记录模板
│   └── FEATURE_REQUESTS.md    # 功能需求记录模板
├── hooks/                       # Hook 配置
│   └── openclaw/               # OpenClaw Hook
│       ├── HOOK.md
│       ├── handler.js
│       └── handler.ts
└── scripts/                     # 辅助脚本
```

## 配置说明

### 1. Hook 自动提醒

启用后，每次 OpenClaw 启动时都会自动提醒：
- 检查是否有新的教训要记录
- 检查是否有错误要记录
- 检查是否有功能需求

### 2. 学习记录格式

#### LEARNINGS.md 格式

```markdown
## [LRN-20260307-001] category

**Logged**: 2026-03-07T12:00:00Z
**Priority**: high
**Status**: pending
**Area**: config

### Summary
简短的总结

### Details
详细描述

### Suggested Action
建议的改进措施
```

#### ERRORS.md 格式

```markdown
## [ERR-20260307-001] skill_name

**Logged**: 2026-03-07T12:00:00Z
**Priority**: high
**Status**: pending
**Area**: config

### Summary
简短描述

### Error
错误信息

### Context
上下文信息
```

#### FEATURE_REQUESTS.md 格式

```markdown
## [FEAT-20260307-001] feature_name

**Logged**: 2026-03-07T12:00:00Z
**Priority**: medium
**Status**: pending
**Area**: config

### Requested Capability
需要什么功能

### User Context
使用场景
```

### 3. 重要教训升级

当某个教训很重要时，应该升级到 MEMORY.md：

```bash
# 编辑记忆文件
vim ~/.openclaw/workspace/MEMORY.md
```

## 使用场景

### 场景 1: 用户纠正你

当用户说 "不是这样的"、"你错了" 等：
→ 记录到 `.learnings/LEARNINGS.md`

### 场景 2: 命令执行失败

当命令返回错误：
→ 记录到 `.learnings/ERRORS.md`

### 场景 3: 用户想要新功能

当用户说 "能不能..."、"如果能...就好了"：
→ 记录到 `.learnings/FEATURE_REQUESTS.md`

### 场景 4: 定期回顾

每次重要任务完成后：
→ 回顾 `.learnings/` 目录，整理教训

## 卸载

```bash
# 1. 禁用 Hook
openclaw hooks disable self-improvement

# 2. 删除 Hook 目录
rm -rf ~/.openclaw/hooks/self-improvement

# 3. 删除学习记录（可选，保留可保留）
# rm -rf ~/.openclaw/workspace/.learnings/
```

## 常见问题

### Q: 安装后需要重启 OpenClaw 吗？

A: 不需要，Hook 会自动生效。下次启动时就会看到提醒。

### Q: 学习记录会丢失吗？

A: 只要不删除 `~/.openclaw/workspace/.learnings/` 目录就不会丢。建议定期备份。

### Q: 可以跨设备同步吗？

A: 可以把 `.learnings/` 目录放到 GitHub 或 iCloud 等云盘。

## 更新日志

- 2026-03-07: 初始版本

## 作者

lin-tong

## License

MIT
