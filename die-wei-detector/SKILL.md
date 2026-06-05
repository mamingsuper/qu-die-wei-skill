---
name: die-wei-detector
description: Detect and score "爹味" in Chinese text, comments, advice, workplace messages, social posts, drafts, or conversation snippets. Use when the user asks to judge whether wording feels patronizing, preachy, boundary-crossing, mansplaining-like, controlling, lacking empathy, or wants a 0-100 爹味 score with dimension scores, evidence, and rewrite directions.
---

# 爹味检测

## Overview

Use this skill to score the "爹味" level of Chinese communication. Judge the expression, not the person. Treat "爹味" as a communication pattern: condescending posture, unsolicited instruction, weak boundaries, low empathy, hidden superiority, or control disguised as care.

Load `references/rubric.md` before scoring unless the user only asks for a quick impression.

## Workflow

1. Identify the text, speaker role, audience, and context. If context is missing, score only the visible wording and say that context may change the score.
2. Scan for five dimensions: posture, boundary, empathy, purpose, and result.
3. Assign a 0-100 total score using the weighted rubric.
4. Quote only short evidence snippets. Do not over-quote long user text.
5. Explain why points were added. Be specific about wording, assumptions, and likely reader impact.
6. Give rewrite directions without rewriting the whole text unless the user asks.

## Required Output

Use this structure:

```markdown
## 爹味总分

**总分：X/100｜昵称：区间昵称**

一句话判断：...

## 维度评分

| 维度 | 分数 | 依据 |
|---|---:|---|
| 姿态维度 | X/25 | ... |
| 边界维度 | X/25 | ... |
| 共情维度 | X/20 | ... |
| 目的维度 | X/15 | ... |
| 结果维度 | X/15 | ... |

## 高风险表达

| 原表达 | 问题 | 去爹味方向 |
|---|---|---|
| ... | ... | ... |

## 结论

...
```

## Nickname Bands

- `0-9`: 清爽可读
- `10-29`: 一丝爹味
- `30-49`: 少量爹味
- `50-69`: 爹言爹语
- `70-84`: 爹爹不休
- `85-100`: 爹味包浆

## Guardrails

- Do not diagnose personality, gender, age, intent, or morality from text alone.
- Do not treat every suggestion as 爹味. Advice can be low-score when it is invited, humble, contextual, and leaves choice to the other person.
- Do not reward fake politeness if the substance is still controlling or boundary-crossing.
- If the user asks for "火力全开", keep the labels sharp but keep the analysis fair.
