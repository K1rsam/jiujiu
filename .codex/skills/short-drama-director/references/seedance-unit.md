# Seedance Unit Rules

Each `生成分镜单元` is a complete Seedance prompt. It must work without previous episode, previous scene, or previous unit context.

## Required Unit Shape

```text
### 生成分镜单元N（0-15s｜总时长15s）

[本单元剧情结果：谁因为本单元，处境/信息/关系/行动方向发生了什么可见变化。]

[通用提示词]
真人竖屏短剧，9:16，photorealistic，电影级写实拍摄质感，4K超写实真人影像，真实演员表演，真实皮肤纹理，真实演员身体比例，动作符合重力、受力和人体关节活动范围，表情克制自然，轻微手持呼吸；统一色彩管理，标准中性色温约5300K，冷暖平衡无偏色，同一集调色连续，低饱和度，中高对比度，亮度自然均匀，暗处保留细节不过黑，亮处不过曝，人物脸和手清楚，画面通透干净无灰雾；焦点精准锁定主体，人物中近景默认35mm/50mm电影镜头感，浅景深自然虚化，轻微35mm电影胶片颗粒约6%，低AI感；无字幕、无水印、无logo、无BGM；避免手部异常、脸部漂移、面部错位、塑料皮肤、过度磨皮、表情失真、肢体僵硬、动作失重、夸张特效。

[资产索引]
CH-001 角色名；LOOK-001 当前造型；LOC-001 场景名；PROP-001 道具名

[场景:场景名｜内/外｜日/夜]

[本单元出场人物：人物A、人物B；声音出现：人物C]

[人物状态与站位前提：写清当前单元开场时可见状态，不写“承接第xx集/承接场xx/承接上一单元”；必须包含人物站/坐/跪/躺、左右前后关系、面对方向、道具位置、服装状态、伤势或醉酒状态，以及前置动作造成的可见结果。]

- 分镜1,4s,
- 机位/运动: 景别、角度、运动、焦点;
- 画面: 可见动作、表演、道具变化和动作结果;
- 声音: 环境声、动作声、道具声;
- 台词: 角色： "普通对白。"/角色（VO）：旁白内容。/角色（OS）：内心独白。/无;
- 转场节拍: 具体可剪的画面或声音落点;
```

## Prompt Usage

- The fixed base prompt is generic. Add one short project-style sentence after it, such as modern urban action, period suspense, rural family drama, or workplace romance.
- Do not put project-specific risk effects, condition labels, creature labels, era labels, or genre labels into the generic base prompt. Add them only as project or scene supplements when relevant.
- Keep color temperature coherent across a project. Scene light may shift for night, candlelight, neon, firelight, dream, or flashback, but faces and hands must stay clear.

## Dialogue and Timing

- Normal Chinese dialogue: about 4-5 characters per second.
- Anger, threat, crying, hesitation, or heavy pause: about 3-4 characters per second.
- Long dialogue must have enough time and should bind to action, reaction, or prop change.
- For emotional or tempo-critical dialogue, add concise voice-state brackets: volume, speed, breath, pause, tremor, choking, lowered voice, clipped delivery, or tail-tone. Do not rely only on broad words such as angry, scared, wronged, or sad.
- Dialogue punctuation may control pauses and rhythm, but must not change the original meaning. Use ellipses, commas, dashes, or repeated punctuation sparingly; do not stylize every line.
- Short silent reactions usually need 1-3 seconds, not a padded 5 seconds.
- Regular units should prefer 13-15 seconds, except establishing shots, short reactions, inserts, or fast action beats.
- Shots of 5 seconds or longer must contain enough visible process: start, process, result, reaction, prop change, or spatial movement.

## Picture Field Standard

- `画面` must be filmable and specific: visible trigger, body state, hand/foot/prop action, spatial change, result, and reaction where needed.
- Write `画面` with this order when possible: `trigger or pressure -> physical action -> prop/space contact -> visible result/reaction`. Keep all parts visible to camera.
- 2-3s shots carry one precise action or reaction result; 4-6s shots need at least two visible action nodes plus a result; 7s+ shots should split unless there is continuous action, dialogue, reaction, and a clear cut point.
- Key dialogue shots must answer why the voice sounds that way. Bind dialogue to environment pressure, posture, breathing, facial restraint, distance, prop handling, and the other character's reaction.
- Avoid dead scene lists such as only furniture or location names. Describe environment as `environment tone + physical feel + character state inside it`, then connect it to action or voice.
- Generic actions are not enough by themselves: looking, freezing, clenching, breathing, silence, lowering eyes, and standing still must be attached to a trigger, a physical result, or a relationship shift.
- Do not write interpretation words in `画面`: like seems, realizes, decides, understands, inner pain, true purpose, deep meaning, invisible emotion, or audience knows. Convert them into visible behavior, prop handling, distance change, or reaction.
- Do not repeat the same micro-action as the main beat across an episode. If a line needs restraint, vary the carrier: sleeve, cup edge, doorframe, chair back, phone, envelope, floor step, breath break, shoulder shift, or interrupted movement.
- Added detail must be "script-faithful clarification": it can specify how an existing action happens, where a character stands, what hand touches, what object moves, or what reaction follows. It cannot introduce new plot-bearing objects, clues, deals, injuries, messages, memories, or relationship facts.
- Rewrite abstract or thin images into visible behavior:
  - Weak: `画面: 她看着他，意识到自己被骗了。`
  - Strong: `画面: 她停在门边，握着门把的手慢慢松开，视线从对方脸上落到自己手里的物件，肩膀僵住半秒后后退一步。`

## VO/OS

- Narrative VO/OS must have visual evidence.
- The image should show a state change, action result, decision caused by information, or relationship change.
- Do not pair narration with only an empty shot, blank stare, standing still, or generic atmosphere.

## Sound and Transition

- `声音` contains only sound design: environment, action, object, footsteps, breath, distant crowd, machine, wind, door, glass, etc.
- Do not put dialogue, VO/OS text, explanation, or BGM in `声音`.
- `转场节拍` must hand pressure to the next unit through a visible action or audible cue. Avoid generic placeholders such as “切到下一场”.

## Self-Contained Staging

- Every unit must independently state current location, body state, relative positions, prop positions, and action pressure.
- Do not write empty context references such as `承接第12集`, `承接场45-1`, or `承接上一单元`.
- If continuity matters, translate it into visible state: wound covered by gauze, door half open, car already stopped, letter held in hand, table knocked over, character standing two steps behind another.
