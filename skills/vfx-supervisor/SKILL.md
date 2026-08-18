---
name: vfx-supervisor
description: Design physically legible anime/fantasy VFX with source, material, path, collision, light interaction, secondary motion, dissipation, and aftermath. Use for destruction, sword energy, particles, water, fire, smoke, debris, shockwaves, magic, and environment reactions.
license: MIT
---

# VFX Supervisor

## Mission

特效不是“贴在画面上的发光层”。每个特效必须是一个有来源、有路径、有碰撞、有消散、有残留结果的事件。

## Causal VFX Contract

关键 VFX 使用：

`Source → Trigger → Material/Medium → Path → Collision/Interaction → Secondary Motion → Light/Camera Response → Dissipation → Aftermath`

## Destruction Chain

遇到剑砍障碍物、拳击地面、能量撞击等场景时，强制检查：

1. **接触点是否可见**
2. **材料如何先发生局部变化**
3. **裂纹/形变如何传播**
4. **碎片朝什么方向飞**
5. **尘、烟、水、火是否晚于固体反应一个节拍**
6. **光线/阴影是否响应爆发**
7. **镜头是否只在关键冲击时反馈**
8. **最终环境是否留下改变后的状态**

## Five-Layer Impact Stack

按强度选择，不要每击全开：

- **L1 Contact**：火花、亮点、冲击小粒子
- **L2 Flash**：极短 bloom / 曝光提升 / 边缘高光
- **L3 Material**：碎石、水花、木屑、冰屑、元素飞溅
- **L4 Motion Trail**：剑光、角色残影、冲击波
- **L5 Aftermath**：烟尘、余烬、漂浮碎片、能量残留、热浪、涟漪

关键原则：层级错峰出现，不要同一时刻全部爆成一团。

## Physics Rules

描述至少一个物理依据：

- gravity
- inertia
- friction
- drag
- buoyancy
- wind
- collision
- occlusion
- reflection
- refraction
- heat distortion

奇幻不等于无物理。越不可能的现象，越需要稳定的内部规则。

## Environment Participation

当人物靠近场景物体时，环境必须参与：

- 风压推开叶片/灰尘
- 水面被脚步或剑气切开
- 石材按命中方向破裂
- 木结构先弯曲再折断
- 火焰因高速经过偏斜
- 悬浮物因冲击波产生延迟位移

## VFX Failure Flags

以下任一出现则判高风险：

- 发光效果与武器轨迹脱离
- 破坏发生在命中之前
- 障碍物完全不响应攻击
- 碎片无重力或随机漂浮
- 烟尘和碎片同速同方向
- 全屏一直高亮，没有强弱层级
- 结束时环境恢复原状

## Output

每个关键特效返回：

- source
- trigger time
- material
- motion path
- interaction target
- secondary effects
- light/camera response
- dissipation
- final residue/state
