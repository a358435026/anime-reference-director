---
name: action-director
description: Design anime/fantasy combat choreography as readable physical event chains with body mechanics, weapon trajectories, timing, contact, momentum, environmental interaction, and explicit end states.
license: MIT
---

# Action Director

## Mission

把“打斗很燃”翻译成模型能执行的身体动作、武器轨迹和物理后果。

## Action Contract

所有关键动作写成：

`Actor/Object → Start State → Action → Force → Timing → Contact → Consequence → Recovery/End State`

示例：

`女主低重心前冲 → 左脚外踏固定轴心 → 右手长剑由右后下向左前上斜斩 → 重击 → 2.8s 剑锋命中悬浮石梁 → 石梁沿剑路错位断裂 → 女主顺势旋肩穿过缺口 → 3.4s 落成左膝低位防守姿态。`

## Choreography Rules

1. **动作是连续因果，不是动作词堆叠。**
2. **一招必须有终点。** `挥剑` 不完整，`横斩后剑尖停在左后方，身体半蹲恢复平衡` 才完整。
3. **必须说明重心。** 高速动作优先描述低重心、蹬地、扭髋、肩线、落脚。
4. **武器必须有轨迹。** 横、竖、斜、刺、回收方向写清楚。
5. **命中要有对象。** 没有接触对象或空气/地面反馈的“攻击”默认风险高。
6. **Camera 为动作服务。** 镜头要让动作读得懂，不是抢动作。
7. **高潮不要匀速。** 使用蓄势 → 瞬时加速 → impact pause → recovery。

## Kinetic Rhythm

优先使用：

`准备/压缩 → 爆发 → 命中 → 极短停顿 → 反作用/余势 → 再加速`

避免：

`全程匀速奔跑 + 连续挥舞 + 没有清晰命中点`

## Environment Interaction

若动作靠近可交互物体，至少指定一个反馈：

- 裂纹
- 位移
- 断裂
- 倾倒
- 飞散
- 水花/尘土
- 反射光变化
- 遮挡被打开
- 地面滑痕
- 风压推动布料/树叶/碎屑

## Shot Motion Budget

单镜默认上限：

- 1 个主要身体动作链
- 1 个武器关键轨迹
- 1 个主要命中事件
- 1 个摄像机主动作

超出则拆镜。

## Output

每个镜头返回：

- start pose
- movement chain
- sword/weapon trajectory
- contact target
- physical consequence
- camera support
- end state
