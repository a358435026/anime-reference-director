---
name: seedance-compiler
description: Compile an approved anime/fantasy directing plan into concise, executable Seedance prompts with time beats, one dominant action chain per shot, camera support, physical consequences, VFX causality, continuity locks, stability constraints, and reference-relative kinetic fidelity.
license: MIT
---

# Seedance Compiler

## Mission

把导演方案压缩成 Seedance 真正能执行的语言。不是“写得更华丽”，而是减少歧义、建立动作因果和结束状态。

高动作参考项目必须读取 `../../references/kinetic-fidelity-gate.md`。编译时优先保留参考片的 kinetic function，再进行原创视觉表达。

## Prompt Assembly Order

按以下顺序编译：

1. **Reference role** — 用户人物图只负责身份/脸/造型锚定时，明确这一点。
2. **Scene state** — 地点、时间、唯一关键视觉锚点。
3. **Start state** — 第一帧人物姿态、位置、运动方向。
4. **Reference-relative energy constraint** — 开场能量、地面/空中占比、景别变化频率、高潮位置。
5. **Timed action beats** — 以 3–6 个可执行 beat 为主；高动作段可更密，但每个 beat 必须有清楚功能。
6. **Camera** — 每个 beat 一个主导摄影机行为，必要时通过 cut/occlusion 进入下一机位。
7. **Contact + consequence** — 命中点和环境结果必须紧跟动作。
8. **VFX** — 来源、传播、碰撞、消散。
9. **End state** — 15 秒最后一帧必须清楚。
10. **Stability constraints** — 人物、武器、数量、服装、空间连续性。

## Character Reference Rule

如果用户只提供人物图：

`参考图仅锁定角色身份、面部、发型与服装视觉锚点；不要复制参考图背景、姿势或构图。`

不要在 Prompt 中反复重新发明已经由参考图锁定的静态外观。

## 15-Second Structure

不要机械切每 0.5 秒，也不要为了简洁把高动作参考压成 2–3 个长段落。根据参考片信息密度选择 3–8 个 beat。

高动作参考片的默认目标：

- 第一帧已经在运动，不先走路/站姿。
- 单一稳定构图通常不超过 1–1.5 秒。
- 连续空中展示尽量不超过 1.5 秒，除非承担明确空间升级功能。
- 高潮前仍需保留推进/碰撞/方向变化，不提前用长 hero pose 消耗时长。
- 如果参考片同一 15 秒窗口没有换场，不要为了“原创丰富度”提前切入第二个世界或第二套色彩主题。

## Physical Language

优先使用可观察的动词：

`蹬地、压低重心、扭髋、横斩、斜劈、刺入、撞击、裂开、错位、倾倒、飞散、滑行、减速、落地、回收、停住、消散。`

避免只写：

`震撼、华丽、史诗、很快、电影感、超强打击感。`

## Collision Rule

每一个关键攻击后面立刻跟一句可见结果：

`剑锋真正触到石梁，接触点瞬时高亮并产生极短顿挫；石梁沿斩击轨迹先出现裂口，随后两段错位分离，碎石沿剑势方向飞出，尘雾晚半拍爆开，镜头短震后继续跟随人物穿过新打开的通道。`

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
- cut-on-action
- foreground occlusion cut

高动作参考片不能全程平滑跟拍。需要明确写出景别/机位关系的改变：例如 `低位侧跟 -> 命中瞬间近景冲击 -> whip cut 到高角度远景`，但不要让同一个 beat 同时执行多种持续运镜。

## Kinetic Preservation Rule

原创元素只能替换“表达”，不得自动替换“功能”。

例如参考片：

`地面高速冲刺 -> 近距离命中障碍 -> 立刻旋转斩 -> 腾空空间升级`

原创可以变成：

`踏过悬空符石高速冲刺 -> 斩断旋转剑门 -> 利用反冲反向扭身 -> 穿入高空裂隙`

但不能改成：

`缓慢靠近原创大门 -> 站定摆姿 -> 大门自动碎裂 -> 漂浮展示特效。`

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
较完整，便于检查动作因果和 kinetic function。

### B. Paste-Ready Prompt
压缩到可以直接复制进 Seedance 的版本，不重复解释。

## Final Gate

如果 Prompt 中存在：

- 两个以上互相冲突的持续相机动作
- 大量主要动作没有清晰 end state
- 关键命中没有环境反馈
- VFX 没有 source 或 dissipation
- 高动作参考片出现 >1.5s 无功能 hero pose
- 原创换场提前破坏参考能量曲线
- 三秒以上都围绕同一视觉中心/同一景别重复运动

则不要提交，先拆镜、重新分配时间或恢复 kinetic DNA。
