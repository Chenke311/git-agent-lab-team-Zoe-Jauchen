# Git 关键词说明

## repo
repo 是被 Git 管理的项目文件夹。它里面不仅有当前文件，也有每次修改的历史记录。

## commit
commit 是一次带说明的存档点。它记录谁在什么时候改了什么。

## branch
branch 是一条独立修改路线。我们可以在自己的 branch 上改内容，不直接影响 main。

## main
main 是团队当前认可的正式版本。一般不要直接在 main 上做正式修改。

## PR
PR 是 Pull Request，意思是“我改好了，请别人检查，没问题再合并进 main”。

## conflict
conflict 是两个人改了同一处，Git 不知道该保留谁，需要人来判断和合并。

## worktree
worktree 是同一个 repo 的多个本地工作目录，可以让不同分支同时打开，适合多个 agent 并行工作。
