# Coding Agent 安全提示词

## 日常工作流提示词
在让 Agent 介入 Git 系统时，必须以明确的指令控制其行为边界：
* **开始工作**：请检查 git status、当前分支、远程同步状态。若有未提交修改，请先提醒，不要覆盖。
* **审查修改**：请总结当前 diff，列出修改文件、主要变化。先不要 commit。
* **生成 PR**：请根据当前分支相对 main 的变化，生成 PR 描述，包含修改内容与原因。

## 危险操作的安全边界
严禁让 Agent 自行决定执行具有破坏性或历史篡改性质的操作：
* **禁止重置**：当涉及 `git reset` 时，提示词应为：“请先解释 reset 会影响哪些文件和 commit，不要直接执行。”
* **禁止强推**：绝不使用 `force push`，避免抹除他人的数字劳动痕迹。
* **主干保护**：任何修改前，必须确认当前不在 main 分支。

## Worktree 中使用 Agent 的提示词

当我在 worktree 中使用 coding agent 时，我会先说明边界：

```text
你现在只能在当前 worktree 工作。
先运行 pwd、git branch --show-current、git status。
确认当前分支不是 main。
不要切换分支，不要使用 reset，不要 force push。
只修改本次任务指定的文件。
完成后总结 diff，先不要 commit，等我确认。
多 Agent 并行注意事项
不要让两个 agent 在同一个目录工作。
每个 agent 使用独立 worktree 和独立分支。
每个任务只修改指定文件。
合并前必须通过 PR review。
