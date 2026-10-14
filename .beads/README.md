# 本项目的 Beads 入口

Beads 管工作状态，文档管规格。项目总目标 `sus-nnl`；先读 [交接入口](../handoffs/2026-10-14-beads-onboarding/handoff.md) 与 [项目规则](../AGENTS.md)。

本项目使用 Beads 1.3.0（f45b249ce）、embedded Dolt。安装／升级不属于普通接手动作；若 `bd` 不在 PATH，使用运行环境已经提供的兼容可执行文件，或报告缺工具。本机工具定位不写进公开仓库。

## 查看已有工作区

```sh
bd --version
bd --readonly show sus-nnl --json
bd --readonly list --all --json
```

先确认目录和工作编号再写入；`ready` 不是执行授权。所有任务当前的默认 P2 是工具默认值，不表示用户裁定了任务优先级。只有真实阻断才建依赖，父子归属不等于阻断。

## 新副本接入

先正常 clone 本仓库，核对远端、版本与工作区。在确实全新的副本中：

```sh
bd bootstrap --help
bd bootstrap --dry-run
bd bootstrap --yes
bd --readonly show sus-nnl --json
```

Bootstrap 会写本地库，不是只读操作。核对其来源是已发布的 `refs/dolt/data`；失败时不执行 `bd init` 创建空库冒充恢复，不复制运行数据库。

## 发布与刷新

- 普通文件发布到 Git `main`；工作库发布到同仓库 `refs/dolt/data`。配置见 `config.yaml`，不把专用数据引用合并进代码分支。
- 获得发布授权后先提交／推送文档，再更新对应 Beads 文件版本引用并 `bd dolt push --remote origin --no-adopt`。回读实际输出与远端引用，skipping 不算成功。
- 已有副本刷新前保护改动，核对文档版本，再按获准范围 `bd dolt pull`。冲突停止，不 reset、强推或重新初始化。
- 活数据库、运行状态与本机信息由本目录忽略规则排除。Git-backed 数据引用是公开的，不是敏感内容隔离区。

具体交接、领取、检查点与回执遵循 `work-handoff` 技能及项目规则。没有技能时先读仓库交接包理解授权与验收，不运行外部安装脚本。
