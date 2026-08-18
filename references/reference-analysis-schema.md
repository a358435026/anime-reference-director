# Reference Analysis Schema

Use this schema internally when analyzing a supplied reference video.

```yaml
reference:
  duration_s: 0
  aspect_ratio: ""
  fps: 0
  overall_director_judgment: ""

shots:
  - id: S01
    time: "0.00-0.00"
    shot_function: ""
    framing: ""
    camera_position: ""
    camera_motion: ""
    subject_start_state: ""
    subject_action: ""
    subject_end_state: ""
    weapon_or_prop_path: ""
    spatial_layers: []
    visual_anchor: ""
    environment_interaction: ""
    vfx_cause: ""
    vfx_consequence: ""
    transition: ""
    energy: 0
    why_it_works: ""
    reusable_rule: ""

creative_dna:
  - observed_pattern: ""
    function: ""
    abstract_rule: ""
    possible_original_transforms: []

do_not_copy:
  - ""

reference_weaknesses:
  - ""
```

## Rules

- `why_it_works` must name a mechanism, not praise.
- `reusable_rule` must still make sense after all reference-specific nouns are removed.
- `creative_dna` should preserve function while allowing a radically different visual implementation.
- High-action passages deserve finer temporal inspection than static passages.
- A scene change is not the same as every high-amplitude VFX change; distinguish editorial cuts from impact flashes or full-frame effects.
