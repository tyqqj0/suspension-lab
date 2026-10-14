# 仓库与 Beads 接入验证回执

## 身份与验证边界

- 日期：2026-10-14；工作：`sus-nnl.1`；交接包：[r3](handoff.md)；契约：work-handoff/0.1。
- 执行方：Life~，actor `life-20261014-publish`；macOS arm64；Git 2.54.0（Apple Git-157）、GitHub CLI 2.95.0、Beads 1.3.0（f45b249ce，embedded Dolt）。
- 发送端自检；继承发送方历史并使用同版交接技能。接收位置是同机全新临时 clone，不是另一台设备或独立 Agent。
- 开工理解：交付公开文档仓库和可从远端恢复的 Beads 工作库；不实现应用、不做实车实验、不替用户选栈。先核对已有改动、授权和远端，再沿用固定验收完成两条发布通道。
- 人工补充：本次收尾未请求用户补充资料；用户已明确允许初始化、公开 GitHub 发布和配置 Beads。
- 本文是一次验证的固定证据，不是进度表。当前状态、下一步与最终发布引用只查 Beads。

## 已验证的基线

| 对象 | 实际版本 |
|---|---|
| 公开仓库 | https://github.com/tyqqj0/suspension-lab |
| 最初文档提交 | `cccd4205e640d45c9bf8fe0e3e8754e250b472ae` |
| Beads 初始化自动提交 | `870f191a5ade117a96d50ddc5a822f6405e95bf5` |
| r3 正式工作入口 | `d11babb72cd3c0392bc8235c11367077392ee5bc` |
| 全新副本复验的文件提交 | `e938867ad0d39e2bedb1f62297a492de43b1a7f0` |
| 复验时远端 `refs/dolt/data` | `e77ed608a16a7d0095a6b2aba5df8c228944e0c4` |

后续加入本回执的提交及最终数据发布引用由 `sus-nnl.1` 关联；上表是固定测试快照，不宣称永久等于远端最新值。两条通道不是原子事务。

## 通过

1. **公开 Git 仓库**：`gh repo view` 返回 `PUBLIC`、默认分支 `main`；`git push origin HEAD:refs/heads/main` 成功；`git ls-remote origin refs/heads/main` 与本地文件提交一致。未强推、镜像或覆盖远端历史。
2. **公开范围检查**：对当时 14 个普通 Git 跟踪文件、待发布差异和已有 Git 历史执行私有路径／常见密钥模式检查；本项目四个工作项及其历史同样检查。没有命中所查模式；这不是穷尽式安全审计。原始数据、私人备份、未授权模型、活数据库未进入普通 Git 跟踪。
3. **初始化与规则保护**：初始化提交仅涉及根 `.gitignore` 和 `.beads` 四个配置／说明文件。`AGENTS.md` SHA256 仍为 `253bb17ad48428cc671e7570609fdad7c4aad3df493ff0c9496b32858c899f21`；未安装新工具、修改共享技能或全局配置。Git 作者使用 GitHub noreply 邮箱。
4. **真实工作项**：回读 `sus-nnl`、`sus-nnl.1`、`sus-nnl.2`、`sus-nnl.3`；未重复创建。三项子工作归属总目标，不人为添加串行阻断；P2 是工具默认值，不代表用户排定优先级。
5. **Beads 发布**：远端为 `git+https://github.com/tyqqj0/suspension-lab.git`；`bd dolt push --remote origin --no-adopt` 输出 `Push complete.`；`refs/dolt/data` 实际存在。数据推送前后 `refs/heads/main` 没有被数据通道改写。
6. **全新副本恢复复验**：正常 clone `main`，`bd bootstrap --dry-run` 明确为 `clone from remote`，`bd bootstrap --yes` 返回 `Synced database from ...`。未复制运行数据库，未重新 init。
7. **逐项一致性**：四项工作的 `id/title/description/notes/status/assignee/priority/issue_type/parent/dependencies/created_at/updated_at` 与发送端快照相同；描述引用已发布提交，交接包为 r3。14 个跟踪文件逐字节一致，源端与恢复副本均为干净工作树。测试副本未领取或修改业务工作。
8. **文档与数据护栏**：当时 30 个本地 Markdown 链接存在；`git diff --check` 通过；原调研 SHA256 保持 `0a7719eebc98e97a2f828d205ea0cf83616815ee71aae0a477dabc78e25b9a8f`。`git check-ignore` 确认 `local-data/`、`private-assets/`、`exports/`、`.env`、`.beads/dolt/`、`.beads/backup/` 被忽略；仓库外原调研入口的符号链接仍指向权威正文。

## 失败、修正与提示

- **首轮额外字节一致性检查失败**：首次 bootstrap 已恢复全部工作项，但 Beads 重写 `.beads/config.yaml` 时移除了末尾换行，导致文件字节检查与干净工作树断言失败。没有把这个结果报告为全通过。
- **修正**：保留 Beads 生成的无末尾换行格式，提交 `e938867`，不改配置语义。随后使用另一个全新目录从远端重新 clone/bootstrap；全部字段、文件字节和干净状态检查通过。
- **权限提示**：新 clone 中 `.beads` 为 0755，按提示仅在测试副本收紧为 0700；不改全局权限。
- **角色提示**：新 clone 未设置 `beads.role`，但只读列表／恢复正常。未为测试副本擅自赋予写入角色；必要配置方法见 [Beads 使用入口](../../.beads/README.md)。
- **材料修正**：先前工作项已引用 r3，而实际文件仍为 r2；本轮在数据发布前补齐 r3 和真实编号。没有把聊天摘要当成文件已经更新的证据。

## 未运行／不作结论

- 独立 Agent 在不继承发送方历史时的理解与执行验收；真正跨设备、跨平台接入。
- 双方并发写入、冲突合并、网络中断恢复、权限拒绝、自动调度或自动唤醒。
- 应用、传感器采集、后台／锁屏、车辆物理、实车实验与产品功能测试。
- 开源许可证选择；仓库公开不等于已授予任意再分发许可。

## 复现与证据位置

公开复现入口见 [Beads README](../../.beads/README.md)：分别检查普通 Git 文件、Beads 远端引用和恢复后的真实工作。需要兼容 `bd`；缺工具时报告，不自动安装或用空库代替恢复。

本地命令输出、发送／恢复 JSON 快照和测试目录定位保存在被忽略的 `local-data/beads-onboarding-20261014/`，未发布本机路径或原始本地日志。公开回执记录命令、版本、结果和已知失败；工作库提供状态及最终产物引用。

本轮不修改共享交接技能。后续若验证独立执行器理解，应使用本包和 Beads 入口重新开展独立验收，不能沿用此次传输成功作为理解成功的证据。
