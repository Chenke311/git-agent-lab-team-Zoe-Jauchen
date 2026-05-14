# Manual Answers

> 声明：以下回答由本人独立完成，未使用 AI 生成或润色。


### Q10. 使用 coding agent 做 Git 操作时，你最担心的一个危险动作是什么？你会怎样写提示词避免它？
<自己的回答>
=======
<自己的回答>git是本地的版本管理，记录的是每次这个设备上的更改。
=======
## Jauchen

### Q1. Git 和 GitHub 分别是什么？repo 和 remote 又是什么？

github算是一个云端的，和多人可以协同管理代码。
repo是git的本地文件夹
remote是repo的云端版本

### Q2. commit 是什么？为什么 commit message 不能只写 update 或 final？
commit是带说明的代码行，谁在神么时候做了什么时候都记住。
update是对一次修改的整体说明，包括final的范围更大，commit是精细化的归档，让每一次输入都有人可以对此负责，可以对此回溯。

### Q3. branch 是什么？main 分支代表什么？为什么不建议直接在 main 上改？
branch是相对独立于main的草稿纸，写错了不会影响整体。
main就是确定的主体部分，main的分支就不是草稿了
在main撒和你直接改坏了 容易造成整体的影响，branch可以试错，可以删

### Q4. Pull Request 做了什么？reviewer 应该看什么，而不是只点 approve？
pull等于把饭端上饭桌前给厨房里的大家都尝一口，提交审核，每个人都检查了以后才确认并到main里
要看代码正不正确，针对此次任务，还要特别地看能不能让非专业人士看懂。

### Q5. 你们组哪一个 PR 是你负责的？你做了哪些 commit？每个 commit 大概改了什么？
我负责的是feature/ppt-case、feature/agent-prompts、feature/conflict-b，我做了关于协作流程、安全边界的commit，在conflict-b，我写的有“减少最终版地狱和文件来回传”，chenke的版本是“本项目展示了 Git 如何记录修改历史并帮助多人协作”。

### Q6. 你们组如何制造冲突？冲突发生在哪个文件？最终怎样合并两边意思？
我们组从同一个路径点开main，改了 docs/shared-summary.md 的同一行
但我下手快，导致我的conflict-b先落地，所以实际上我是conflict-a，也就是第一个版本吧。
chenke后来点进入做了一版conflict-a，不过只要两版不一样就是“conflict”，后来是我合并了两个人的意思，变成一句话，并且删除了乱七八糟符号。

### Q7. worktree 是什么？它和 branch 的关系是什么？
worktree是本地开的一个独立的工作区。
branch的分支是在github里的，并不完全独立，都能归到一条main上。
branch可以在worktree里工作，关键是worktree能隔开不同的agent。

### Q8. 什么时候多个 branch 已经够了？什么时候需要一台设备多个 worktree？各举一个例子。
一个人工作duogebranch足够，同时用两个coding agent的时候要让他们进不同的work tree

### Q9. 如果你是老师，你如何审计一个 repo 是否真的通过 PR 合并，而不是直接改 main？
有没有解决冲突，再读不懂代码的情况下，让ai帮我看一眼，并且看commit是不是都来自merge。

### Q10. 使用 coding agent 做 Git 操作时，你最担心的一个危险动作是什么？你会怎样写提示词避免它？

<自己的回答>直接把我的活着别人的工作删掉，如果没有备份就会很难复原。或者没有有效建立worktree，各人做的东西混在一起。
=======
直接把我的活着别人的工作删掉，如果没有备份就会很难复原。或者没有有效建立worktree，各人做的东西混在一起。

---

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
