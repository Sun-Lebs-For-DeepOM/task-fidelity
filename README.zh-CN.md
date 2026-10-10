# Task Fidelity｜任务执行防跑偏

这是一个用于复杂、多轮任务的指令型 Agent Skill。它要求 AI 结合用户原始要求、相关材料和后续决定理解完整工作，设计并实施方案，在执行中持续核对，最后依据实际产物判断任务是否完成。

[English](README.md)

## 适合处理什么问题

- AI 的摘要、计划或旧回答逐渐替代用户原始要求。
- 局部修改看起来更好，却遗漏了必须保留的条件。
- 用户反复指出偏差，AI 只修改表述，没有调整导致问题的理解或方法。
- 文件生成、步骤执行或“已经完成”的声明被当作任务完成的证据。

Skill 要求识别造成偏差的位置，修正理解、设计或执行，并同步处理受影响的工作。简单明确的任务可以直接推进，不强制逐阶段审批或额外创建治理文件。

## 安装与调用

将完整仓库放在客户端能够发现的技能目录。当前 Codex 官方文档列出的用户级目录包括 `~/.agents/skills`。Windows PowerShell 示例：

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.agents\skills" | Out-Null
git clone https://github.com/Sun-Lebs-For-DeepOM/task-fidelity.git "$env:USERPROFILE\.agents\skills\task-fidelity"
```

不要只复制 `SKILL.md`；`references/text-governance.md` 是共同执行要求。安装后未被发现时，可重启客户端。目录与发现方式以 [OpenAI 官方说明](https://learn.chatgpt.com/docs/build-skills#where-to-save-skills) 为准。

在任务中明确调用：

```text
使用 $task-fidelity 完成这项工作。结合原始要求和后续决定理解需求，持续核对关键实施选择，并依据实际产物验证任务完成情况。
```

本 Skill 的执行指令为中文；`agents/openai.yaml` 提供 Codex 界面元数据。其他客户端的兼容性与实际行为效果尚未开展系统评测。

## 使用时需要提供什么

提供要完成的工作、实际用途、相关材料，以及必须保留的范围、条件、方法和质量要求。已有明确决定直接应用；真正影响工作含义的歧义再澄清。

执行中保持以下联系：

> 用户要求 → 产物需要具备的具体质量 → 形成质量的实际活动 → 支持完成判断的证据

对应关系应当帮助改变实际决定。列出条款、写出计划或保存摘要，本身不能证明工作已经完成。

## 效果与使用边界

这套 Skill 能在一定程度上帮助改善任务跑偏。它由模型理解和执行，不是确定性的强制控制器。使用者仍需对照原始要求，核查 AI 的实际产出：有没有遗漏关键条件，事实与结论有没有依据，结果能否用于当前任务。

[三个示例](examples/illustrative-cases.md) 解释预期处理方式，均为说明性示例，不是同条件对照实测。发布验证的支持范围见 [VALIDATION.md](VALIDATION.md)。

本 Skill 不自带领域质量标准，也不要求外部 API、可执行程序、账号凭证或论文生成系统。

## 文件与来源

- [SKILL.md](SKILL.md)：主要执行要求。
- [文本治理](references/text-governance.md)：区分需求、解释、方案、授权、证据与结论。
- [方法依据与适配](references/method-basis.md)：QFD、双环学习、PDSA 与需求追溯等设计来源。
- [隐私与发布范围](PRIVACY.md)：公开包所含内容与排除内容。

## 许可证

仓库文件采用 [MIT License](LICENSE)。理论与方法来源已在参考文件中注明；来源本身不证明 Skill 对模型行为的实际效果。
