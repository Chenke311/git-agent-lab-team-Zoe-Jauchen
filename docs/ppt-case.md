# 小组 PPT 协作案例

## 1. 传统协作的问题
小组做 PPT 时，通常把文件发到群里，每个人改一版再传回来。最后出现 `最终版.pptx`、`最终版_真的.pptx`、`最终版_不改了.pptx`，根本不知道哪个才是最新的。

## 2. 用 Git 分支解决
每个人从 main 创建自己的分支，比如：
- `feature/ppt-introduction-Zoe`
- `feature/ppt-analysis-Jauchen`

在自己的分支上修改大纲、文案、素材，互不干扰。

## 3. PR Review 流程
改完后 push 分支，发 Pull Request。组员在 Files changed 里看修改，留评论提建议。确认没问题后，合并到 main。

## 4. Git 不适合直接管 pptx 文件
Git 无法显示 .pptx 的 diff（二进制文件），多人同时编辑同一个 pptx 会导致冲突无法解决。

**更适合的做法**：在 Git 里管理 PPT 的文本大纲、文案、素材清单，最终由一个人汇总到 pptx 文件中。

## 5. 总结
- 用 branch 做独立草稿区
- 用 PR 做 review 和合并
- Git 管文本和流程，不管二进制文件本身

## 6. 具体协作流程示例
一个三人小组做 PPT：

1. 组长在 main 放 `outline.md`，写每页的大标题
2. 组员 A 拉分支 `feature/ppt-design`，负责视觉风格说明
3. 组员 B 拉分支 `feature/ppt-data`，负责数据页文案
4. 两人都发 PR，互相 review 对方的大纲是否和自己的页冲突
5. 合并到 main 后，组长根据 Git 里的文本最终汇总成 pptx

这样每个人的贡献都有 commit 记录，可以追溯谁写了哪段内容。
