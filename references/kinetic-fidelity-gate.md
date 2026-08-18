# Kinetic Fidelity Gate

用于“参考优秀视频后进行原创重构”的高动作密度项目。核心原则：**原创可以改变内容，但不能无意中牺牲参考片真正有效的运动语法、能量曲线和镜头信息密度。**

## 1. Kinetic DNA 比视觉符号优先

参考片中的月亮、石柱、水、枫叶都属于“表达”；真正要保留的是它们承担的功能：视觉锚点、纵深门槛、环境受击、空间升级、高潮闭合。

原创重构时可以改变这些视觉符号，但必须先锁住：

- 起始能量等级
- 加速/减速节奏
- 地面 vs 空中比例
- 景别变化频率
- 机位变化强度
- 环境交互频率
- 高潮位置
- 终止状态

**禁止为了一个更漂亮的新视觉 motif，把高动作段改成数秒静态 hero pose。**

## 2. Reference-Relative Energy Curve

先把参考片同长度窗口的能量曲线记录为：

`E(t) = body motion + camera motion + scale change + environment reaction + VFX state change + edit/occlusion change`

原创方案不要求逐镜相同，但宏观能量曲线必须近似：

- 参考片开场即高速 → 原创不能先慢走/站姿。
- 参考片中段持续升级空间 → 原创不能用长时间绕月/漂浮代替。
- 参考片尾段仍在加速冲击 → 原创不能提前进入 3–4 秒静态高潮展示。

## 3. Information Density Gate

对于高动作参考片，QC 至少做以下近似比较（同长度、同采样率）：

- Mean frame difference
- P90 frame difference
- Mean optical-flow magnitude
- High-amplitude visual-change count

这些不是“画质评分”，只用来检测新片是否明显更静、更重复、更少状态变化。

建议阈值：

- 若生成片 mean frame difference < 参考片的 70%，标记 `KINETIC_UNDERLOAD`。
- 若 P90 frame difference < 参考片的 65%，标记 `PEAK_IMPACT_WEAK`。
- 若 mean optical flow < 参考片的 75%，标记 `MOTION_UNDERLOAD`。
- 若参考片是高速战斗且单一构图停留 >1.5s，而参考片同段没有类似停留，标记 `HOLD_TOO_LONG`。

这些阈值是诊断线，不是绝对美学标准。

## 4. Contact Event Graph

关键攻击禁止只写“角色动作 + 特效”。每个命中都记录事件图：

`Approach -> Contact -> Peak -> Target state change -> Secondary motion -> Camera response -> Aftermath`

例如：

`冲刺接近 -> 剑锋真的触到石面 -> 接触点瞬时高亮/顿挫 -> 裂纹沿剑轨扩散 -> 石块错位与碎屑飞散 -> 镜头短震/穿越遮挡 -> 留下可见断面和尘雾。`

如果 Target state change 缺失，则即使剑光很好看也判定接触失败。

## 5. Camera Aggression Gate

高强度参考片必须记录并迁移“机位功能”，不是只写一个运镜词。

检查：

- 近/中/远景是否有快速切换
- 低机位/俯拍/仰拍是否改变空间阅读
- 摄像机是否在命中时提供冲击，而不是一直平滑跟拍
- 是否有 whip / occlusion / cut-on-action / rapid push 等高能转换
- 是否长期保持月亮居中 + 人物绕圈这类稳定构图

如果 3 秒以上都在同一尺度和同一视觉中心附近运动，通常视为 `CAMERA_REPETITION`。

## 6. Ground/Air Balance

空中动作很容易被模型生成成“漂浮展示”。如果参考片含大量地面冲刺、低重心、滑行、踏地转向，则原创必须保留相近的地面战斗占比。

除非叙事有明确理由，否则：

- 单次连续漂浮/悬空展示尽量 <= 1.5s
- 落地后必须有重量：屈膝、滑移、尘水反馈、方向变化
- 空中段必须承担空间升级或攻击功能，不是纯造型展示

## 7. Originality Rule

原创度检查针对“表达”，不是针对“动力学功能”。

可以改变：

- 世界
- 障碍物形态
- VFX 材质
- 角色招式造型
- 色彩
- 视觉锚点

但不要无理由改变：

- 参考片开场是否立即进入动作
- 中段是否持续加速/换空间
- 高潮前是否还有最后一次推进
- 命中是否改变环境状态
- 镜头是否频繁改变观看关系

一句话：**复制内容是错的；复制方法并重新发明内容是目标。**

## 8. Rewrite Trigger

出现以下任一情况，不再“加形容词”，直接重规划：

- 静态 hero pose 占据高动作片段 20% 以上时长
- 大量动作变成同一个环形挥剑/漂浮动作
- 环境只有一次大特效，而参考片中环境持续参与运动
- 关键碰撞只表现为光闪，目标没有可读状态改变
- 新的原创场景过早切入，破坏参考片原有的能量曲线
- 生成片信息密度明显低于参考片
