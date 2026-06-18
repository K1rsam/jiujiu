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
- Fighting, action-heavy, weapon, chase, crowd-conflict units, or post-completion fight storyboard selection: `references/fight-units.md`
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
- Unit titles must use cumulative time inside the episode: `生成分镜单元N（A-Bs｜总时长Xs）`. The first unit starts at `0s`, each next unit starts from the prior endpoint, and the last endpoint shows the episode total duration. `总时长Xs` is the current unit duration and must equal its shot sum.
- Every unit must include the full fixed `[通用提示词]` base prompt. Do not write "same as above", "standard prompt", "omitted", or a shortened prompt.
- Every unit must include `[本单元剧情结果]`, `[通用提示词]`, `[资产索引]`, `[场景]`, `[本单元出场人物]`, `[人物状态与站位前提]`, then the five fields `机位/运动`, `画面`, `声音`, `台词`, `转场节拍`.
- `[人物状态与站位前提]` must be self-contained. Do not write empty references such as `承接第xx集`, `承接场xx`, or `承接上一单元`; write the visible current state, location, posture, relative positions, prop positions, clothing/injury state, and visible result of prior action.
- Final scripts must not contain director outlines, evidence cards, coverage tables, scoring tables, task-package notes, or process analysis unless the user explicitly asks for review records.
- Final scripts must be video-generation clean: `[通用提示词]` must keep the video-generation constraints `无字幕、无水印、无logo、无BGM`; other fields must not add extra subtitle, watermark, logo, BGM, screen text overlay, 人名条, 地点条, or 时间条 instructions.

## Internal Quality Gate

Before final shot generation, internally complete or verify:

- Six evidence cards: 剧情覆盖表, 单元导演小纲, 专属动作词库, 场景声场库, 转场库, 降尺度替代表达表.
- Asset supplement gate: after any new script, inserted episode, or merge, verify new characters, looks, locations, props, organizations, and visual-material needs before final batch generation.
- Bidirectional source coverage: source-to-shot coverage must preserve events, dialogue, relationship turns, foreshadowing, and episode hooks; shot-to-source review must reject invented plot-bearing props, clues, causes, transactions, injuries, route changes, or relationship outcomes.
- Dialogue rhythm preplan: for every continuous same-speaker dialogue segment, lock source line, semantic nodes, total duration, per-node shot duration, and required listener/prop/space reaction before final prose.
- Dialogue capacity gate: before final prose, calculate the dialogue body after the speaker colon only, then pre-allocate screen time by source line and continuous same-speaker segment. If the source dialogue plus necessary reaction beats cannot fit within a 15s unit, split or add units before writing. Do not treat an old draft unit count as fixed.
- Unit lock for every unit: 剧情结果, 冲突点, 功能锚点, 动作链, 反应升级, 剪辑落点.
- 9.0 target quality score by `references/quality-gates.md`; 8.5 is the minimum final-pass line.
- Excellent-sample comparison is required for batch quality. Each 3-5 episode stage must compare against approved samples, including this project's strongest current sample and cross-project优秀稿 when relevant, focusing on visual conflict, functional anchors, shot density, Seedance stability, tail handles, and emotional force rather than only numeric metrics.
- Continuous-dialogue aggregate timing must pass before writing final shots. Do not split one speaker's long line into several mechanically valid shots if the whole segment becomes slow, random, or visually repetitive.
- Unit duration budget must be locked before final prose: dialogue-shot total, silent action/reaction total, tail-handle location, compressible loose shots, and non-compressible tight shots. Fix loose silent beats before squeezing dialogue.
- Do not use final review as the first place to discover obvious capacity failures. New generation should not keep any dialogue above 5.0 chars/sec; long information, apology, medical, strategy, confession, identity, and accusation lines must be semantically split or moved into extra units during generation.
- Generation and review are two separate gates. Generation must proactively solve loose pacing, squeezed dialogue, group-speaker clarity, placeholder pictures, tail handles, close-up control, and Seedance drift anchors before final prose; final review must still run the complete hard scans and 9.0 director scoring instead of trusting the preflight.
- If final review finds a foundational issue that should have been caught before prose, return to unit design or generation preflight. Do not approve the batch by patching only surface wording or repeatedly moving seconds around.
- Resolve rule conflicts before final prose. If project rules, skill rules, or Obsidian rules disagree, state the conflict, choose the newest project/user-approved rule as the project override, and update or record the matching rule fix before generation continues. Do not generate with conflicting rules and rely on final review to catch the result.
- Batch rewrite safety gate: do not use global replacement as a substitute for director judgment. After any batch generation, rewrite, or mechanical replacement, immediately run reverse side-effect scans for orphan fields, malformed camera terms, prompt shrinkage, fixed-camera zeroing, slow-push spikes, half-beat spikes, action-hard-cut spikes, broad group subjects, and media instructions outside `[通用提示词]`.
- If a side-effect scan fails, discard that batch as a candidate and return to the last trusted base version. Do not stack local patches on a batch with foundational generation side effects unless the user explicitly asks for emergency salvage.
- Hard-scan tooling must match the actual draft format before declaring pass. Scan both legacy comma style (`- 分镜1,4s,`) and pipe style (`- 分镜1｜4s｜`) for unit sums, 1s shots, dialogue density, OS/VO format, old fields, broad subjects, and duplicate unit numbers. If the scanner misses the active format, the result is invalid; update the scan and rerun before any scoring.
- Hard-scan tooling must reject orphan shot fields. Any `机位/运动`, `画面`, `声音`, `台词`, or `转场节拍` field without a directly preceding legal `分镜N,时长s,` shot container is a hard failure.
- Hard-scan tooling must reject malformed or obsolete camera terms such as `轻微推近`, `微微推近`, `轻微推进`, `轻缓慢推近近`, and `轻缓慢推近进`; rewrite them into clear Seedance-readable motion based on shot function.
- If a batch fails because the generation preflight missed dialogue capacity, loose pacing, or format compatibility, record the miss as a process failure and fix the generation rules before continuing. Do not hide the failure by only saying the later rewrite passed.
- For information-heavy episodes such as purchase lists, compensation promises, house-building plans, medical explanation, strategy, confession, or public accusation, generation must first allocate extra units and bind every semantic node to a visible prop/reaction. Do not create a compact v1 that will predictably require structural rewrite.

If a foundational item fails, return to unit splitting or director design. Do not fix foundational gaps by surface polishing.

## Script Fidelity

Shot generation may translate abstract psychology, narration, or unsafe script content into filmable visuals, but must not add plot-changing props, clues, events, transactions, relationships, or action outcomes beyond the source script. Small added props may only serve natural visual carrying and must not become new plot.

In strict source-dialogue mode, source words are locked even when the source contains typos or awkward wording. Only punctuation, quotation marks, and OS/VO formatting may be adjusted; words may not be added, deleted, replaced, reordered, or synonymized. Any word-level correction requires a separate source-revision record before the final shot script changes that word.

When repairing or splitting generated shots, never leave placeholder language such as `原站位继续开口`, `对方听到这句`, `手边物件`, `目标身上`, `前方人物`, or `场中人物`. Rewrite the shot with named characters, exact props, exact space anchors, and visible result/reaction.

Hard scans are not quality scores. A final review must distinguish mechanical pass/fail from 10-point scoring, and repeated identical scores need concrete evidence rather than being assigned by default.

## Workflow

1. Resolve project directory, source scripts, updated versions, output location, and project-only rules.
2. Normalize and merge scripts before generating any shot units.
3. Register or verify character, look, location, prop, organization, and visual-material assets.
4. Run bidirectional source coverage precheck: source-to-shot requirements and shot-to-source invention risks.
5. Create scene snapshots and director layer.
6. Create internal evidence cards and unit locks.
7. Create the internal dialogue rhythm preplan for continuous same-speaker lines; verify semantic split points and aggregate speaking speed.
8. Create the internal unit duration and dialogue-capacity budget before final prose; if 15s cannot hold source dialogue, required reactions, and tail handle, increase unit count or redesign unit boundaries first.
9. Generate Seedance-ready shot units.
10. Run the complete hard scan and 9.0-target quality review, including source coverage, invention, asset-completeness, group-speaker clarity, timing/granularity, Seedance execution prediction, and continuous-dialogue aggregate scans. Preflight completion does not replace final review.
11. For batches, review every 3-5 episodes with scoring, tie-line tracking, and excellent-sample comparison before continuing.

Follow the newest user instruction first, then this skill, then referenced rules.
