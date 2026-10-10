# Task Fidelity

**任务执行防跑偏 · An instruction-only Agent Skill for complex, multi-turn tasks.**

[中文说明](README.zh-CN.md)

Task Fidelity helps an agent keep its understanding, implementation choices, and completion claims tied to the user's original requirements and subsequent decisions. It covers the whole task: understanding the work, resolving material ambiguity, designing an implementation, checking execution, and verifying the actual result.

## What it addresses

- A plan or summary quietly replacing the original task.
- A local improvement breaking a condition that should have been preserved.
- Corrections changing the wording while leaving the mistaken approach intact.
- Files, steps, or self-reported success being treated as proof of completion.

The skill instructs an agent to return to the stage that caused the deviation and update affected work. Clear, simple tasks can proceed directly; it does not impose mandatory stage approvals or extra management documents.

## Install for local Codex use

An Agent Skill is a directory containing `SKILL.md` and its supporting resources. For local Codex use, install this repository under a discovered skill directory. For example, in PowerShell:

```powershell
New-Item -ItemType Directory -Force "$env:USERPROFILE\.agents\skills" | Out-Null
git clone https://github.com/Sun-Lebs-For-DeepOM/task-fidelity.git "$env:USERPROFILE\.agents\skills\task-fidelity"
```

Keep the entire directory, especially `references/text-governance.md`. If the skill is not discovered after installation, restart the client. Refer to the [official local skill documentation](https://learn.chatgpt.com/docs/build-skills#where-to-save-skills) for current locations.

Invoke it explicitly when needed:

```text
Use $task-fidelity to carry out this task. Keep the original requirements and later decisions available, check important implementation choices against them, and verify the actual deliverable.
```

The workflow instructions are in Chinese. `agents/openai.yaml` supplies Codex presentation metadata. Compatibility and behavioral effectiveness on other clients have not been systematically evaluated.

## How to use the workflow

1. Provide the task, its intended use, relevant source materials, and concrete constraints.
2. Resolve only ambiguity that materially affects the work.
3. Connect requirements to the qualities the result needs and the activities that can produce them.
4. Recheck consequential substitutions, omissions, method changes, and handoffs.
5. Evaluate both compliance with specific requirements and usefulness for the original task.

If a correction identifies an existing omission, treat it as a correction to the work. Do not silently redefine it as a newly added requirement.

## Scope and evidence

This is a set of instructions interpreted by the model, not a deterministic enforcement mechanism. It may help improve task fidelity to a degree. Users still need to inspect the actual output against the original task, including factual support, omitted conditions, and practical usability.

[Examples](examples/illustrative-cases.md) demonstrate the intended handling of deviations. They are not controlled before-and-after model evaluations. See [VALIDATION.md](VALIDATION.md) for the release's validation scope.

## Files

- [SKILL.md](SKILL.md): workflow and essential requirements.
- [Text governance](references/text-governance.md): distinguish requirements, interpretations, plans, evidence, and conclusions.
- [Method basis](references/method-basis.md): cited design influences and their adaptation.
- [Privacy and release scope](PRIVACY.md): what is included in this public package.

No external API, executable helper, account credential, or paper-writing system is required by this skill itself.

## License and attribution

The files in this repository are released under the [MIT License](LICENSE). The management and systems-engineering sources informing the workflow are credited in [method-basis.md](references/method-basis.md); citing those sources does not establish the skill's effectiveness.
