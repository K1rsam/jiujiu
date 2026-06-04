---
name: short-drama-director
description: Use when the user asks to run, apply, or follow the short-drama director workflow, Seedance 2.0 prompt workflow, 真人竖屏短剧分镜, 剧本清洗, 剧本更新合并, 场次快照, 导演表现层, subagent任务包, 批量分镜质检, or generate Seedance-ready 分镜单元.
---

# Short Drama Director

Use this skill to turn short-drama scripts into Seedance-ready 真人竖屏短剧分镜单元.

The active operating rules are this `SKILL.md` plus the files in `references/`. The local Obsidian knowledge base under `短剧导演知识库/` remains supporting context; load it when the user explicitly asks for the knowledge base, when project rules refer to it, or when a referenced rule needs more detail.

## Required Reads

For any generation or review task, read only what is needed:

- New script, script merge, or batch planning: `references/workflow.md`
- Writing or reviewing final shot units: `references/seedance-unit.md`
- Final quality review, scoring, or batch gate: `references/quality-gates.md`
- Injury, violence, mutation, poisoning, experiments, weapons, or audit risk: `references/platform-safety.md`
- Subagent or concurrent production: `references/concurrency.md`

## Non-Negotiable Output Rules

- The final shot unit field is `台词`, never `文本`.
- Dialogue format:
  - 普通对白：`角色： "台词。"`
  - 带状态对白：`角色（急切）： "台词！"`
  - OS/VO：`角色（OS）：内心独白。` or `角色（VO）：旁白内容。`
- OS/VO must not use quotation marks.
- Quoted dialogue must not keep leading or trailing spaces inside the quotes.
- Each `生成分镜单元` is the whole Seedance prompt; do not add `[Seedance生成提示词]`.
- Every unit must include `[本单元剧情结果]`, `[通用提示词]`, `[资产索引]`, `[场景]`, `[本单元出场人物]`, `[人物状态与站位前提]`, then the five fields `机位/运动`, `画面`, `声音`, `台词`, `转场节拍`.
- `[人物状态与站位前提]` must be self-contained. Do not write empty references such as `承接第xx集`, `承接场xx`, or `承接上一单元`; write the visible current state, location, posture, relative positions, prop positions, clothing/injury state, and visible result of prior action.
- Final scripts must not contain director outlines, evidence cards, coverage tables, scoring tables, task-package notes, or process analysis unless the user explicitly asks for review records.
- Final scripts must be video-generation clean: no subtitles, no watermark, no logo, no BGM, no screen text overlays, no 人名条/地点条/时间条 instructions.

## Internal Quality Gate

Before final shot generation, internally complete or verify:

- Six evidence cards: 剧情覆盖表, 单元导演小纲, 专属动作词库, 场景声场库, 转场库, 降尺度替代表达表.
- Unit lock for every unit: 剧情结果, 冲突点, 功能锚点, 动作链, 反应升级, 剪辑落点.
- 9.0 target quality score by `references/quality-gates.md`; 8.5 is the minimum final-pass line.

If a foundational item fails, return to unit splitting or director design. Do not fix foundational gaps by surface polishing.

## Script Fidelity

Shot generation may translate abstract psychology, narration, or unsafe script content into filmable visuals, but must not add plot-changing props, clues, events, transactions, relationships, or action outcomes beyond the source script. Small added props may only serve natural visual carrying and must not become new plot.

## Workflow

1. Resolve project directory, source scripts, updated versions, output location, and project-only rules.
2. Normalize and merge scripts before generating any shot units.
3. Register or verify character, look, location, and prop assets.
4. Create scene snapshots and director layer.
5. Create internal evidence cards and unit locks.
6. Generate Seedance-ready shot units.
7. Run hard scan and 9.0-target quality review.
8. For batches, review every 3-5 episodes with scoring and tie-line tracking.

Follow the newest user instruction first, then this skill, then referenced rules.
