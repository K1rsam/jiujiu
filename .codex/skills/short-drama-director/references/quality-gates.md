# Quality Gates

Final shot scripts target 9.0/10. Anything below 8.5 is draft, not final; 8.5-8.9 is a tie-line pass that needs concrete upgrade notes.

## 10-Point Score

- 剧情推进 2: every unit has a visible story result; removing a unit would hurt comprehension.
- 动作链 2: core shots have start, process, result, and reaction where needed.
- 功能道具/空间 1.5: each scene uses functional props or space anchors that move the scene forward.
- 台词与时长 1: dialogue fits duration; short beats are not padded; long lines are not rushed.
- Seedance稳定性 1: characters, space, action, safety limits, and visual continuity are generatable.
- 重复度 1: no repeated generic action templates, sound templates, or transition fillers.
- 导演感 1.5: rhythm, reactions, cuts, sound, and staging are designed, not synopsis with pictures.

## 9-Point Upgrade Line

- `画面` carries a visible action chain, not a synopsis sentence. Important shots include trigger, physical state, prop/space contact, result, and reaction.
- 9.0-level `画面` usually follows: pressure -> action -> contact -> result/reaction. Missing contact or result is a likely downgrade unless the shot is intentionally brief.
- Dialogue performance is directed when needed: voice volume, speed, breath, pause, tremor, clipped delivery, lowered voice, choking, or tail-tone match the visible body state.
- Environment supports performance: quiet, noisy, oppressive, empty, crowded, hot, cold, bright, dim, cramped, or exposed conditions change how characters move and speak.
- Long shots earn their duration through changing screen information. A 5s+ shot with only one action or one expression cannot exceed 8.5.
- The scene stays faithful to the script. Added details may clarify action, pressure, and blocking, but cannot create new clues, props, events, causes, deals, or relationship outcomes.

## Hard Gates

- Missing required fields, wrong `台词` field, `[Seedance生成提示词]`, subtitle instructions, or dialogue in `声音`: return for correction.
- Missing internal evidence cards or unit locks: cannot be final.
- Unclear unit story result: maximum 7.
- Foundational coverage gap: maximum 8.
- Risky content deleted without safe replacement: maximum 8.
- Long VO/OS or narration with no visual evidence: maximum 8.
- Generic synopsis style without physical pressure or reaction escalation: maximum 8.
- Key dialogue paired with unsupported generic emotion, with no matching body state or environmental pressure: maximum 8.5.
- Repeated generic micro-actions used as the main visual engine across many shots: maximum 8.5.
- `画面` using invisible interpretation instead of visible behavior: maximum 8.5; severe cases maximum 8.
- Added "cinematic detail" that creates new plot information: maximum 8 even if the shot reads well.
- Plot-changing added props, clues, events, relationships, transactions, or action outcomes: maximum 8; severe cases return to source coverage.
- Episode end without action direction, risk escalation, or relationship change: maximum 8.3.

## Required Scans

- Field scan: required headers, five shot fields, `台词` format, OS/VO quote rule.
- Duration scan: unit total equals shot sum; dialogue can be spoken; 5s+ shots have visible nodes.
- Picture scan: every key `画面` has action nodes, body state, spatial or prop interaction, and a result/reaction.
- Performance scan: emotional dialogue has matching voice-state and visible body/environment support.
- Interpretation scan: remove invisible words and replace them with visible action, prop, distance, posture, or reaction.
- Invention scan: added detail clarifies existing script action and does not create new plot information.
- Safety scan: platform-risk visuals are safely expressed when present.
- Subtitle scan: no generated subtitles, 人名条, 地点条, 时间条, screen text overlays, watermark, logo, or BGM.
- Repetition scan: track generic actions such as stare, breath, pause, hand movement, silence, looking away, freezing, and repeated transition phrases.
- Sound scan: sounds should identify location and pressure, not reuse one generic sound bed for all scenes.
- Staging scan: `[人物状态与站位前提]` is self-contained and does not rely on previous context.

## Stage Review

For each 3-5 episode batch, the review record must include:

- Per-episode 10-point score.
- One concrete deduction or risk note per episode.
- Stage average, minimum, and maximum score.
- Tie-line episodes at 8.5-8.9.
- Whether any episode must return to unit split or director design.

Hard audit is not quality scoring. A record that only says “passed” is not enough to approve a batch.

## Final Document Check

Final shot scripts must not contain:

- Director layer text.
- Evidence cards.
- Unit locks.
- Score tables.
- Task package notes.
- Process explanations.
- Review records.

If the user asks for any of those, write them in a separate review or planning file.
