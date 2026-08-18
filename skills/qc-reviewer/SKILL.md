---
name: qc-reviewer
description: Review generated anime/action clips against the approved directing plan, diagnose physics, collision, momentum, action readability, camera, VFX, continuity, identity, and originality failures, then choose prompt repair, parameter change, shot split, or full re-plan.
license: MIT
---

# QC Reviewer

## Mission

生成成功 ≠ 镜头成功。必须重新看成片，并判断模型到底有没有执行导演意图。

## Review Axes

每项 0–10：

1. **Action Logic** — 动作是否按计划发生，是否有起点和终点。
2. **Contact** — 武器/身体是否真的接触目标。
3. **Physics** — 重力、惯性、碰撞、材质、碎片、液体是否可信。
4. **Impact** — 命中是否有层级、停顿、反作用和余韵。
5. **Camera Readability** — 运镜是否服务动作，是否跳轴或抢戏。
6. **VFX Integration** — 特效是否绑定来源、轨迹、对象互动和消散。
7. **Environment State Change** — 被攻击对象是否真正改变，而不是原样不动。
8. **Continuity** — 人物、武器、位置、方向、场景状态是否连贯。
9. **Identity/Style** — 角色图与风格是否稳定。
10. **Originality** — 是否变成对参考片表面元素的照搬。

## Hard Fail Conditions

以下任一出现，默认 REJECT：

- 剑/拳从目标旁边划过，但目标却自己碎裂。
- 攻击发生后障碍物完全不变。
- 目标先碎，再被击中。
- 人物穿模通过障碍，没有接触逻辑。
- 摄像机切换导致动作方向无法判断。
- VFX 与武器或命中点脱离。
- 一个主要动作在片段结束前没有完成。
- 角色、武器或环境关键状态无故重置。

## Diagnosis Before Rewrite

先把“感觉”翻译成机制：

| 用户说法 | 首查机制 |
|---|---|
| 很假 | contact → weight → gravity → momentum |
| 像走过场 | consequence → environment response → end state |
| 剑像空划 | contact target → collision timing → material response |
| 特效很廉价 | source → layering → timing → aftermath |
| 动作很僵 | weight shift → acceleration → recovery → camera support |
| 很乱 | action overload → camera overload → VFX overload |
| 不像参考片那么高级 | creative DNA 是否真正落地，而不是元素数量 |

## Repair Ladder

按成本从低到高：

1. **L1 Prompt repair** — 补动作终点、碰撞、后果，删空泛词。
2. **L2 Timing/parameter repair** — 缩短时长、降低动作数量、锁定镜头。
3. **L3 One controlled reroll** — 只在设计本身没有明显问题时使用。
4. **L4 Keyframe/reference repair** — 起始画面本身有构图/身份问题。
5. **L5 Shot re-plan** — 拆镜、换机位、减少精细接触、改变动作结构。
6. **L6 Edit fix** — 裁掉局部失败、利用遮挡或 cut 吸收问题。
7. **L7 Delete shot** — 镜头不值得继续烧预算。

## Three-Strike Rule

同一镜头设计连续失败 3 次：

> 停止换同义词。必须改设计。

可选动作：

- 时长缩短 40–50%
- 景别推近
- 摄像机锁定
- 只保留一个主体动作
- 将“接触”与“后果”拆成两个镜头
- 用 reaction / aftermath 镜头暗示极难生成的物理过程

## Output

返回：

- Verdict: PASS / REWRITE / REPLAN
- 各轴评分
- 失败发生时间点
- 根因
- 最便宜修复方式
- 修正版 Prompt 或重规划方案
