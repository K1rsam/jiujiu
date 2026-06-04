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

1. Create or verify asset IDs for characters, looks, locations, and important props.
2. Create scene snapshots: time, location, characters, physical state, prop positions, action objective, risk content, and exit state.
3. Create director layer: audience perspective, main action chain, functional anchors, sound field, transitions, risk avoidance, and pacing.
4. Create internal evidence cards:
   - 剧情覆盖表
   - 单元导演小纲
   - 专属动作词库
   - 场景声场库
   - 转场库
   - 降尺度替代表达表
5. Verify every unit lock before writing final prose:
   - 剧情结果
   - 冲突点
   - 功能锚点
   - 动作链
   - 反应升级
   - 剪辑落点
6. Generate final Seedance units only after the internal gates pass.

## Final Output Boundary

- Final shot scripts contain only Seedance-ready units.
- Do not include scene snapshots, director layer notes, evidence cards, unit locks, scoring, or task-package analysis in final scripts.
- If the user asks for a review record, write it as a separate review document, not inside the final shot script.

## Batch Workflow

- Establish 1-3 sample episodes before expanding a new project or style.
- Batch in 3-5 episode stages by default.
- After each stage, run hard checks and 9.0-target scoring by `quality-gates.md`.
- If any episode scores below 8.5, treat it as draft and return to director design or unit split. Episodes at 8.5-8.9 pass only as tie-line items and must carry concrete upgrade notes.
- Keep project-specific rules separate from generic skill rules.
