# Fight Unit Rules

Use this reference only for fighting, action-heavy, weapon, chase, restraint, or crowd-conflict units. Do not put fight wording into ordinary dialogue, romance, family, workplace, or suspense units.

## Core Method

Fight units use the normal `生成分镜单元` shape. Do not add new final fields. In `[通用提示词]`, append one fight-specific supplement after the base prompt and project-style sentence.

Fight supplement template:

```text
本单元为真人近身打斗，动作按起势、闪避/格挡、接触点、受力方向、失衡、落点、对手反应连续呈现；拳脚动作保持真人可完成，人物脸和手脚清楚，空间方向稳定，避免飞天、冲击波、夸张慢动作特效、血腥伤口和违反人体物理的动作。
```

If weapons or obvious injury risk appear, add the platform-safe sentence from `platform-safety.md` after the fight supplement.

## Storyboard-First Upgrade

For major fight units, a separate storyboard prompt may be generated after final shot scripts are complete. This is not part of the normal final script, and it should not be mixed into every unit.

Use storyboard-first only when at least two are true:

- The fight has 3+ continuous action beats, such as attack, dodge/block, counter, fall, crowd reaction.
- The unit contains two-person or group spatial movement where direction continuity matters.
- The result depends on physical force, balance, contact point, or object collision.
- The action would benefit from a 9-panel or 12-panel visual board before Seedance.
- A character's combat style, stance, weapon, or power relation must stay consistent across multiple shots.

Do not use storyboard-first for:

- One quick grab, one shove, one slap, one person blocking a doorway, or a threat with no real fight exchange.
- Dialogue-heavy confrontations where the action is only a small beat.
- Unsafe material that would require graphic visualization.

Post-completion selection output should be a separate audit file, not final script text. Use this table shape:

```text
| Episode | Unit | Fight Type | Storyboard Level | Reason | Storyboard Prompt Needed |
| --- | --- | --- | --- | --- | --- |
| 第13集 | 单元4 | 一对一腿法反制 | A | 连续侧踢、闪避、锁腿、失衡、倒地，方向和受力必须清楚 | 12-panel action storyboard |
```

Storyboard levels:

- A: Must storyboard. Main fight, multiple continuous beats, high visual gain.
- B: Optional storyboard. Has action exchange, but normal fight prompt may be enough.
- C: No storyboard. Keep normal fight supplement only.

## Action Storyboard Prompt Shape

When a unit is rated A or selected B, generate a separate prompt for image/storyboard creation:

```text
Create a 16:9 monochrome action storyboard sheet for a realistic vertical short-drama fight sequence, 9 or 12 numbered panels, rough pencil sketch style, clear readable silhouettes, no text overlay in the image except small panel numbers. Show stable character identity, consistent clothing, exact room layout, start distance, attack path, dodge/block, contact point, force direction, loss of balance, landing/result, and opponent or bystander reaction. Use red arrows for body motion and attack/impact direction, blue arrows for camera movement, green marks for set/prop notes, orange marks for light direction, purple marks for sound or pain-reaction emphasis. Keep live-action human scale, no gore, no flying bodies, no energy waves, no impossible joints.
```

Then append the actual unit-specific sequence, rewritten as 9 or 12 numbered beats. Each beat should contain:

```text
Panel N: camera angle + character positions + action/contact + force/result + reaction.
```

The storyboard prompt should be placed in a separate storyboard file. The Seedance final unit remains clean.

## Fight Splitting

- A fight unit still must be `<=15s`.
- Do not write a whole fight as one summary sentence. Split by action result:
  - 起冲突: stance, distance, first grab, first swing, or object raised.
  - 试探/拦截: dodge, block, step back, hand catches wrist, body turns aside.
  - 反击: strike, sweep, push, shoulder check, kick, disarm, or throw within real human scale.
  - 结果: opponent stumbles, falls behind furniture, loses grip, backs away, or crowd reacts.
  - 收束: threat stops, power relation changes, hostage/protectee becomes safe, or next opponent enters.
- Long dialogue inside fights should be split into separate units or silent reaction beats. Do not squeeze fight action and long lines into the same 6s shot.
- Already split units should keep natural action duration; do not shorten readable setup shots just to fit later dialogue.

## Picture Field

Fight `画面` must follow:

```text
起点/距离 -> 发力动作 -> 接触或近接触点 -> 受力方向 -> 身体结果 -> 对手/旁观者反应
```

Good fight image details:

- Where both bodies start: left/right, front/back, distance, who blocks whose path.
- Which limb or prop leads the action: right hand grabs wrist, shoulder撞开, foot steps across, forearm blocks.
- Contact point or near-contact: sleeve, wrist, shoulder, forearm, chair edge, doorway, table corner.
- Force direction: pulled back, pushed sideways, swept off balance, forced to step back, shoulder turns.
- Result: grip loosens, opponent staggers two steps, chair slides, glass shakes, bystander retreats.
- Reaction: crowd gasps, protector moves in, villain covers wrist, heroine steps behind hero.

Avoid:

- "打成一团", "一招制敌", "气场压制", "瞬间飞出", "狠狠暴打", "血肉模糊", "骨头断裂特写".
- Unclear group action where positions disappear.
- Repeating the same punch/kick beat across many shots.
- Superhuman speed, floating bodies, energy waves, or impossible joint angles unless the project explicitly requires fantasy style.

## Camera and Sound

- Camera should help continuity: side angle, over-shoulder, waist-up two-shot, hand/foot insert, low angle for stance, short handheld follow for impact.
- Avoid excessive spinning camera or fast cutting that hides the action.
- Use sound to sell safe impact: shoes scraping floor, sleeve being grabbed, chair leg sliding, body hitting sofa, crowd inhaling, glass trembling. Do not describe gore sounds.
- `转场节拍` should land on a visible action result: opponent退半步, prop落地, crowd让开, hero抬眼看向下一个人.

## Safety Scale

- Show force through balance, blocking, distance, objects, and reactions, not graphic injury.
- If the script says severe injury, preserve plot function by showing safe aftermath: opponent clutching covered area, unable to stand, needing support, weapon dropped, crowd silent, dialogue confirms consequence.
- Keep martial arts as modern live-action short-drama realism unless the project rule explicitly defines another style.

## Quality Gate

A fight unit cannot score 9.0 if:

- The action has no clear start, contact/near-contact, force direction, result, and reaction.
- The viewer cannot tell who is where after a strike or dodge.
- The prompt relies on "一招/秒杀/打飞/爆发气势" instead of visible physical action.
- Long dialogue is rushed inside the fight instead of split.
- Safety replacement deletes the plot result.
