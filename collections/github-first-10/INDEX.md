# GitHub first 10 curated skills

这 10 个不是“最火”，而是当前更适合先收进我们自己仓库的一批：
- 相对容易解释
- 价值明确
- 风险较低或至少边界清楚
- 适合作为第一批展示和继续打磨的样本

## Selection principles

1. 面向普通用户或轻技术用户也能讲清楚
2. 不优先收过度依赖秘密环境、代理网络、自动交易、反检测、可疑脚本的技能
3. 优先收文档完整、结构清楚、引用资料齐的技能
4. 对外部依赖明确标注，不装作“开箱即用”

## The 10 picks

### From `kepano/obsidian-skills`

1. `obsidian-markdown`
- Why: Obsidian 写作的基础能力，边界清楚，适合知识管理用户
- Audience: Obsidian / PKM 用户
- Risk: 低
- Display fit: 很适合

2. `obsidian-cli`
- Why: 把 Obsidian 从“笔记软件”拉到“可自动化工具”层
- Audience: 稍微进阶一点的 Obsidian 用户
- Risk: 低到中，要求本地 Obsidian 运行中
- Display fit: 适合

3. `json-canvas`
- Why: 很适合做可视化、思维导图、流程图类展示
- Audience: 视觉化笔记用户
- Risk: 低
- Display fit: 很适合

4. `defuddle`
- Why: 把网页抽干净成 Markdown，很实用，也很好懂
- Audience: 阅读、研究、做知识库的人
- Risk: 低到中，需要额外 CLI
- Display fit: 很适合

5. `obsidian-bases`
- Why: 能把笔记变成数据库视图，属于“懂了就会很爱”的类型
- Audience: 进阶 Obsidian 用户
- Risk: 低
- Display fit: 适合

### From `TerminalSkills/skills`

6. `pdf-analyzer`
- Why: PDF 是真实世界的刚需，不是玩具场景
- Audience: 办公、学习、研究用户
- Risk: 低到中，需要 Python 依赖
- Display fit: 很适合

7. `excel-processor`
- Why: 表格处理同样是刚需，而且人人都会遇到
- Audience: 办公、运营、分析用户
- Risk: 低到中，需要 pandas/openpyxl
- Display fit: 很适合

8. `markdown-writer`
- Why: 适合 README、说明文档、操作指南等高频场景
- Audience: 所有人，尤其是写文档的人
- Risk: 低
- Display fit: 很适合

9. `calendar-integration`
- Why: 日历/排期是非常自然的 agent 场景
- Audience: 有日程管理需求的人
- Risk: 中，需要真实日历 API 接入与鉴权
- Display fit: 适合，但要注明集成门槛

10. `git-commit-pro`
- Why: 对 GitHub 用户很实用，且范围清楚、风险低
- Audience: 轻度到中度开发者
- Risk: 低
- Display fit: 适合

## Notes on optimization

这批先做了 **vendor 保存**，暂时不重写原始 skill 内容。
原因很简单：
- 先把样本固定下来
- 先保证可追溯
- 后续再做“OpenClaw 适配优化版”会更稳

下一步建议：
1. 给每个 skill 加 `REVIEW.md`
2. 标注是否适合小白、是否需额外依赖、是否建议默认展示
3. 选择其中 3-5 个做“本仓库优化版”
4. 再补一版主页 README 展示文案

## Provenance

Sources:
- `~/Documents/github/kepano-obsidian-skills`
- `~/Documents/github/TerminalSkills-skills`

These copies are curated snapshots for local review and future adaptation.
