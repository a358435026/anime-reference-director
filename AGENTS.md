# Agent Orchestration Guide

This repository is designed to be used as one composite director skill, not as a bag of unrelated prompt files.

## Entry Point

Always start with root `SKILL.md`.

For the canonical user request:

> 分析这个参考视频，保留它优秀的导演方法，但重新设计原创动漫，角色用我的人物图，最终给我 Seedance 15 秒提示词。

route in this order:

1. `skills/reference-critic/SKILL.md`
2. `skills/creative-director/SKILL.md`
3. `skills/action-director/SKILL.md`
4. `skills/vfx-supervisor/SKILL.md`
5. `skills/seedance-compiler/SKILL.md`
6. After the user returns a generated clip: `skills/qc-reviewer/SKILL.md`

## Handoff Contract

Each stage must pass a structured handoff rather than prose-only impressions.

### Reference Critic → Creative Director

Must include:
- creative_dna[]
- reference_strengths[]
- reference_weaknesses[]
- do_not_copy[]
- energy_curve
- shot_function_map[]

### Creative Director → Action Director

Must include:
- original_concept
- visual_thesis
- world_design
- visual_anchor
- obstacle_system
- beat_timeline[]
- final_end_state

### Action Director → VFX Supervisor

For every impact beat:
- actor
- start_state
- body_action
- weapon_path
- contact_target
- contact_time
- force_level
- expected_material_response
- recovery_state

### VFX Supervisor → Seedance Compiler

For every hero effect:
- source
- trigger
- material
- path
- collision
- secondary_motion
- light_response
- camera_response
- dissipation
- aftermath

### Seedance Compiler → QC

Persist:
- director_intent
- timed_beats
- must_happen[]
- must_not_happen[]
- expected_end_state

QC scores the generated clip against these fields, not against vague taste.

## Core Safety / Originality Boundary

Reference videos are used to learn general cinematic grammar and methods. Do not instruct the model to reproduce a reference's exact sequence of shots, protected characters, dialogue, music, or distinctive finished expression. Rebuild with new story content and new visual choices.

## Anti-Pattern

Never do this:

`reference video → one long prompt`

Always do this:

`reference video → analysis → abstraction → original design → action physics → VFX physics → prompt compile → rendered-clip review`
