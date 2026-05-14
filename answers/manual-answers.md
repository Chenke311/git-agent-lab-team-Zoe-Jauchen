
> 声明：以下回答由本人独立完成，未使用 AI 生成或润色。

## Zoe

### Q1. Git 和 GitHub 分别是什么？repo 和 remote 又是什么？
Git是本地的版本管理工具，GitHub是云端的协作平台，repo是项目仓库，remote是GitHub上的远程的仓库。

### Q2. commit 是什么？为什么 commit message 不能只写 update 或 final？
commit是一次保存记录，因为要写清楚，让别人知道这次改动了哪些内容。

### Q3. branch 是什么？main 分支代表什么？为什么不建议直接在 main 上改？
branch是分支，也是草稿；main是主进程；因为需要让其他人review，以避免错误冲突，也方便保留记录。

### Q4. Pull Request 做了什么？reviewer 应该看什么，而不是只点 approve？
PR是把分支修改提交给团队检查。reviewer要看改了什么，有没有错误，内容清不清楚以及有没有什么潜在的风险。

### Q5. 你们组哪一个 PR 是你负责的？你做了哪些 commit？每个 commit 大概改了什么？
我负责 concepts PR，里面有两个commit，一个写的git关键词初版，一个补充论文类比。

### Q6. 你们组如何制造冲突？冲突发生在哪个文件？最终怎样合并两边意思？
冲突文件是：docs/shared-summary.md；我们在这里放了一句共同的初始总结，然后两个分支都改了同一行；因为同一行被改成了不同的内容，git不知道保留哪个，所以出现了冲突；最后是把两边的意思合成了一句话。

### Q7. worktree 是什么？它和 branch 的关系是什么？
branch是分支，worktree是本地的目录，一个repo可以有多个worktree，每个对应不同branch。

### Q8. 什么时候多个 branch 已经够了？什么时候需要一台设备多个 worktree？各举一个例子。
只做concepts，一个任务做完再做下一个，这种情况就只需要branch；同时做worktree-notes和worktree-prompts，或者两个agent并行工作就需要worktree。

### Q9. 如果你是老师，你如何审计一个 repo 是否真的通过 PR 合并，而不是直接改 main？
需要打开PR看是不是从feature branch合并到main、看PR是否merged、看files changed是否有review
 comment、看audit/evidence.md里的worktree list和PR链接、看main有没有大量commit。

### Q10. 使用 coding agent 做 Git 操作时，你最担心的一个危险动作是什么？你会怎样写提示词避免它？
先检查git status和当前分支，不要reset和force push，不要直接覆盖冲突，先解释影响再等我确认。
