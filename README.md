<h1 align="center">deep-standard</h1>

<p align="center">
  <strong>把工程规范从"没人读的文档"变成"会拒绝违规的程序"。</strong><br/>
  一套可迁移的工程标准体系：约定必须有门禁、门禁必须自证、每个改动必须留下决策记录与最小充分证据。
  从一个由 agent 长期维护的大型 monorepo 的实践中蒸馏而来，剥离了框架与语言相关的部分，可装进任意项目。
</p>

<p align="center">
  <img src="https://badgen.net/badge/license/MIT/blue" alt="MIT" />
  <img src="https://badgen.net/badge/spec/Agent%20Skills/8257D0" alt="Agent Skills spec" />
</p>

---

## 它解决什么

绝大多数项目的"工程规范"是一份没人读、没人查、逐月腐烂的文档。当主要维护者是**会被随时终止、下次只能靠文件系统恢复上下文的 agent** 时，这个问题会被放大：任何只存在于对话历史里的约定，等于不存在。

本技能给出六条可落地的法则，并把它们变成可执行、可审计的机制：

| 法则 | 一句话 |
|------|--------|
| 常驻规则分层 | 每个 session 都要知道的规则集中在一个有字数上限的文件里，每条只链接不复述；一个事实一个家 |
| 门禁即代码 | 机械可查的约定必须有一个只拒绝一条不变量的程序；**门禁必须用非法样例证明自己会拒绝** |
| 决策记录生命周期 | 决策记录的状态编码在路径里，备选方案强制填写，归档即永久冻结 |
| 最小充分证据 | 每个改动只跑覆盖它所触及表面的最窄证据，一次；hook 窄、CI 全 |
| 散文即契约 | 注释与文档写契约，不写推理转录；只写当前态 |
| 落地纪律 | 一个 PR 一种性质；在引入问题的 PR 上修，而不是往下游打补丁 |

配套提供**三档采纳阶梯**（L1/L2/L3）：小项目只装常驻规则、决策记录和一个链接门禁，不会被整套体系压垮。

## 什么时候不要装

- 一次性脚本、实验代码、生命周期以周计的项目——收益不足以抵消成本。
- 只想装文档层、不打算真的建门禁。那样只会又造一份没人查的规范，正是本体系要消灭的东西。

## 安装

### [skit](https://github.com/vlln/skit)（推荐）

```bash
skit install https://github.com/vlln/deep-standard-skill/tree/main/skills/deep-standard
```

### 手动安装

| Agent | 命令 |
|-------|------|
| **Claude Code** | `cp -r skills/deep-standard .claude/skills/` |
| **Codex** | `cp -r skills/deep-standard ~/.codex/skills/` |
| **OpenCode** | `git clone https://github.com/vlln/deep-standard-skill.git ~/.opencode/skills/deep-standard-skill` |
| **任意 Agent（符号链接）** | `ln -s <repo>/skills/deep-standard <agent-skills-dir>/deep-standard` |

## 技能

| 技能 | 说明 |
|------|------|
| [`deep-standard`](skills/deep-standard/SKILL.md) | 为项目建立或审计工程规范：门禁体系、决策记录、证据选择、文档分层、散文契约、PR 纪律 |

技能内含可直接实例化的模板（常驻规则文件、文档分层表、决策记录契约与骨架、字数预算 manifest），位于 [`skills/deep-standard/assets/templates/`](skills/deep-standard/assets/templates/)。

## 依赖

无。技能不含可执行脚本——门禁按各项目自己的技术栈实现，技能提供的是门禁的**验收契约**而不是现成脚本。

## 致谢与参考

本体系蒸馏自 **DeepSeek Harness** —— 一个由 agent 长期维护的大型 monorepo 的工程实践。六条法则、采纳阶梯与门禁自证机制均从该项目的实际运作中提炼，剥离了框架与语言相关的部分后泛化而来。

方法论的组织形式（可迁移的 agent skill、状态化的推进流程、模板即资产）参考了 [devloop](https://github.com/vlln/devloop) —— 一套契约驱动的项目开发系统。

## 许可

[MIT](LICENSE)
