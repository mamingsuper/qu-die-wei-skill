---
name: de-die-wei
description: Rewrite Chinese text to remove "爹味" by first detecting patronizing, preachy, boundary-crossing, controlling, superiority-driven, or low-empathy wording, then improving it into equal, restrained, empathetic communication. Use when the user asks to 去爹味, soften advice, reduce mansplaining-like tone, make feedback less preachy, or turn commands into respectful suggestions.
---

# 去爹味

## Overview

Use this skill to turn high-control, high-posture, unsolicited, or preachy Chinese communication into wording that respects boundaries and treats the reader as an adult with judgment.

Always start with a 爹味 scan. If `../die-wei-detector/references/rubric.md` is available, use its five-dimension scoring framework. Then load `references/rewrite-playbook.md` for rewrite tactics.

## Workflow

1. Detect first. Score the text across posture, boundary, empathy, purpose, and result. Record the exact points that need changes.
2. Rewrite second. Apply the smallest useful edits first: ask before advising, replace commands with options, turn absolute claims into experience-sharing, add empathy, and return agency to the reader.
3. Preserve the user's intent, facts, and practical advice. Remove the hierarchy, not the useful content.
4. Provide one clean rewritten version. If the original is complex, also provide line-by-line edits.
5. Estimate the post-rewrite 爹味 score and explain what improved.

## Required Output

Use this structure:

```markdown
## 先检测

**原文总分：X/100｜昵称：...**

| 维度 | 分数 | 主要问题 |
|---|---:|---|
| 姿态维度 | X/25 | ... |
| 边界维度 | X/25 | ... |
| 共情维度 | X/20 | ... |
| 目的维度 | X/15 | ... |
| 结果维度 | X/15 | ... |

## 需要改的点

| 原表达 | 问题 | 改法 |
|---|---|---|
| ... | ... | ... |

## 去爹味版本

...

## 改后评估

**预计分数：X/100｜昵称：...**

改进说明：...
```

## Rewrite Rules

- Ask before advising: add "你想听建议，还是只是想聊聊？" or "需要我提供一些思路吗？" when advice was not requested.
- Share instead of instructing: change "你应该" into "我之前试过...你可以看看是否适合你"。
- Keep boundaries: remove comments on private life, body, clothing, marriage, spending, sleep, hobbies, or work style unless directly relevant and invited.
- Empathize first: acknowledge the other person's feeling before offering analysis.
- Lower posture: use uncertainty honestly, not as a fake humble prefix before a command.
- Leave agency: end with options, tradeoffs, or an invitation, not a verdict.

## Guardrails

- Do not make the rewrite bland or corporate by default. Keep the user's voice where possible.
- Do not erase necessary feedback. Directness is fine when it is requested, specific, and respectful.
- Do not add fake intimacy, flattery, or excessive apologies.
