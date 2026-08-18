---
name: seedance-compiler
description: Compile an approved anime/fantasy directing plan into concise, executable Seedance prompts with time beats, one dominant action chain per shot, camera support, physical consequences, VFX causality, continuity locks, and stability constraints.
license: MIT
---

# Seedance Compiler

## Mission

把导演方案压缩成 Seedance 真正能执行的语言。不是“写得更华丽”，而是减少歧义、建立动作因果和结束状态。

## Prompt Assembly Order

按以下顺序编译：

1. **Reference role** — 用户人物图只负责身份/脸/造型锚定时，明确这一点。
2. **Scene state** — 地点、时间、唯一关键视觉锚点。
3. **Start state** — 第一帧人物姿态、位置、运动方向。
4. **Timed action beats** — 以 2–5 个可执行 beat 为主。
5. **Camera** — 每个 beat 最多一个主导摄影机行为。
6. **Contact + consequence** — 命中点和环境结果必须紧跟动作。
7. **VFX** — 来源、传播、碰撞、消散。
8. **End state** — 15 秒最后一帧必须清楚。
9. **Stability constraints** — 人物、武器、数量、服装、空间连续性。

## Character Reference Rule

如果用户只提供人物图：

`参考图仅锁定角色身份、面部、发型与服装视觉锚点；不要复制参考图背景、姿势或构图。`

不要在 Prompt 中反复重新发明已经由参考图锁定的静态外观。

## 15-Second Structure

不要机械切每 0.5 秒。优先写 **2–5 个清晰 action beats**，每个 beat 都有 end state。

示例：

- `0–3s`：低位突进，建立运动方向与障碍。
- `3–6s`：斜斩命中，障碍真正断裂并打开通道。
- `6–10s`：利用断裂后的空间继续穿行，摄影机改变机位而不是重复动作。
- `10–13s`：最大冲击事件，环境状态发生不可逆变化。
- `13–15s`：落地/收势/余韵，为下一镜留清晰状态。

## Physical Language

优先使用可观察的动词：

`蹬地、压低重心、扭髋、横斩、斜劈、刺入、撞击、裂开、错位、倾倒、飞散、滑行、减速、落地、回收、停住、消散。`

避免只写：

`震撼、华丽、史诗、很快、电影感、超强打击感。`

## Collision Rule

每一个关键攻击后面立刻跟一句可见结果：

`剑锋命中石梁，石梁沿斩击轨迹先出现发光裂口，随后上下两段错位分离，碎石沿剑势方向飞出，尘雾延迟爆开。`

不要把“挥剑”和“障碍破坏”隔成两个互不相干的句子。

## Camera Rule

单个 beat 只选一个主导运镜：

- 低机位侧跟
- 反向退镜
- 急推
- 俯拍下压
- 短 orbit
- whip pan
- locked impact shot

复杂动作优先保证人物与命中可读，再追求运镜。

## Stability Constraints

按真实风险写，不要无脑长 negative list：

- 仅一名主角，不复制人物实体
- 武器始终是一把同一长剑，不变形、不分叉、不消失
- 接触前障碍物保持完整；接触后才发生断裂
- 碎片遵循重力和原运动方向
- 摄像机不随机跳轴
- 角色脸部与参考图保持一致
- 不出现字幕、UI、logo

## Output Modes

默认输出两份：

### A. Director Prompt
较完整，便于检查动作因果。

### B. Paste-Ready Prompt
压缩到可以直接复制进 Seedance 的版本，不重复解释。

## Final Gate

如果 Prompt 中存在：

- 两个以上互相冲突的相机动作
- 三个以上主要动作链
- 没有明确 end state
- 关键命中没有环境反馈
- VFX 没有 source 或 dissipation

则不要提交，先拆镜或简化。
