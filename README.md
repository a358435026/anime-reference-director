# anime-reference-director

一个面向 AI 动漫 / 玄幻 / 动作短片的“参考学习型导演 Skill 套件”。

它的目标不是复刻参考视频，也不是做人物替换，而是：

**参考视频深度分析 → 提炼创作 DNA → 原创重构 → 战斗动作与物理因果设计 → VFX 设计 → Seedance 15 秒提示词编译 → 成片 QC / 失败修复。**

## 核心原则

1. **学习方法，不复制表达。** 保留参考片优秀的节奏、空间、构图、动作逻辑、冲击结构和特效方法，但主动改变剧情、场景符号、动作设计和镜头表达。
2. **先导演，后提示词。** 先做 beat、blocking、shot、camera、action、VFX，再压缩成模型可执行提示词。
3. **动作必须有后果。** 不接受“挥剑但障碍物没反应”的走过场式动作。所有关键动作都使用：Cause → Contact → Reaction → Damage/Change → Debris/Secondary Motion → Aftermath。
4. **VFX 必须物理化。** 特效必须有来源、路径、材质、碰撞、遮挡、光照、消散和最终状态。
5. **成片必须复检。** Prompt 写得好不等于视频生成得好。最终要检查 physics、collision、momentum、continuity、style、identity、camera、impact。
6. **失败三次就改镜头设计，不继续堆形容词。**

## 总控工作流

```text
Reference Video
   ↓
Reference Critic
   ↓
Creative DNA
   ↓
Original Creative Director
   ↓
Action Choreographer
   ↓
Physics / VFX Supervisor
   ↓
Shot & Camera Plan
   ↓
Seedance 15s Compiler
   ↓
Generated Clip
   ↓
QC Reviewer
   ↓
PASS / REWRITE / REPLAN
```

## Skill 结构

- `SKILL.md` — 总入口 / 路由器
- `skills/reference-critic/` — 参考片深度拉片与“创作 DNA”提炼
- `skills/creative-director/` — 原创重构与导演方案
- `skills/action-director/` — 战斗动作、武器轨迹、动量、命中和空间关系
- `skills/vfx-supervisor/` — 碰撞、破坏、碎片、烟尘、能量、水火等物理化特效
- `skills/seedance-compiler/` — 把导演方案压缩成 Seedance 15 秒可执行提示词
- `skills/qc-reviewer/` — 成片评分、失败诊断、重写或重规划
- `sources/SOURCES.md` — 上游 Skill / 方法论来源与许可说明

## 使用方式

理想用户指令：

> 分析这个参考视频，保留它优秀的导演方法，但重新设计原创动漫，角色用我的人物图，最终给我 Seedance 15 秒提示词。

总控 Skill 应自动完成：

- 参考片镜头/动作/节奏/构图/VFX 拆解
- 创作 DNA 与不可照抄内容分离
- 原创故事、动作、场景、镜头和特效重构
- 角色图只负责身份与视觉锚定，不绑死动作
- 15 秒时间轴编排
- 动作-环境因果链
- Seedance 执行 Prompt
- 负面约束
- 成片 QC 与失败修复方案

## 当前阶段

`v0.1`：建立总控和六个专业子 Skill。后续会继续加入参考视频自动拉片、镜头节奏量化、轨迹分析、质量评分与模型适配层。
