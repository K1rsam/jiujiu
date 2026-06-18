# Workflow

Use this workflow for new short-drama projects and for updating an existing script set.

## Project Setup

- Confirm the project directory and write outputs only to the user-specified project path.
- If the user provides multiple script versions, merge newer episode ranges into the base script before generating. Treat the updated version as authoritative for its covered episodes.
- Normalize script text before storyboarding: dialogue punctuation, OS/VO markers, scene labels, episode boundaries, and obvious copy/paste artifacts.
- If converted text conflicts with the `.docx` structure or seems to miss scenes, inspect the document structure rather than guessing.

## Source Fidelity

- Build the split-shot plan from the source script, not from invented connective material.
- Preserve key events, dialogue information, relationship turns, foreshadowing, reveals, and episode-end direction.
- Convert abstract psychology, narration, and risky visuals into filmable action only when needed.
- Added environmental details must remain non-plot-bearing unless clearly present in the source script or asset list.

## Production Chain

1. Create or verify asset IDs for characters, looks, locations, important props, organizations, and visual-material needs. New or inserted scripts must produce a supplement list before final batch generation.
2. Run bidirectional source coverage:
   - Source to shot: key events, source dialogue, relationship turns, foreshadowing, and episode hooks must have final-shot carriers.
   - Shot to source: added props, clues, causes, transactions, injuries, route changes, and relationship outcomes must trace back to the source script or project bible.
3. Create scene snapshots: time, location, characters, physical state, prop positions, action objective, risk content, and exit state.
4. Create director layer: audience perspective, main action chain, functional anchors, sound field, transitions, risk avoidance, and pacing.
5. Create internal evidence cards:
   - 剧情覆盖表
   - 单元导演小纲
   - 专属动作词库
   - 场景声场库
   - 转场库
   - 降尺度替代表达表
6. Create the internal dialogue rhythm preplan before writing final prose:
   - 原文台词
   - 说话人
   - 语义节点
   - 建议总时长
   - 每个节点分镜时长
   - 是否需要听者反应、道具变化或空间压力
7. Run the dialogue-capacity gate before writing final prose:
   - Count only dialogue body after the speaker colon.
   - Verify every source line and continuous same-speaker segment can fit its planned shots without exceeding 5.0 chars/sec.
   - For long or information-heavy lines, pre-split by semantic node and assign a visible carrier to each node.
   - If source dialogue, required reactions, and tail handle cannot fit in 15s, add units or redesign boundaries before prose. Do not preserve an old draft unit count just to save time.
8. Verify every unit lock before writing final prose:
   - 剧情结果
   - 冲突点
   - 功能锚点
   - 动作链
   - 反应升级
   - 剪辑落点
9. Generate final Seedance units only after the internal gates pass, including source coverage, invention risk, asset completeness, dialogue capacity, continuous same-speaker aggregate timing, and semantic split checks.

## Final Output Boundary

- Final shot scripts contain only Seedance-ready units.
- Do not include scene snapshots, director layer notes, evidence cards, unit locks, scoring, or task-package analysis in final scripts.
- If the user asks for a review record, write it as a separate review document, not inside the final shot script.

## Batch Workflow

- Establish 1-3 sample episodes before expanding a new project or style.
- Batch in 3-5 episode stages by default.
- Before writing a batch, run capacity planning for all episodes in the stage and decide where unit count must grow. Do this before final prose, not during review repair.
- After each stage, run hard checks and 9.0-target scoring by `quality-gates.md`.
- Stage review must include continuous same-speaker aggregate scan, not only single-shot dialogue-density scan.
- If any episode scores below 8.5, treat it as draft and return to director design or unit split. Episodes at 8.5-8.9 pass only as tie-line items and must carry concrete upgrade notes.
- Keep project-specific rules separate from generic skill rules.
