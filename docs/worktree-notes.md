# Worktree 使用说明

## worktree 是什么
worktree 是同一个 Git repo 的多个本地工作目录。每个 worktree 可以对应不同分支，所以可以同时打开多个任务现场。

## 它和 branch 的关系
branch 是修改路线，worktree 是本地目录。一个 repo 可以有多个 branch，也可以为不同 branch 创建不同 worktree。

## 什么时候多个 branch 就够了
如果一个人一次只做一个任务，做完再切换到下一个分支，那么只用 branch 就够了。

## 什么时候需要多个 worktree
如果同一台电脑上要让两个 coding agent 同时工作，或者想保留一个未完成现场，同时处理另一个紧急任务，就适合用 worktree。

## 多 agent 并行时的安全规则
- 一个 agent 一个 worktree。
- 一个 worktree 一个任务分支。
- 不要让两个 agent 在同一个目录里并行修改。
- 不要在 worktree 里随便切换到 main。
- 提交前必须检查 git status 和 git diff。
