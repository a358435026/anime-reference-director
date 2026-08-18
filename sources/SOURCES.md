# Upstream Skills & Methodology Sources

本仓库不是把上游 Skill 原文简单拼接，而是把多个公开 Skill 中与“参考学习型原创动漫导演”有关的方法重新整理成统一工作流。除非另有说明，本仓库中的 Skill 文本均为重新编写的整合实现。

## 1. Director / Previs

### wuwangzhang1216/DirectorSKILL
- Repository: https://github.com/wuwangzhang1216/DirectorSKILL
- Role in this project: 总导演、blocking/staging、shot function、keyframe-first、AI video failure diagnosis、three-strike repair logic。
- Upstream skill declares MIT license.
- Adaptation: 本仓库重新组织为 `creative-director`、`seedance-compiler`、`qc-reviewer`，不复制具体导演风格模块。

## 2. Seedance Motion / Physics / VFX / Troubleshooting

### Emily2040/seedance-2.0
- Repository: https://github.com/Emily2040/seedance-2.0
- Relevant upstream skills:
  - `skills/seedance-motion/SKILL.md`
  - `skills/seedance-vfx/SKILL.md`
  - `skills/seedance-troubleshoot/SKILL.md`
  - `references/directors-read.md`
- License: MIT (declared by upstream skill metadata).
- Role in this project: motion contract、physical consequence、VFX source/path/interaction/dissipation、root-cause-first repair。
- Adaptation: 合并进 `action-director`、`vfx-supervisor`、`seedance-compiler`、`qc-reviewer`。

## 3. Anime ACT Combat & Hit Feel

### koisama0411/act-combat-design
- Repository: https://github.com/koisama0411/act-combat-design
- License: MIT.
- Role in this project: 动作游戏战斗设计、招式可读性、命中反馈、hit-stop、camera shake、VFX 分层、前摇/命中/余韵结构。
- Adaptation: 只提炼适合 AI 动漫视频的导演与视觉表现部分，不引入项目无关的数值、养成或游戏系统。

## 4. Seedance Fight & Anime Prompt Craft

### beshuaxian/higgsfield-seedance2-jineng
- Repository: https://github.com/beshuaxian/higgsfield-seedance2-jineng
- Relevant skills:
  - `skills/05-fight-scenes/SKILL.md`
  - `skills/08-anime-action/SKILL.md`
- Role in this project: 剑斗动作词汇、环境反馈、动作相机、anime impact frame、动作节奏与 15s prompt 结构。
- License note: repository license file was not found during initial integration, so this project does **not** copy its skill text verbatim. Only general filmmaking/prompting concepts are summarized independently.

## 5. AI Video Production & Review Pipeline

### modelstudioai/skills
- Repository: https://github.com/modelstudioai/skills
- License: Apache-2.0.
- Relevant components:
  - `skills/spark-video/references/spark-video-director/SKILL.md`
  - `skills/spark-video/references/spark-video-vfx-review/SKILL.md`
  - `skills/spark-video/references/spark-video-clip-review/SKILL.md`
- Role in this project: pre-render VFX review、per-clip QC、physics/collision review、REJECT→rewrite→replan loop。
- Adaptation: 本仓库目前只吸收审核思想与字段设计，不复制 spark-video 的 provider/runtime 代码。

## 6. Edit Grammar / Reverse Engineering

### coreyhaines31/marketingskills
- Repository: https://github.com/coreyhaines31/marketingskills
- Relevant reference: `skills/video/references/edit-anatomy.md`
- Role in this project: 从参考视频抽取 edit grammar / beat sheet，而不是照搬具体素材与脚本。

## 7. Visual Director Architecture

### jijiutong/ai-visual-director
- Repository: https://github.com/jijiutong/ai-visual-director
- Role in this project: 多子技能导演架构、continuity state、reference anchor、failure routing、aesthetic/shot planning 的模块化思想。
- Adaptation: 本仓库采用更聚焦于“参考动漫动作片 → 原创 15 秒 Seedance”的轻量结构。

## 8. Video-to-Superprompt Workflow Inspiration

### MengTo/Skills
- Repository: https://github.com/MengTo/Skills
- Relevant skill: `agent-skills/codex/video-to-superprompt/SKILL.md`
- Role in this project: 技术检查参考视频、按 timeline beat 而非均匀缩略图分析、把模糊审美词转换为可执行机制。

---

## Integration Policy

1. 上游有明确开源许可证时，保留来源和许可证信息。
2. 上游许可证不明确时，不复制原文，只重新表述通用方法。
3. 参考真实作品时只学习导演方法、节奏、镜头语法、动作逻辑和技术规律，不复制特定镜头、角色、台词、音乐或独特成品表达。
4. 本仓库自己的原创整合层采用 MIT License。
