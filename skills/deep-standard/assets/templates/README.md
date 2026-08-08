# 模板

实例化到目标项目时的规则：

- **Markdown 注释（`<!-- -->`）里的内容是填写指引，实例化时删除。** 未被注释包裹的内容（标题、表格结构、字段名）是骨架，保留。
- **被门禁机械校验的结构标记保持英文**：决策记录的 `# Decision: `、`Status:`、`Archived:`、章节标题（`## Problem` 等）、生命周期与分类目录名。正文语言随项目。
- 模板是**临时参考，不是永久文档**：某类型的第一份正式文件创建后，删除对应模板文件。这是正式文件创建后的原子清理，不单独执行。
- **模板里的链接指向的是目标项目的路径**（`docs/architecture.md`、`decisions/README.md` 等），在模板目录里当然不可达。实例化后按项目实际路径核对一遍，指向不存在文件的链接要么补文件要么删链接——不要留断链给链接门禁。
- 不要装用不上的模板（见 [adoption.md](../../references/adoption.md) 的"不要为了体系完整而制造空壳"）。

| 文件 | 实例化到 | 档位 |
|------|---------|------|
| [AGENTS.md](AGENTS.md) | 仓库根 `AGENTS.md`（或项目的 agent 指令文件） | L1 |
| [decisions-README.md](decisions-README.md) | `decisions/README.md`（决策记录树的契约文件） | L1 |
| [decision-proposed.md](decision-proposed.md) | `decisions/proposed/<分类>/yyyy-mm-dd-主题.md` | L1 |
| [decision-implemented.md](decision-implemented.md) | `decisions/implemented/<分类>/yyyy-mm-dd-主题.md` | L1 |
| [docs-AGENTS.md](docs-AGENTS.md) | `docs/AGENTS.md`（文档标准与分层表） | L2 |
| [doc-budgets.manifest.json](doc-budgets.manifest.json) | 字数预算 manifest（路径随项目） | L3 |
