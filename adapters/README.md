# Claude Code IM Adapters

当前目录只放 IM Adapter 运行时代码。

用户文档已经迁移到 `docs/`，并且以 Desktop Webapp 配置流程为准：

- `docs/im/index.md`
- `docs/im/telegram.md`
- `docs/im/feishu.md`

## 当前方案摘要

当前真实链路是：

```text
Desktop Webapp Settings
  -> /api/adapters
  -> ~/.claude/adapters.json
  -> adapters/<platform>/index.ts
  -> /api/sessions + /ws/:sessionId
  -> Claude Code session
```

注意两点：

- IM 配置和配对都在 Desktop Webapp 的 `Settings -> IM 接入`
- Webapp 不会自动启动 Adapter 进程，仍需手动运行 `bun run telegram` 或 `bun run feishu`

## 快速启动

```bash
cd adapters
bun install
bun run telegram
# 或
bun run feishu
```

## 开发

### 运行测试

```bash
cd adapters
bun test
bun test common/
bun test telegram/
bun test feishu/
```

### 目录结构

```text
adapters/
├── common/
├── telegram/
├── feishu/
├── package.json
├── tsconfig.json
└── README.md
```
