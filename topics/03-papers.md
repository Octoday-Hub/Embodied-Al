## 📄Table Of Contents
- [Embodied Foundation Models](#embodied-foundation-models)
- [Manipulation & Teleoperation](#manipulation)
- [Locomotion](#locomotion)
- [Navigation & Spatial Intelligence](#navigation-spatial-intelligence)
- [Simulators & Sim2Real](#simulation-sim2real)
- [Datasets](#datasets)
- [Benchmarks & Evaluation](#benchmarks-evaluation)
- [Survey](#survey)
---
<a id="embodied-foundation-models" name="embodied-foundation-models"></a>

## Embodied Foundation Models

### [AnyWorld: Factorized Egocentric World Models for Cross-Embodiment Generalization](https://arxiv.org/abs/2608.29242)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">把单条人类交互分解重组为多样机器人域数据，无需配对示教即可跨具身扩展。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">小鹏机器人（合作腾讯、南洋理工大学）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>因子化世界模型</strong>：把一次交互分解为 action / camera / embodiment 三组独立控制，自由重组后把单条人类视频扩展为多样"机器人原生"数据</li><li>纯<strong>人类第一视角视频大语料预训练 + 混合本体微调</strong>，全程无需成对的人-机器人演示</li><li>重组数据可定向补足策略弱点（纠正"虚假完成"先验、建立语言锚定目标选择）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>可控性指标 <strong>0.778</strong>，对比 Cosmos-Predict2.5 0.417、WAN Fun-Control 0.609</li><li>RoboCasa GR1 桌面抓放成功率 49.8% → <strong>54.6%</strong>；小鹏 IRON 人形真机 20 次抓取 20.0% → <strong>55.0%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">AnyWorld（开源，xpeng-robotics/AnyWorld）；人类 egocentric 交互视频预训练语料</td></tr>
</tbody>
</table>

### [Beyond Data Scaling: Representation-Centric Continued Pre-training for Vision-Language-Action Models](https://arxiv.org/abs/2608.27550)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">把 VLA 继续预训练重心从堆数据转向学表示，小数据预算反超全量基线。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">StarVLA 团队（VLAct 项目，作者含 Hengshuang Zhao、Bei Yu、Jiaya Jia 等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>提出独立于数据规模的<strong>以表示为中心的 VLA 继续预训练</strong>，把有限轨迹转成可迁移的视觉-动作知识</li><li><strong>OFT / PI / GR00T 三种动作头同时共同监督同一骨干</strong>，预训练后丢弃动作头、下游另挂任务专用头</li><li>基座 Qwen3-VL-4B，仅 <strong>16 张 GPU + 全开源数据</strong>，权重/检查点/数据管线/训练框架全量公开</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO-Plus <strong>82.6%</strong>、RoboTwin 2.0 <strong>92.5%</strong>，超过 ABot-M0、LingBot-VLA 等基线</li><li>未见人形本体 RoboCasa-GR1 仅用 <strong>20%</strong> 下游轨迹达 <strong>49.5%</strong>，高于全量数据的 GR00T-N1.6（47.6%）</li><li>真机 4 个域内单臂任务平均 <strong>92.5%</strong>（无继续预训练基线 77.5%）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VLAct（基于 Qwen3-VL-4B）</td></tr>
</tbody>
</table>

### [Riemann-1.0: An Embodied World Action Model for Physical AI](https://arxiv.org/abs/2608.27033)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">全因果自回归世界动作模型，同一模型既当可执行机器人策略又是世界模拟器。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">黎曼动力（昆仑万维孵化的机器人公司）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>全因果自回归 World Action Model</strong>：动作位于视觉状态转移的因果链中（先动作、后视觉），区别于联合生成/视频优先/解耦路线</li><li>同一模型双用：既是<strong>闭环机器人策略</strong>，又是<strong>动作条件多本体视觉世界模拟器</strong></li><li><strong>三阶段渐进式具身预训练</strong>：LAM 潜在动作 bootstrap（人类视频）→ UMI/外骨骼轨迹对齐 → 机器人策略增强</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>仿真：LIBERO <strong>99.0%</strong>、RoboTwin 2.0 <strong>94.3%</strong>、长程组合基准 RoboCasa-365 <strong>62.6%</strong>（较此前最佳 +8.4 pp）</li><li>真机（天机双臂）四类家居任务平均 SR <strong>85.0%</strong>、PSR <strong>94.4%</strong>，平均领先最强开源基线 15 个 SR 点</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Riemann-1.0；23.2 万小时多源数据（20 万+ 小时人类第一视角视频、1.2 万+ 小时 UMI/外骨骼示教、2 万+ 小时机器人轨迹，覆盖 41 种本体）</td></tr>
</tbody>
</table>

### [One Policy, Many Embodiments: Unified Camera-Centric Action Geometry Pre-training for Heterogeneous Embodied Manipulation](https://arxiv.org/abs/2608.26058)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">相机中心统一动作几何，让机械臂、人形与人手共享同一 VLA 策略的动作图式。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">小米具身智能团队 + 澳门大学</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>提出<strong>相机中心统一动作公式 UCAG-P</strong>：以相机可观测的末端锚点运动作为统一学习目标，绕开显式 action retargeting 与数据特异分支</li><li><strong>几何条件动作翻译器</strong>结合目标具身运动学，把共享预测运动转成可执行控制</li><li>解耦架构使共享 VLA 学到可迁移操作几何，同时保留各本体特异性可控性</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>单一 checkpoint、无 benchmark 特化微调：LIBERO <strong>98.3%</strong>、RoboTwin Easy <strong>88.7%</strong> / Hard <strong>89.2%</strong></li><li>LIBERO-Plus 零样本 <strong>82.0%</strong>、RoboCasa GR-1 <strong>62.0%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UCAG-P；4.03K 小时机器人+仿真数据与 2.34K 小时人类演示</td></tr>
</tbody>
</table>

### [τ0-VLA: a Hierarchical Robot Foundation Model with World-Model-Guided Test-Time Computation](https://arxiv.org/abs/2608.16885)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">慢思考+快执行分层 VLA，世界模型引导测试时计算，长程真机成功率翻倍。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">上海创智学院（罗剑岚团队）+ 智元机器人 + 香港中文大学</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>双策略分层架构</strong>：高层生成语义子任务（"慢思考"），低层以更高频执行动作（"快执行"），两策略异步并行</li><li>首次将<strong>测试时计算扩展引入具身上层决策</strong>：低置信决策触发"候选子任务→世界模型预测→价值模型打分→束搜索"循环</li><li>配套<strong>执行记忆、世界模型、价值模型与反思模型</strong>四组件</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>4 个 13–25 步长程真机任务平均成功率 <strong>45.0%</strong>，对比 π0.5 22.5%、GR00T N1.7 2.5%</li><li>未见布局下测试时计算把下一子任务预测准确率从 50.0% 提升至 <strong>74.0%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">τ0-VLA（开源，Apache-2.0）；40,115 小时异构真实世界机器人数据</td></tr>
</tbody>
</table>

### [StellaVLA: In-Context Structured Demonstration for Generalizable Vision-Language-Action Models](https://arxiv.org/abs/2608.11671)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">检索一条结构化演示注入上下文，VLA 无需微调即可适应分布外场景。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">悉尼大学（Chang Xu 团队）+ StellarEdge AI</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>离线流水线把原始轨迹自动转为<strong>结构化演示</strong>（任务计划、子目标描述、语言化的 3D 运动），零人工标注</li><li><strong>并行双训练</strong>：动作专家 + 原生语言头共同监督同一骨干，推理时仅用动作专家，<strong>零推理延迟</strong></li><li>跨本体可迁移：真实机器人、人手与 XR 演示均可作为上下文</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>VLA-Arena 排行榜（2026-08-01）总分 <strong>0.63</strong> 居首，对比 π0.5 0.44、LingBot-VLA 0.22</li><li>LIBERO 平均成功率 <strong>98.8%</strong>，LIBERO-Plus 零样本 <strong>85.1%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">StellaVLA；结构化演示基于 Qwen3-VL 自动生成，真机验证于 AgileX Piper</td></tr>
</tbody>
</table>

### [Harness VLA: Steering Frozen VLAs into Reliable Manipulation Primitives via Memory-Guided Agent](https://arxiv.org/abs/2607.08448)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">在冻结 VLA 之外加一层系统级 Harness，组织复用基础模型为可靠操作原语。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学（于超教授团队）联合正行创新、无问芯穹</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>首次将 <strong>Harness Layer</strong>（执行组织系统层）引入具身智能，让冻结的底层 VLA 专注接触密集操作</li><li>Harness 学习如何<strong>组织、调用、复用</strong>基础模型，全程不更新 VLA 权重</li><li>通用系统层框架，可与 <strong>WAM</strong> 等其它具身基础模型组合</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO-Pro 扰动评估成功率 <strong>82.4%</strong>（Pi_RLinf 50%、NVIDIA Cap-X 18.2%、Berkeley RATS 43.8%）</li><li>显著提升复杂扰动环境下的任务成功率</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Harness VLA 框架（项目页 harnessvla.github.io）</td></tr>
</tbody>
</table>
- **[arXiv 2026年7月](https://arxiv.org/abs/2607.10655)** Artificial Foveated Perception for Mitigating Shortcut Learning in Robotic Foundation Models. 提出人工中央凹感知机制，缓解机器人基础模型中的捷径学习问题。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.09818)** TS-Mask VLA: 2D Temporal-Spatial Masking for VLA with Effective Bridging. 提出2D时空间掩码VLA框架及Bridge Attention条件桥梁，0.5B参数在LIBERO上达95.7%成功率。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.06564)** Lift3D-VLA: Lifting VLA Models to 3D Geometry and Dynamics-Aware Manipulation. 将VLA模型提升至3D几何与动力学感知的操作框架，引入3D几何特征与物理动态建模。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.03941)** WSA1: A 3D-Centric World-Spatial-Action Model for Generalizable Robot Control. 提出以3D为中心的世界-空间-动作模型WSA1，通过3D场景理解实现通用机器人控制。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.02865)** DREAMSTEER: Latent World Models Steer VLA Policies During Deployment Without Finetuning. 利用潜在世界模型在部署时引导VLA策略，无需额外微调。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.02501)** Embodied.cpp: A Portable Inference Runtime for Embodied AI on Heterogeneous Robots. 提出便携式具身AI推理运行时，类似llama.cpp但面向机器人，支持异构硬件部署。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.01088)** ROSA: A Robotics Foundation Model Serving System for Robot Factories. 提出面向机器人工厂的基础模型服务系统ROSA，支持多模型部署与异构机器人协调。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.01002)** Hy-Embodied-RxBrain-1.0: A Cognitive World Model with Unified Textual Reasoning and Visual Imagination. 腾讯在 WAIC 2026 发布的具身原生世界认知模型，首次将文本推理与视觉想象在连续认知序列中深度协同，为机器人决策提供高维指导。

### [Xiaomi-Robotics-1: Scaling VLA Models with over 100K Hours of Real-World Trajectories](https://arxiv.org/abs/2607.15330)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用 10 万小时真实轨迹训练 VLA，RoboCasa365 达 57.4%。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">小米（Xiaomi Robotics）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>MoT（Mixture-of-Transformers）架构</strong>：Qwen3-VL 视觉语言模型负责语义理解，Diffusion Transformer（DiT）以流匹配生成动作块，VLM 侧动作 token 不参与 DiT 注意力</li><li><strong>两阶段训练</strong>：10 万小时 UMI 真实轨迹预训练 + 约 1 万小时跨本体数据后训练（自采移动/双臂机器人数据、指令标注 UMI 与开源数据集）</li><li><strong>可扩展自动标注管线</strong>：VLM 自动生成场景状态转移语言描述，约 2 周完成全量标注</li><li>提供 <strong>2B / 5B / 10B</strong> 三个规模；跨本体动作空间通过末端执行器坐标系增量统一，缺失维度按损失掩码</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>RoboCasa365 平均成功率 <strong>57.4%</strong>，超越此前 SOTA（46.6%）</li><li>RoboDojo 平均得分 <strong>20.07</strong>，前 SOTA 为 13.07</li><li>真机开箱 4 个 household 任务平均 <strong>75%</strong>；新任务微调平均不到 10 小时数据</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Xiaomi-Robotics-1（2B / 5B / 10B）；数据集 Xiaomi-Robotics-1 Dataset（10 万小时 UMI 真实操作轨迹）；开源（Apache-2.0）</td></tr>
</tbody>
</table>

### [Cortex: A Bidirectionally Aligned Embodied Agent Framework for Long-horizon Manipulation](https://arxiv.org/abs/2607.05377)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VLM 规划 + VLA 执行的双系统双向对齐框架，LIBERO-Long 零样本 95.5%。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学、上海 AI Lab</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>双系统架构</strong>：高层 VLM 以文本语义记忆追踪任务进度、逐个子任务派发，低层 VLA 反应式执行</li><li><strong>双向对齐子任务接口</strong>：操作子任务标准化为 32 个规范技能原语与严格语言模板，规划输出受限于可执行、可处理的子任务</li><li><strong>事件平衡采样</strong>：对子任务转换边界附近样本过采样，缓解长时程任务中的规划模糊性</li><li>训练数据：4000+ 小时自动标注开源视频 + 30 小时仿真数据；推理侧 harness 支持语言规范化与超时重置</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO-Long 零样本成功率 <strong>95.5%</strong>，比单体基线高 3.1%</li><li>RoboTwin <strong>86.8%</strong>，比单体基线高 4.1%</li><li>真机零样本完成未见过的 14 步化学实验，成功率 <strong>65%</strong>（端到端 VLA 微调为 0%）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Cortex；训练数据 4000+ 小时自动标注开源视频 + 30 小时仿真数据</td></tr>
</tbody>
</table>

### [Hy-Embodied-VLA-0.5: A Scalable Vision-Language-Action Model for Cross-Embodiment Deployment](https://arxiv.org/abs/2607.01001)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">腾讯具身 VLA 基座模型，超万小时数据训练，支持跨本体部署。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 7 月（WAIC 2026 发布）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">腾讯（Robotics X / 混元）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>与 Hy-Embodied-VLM-1.0、Hy-Embodied-RxBrain-1.0 组成 <strong>「感知—认知—行动」三层模型栈</strong>，VLA 负责把高层目标转化为连续、可纠错的低层动作</li><li><strong>面向高频连续动作生成</strong>，按频率分层匹配物理世界多时间尺度</li><li><strong>化工工厂试产</strong>：单件节拍小于 6 秒，新 SKU 仅需约 8 小时数据采集与微调即可适配</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>统一建模与跨本体能力在发布评测中表现优异</li><li>工厂试产验证了面向高混合、低批量产线的工业落地能力</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Hy-Embodied-VLA-0.5；训练数据超万小时高精度数据；开源</td></tr>
</tbody>
</table>

### [MiniCPM-RobotManip: A 1.5B General-Purpose VLA Model with Native Context Memory](https://github.com/OpenBMB/MiniCPM-Robot)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">1.5B 轻量 VLA，流式原生记忆，单步推理 120ms。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 7 月（WAIC 2026 发布）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">面壁智能（OpenBMB）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>架构</strong>：SigLIP 视觉塔 + Qwen3.5 语言骨干 + 16 层 DiT 动作头，一次生成 30 步 80 维动作块</li><li><strong>流式记忆</strong>：继承 MiniCPM-V 4.6 视觉 token 压缩（每帧 256→64），增量缓存历史观测，保留最长约 1 分钟上下文且推理成本与单帧持平</li><li><strong>1.5B 参数通用策略</strong>，单决策步前向 120ms（H100 BF16），对比 π0.5 约 234ms</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">LIBERO <strong>97.5</strong>、Calvin ABC→D 4.1、RoboTwin2 easy/hard 91.3/91.6、RMBench <strong>53.3</strong>（π0.5 仅 10.4，约 5 倍）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 MiniCPM-RobotManip（1.5B）；开源（Apache-2.0，仓库 MiniCPM-Robot）</td></tr>
</tbody>
</table>

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.26025)** In-Context World Modeling for Robotic Control. 提出上下文世界模型，通过上下文学习实现机器人控制。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.24049)** SPACE: Enabling Learning from Cross-Robot Data Toward Generalist Policies. 提出SPACE框架，通过笛卡尔状态增量作为通用动作表示，结合动作适配器处理机器人动力学差异，实现跨本体策略学习。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.22174)** OpenHLM: An Empirical Recipe for Whole-Body Humanoid Loco-Manipulation. 清华提出面向人形机器人全身移动操作的开源VLA配方，支持下蹲、踩踏板等全身协调动作。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.17846)** Qwen-RobotManip: Alignment Unlocks Scale for Robotic Manipulation Foundation Models. 通义团队提出统一对齐框架，构建~38,100小时预训练语料，在零样本指令跟随、跨本体迁移上超越先前模型。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.17200)** ACE-Ego-0: Unifying Egocentric Human and Robotic Data for VLA Pretraining. 提出统一人类第一视角视频与机器人的跨本体VLA预训练框架，通过相机空间动作映射与时间对齐实现异构数据联合训练。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.13886)** PhysVLA: Towards Physically-Grounded VLA for Embodied Robotic Manipulation. 提出物理接地VLA，将物理推理引入VLA模型，增强对物体物理属性的理解与操作泛化。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.13769)** μ0: A Scalable 3D Interaction-Trace World Model. 提出基于3D轨迹的可扩展世界模型μ0，通过预测交互点轨迹实现跨本体机器人学习，无需动作标签。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.11270)** Lumo-2: Towards Predictive, Aligned, and Scalable Robot Learning. 引入Lumo-2潜在世界-动作模型，提出多阶段模态预对齐策略。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.08530)** GEAR-VLA: Learning Geometry-Aware Action Representations for Generalizable Robotic Manipulation. 提出几何感知动作表示VLA框架，通过粗到细动作学习与跨本体规范化，在LIBERO/零样本LIBERO-Plus等基准上取得SOTA。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.08242)** Light-WAM: Efficient World Action Models with State-Fusion Action Decoding. 提出轻量级世界动作模型Light-WAM，通过紧凑视频骨干和降维潜空间降低训练成本。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.06556)** Robots Need More than VLA and World Models. 系统分析VLA与世界模型的局限性，提出机器人系统所需的额外能力：物理推理、因果理解和持续学习。

### [Galaxea G0.5: Open-Sourced Generalist VLA with Unified Autoregressive Action Generation](https://arxiv.org/abs/2608.11739)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 WRC 旗舰开源 VLA，以单条自回归流统一推理与动作生成。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">星海图（Galaxea，清华大学赵行团队）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>统一自回归 VLA</strong>：视觉、语言、推理与动作 token 在同一条流中由单一 Transformer Decoder（初始自 Qwen3.5-2B）以 next-token 预测生成</li><li><strong>ActionCodec</strong> 结构化残差量化把跨本体动作压入 27 维共享部件空间（左右臂各 9、夹爪各 1、下身 7）</li><li>原生 CoT（子任务 / BBox / 轨迹 / 动作提示）可选；<strong>14 种本体</strong>预训练</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>真机 R1-Lite/R1-Pro 平均成功率 <strong>76.7%</strong>（π0.5 为 53.3%、GR00T-N1.7 为 24.4%）</li><li>DROID 零样本 <strong>82.5%</strong>（π0.5 57.5%）；LIBERO 98.9%、RoboTwin 2.0 93.3%</li><li>AR+CoT 推理约 <strong>192 ms</strong>；BEHAVIOR 挑战赛 Task Success 0.3136（冠军 0.2605）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 G0.5（权重代码开源，HuggingFace OpenGalaxea/G05）；14 种本体预训练数据；Fast-WAM 世界模型并行公开</td></tr>
</tbody>
</table>

### [WeaveLA: Event-Driven Latent Memory for VLA Long-Horizon Manipulation](https://arxiv.org/abs/2606.17463)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用事件驱动潜在记忆解决 VLA 重复性长程任务跨子任务信息断链问题。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">复旦大学（联合港中文深圳等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>事件驱动的跨子任务潜在记忆接口</strong>：在冻结 VLA 主干（π0.5）之上，以查询驱动注意力池化把每个完成的子任务片段压缩为 8 个潜在 token</li><li>路由进下一子任务的动作生成路径；只在子目标完成事件触发，<strong>不逐帧写入</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>RoboMME 基准最难重复任务子集（SwingXtimes, N=3）成功率从 <strong>0% 提升至 47.8%</strong></li><li>单次执行任务性能不变；逐 episode 配对分析确认收益集中于需要跨子任务因果结构的任务</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 WeaveLA；基于 π0.5 主干与 RoboMME 基准评估</td></tr>
</tbody>
</table>

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30350)** DynaFLIP: Rethinking Robotics Perception via Tri-Modal-Dynamics Guided Representation. 提出DynaFLIP动力学感知多模态预训练框架，整合视觉、语言和动力学信息，提升机器人操作中的场景理解和动作执行能力。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30311)** Archon: A Unified Multimodal Model for Holistic Digital Human Generation. 提出Archon统一多模态模型，整合七种模态实现整体数字人生成，提出"模态内思考"方法逐步增强保真度和可控性。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30263)** minWM: A Full-Stack Open-Source Framework for Real-Time Interactive Video World Models. 提出minWM全栈开源框架，将双向视频扩散模型转换为相机可控的少步自回归世界模型，支持实时低延迟推出。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30260)** How LoRA Remembers? A Parametric Memory Law for LLM Finetuning. 提出参数化记忆法则，量化LoRA在LLM微调中的记忆容量极限，为具身智能模型微调提供理论指导。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30248)** GenClaw: Code-Driven Agentic Image Generation. 提出GenClaw代码驱动智能体图像生成范式，代理首先概念化，然后使用代码渲染视觉草图，最后用生成模型补充纹理，实现高度可控的视觉生成。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30056)** Sample-Efficient Diffusion-based Reinforcement Learning with Critic Guidance. 提出基于扩散模型的样本高效强化学习方法，结合Critic引导提升学习效率，在机器人控制任务中表现优异。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.29488)** AnyMo: Scaling Any-Modality Conditional Motion Generation with Masked Modeling. 提出AnyMo统一多模态框架，结合残差FSQ运动分词器和可扩展掩码建模Transformer，支持任意模态组合的高质量运动合成。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.28548)** GEM: Generative Supervision Helps Embodied Intelligence. 提出GEM生成式监督具身视觉语言模型，将深度图生成任务整合到VLM预训练阶段，在模拟和真实环境评估中展现卓越的任务执行能力。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.28272)** EchoAvatar: Real-time Generative Avatar Animation from Audio Streams. 提出统一流式架构，从增量音频输入合成连续全身运动，支持语音和音乐的无缝泛化，通过工具调用接口实现LLM显式语义控制。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.26933)** Diff-Tracking: Leveraging Text-to-Image Diffusion Models for Unsupervised Visual Object Tracking. 提出Diff-Tracking方法，利用预训练文本到图像扩散模型的丰富语义知识，通过交叉注意力机制实现无监督视觉目标跟踪。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.15153)** Pelican-Unified 1.0: A Unified Embodied Intelligence Model for Understanding, Reasoning, Imagination and Action. 北京人形推出的首个按统一原则训练的具身基础模型，将理解、推理、想象和动作生成集成到单一架构，在WorldArena想象评测上排名第一。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.14211)** ASH: Agents that Self-Hone via Embodied Learning. 通过从自生成轨迹学习逆动力学模型，从未标注网络视频中提取监督，实现长时程具身学习的自改进智能体框架。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13778)** Realtime-VLA FLASH: Speculative Inference Framework for Diffusion-based VLAs. 推测推理框架，引入轻量草稿模型和主模型并行验证，将平均任务级延迟降至19.1ms，实现3倍加速，真实传送带分拣验证。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13757)** FrameSkip: Learning from Fewer but More Informative Frames in VLA Training. 数据层帧选择框架，基于动作变化、视觉一致性和任务进度评分帧，仅保留20%帧即达76.15%宏平均成功率，大幅提升VLA训练效率。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13548)** AttenA+: Rectifying Action Inequality in Robotic Foundation Models. 速度驱动动作注意力优先处理运动学关键段，即插即用框架，OpenVLA-OFT提升至98.6%，Franka上验证鲁棒性。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13403)** RotVLA: Rotational Latent Action for Vision-Language-Action Model. 基于SO(n)旋转潜在动作的VLA框架，提供连续性、组合性和与真实动作动力学对齐的几何结构，仅1.7B参数在LIBERO达98.2%。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13382)** BlockVLA: Accelerating Autoregressive VLA via Block Diffusion Finetuning. 通过块扩散范式将AR骨干适配为高效离散扩散策略，块内并行去噪，在LIBERO和SimplerEnv上实现3.3倍推理加速。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13276)** D-VLA: A High-Concurrency Distributed Asynchronous Reinforcement Learning Framework for Vision-Language-Action Models. 高并发分布式异步RL框架，引入"平面解耦"隔离仿真与优化，四线程异步Swimlane流水线实现全并行，万亿参数规模保持线性加速。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13119)** Towards Long-horizon Embodied Agents with Tool-Aligned Vision-Language-Action Models (VLAs-as-Tools). 将长期任务分配给高层VLM和专用VLA工具族，引入工具对齐后训练，LIBERO-Long上pi_0.5提升4.8pp，RoboTwin提升23.1pp。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13105)** What to Ignore, What to React: Visually Robust RL Fine-Tuning of VLA Models (PAIR-VLA). 通过不变性项和敏感性目标解决视觉偏移，ManiSkill3上pi_0.5平均提升16.62%，OpenVLA提升9.10%。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.10332)** EmbodiSkill: Skill-Aware Reflection for Self-Evolving Embodied Agents. 面向具身智能体的技能自进化框架，通过技能感知反思区分技能内容错误与执行失误，ALFWorld上达93.28%任务成功率。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00416)** Learning while Deploying: Fleet-Scale Reinforcement Learning for Generalist Robot Policies. 提出 Learning while Deploying：一个面向通用机器人策略的车队级强化学习框架。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00321)** Embodied Interpretability: Linking Causal Understanding to Generalization in Vision-Language-Action Models. 研究 VLA 模型的可解释性，分析因果理解如何与模型泛化能力相关联。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00078)** Being-H0.7: A Latent World-Action Model from Egocentric Videos. 提出 Being-H0.7：一种来自第一人称视频的潜在世界-动作模型，在引入世界模型的同时将真实场景部署作为重要考量。

### [Qwen-VLA: A Unified Embodied Foundation Model](https://arxiv.org/abs/2605.30280)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">通义统一具身基座，单模型横跨操作、导航与轨迹预测。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 5 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">阿里巴巴通义千问团队</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Qwen3.5-4B VLM + 1.15B DiT flow-matching 动作解码器</strong>（总约 5.1B）</li><li>四阶段训练：T2A 文本到动作预训练 → CPT → SFT → RL</li><li>将操作、导航、轨迹预测统一为动作-轨迹框架</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO <strong>97.9%</strong>、Simpler-WidowX <strong>73.7%</strong>、RoboTwin Easy/Hard 86.1%/87.2%</li><li>真机 ALOHA 平均 OOD 成功率 <strong>76.9%</strong>，优于 GR00T N1.6 与 π0.5</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Qwen-VLA-Base / Instruct；训练数据 1 万+ 小时多源（操作轨迹、Ego4D 等人类演示、仿真、VLN、VL）；开源（QwenLM/Qwen-VLA）</td></tr>
</tbody>
</table>

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.27792)** MotuBrain: An Advanced World Action Model for Robot Control. 提出 MotuBrain：一种面向机器人控制的高级世界-动作模型，聚焦长时程任务，并结合异构数据提升任务成功率。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24921)** libra-vla: achieving learning equilibrium via asynchronous coarse-to-fine dual-system. 提出 libra-vla：一种面向开放世界场景的异步粗到细双系统架构，用于实现学习平衡并提升鲁棒性。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24622)** CF-VLA: Efficient Coarse-to-Fine Action Generation for Vision-Language-Action Policies. 面向 VLA 策略的高效粗到细动作生成方法，重点针对多步骤执行场景。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24447)** Characterizing Vision-Language-Action Models across XPUs: Constraints and Acceleration for On-Robot Deployment. 研究 VLA 模型在不同 XPU 平台上的部署特性，重点关注机器人端部署中的硬件约束、效率与加速问题。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24182)** $M^2$-VLA: Boosting Vision-Language Models for Generalizable Manipulation via Layer Mixture and Meta-Skills. 通过层混合与元技能机制增强视觉-语言模型在可泛化操作任务中的表现。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.23272)** Modular Sensory Stream for Integrating Physical Feedback in Vision-Language-Action Models. 通过模块化感知流将物理反馈集成到 VLA 模型中，以更好支持触觉交互。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.23121)** Breaking Lock-In: Preserving Steerability under Low-Data VLA Post-Training. 针对低数据VLA后训练中的“锁定”现象，提出保留视觉接地并结合测试时对比提示引导的方法，缓解模型对训练对象和空间目标的过拟合。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.23073)** RL Token: Bootstrapping Online RL with Vision-Language-Action Models. 提出 RL Token：一种利用 VLA 模型引导在线强化学习启动的方法，通过稀疏空间锚点约束动作生成。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21741)** Hi-WM: Human-in-the-World-Model for Scalable Robot Post-Training. 利用动作条件世界模型在闭环想象环境中对通用机器人策略进行失败导向后训练，把人类纠正从真实执行迁移到可复用的模型内修正流程.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21391)** From Noise to Intent: Anchoring Generative VLA Policies with Residual Bridges. 提出ResVLA残差桥接架构，在高层语义理解与低层物理控制之间建立显式过渡，提升生成式VLA的条件对齐与表示效率.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21241)** CorridorVLA: Explicit Spatial Constraints for Generative Action Heads via Sparse Anchors. 为生成式动作头引入稀疏空间锚点与显式容差走廊，用可解释的物理约束提升VLA策略的动作对齐与成功率。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21232)** ReCAPA: Hierarchical Predictive Correction to Mitigate Cascading Failures. 面向多步骤VLA执行的层次化预测纠错框架，通过前瞻式对齐与规划减轻中间步骤错误带来的级联失误.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20834)** PokeVLA: Empowering Pocket-Sized Vision-Language-Action Model with Comprehensive World Knowledge Guidance. 面向轻量部署的小型VLA模型，通过世界知识引导增强参数受限条件下的高层理解、空间感知与操作能力.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20627)** Occupancy Reward Shaping: Improving Credit Assignment for Offline Goal-Conditioned Reinforcement Learning. 离线目标条件强化学习的奖励塑形方法，从世界模型占据测度中提取时序几何结构，缓解稀疏奖励下的信用分配难题。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20246)** Cortex 2.0: Grounding World Models in Real-World Industrial Deployment. 面向工业长时程操作的世界模型框架，从反应式控制转向“规划-执行”（plan-and-act），通过生成候选未来状态提升跨任务与跨本体执行稳定性.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20100)** JoyAI-RA 0.1: A Foundation Model for Robotic Autonomy. 面向开放世界机器人自主性的VLA基础模型，通过多形态数据组织与跨本体训练缓解数据多样性不足和泛化困难.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20012)** EmbodiedMidtrain: Bridging the Gap between Vision-Language Models and Vision-Language-Action Models via Mid-training. 通过mid-training在VLM与VLA之间建立具身过渡阶段，缓解数据分布落差并提升下游动作建模效果.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.19683)** Mask World Model: Predicting What Matters for Robust Robot Policy Learning. 用于机器人策略学习的掩码世界模型，只预测与决策最相关的状态变化，提升世界模型训练效率与策略鲁棒性。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.16484)** DexWorldModel: Causal Latent World Modeling towards Automated Learning of Embodied Tasks. 提出因果潜在世界模型(CLWM)，以DINOv3特征为生成目标解耦交互语义与视觉噪声，引入对偶状态TTT记忆实现O(1)长程记忆，推测式异步推理降低50%阻塞延迟。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.08168)** ViVa: A Video-Generative Value Model for Robot Reinforcement Learning. 视频生成价值模型，利用预训练视频生成器的时空先验进行价值估计，在真实世界箱体组装任务中取得显著提升.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.07799)** Learning Without Losing Identity: Capability Evolution for Embodied Agents. 能力中心演化的具身智能体新范式，引入模块化能力模块实现连续学习，在20次迭代中将任务成功率从32.4%提升至91.3%，零策略漂移.

- ★ **[CVPR 2026年4月](https://arxiv.org/abs/2604.07774)** RoboAgent: Chaining Basic Capabilities for Embodied Task Planning. 面向具身任务规划的VLM能力链框架，将复杂规划分解为基本视觉-语言问题的序列，实现更透明可控的推理过程.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.07430)** HY-Embodied-0.5: Embodied Foundation Models for Real-World Agents. 专为真实世界具身智能体设计的VLM系列模型，采用MoE架构，覆盖2B/32B两种规模，在22个基准上表现优异.

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.29844)** DIAL: Decoupling Intent and Action via Latent World Modeling for End-to-End VLA. 提出 DIAL：一种面向端到端 VLA 的潜在世界建模方法，通过解耦意图与动作来增强真实世界部署能力与泛化性。

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.27670)** ProgressVLA: Progress-Guided Diffusion Policy for Vision-Language Robotic Manipulation. 进度引导的扩散策略VLA，通过预训练进度估计器和可微分进度引导实现长程任务中的进度感知.

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.20711)** RoboECC: Multi-Factor-Aware Edge-Cloud Collaborative Deployment for VLA Models. 面向VLA模型的边云协同部署框架，通过模型-硬件协同切分与网络感知调整，在带宽波动下兼顾实时性与推理性能。

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.17573)** HeiSD: Hybrid Speculative Decoding for Embodied Vision-Language-Action Models with Kinematic Awareness. 提出 HeiSD：一种面向具身 VLA 的运动学感知混合推测解码方法，旨在提升推理效率。

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.17192)** Not All Features Are Created Equal: A Mechanistic Study of Vision-Language-Action Models. VLA模型内部机制的机械可解释性研究，揭示注意力头在编码指令遵循、物体交互和机器人控制等功能中的分工.

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.01581)** KERV: Kinematic-Rectified Speculative Decoding for Embodied VLA Models. 将机器人运动学引入VLA的推测解码过程，利用运动学预测与阈值校正减少重推理开销，在保持成功率的同时显著加速推理。

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.00376)** NeuroHex: A Brain-Inspired Hex Coordinate System to Enable Highly Computationally-Efficient World Models for Continuous Online-Adaptive Learning. 提出 NeuroHex：一种受大脑启发的六边形坐标系统与层次化世界建模方法，用于实现面向持续在线自适应学习的高计算效率世界模型。

- **[arXiv 2026年2月](https://arxiv.org/abs/2602.14979)** RynnBrain: Open Embodied Foundation Models. 开源具身智能时空基础模型，在一个统一框架内集成了自我中心理解、时空定位、物理推理和物理感知规划四大核心能力.

- **[arXiv 2026年2月](https://arxiv.org/abs/2602.11075)** RISE: Self-Improving Robot Policy with Compositional World Model. 组合式世界模型驱动的自改进机器人策略框架，通过在模型内生成经验并迭代优化策略，提升具身任务中的泛化与适应能力。

- **[arXiv 2026年2月](https://arxiv.org/abs/2602.09971)** VLA-JEPA: Enhancing Vision-Language-Action Model with Latent World Model. 将联合嵌入预测架构（JEPA）集成到VLA模型中，通过潜在空间预测世界动态，提升泛化能力和鲁棒性.

- **[arXiv 2026年2月](https://arxiv.org/abs/2602.04315)** GeneralVLA: Generalizable Vision-Language-Action Models with Knowledge-Guided Trajectory Planning. 知识引导轨迹规划的层次化VLA模型，无需真实机器人数据实现零样本操纵和自动数据生成.

- **[arXiv 2026年1月](https://arxiv.org/abs/2601.18692)** A Pragmatic VLA Foundation Model. 文中模型名为 LingBot-VLA，基于约20,000小时真实世界数据和9种双机械臂配置训练，强调真实部署下的泛化能力与训练效率.

- **[arXiv 2026年1月](https://arxiv.org/abs/2601.12993)** Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization. 以人为中心的跨本体VLA基础模型，构建35,000小时跨30种本体的多模态数据集，实现LIBERO基准98.9%的成功率.

- **[arXiv 2026年1月](https://arxiv.org/abs/2601.04052)** Stable Language Guidance for Vision-Language-Action Models. 提出残差语义引导概率框架，将物理可供性与语义执行解耦，提升VLA模型的语言指导稳定性.

- **[arXiv 2025年11月](https://arxiv.org/abs/2511.18112)** EchoVLA: Vision-Language-Action Model with Synergistic Declarative Memory. 结合声明式记忆的VLA模型，通过外部记忆模块缓解长程任务中的遗忘问题，提升多步骤任务执行能力.

- **[arXiv 2025年11月](https://arxiv.org/abs/2511.17502)** RynnVLA-002: A Unified Vision-Language-Action and World Model. 统一VLA与世界模型的框架，世界模型利用动作和视觉输入预测未来图像状态，学习环境物理以细化动作生成.

- **[arXiv 2025年11月](https://arxiv.org/abs/2511.01718)** Unified Diffusion VLA: Vision-Language-Action Model via Joint Discrete Denoising Diffusion Process. 通过联合离散去噪扩散过程统一理解、生成和行动的VLA模型.

### [π_RL: Online RL Fine-tuning for Flow-based Vision-Language-Action Models](https://arxiv.org/abs/2510.25889)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">面向流匹配 VLA（π0 / π0.5）的在线强化学习微调框架。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学、北京大学等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Flow-Noise</strong>：将去噪过程建模为离散时间 MDP，用可学习噪声网络实现精确对数似然计算</li><li><strong>Flow-SDE</strong>：把去噪与智能体-环境交互结合为双层 MDP，通过 ODE-to-SDE 转换实现高效 RL 探索</li><li>解决流匹配动作对数似然难解问题，支持大规模流式 VLA 在线 RL</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>多个基准上 RL 微调在<strong>分布内与分布外</strong>场景均带来显著性能提升</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">πRL 微调框架（基于 π0 / π0.5 等开源模型）</td></tr>
</tbody>
</table>
- **[arXiv 2025年10月](https://arxiv.org/abs/2510.25122)** NanoVLA: Routing Decoupled Vision-Language Understanding for Nano-sized Generalist Robotic Policies. 轻量化VLA架构，通过视觉-语言解耦和动态路由实现高达52倍边缘设备推理加速，参数减少98%.

- **[arXiv 2025年10月](https://arxiv.org/abs/2510.12710)** Reflection-Based Task Adaptation for Self-Improving VLA. 通过失败驱动的反思性RL和成功驱动的质量引导SFT双路径架构，实现VLA模型的快速自主任务自适应.

- **[arXiv 2025年10月](https://arxiv.org/abs/2510.10274)** X-VLA: The First Soft-Prompted Robot Foundation Model for Any Robot, Any Task. 软提示驱动的机器人基础模型，通过参数高效微调实现任意机器人、任意任务的泛化.

- **[arXiv 2025年10月](https://arxiv.org/abs/2510.07778)** IntentionVLA: Embodied Intention Reasoning for Human-Robot Interaction. 具身意图推理的VLA模型，通过意图理解增强人机协作的流畅性和安全性.

- **[arXiv 2025年10月](https://arxiv.org/abs/2510.01623)** VLA-R1: Enhancing Reasoning in Vision-Language-Action Models. 通过RLVR和GRPO系统优化推理与执行的推理增强VLA，并发布VLA-CoT-13K思维链监督数据集.

- **[arXiv 2025年9月](https://arxiv.org/abs/2509.15293)** FoMER: How Good are Foundation Models in Step-by-Step Embodied Reasoning. 提出FoMER基准，专门评估大语言模型在复杂具身决策场景中的逐步推理能力.

- **[arXiv 2025年9月](https://arxiv.org/abs/2509.11767)** WALL-OSS: Igniting VLMs toward the Embodied Space. 端到端具身基础模型，通过大规模多模态预训练实现具身感知、语言-动作关联和鲁棒操纵.

- ★ **[ICLR 2025年9月](https://arxiv.org/abs/2509.09332)** OmniEVA: Embodied Versatile Planner via Task-Adaptive 3D-Grounded and Embodiment-aware Reasoning. 提出任务自适应的3D接地机制和具身感知推理框架，通过门控路由器根据上下文需求显式选择性调节3D融合，实现上下文感知的3D接地和具身约束感知的规划决策.

- ★ **[NeurIPS 2025年9月](https://arxiv.org/abs/2509.08844)** EfficientVLA: Training-Free Acceleration and Compression for Vision-Language-Action Models. 无训练推理加速框架，实现1.93倍加速和28.9%的FLOPs减少.

- **[arXiv 2025年7月](https://arxiv.org/abs/2507.08421)** SwitchVLA: Execution-Aware Task Switching for Vision-Language-Action Models. 执行感知的任务切换VLA.

- **[arXiv 2025年7月](https://arxiv.org/abs/2507.01424)** TriVLA: A Triple-System Vision-Language-Action Model with Episodic World Modeling. 三系统VLA架构（感知-世界模型-行动），通过情景世界模型提升长期任务规划能力.

### [SmolVLA: A Vision-Language-Action Model for Affordable and Efficient Robotics](https://arxiv.org/abs/2506.01844)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">社区驱动的低成本小型 VLA，单 GPU 可训、消费级设备可部署。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Hugging Face、索邦大学</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>单 GPU 可训练</strong>、消费级 GPU/CPU 可部署</li><li>异步推理栈解耦感知与动作执行</li><li>利用社区众包数据训练（LeRobot 生态）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>性能与<strong>10 倍</strong>大的 VLA 相当（仿真+真机多基准）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">SmolVLA（集成于 LeRobot，开源）</td></tr>
</tbody>
</table>
### [WorldVLA: Towards Autoregressive Action World Model](https://arxiv.org/abs/2506.21539)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">将 VLA 与世界模型统一进单一自回归框架，实现图像与动作双向理解生成。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">阿里巴巴达摩院、湖畔实验室、浙江大学</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>图像/文本/动作 <strong>三 tokenizer 共享词表</strong></li><li>提出<strong>动作注意力掩码</strong>策略抑制动作块生成时的误差累积</li><li>无需大规模预训练即可超越 OpenVLA</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO 抓取成功率较同等骨干动作模型 <strong>+4%</strong></li><li>视频生成 FVD 降低 <strong>10%</strong></li><li>掩码策略使动作块生成成功率提升 <strong>4%~23%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">WorldVLA（代码开源，alibaba-damo-academy）</td></tr>
</tbody>
</table>
- **[arXiv 2025年6月](https://arxiv.org/abs/2506.04500)** Don't Do That. Guiding Embodied Systems through Large Language Model-based Constraint Generation. 提出STPR约束生成框架，利用LLM将自然语言约束翻译为可执行的Python函数，应用于点云表示和传统搜索算法，确保机器人导航中的约束遵从.

- **[arXiv 2025年6月](https://arxiv.org/abs/2506.00411)** LoHoVLA: Vision-Language-Action Model for Long-Horizon Embodied Tasks. 专为长时程具身任务设计的VLA模型，通过分层动作预测缓解复合任务的错误累积问题.

- ★ **[ICML 2025年5月](https://arxiv.org/abs/2505.06412)** DiffusionVLA: Scaling Robot Foundation Models via Unified Diffusion and Autoregression. 将自回归推理与扩散策略集成的框架，在102个未见物体上实现63.7%的零样本拾取准确率.

### [Knowledge Insulating Vision-Language-Action Models: Train Fast, Run Fast, Generalize Better](https://arxiv.org/abs/2505.23705)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">解决动作专家破坏 VLM 预训练知识的问题，π0.5 + KI 训练范式。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 5 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence（π0 团队）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>3B</strong> VLM 主干 + <strong>300M</strong> 流匹配动作专家</li><li>动作专家梯度<strong>不回传主干</strong>（stop-gradient 知识绝缘）</li><li>主干用 FAST 离散动作 token 快速习得运动表征，辅以网络级 VLM 数据共训</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>训练步数比 π0 少 <strong>7.5 倍</strong></li><li>推理保持流匹配速度，语言跟随与 OOD 泛化最优（衬衫折叠、bussing 真机任务）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">π0.5 + KI（模型权重经 PI 发布）</td></tr>
</tbody>
</table>
- **[arXiv 2025年5月](https://arxiv.org/abs/2505.03500)** VLAs are Confined yet Capable of Generalizing to Novel Instructions. 研究 VLA 模型如何在保持受约束行为边界的同时，仍能泛化到新指令，并在统一设置下进行评估。

### [GR00T N1.5: World Model-Enhanced VLA](https://research.nvidia.com/labs/gear/gr00t-n15/)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GR00T N1 升级版，冻结 VLM 加世界建模与合成神经轨迹，语言遵循率翻倍。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 5 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA GEAR Lab</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>世界模型 + 动作专家融合</strong>：VLM（Eagle 2.5）冻结训练保语言能力，DiT 动作专家输出连续动作</li><li><strong>FLARE 未来潜表示对齐</strong>（隐式世界建模），解锁人类第一视角视频学习</li><li>DreamGen / Cosmos 生成神经轨迹作合成数据</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>真机 GR-1 语言指令遵循 <strong>46.6% → 93.3%</strong>（总成功率 43.3% → 83.0%）</li><li>Language Table 52.8% → <strong>93.2%</strong>；12 个 DreamGen 新任务成功率 13.1% → 38.3%</li><li>用合成数据仅 <strong>36 小时</strong>完成升级（人工需近 3 个月）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 GR00T-N1.5-3B；数据集 Open X-Embodiment、AgiBot-Beta、DexMG、DreamGen 神经轨迹、NVIDIA Physical AI 数据（24,000 条模拟轨迹）；开源</td></tr>
</tbody>
</table>

### [π0.5: Scaling VLA with Heterogeneous Data](https://arxiv.org/abs/2504.16054)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">π0 开放世界升级版，异构数据共训练让机器人完成长时家务。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 4 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>异构数据共训练</strong>：多机器人数据 + 高层子任务标签 + 口头指令 + 网页 VL 数据</li><li>预训练用 <strong>FAST 离散动作 token</strong>，后训练用 flow matching 连续动作专家</li><li>双层推理，参数量约 3.3B（SigLIP 400M + Gemma 2B + 300M 专家）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>首次让端到端系统在全新家庭执行 <strong>10-15 分钟长时任务</strong>（清洁厨房/卧室）</li><li>OOD 子任务成功率 <strong>94%</strong>，接近见过测试环境的对照组</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 π0.5；训练数据约 400 小时移动操作（约 100 个家庭）+ 跨形态与网页数据；openpi 部分开源</td></tr>
</tbody>
</table>
### [Gemini Robotics: Bringing AI into the Physical World](https://arxiv.org/abs/2503.20020)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">基于 Gemini 2.0 的 VLA 通用模型家族，把多模态推理落地到真实机器人控制。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 3 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind（Gemini Robotics Team）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>含 VLA 主模型与 <strong>Gemini Robotics-ER</strong> 具身推理模型两个模型</li><li>支持 <strong>3D 理解</strong>（多视角对应、3D 边框、抓取预测）</li><li>新短程任务仅需 <strong>100 次演示</strong>即可学会</li><li>可适配新形态（双臂平台、高自由度人形）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>可解长程灵巧任务（折纸狐狸、纸牌游戏）</li><li>ER 模型支持零样本机器人代码生成与少样本上下文学习</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Gemini Robotics（闭源，API 形式提供）</td></tr>
</tbody>
</table>
- **[arXiv 2025年3月](https://arxiv.org/abs/2503.12438)** ChatVLA: Multimodal Understanding and Robot Control. 对话式多模态理解与机器人控制.

- **[arXiv 2025年3月](https://arxiv.org/abs/2503.04123)** SmolVLA: Efficient Vision-Language-Action Models for Robotics. 轻量化VLA模型，适合边缘部署.

### [AgiBot GO-1: Open-Sourced Generalist Embodied Agent](https://arxiv.org/abs/2503.06669)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">智元开源通用具身基座，百万真机数据 + 潜在动作表征。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 3 月（WRC 2025 发布）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">智元机器人 + OpenDriveLab（上海 AI Lab）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>ViLLA 架构</strong>：InternVL-2B VLM + Latent Planner + 扩散 Action Expert</li><li>配套 <strong>AgiBot World</strong> 百万级真机数据集（100 万+ 轨迹、217 任务、5 大场景）</li><li>潜在动作表示随数据量可预测扩展</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>AgiBot World 预训练较 Open X-Embodiment 平均提升 <strong>30%</strong></li><li>GO-1 复杂任务成功率超 <strong>60%</strong>，较 RDT 提升 32%</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 GO-1；数据集 AgiBot World（100 万+ 轨迹）与 AgiBot Digital World 仿真数据；数据集与模型全开源</td></tr>
</tbody>
</table>

### [GR00T N1: An Open Foundation Model for Generalist Humanoid Robots](https://arxiv.org/abs/2503.14734)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">首个开放人形 VLA 基础模型，快慢双系统支撑多步操作。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 3 月（GTC 2025 发布）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA GEAR Lab（Jim Fan、Yuke Zhu 主导）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>双系统架构</strong>：System 2 为 VLM（Eagle-2，10Hz 规划），System 1 为扩散 Transformer 动作专家（120Hz 闭环控制）</li><li><strong>LAPA 潜在动作预训练</strong>，从无标签人类视频学习</li><li>数据金字塔：真实遥操作 + 合成 + 互联网数据混合</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>公开版 GR00T-N1-2B 约 <strong>2.2B 参数</strong>；L40 GPU 上 63.9ms 采样 16 个动作</li><li>预训练约 5 万 H100 GPU 小时；多具身仿真基准超越 SOTA 模仿基线，部署于 Fourier GR-1</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 GR00T-N1-2B；数据集 Open X-Embodiment、AgiBot-Alpha、181,000+ 无标签互联网视频；开源（Apache 2.0）</td></tr>
</tbody>
</table>

### [DexVLA: Vision-Language Model with Plug-In Diffusion Expert for General Robot Control](https://arxiv.org/abs/2502.05855)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">十亿参数扩散动作专家 + 具身课程学习的跨本体 VLA 框架。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 2 月（CoRL 2025）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">美的集团、华东师范大学</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>1B 参数</strong>多头扩散专家，每头对应一种本体</li><li>三阶段课程学习：跨本体预训练 → 本体对齐 → 任务后训练</li><li>子步骤推理自主分解长程任务</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>单臂/双臂/灵巧手等多本体上超 OpenVLA、Octo、Diffusion Policy</li><li>新本体仅需 <strong>100 次演示</strong>掌握复杂技能</li><li>仅 <strong>100 小时</strong>演示完成预训练，可完成 2 分钟以上叠衣长程任务</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">DexVLA（代码开源，dex-vla.github.io）</td></tr>
</tbody>
</table>
### [Helix: A Vision-Language-Action Model for Generalist Humanoid Control](https://www.figure.ai/news/helix)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">首个实现人形全身高速灵巧控制的双系统端到端 VLA。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 2 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Figure AI</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>系统 1 / 系统 2 双系统架构</strong>：S2 为 7B 互联网预训练 VLM（7-9 Hz 场景理解），S1 为 80M 视觉运动 Transformer（200 Hz 连续控制），联合训练、异步部署</li><li>直接输出 <strong>35-DoF 上半身连续控制</strong></li><li>仅约 <strong>500 小时</strong>多机器人遥操作数据（不到以往 VLA 数据集的 5%）</li><li>完全跑在<strong>板载低功耗 GPU</strong>（无需云端）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>双机器人共享同一权重<strong>零样本协作</strong>完成杂货收纳</li><li>自然语言提示下零样本抓取数千种未见小物体</li><li>200 Hz 协调全身 35-DoF 动作空间</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Helix（未开源权重）；自采约 500 小时遥操作数据；S2 基于开源开放权重 VLM</td></tr>
</tbody>
</table>

### [Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models](https://arxiv.org/abs/2502.19417)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">分层 VLM+VLA 框架，让机器人在开放世界跟随复杂指令并回应实时反馈。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 2 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence + Stanford + Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>分层 VLA</strong>：高层 VLM 推理复杂开放指令并输出原子语言命令，底层 π0 VLA（PaliGemma-3B + flow matching 动作专家）执行</li><li>用大 VLM <strong>反向合成</strong>复杂指令 / 人机插话数据训练高层策略</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>单臂、双臂、双臂移动三平台验证</li><li>复杂提示与执行中反馈任务上，指令准确率与任务进度显著高于 GPT-4o 高层方案与扁平 VLA 基线</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Hi Robot；底层策略 π0；合成数据生成方案；未公开完整权重（ICML 2025）</td></tr>
</tbody>
</table>

### [UP-VLA: A Unified Understanding and Prediction Model for Embodied Agent](https://arxiv.org/abs/2501.18867)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">统一多模态理解与未来预测双目标的 VLA 预训练范式。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 1 月（ICML 2025）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学、上海期智研究院</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>CLIP-ViT 连续编码 + VQ-GAN 离散编码</strong>双视觉通路（Phi-1.5 骨干）</li><li>理解增强提示机制</li><li>Bridge 数据 + LLaVA-665k 混合预训练</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CALVIN ABC→D 相比此前 SOTA <strong>+33%</strong></li><li>真实世界中需精确空间信息的任务成功率显著提升</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UP-VLA（代码开源）</td></tr>
</tbody>
</table>
- **[arXiv 2025年1月](https://arxiv.org/abs/2409.20537)** HPT: Hierarchical Pre-trained Transformer for Robot Learning. 分层预训练Transformer架构，通过层次化表征学习实现跨任务的高效迁移学习.

- ★ **[CVPR 2025年1月](https://arxiv.org/abs/2501.10105)** UniAct: Universal Actions for Enhanced Embodied Foundation Models. 提出通用动作空间，将不同形态机器人的底层控制统一为规范化的动作表征，提升基础模型在不同机器人平台间的泛化能力.

- **[arXiv 2025年1月](https://arxiv.org/abs/2501.08132)** HiMoE-VLA: Hierarchical Mixture-of-Experts for Vision-Language-Action Policies. 分层混合专家VLA架构.

### [SpatialVLA: Exploring Spatial Representations for Visual-Language-Action Model](https://arxiv.org/abs/2501.15830)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用 Ego3D 位置编码与自适应动作网格为 VLA 赋予 3D 空间智能的通用操作模型。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 1 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">上海人工智能实验室（联合复旦、上海交大、浙大等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>提出 <strong>Ego3D 位置编码</strong>：在自我中心相机坐标系注入深度 3D 信息，免机器人-相机外参标定</li><li>以<strong>自适应动作网格</strong>将连续动作离散化为空间动作 token，支持跨本体对齐</li><li>在 <strong>1.1M 真实机器人 episode</strong> 上预训练通用策略</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>7 任务套件、16 真实任务、48 仿真设置全面评估</li><li>Franka 空间提示任务理解准确率 <strong>73%</strong>，零样本超过 RT-1-X、Octo、OpenVLA</li><li>相比基线动作 token 更少、推理更快</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 SpatialVLA（开源）；基于 Fractal + Bridge 等 1.1M episodes 混合数据（RSS 2025）</td></tr>
</tbody>
</table>

### [Moto: Latent Motion Token as the Bridging Language for Learning Robot Manipulation from Videos](https://arxiv.org/abs/2412.04445)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以无监督"潜在运动 token"作为视频预训练的桥接语言迁移到机器人控制。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 12 月（ICCV 2025）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">香港大学、腾讯 AI Lab</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>VQ-VAE 式 <strong>Latent Motion Tokenizer</strong> 将帧间运动压缩为离散 token</li><li>Moto-GPT 自回归预测下一运动 token</li><li>co-fine-tuning 打通运动先验与真实控制</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>仅 <strong>98M 参数</strong>在 SIMPLER 与 CALVIN 上媲美 <strong>55B</strong> 模型（RT-2-X）</li><li>人类视频预训练进一步提升操作性能</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Moto（代码开源）</td></tr>
</tbody>
</table>
### [CogACT: A Foundational VLA Model for Synergizing Cognition and Action in Robotic Manipulation](https://arxiv.org/abs/2411.19650)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">组件化 VLA：VLM 负责认知理解、DiT 扩散模块专司动作生成。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 11 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学、微软亚洲研究院等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>DINOv2+SigLIP 视觉、LLaMA-2 语言、DiT 动作模块（最大 <strong>300M 参数</strong>，总规模 7B）</li><li>自适应动作集成（AAE）策略</li><li><strong>0.4M 轨迹</strong>（OXE 子集）预训练</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>模拟评测超 OpenVLA <strong>35%</strong>、真实机器人超 <strong>55%</strong></li><li>模拟中超 RT-2-X（55B）<strong>18%</strong> 绝对成功率</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CogACT（代码与模型开源，cogact.github.io）</td></tr>
</tbody>
</table>
### [GR-2: A Generative Video-Language-Action Model with Web-Scale Knowledge for Robot Manipulation](https://arxiv.org/abs/2410.06158)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">3800 万网络视频生成式预训练的 VLA，100+ 真实操作任务平均成功率 97.7%。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">字节跳动 Seed</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>3800 万视频片段、超 500 亿 token</strong> 网络视频预训练（较 GR-1 的 0.8M 扩大 47 倍）</li><li>视频生成 + 动作预测联合微调</li><li>模型规模扩展性良好</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>100+ 真实桌面任务</strong>平均成功率 <strong>97.7%</strong></li><li>端到端桶拣选（bin picking）成功率 33.3% → <strong>79.0%</strong>（较 GR-1）</li><li>CALVIN 五连任务 73.1% → <strong>85.9%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GR-2（技术报告，项目页 gr2-manipulation.github.io）</td></tr>
</tbody>
</table>
### [RoboDual: Towards Synergistic, Generalized, and Efficient Dual-System for Robotic Manipulation](https://arxiv.org/abs/2410.08001)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VLA 通才模型（慢系统）与扩散 Transformer 专才模型（快系统）的协同双系统。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">上海人工智能实验室、上海交通大学、HKU、AgiBot</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>通才输出高层理解与离散动作，专才做多步动作展开</li><li>专才仅 <strong>20M 可训练参数</strong></li><li>通才推理频率约 4Hz、专才 <strong>20Hz</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>真实环境成功率较 OpenVLA <strong>+26.7%</strong>、CALVIN <strong>+12%</strong></li><li>仅 <strong>5% 演示数据</strong>保持强性能</li><li>控制频率 <strong>3.8×</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboDual（代码开源）</td></tr>
</tbody>
</table>
### [π0: A Vision-Language-Action Flow Model](https://arxiv.org/abs/2410.24164)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence 首个通用策略，flow matching 连续动作实现灵巧操作。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence（π）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>PaliGemma 3B VLM + 300M 动作专家</strong>（总约 3.3B）</li><li><strong>flow matching</strong> 生成连续动作，50Hz 高频控制、50 步动作块</li><li>1 万+ 小时、8 个机器人平台、68 个任务，预训练 + 后训练范式</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>零样本：整理餐桌 <strong>0.971</strong>、叠衬衫 <strong>1.0</strong>、装袋杂货 <strong>0.786</strong></li><li>OpenVLA / Octo 在这些任务上接近 0；较 π0-small 提升超 2 倍</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 π0（约 3.3B）/ π0-small（470M）；训练数据自有 1 万+ 小时 + Open X-Embodiment；openpi 开源（2025-02）</td></tr>
</tbody>
</table>

### [RDT-1B: A Diffusion Foundation Model for Bimanual Manipulation](https://arxiv.org/abs/2410.07864)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">1.2B 参数扩散双臂基础模型，跨本体预训练实现零样本与少样本泛化。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学（朱军、苏航团队）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>基于扩散 Transformer 的<strong>双臂操作基础模型</strong>，1.2B 参数（当时最大扩散机器人基础模型）</li><li>提出 128 维<strong>物理可解释统一动作空间</strong>实现跨本体训练</li><li><strong>交替条件注入（ACI）</strong>平衡图像与语言条件</li><li>46 个多机器人数据集 <strong>1M+ 轨迹 / 约 21TB</strong> 预训练 + 66K+ 自建双臂轨迹微调</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>未见杯洗杯子零样本 <strong>50%</strong>（见过杯 87.5%，基线近 0）</li><li>跨场景倒水 <strong>62.5%</strong>（基线最高 37.5%）；指令跟随 100%</li><li>板载 RTX 4090 达约 6 Hz 动作块 / 381 Hz 动作推理</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 RDT-1B（1.2B）与 RDT-170M；预训练含 RT-1、RH20T、DROID、BridgeData V2、Open X-Embodiment 子集；微调数据 rdt-ft-data 开源（MIT）</td></tr>
</tbody>
</table>

### [TinyVLA: Towards Fast, Data-Efficient Vision-Language-Action Models for Robotic Manipulation](https://arxiv.org/abs/2409.12514)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">免预训练阶段的紧凑 VLA 家族，速度与数据效率双优。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 9 月（RA-L 2025）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">美的集团、华东师范大学、北京人形机器人创新中心等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>用高速多模态模型<strong>初始化策略骨干</strong>（免机器人数据预训练）</li><li>微调时接入<strong>扩散策略解码器</strong></li><li>紧凑模型家族，速度与数据效率显著优于 OpenVLA</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>性能相当或更优，语言指令/新物体/新位置等维度泛化强</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">TinyVLA（代码开源，tiny-vla.github.io）</td></tr>
</tbody>
</table>
### [RoboPoint: A Vision-Language Model for Spatial Affordance Prediction for Robotics](https://arxiv.org/abs/2406.10721)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">预测空间可供性关键点的 VLM，免真机采集的全自动数据管线。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">华盛顿大学、NVIDIA、Allen AI（AI2）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>全自动合成数据管线</strong>，免真机采集</li><li>点级动作空间结合深度图转 3D</li><li>支持导航、操作、AR 多下游任务</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>空间可供性准确率超 GPT-4o/PIVOT <strong>21.8%</strong></li><li>下游任务成功率提升 <strong>30.5%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboPoint、Where2Place 基准（开源）</td></tr>
</tbody>
</table>
- **[arXiv 2024年6月](https://arxiv.org/abs/2406.06833)** RoboMatrix: Skill-Centric Robot Task Planning. 以技能为中心的机器人任务规划框架.

### [OpenVLA: An Open-Source Vision-Language-Action Model](https://arxiv.org/abs/2406.09246)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">7B 开源 VLA，在开源数据上反超 55B 闭源模型。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford + UC Berkeley + TRI + Google DeepMind + Physical Intelligence + MIT</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>基于 Prismatic-7B VLM：<strong>SigLIP + DINOv2 双视觉编码器</strong> + Llama 2 7B</li><li>在 <strong>Open X-Embodiment 970k 条轨迹</strong>上微调</li><li>权重 / 训练流程全开源，支持 LoRA 与量化高效微调</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>29 个评测任务成功率比 RT-2-X（55B）绝对提升 <strong>16.5%</strong>，参数量少 7 倍</li><li>零样本优于 RT-1-X 与 Octo</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 OpenVLA（7B）；数据集 Open X-Embodiment（970k 轨迹）；权重与代码开源</td></tr>
</tbody>
</table>

### [RoboMamba: Multimodal State Space Model for Efficient Robot Reasoning and Manipulation](https://arxiv.org/abs/2406.04339)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以 Mamba 线性注意力构建的高效机器人多模态大模型，低代价微调即获操纵能力。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">北京大学、北京智源人工智能研究院（BAAI）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>首次将 <strong>Mamba 状态空间模型</strong>引入机器人 MLLM，线性复杂度长序列推理</li><li>CLIP 视觉编码器 + Mamba 语言模型端到端集成</li><li>仅微调 <strong>0.1% 参数</strong>（3.7M 策略头，约 20 分钟 / 单张 A100）即获末端位姿预测能力</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>3.2B 参数在 RoboVQA 取得 <strong>36.3 BLEU-4</strong></li><li>SAPIEN 仿真操作达当时 SOTA（策略头仅 7MB）</li><li>推理速度较当时机器人 MLLM 快约 <strong>7 倍</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 RoboMamba（3.2B，开源）；无公开专属数据集</td></tr>
</tbody>
</table>

- **[CoRL 2024年5月](https://arxiv.org/abs/2405.16789)** MC-Skill: Multi-Context Skill Learning for Vision-Language-Action. 多上下文技能学习的VLA框架，支持复杂场景泛化.

### [Octo: An Open-Source Generalist Robot Policy](https://arxiv.org/abs/2405.12213)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">开源通用机器人扩散策略，灵活适配多传感器与动作空间。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 5 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley + Stanford + CMU + Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Transformer 骨干 + 扩散动作解码</strong>，支持语言 / 目标图像双条件</li><li>首个完全开源通用机器人策略（权重、训练流程、数据）</li><li>可微调到新传感器（力觉）与新动作空间</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Open X-Embodiment <strong>800k 轨迹</strong>预训练，9 个真机平台评估</li><li>零样本超过 RT-1-X、与 RT-2-X（55B）相当；微调平均超次优基线 <strong>52%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Octo-Small（27M）/ Octo-Base（93M）；数据集 Open X-Embodiment（800k 轨迹）；完全开源</td></tr>
</tbody>
</table>

### [3D-VLA: A 3D Vision-Language-Action Generative World Model](https://arxiv.org/abs/2403.09631)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以生成式世界模型连接 3D 感知、推理与动作的具身基础模型。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 3 月（ICML 2024）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UMass Amherst、上海交通大学、MIT-IBM Watson AI Lab 等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>基于 <strong>3D-LLM</strong>，引入交互 token（interaction tokens）</li><li>具身扩散模型生成目标图像与点云</li><li>构建 <strong>2M 对</strong> 3D-语言-动作指令数据集</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>held-in 数据集上推理、多模态生成与规划能力大幅超基线</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">3D-VLA（代码与扩散模型权重开源，Hugging Face）</td></tr>
</tbody>
</table>
- **[arXiv 2024年2月](https://arxiv.org/abs/2402.06149)** GR-2: A Generative Video-Language-Action Model for Robot Manipulation. 生成式视频-语言-动作模型，通过大规模视频预训练学习通用视觉表征，再微调到机器人操控任务.

- **[arXiv 2024年1月](https://arxiv.org/abs/2401.12963)** AutoRT: Embodied Foundation Models for Large-Scale Robot Orchestration. 利用基础模型进行大规模机器人编排的系统，结合LLM任务分解和VLM环境理解，在多个机器人上并行收集数据.

### [GR-1: Unleashing Large-Scale Video Generative Pre-training for Visual Robot Manipulation](https://arxiv.org/abs/2312.13139)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GPT 式视频生成预训练迁移到机器人操作的先行工作（GR-2 前身）。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 12 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">字节跳动 Seed</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>GPT 风格统一 Transformer：输入语言+图像序列+机器人状态</li><li>端到端同时预测动作与未来帧</li><li><strong>Ego4D 约 8M 帧</strong>视频预训练后微调</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CALVIN 成功率 <strong>88.9% → 94.9%</strong></li><li>零样本未见场景 <strong>53.3% → 85.4%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GR-1（代码开源，GR1-Manipulation.github.io）</td></tr>
</tbody>
</table>
- **[arXiv 2023年11月](https://arxiv.org/abs/2311.01355)** RoboFlamingo: A Vision-Language Model for Open-Vocabulary Robot Control. 基于Flamingo的开源VLA模型，通过视觉-语言模型微调实现开放词汇的机器人控制，支持少样本学习.

- **[CoRL 2023年7月](https://arxiv.org/abs/2307.06135)** SayPlan: Grounding Large Language Models using 3D Scene Graphs for Scalable Robot Task Planning. 利用3D场景图提升大语言模型的机器人任务规划能力.

### [RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control](https://arxiv.org/abs/2307.15818)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">动作 token 化并入 VLM 共同微调，互联网知识首次迁移到机器人控制。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>首次提出 <strong>VLA 范式</strong>：动作编码为文本 token，与互联网视觉-语言数据共同微调</li><li>骨干为 <strong>PaLI-X-55B</strong> 与 <strong>PaLM-E-12B</strong></li><li>支持 chain-of-thought 多步推理</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>约 6000 次真机评测，未见场景平均成功率从 RT-1 的 32% 提至 <strong>62%</strong></li><li>涌现能力（符号/推理/人物识别）平均 <strong>60%</strong>，RT-1 仅 17%</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 RT-2（PaLI-X-55B / PaLM-E-12B）；训练数据机器人轨迹 + 互联网 VL 数据；权重未公开</td></tr>
</tbody>
</table>

### [VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models](https://arxiv.org/abs/2307.05973)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">LLM + VLM 组合 3D 价值图直接规划操作轨迹，零训练零样本。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford（Wenlong Huang、李飞飞、吴佳俊团队）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LLM 写代码调用 VLM，<strong>组合 3D 价值图</strong>（affordance + constraint）作为运动规划目标函数</li><li><strong>零训练、零样本</strong>合成 6-DoF 轨迹，支持开放指令与开放物体</li><li>MPC 闭环重规划抗扰动</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>真机 5 类任务平均成功率 <strong>88%</strong>（含扰动 70%），LLM + 动作原语基线仅 24%</li><li>在线学习将接触任务动力学学习从 >12 小时降至约 <strong>3 分钟</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型使用现成 LLM（GPT-4）+ VLM（CLIP）；无专属训练数据；代码开源（huangwl18/VoxPoser）</td></tr>
</tbody>
</table>

- **[arXiv 2023年6月](https://arxiv.org/abs/2306.11706)** RoboCat: A Self-Improving Foundation Agent for Robotic Manipulation. 能够自我改进的机器人基础模型，通过数据聚合和微调在新任务上生成新数据，形成自我提升循环.

- **[arXiv 2023年5月](https://arxiv.org/abs/2305.16291)** Voyager: An Open-Ended Embodied Agent with Large Language Models. 开放世界具身智能体的LLM驱动框架.

- **[ICRA 2023年3月](https://arxiv.org/abs/2303.08734)** PromptCraft: Zero-Shot Task Planning with Large Language Models. 零样本任务规划的提示工程框架.

### [PaLM-E: An Embodied Multimodal Language Model](https://arxiv.org/abs/2303.03378)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">首个具身多模态语言模型，连续传感器信号接入 LLM 统一规划与问答。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 3 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google Robotics + Google Research + TU Berlin</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>图像 / 机器人状态等连续观测编码为向量，注入预训练 PaLM 嵌入空间</li><li>单模型统一 <strong>机器人规划、VQA 与字幕生成</strong></li><li>跨域联合训练实现正迁移</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>最大模型 <strong>PaLM-E-562B</strong></li><li>OK-VQA 上取得 SOTA</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 PaLM-E（12B / 84B / 562B）；训练数据 RT 系列机器人数据 + 互联网视觉语言数据；未开源</td></tr>
</tbody>
</table>

- ★ **[ICLR 2022年12月](https://arxiv.org/abs/2212.04088)** LLM-Planner: Few-Shot Grounded Planning for Embodied Agents with Large Language Models. 少样本具身规划的LLM方法.

### [RT-1: Robotics Transformer for Real-World Control at Scale](https://arxiv.org/abs/2212.06817)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">首个大规模多任务真机 Transformer 策略，验证机器人策略可扩展性。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2022 年 12 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google（Robotics at Google / Everyday Robots）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>输入 6 帧图像 + 语言指令，输出 <strong>11 维离散动作</strong></li><li>轻量架构 <strong>EfficientNet-B3（FiLM）+ TokenLearner</strong>，仅 35M 参数</li><li>700+ 真实任务数据采集训练</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>700+ 真机任务成功率 <strong>97%</strong></li><li>对新物体、新环境具备显著零样本泛化</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 RT-1（35M）；数据集 RT-1 数据集；代码开源（google-research/robotics_transformer）</td></tr>
</tbody>
</table>

- ★ **[ICLR 2022年10月](https://arxiv.org/abs/2210.03629)** ReAct: Synergizing Reasoning and Acting in Language Models. 语言模型中推理与行动协同的框架.

- ★ **[NeurIPS 2022年10月](https://arxiv.org/abs/2210.03094)** VIMA: General Robot Manipulation with Multimodal Prompts. 多模态提示的通用机器人操纵模型.

- **[CoRL 2022年9月](https://arxiv.org/abs/2209.07753)** Code as Policies: Language Model Programs for Embodied Control. 将语言模型生成的代码作为机器人控制策略.

- **[CoRL 2022年7月](https://arxiv.org/abs/2207.05608)** Inner Monologue: Embodied Reasoning through Planning with Language Models. 语言模型辅助的具身推理与规划框架.

- **[arXiv 2022年5月](https://arxiv.org/abs/2205.06175)** GATO: A Generalist Agent. 单一Transformer模型同时处理600+任务，涵盖机器人控制、游戏、对话等，首次展示了通用智能体的可能性.

- **[CoRL 2022年4月](https://arxiv.org/abs/2204.01691)** SayCan: Do As I Can, Not As I Say: Grounding Language in Robotic Affordances. 将语言模型与机器人能力结合，实现自然语言指令执行.

- **[CoRL 2022年3月](https://arxiv.org/abs/2203.12601)** R3M: A Universal Visual Representation for Robot Manipulation. 通用机器人视觉表示，通过Ego4D大规模人类视频预训练，可迁移到多种下游机器人操控任务.

<a id="manipulation" name="manipulation"></a>
## Manipulation & Teleoperation

### [Gripper-aware Vision Language Action Models](https://arxiv.org/abs/2608.24603)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">让 VLA 显式感知夹爪形态，用多夹爪 tokenizer 与适配器路由实现跨夹爪操作。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">利物浦大学 AIRV Lab（联合 IISc、ZHAW、华中科技大学、Physical Intelligence 等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>直指现有 VLA 的<strong>“夹爪不变性”隐含假设</strong>：吸盘与平行爪对同一目标策略天然不同</li><li>提出 <strong>MiGA 多夹爪数据集</strong>：5 类夹爪、103K 演示、36 任务，含约 5% 失败演示</li><li>GVLA 引入<strong>三层软提示多夹爪 tokenizer</strong> + <strong>双 Mixture-of-Adapters 策略路由</strong>，平衡共享参数与策略分化</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>仿真四类任务平均成功率 <strong>66.0%</strong>（π0.5 底座），较最优基线提升 <strong>7.62 pp</strong></li><li>未见夹爪（Robotiq 2F-85）仅用 <strong>10 条演示 + 20K 步</strong>微调，适应成功率 <strong>0.92</strong>（去除适配器跌至 0.52）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GVLA 模型；MiGA 数据集（HuggingFace 开源）</td></tr>
</tbody>
</table>

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.23108)** The Curse of Precision: Data Scaling Law for High-Precision Robotic Manipulation. 研究机器人装配等封闭世界任务中数据与精度的关系，提出新缩放定律log(N) ∝ 1/(P - c)。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.22530)** ViTacWorld: Scaling Visuo-Tactile World Models for Contact-Rich Manipulation. 利用真实和模拟数据预训练视觉-触觉世界模型，提升策略性能。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.18231)** FM-VLA: Force-based Memory for VLA in Contact-Rich Manipulation. 提出基于力的记忆模块增强VLA在丰富接触操作中的表现。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.15641)** IMBench: A Benchmark for Intuitive Robotic Manipulation. 直观机器人操作基准测试。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.11427)** EDAR: Learning Environment-Dependent Action Representations for Robotic Manipulation. 将动作令牌与可执行控制结构和预期视觉后果关联，改善下游策略学习。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.10172)** On the Efficiency of LoRA Fine-Tuning for VLA in Industrial Manipulation. 研究LoRA微调VLA模型在工业操作中的效率。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.08354)** SkillPlug: Unsupervised Skill Mining for Few-Shot Adaptation. 通过技能调节模块挖掘共享可转移技能库，实现少样本适应。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.04234)** SoftVTBench: Safety-Aware Visuo-Tactile Benchmark for Deformable Object Manipulation. 面向可变形物体操作的安全感知视觉-触觉基准。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.02322)** LionRock: Hybrid Dynamic Data Collection for VLA Spatial Generalization. 发现VLA模型的捷径学习问题并提出混合动态数据采集策略，被IROS 2026接收。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.27036)** RelAfford6D: Relational 6D Affordance Graphs for Constraint-Driven Manipulation. 提出关系性6D可供性图用于约束驱动的机器人操作。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.26800)** SSI-Policy: Structured Scene Interfaces for Vision-Language Robotic Manipulation. 学习结构化场景接口用于视觉-语言机器人操作。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.24742)** World Value Models for Robotic Manipulation. 融合世界模型与价值估计，通过时序建模评估数据质量。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.23420)** Flowing With Purpose: Latent Action Guided Flow Matching Policies. 提出潜在动作引导的流匹配策略用于机器人操作。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.23157)** Bridging Semantics and Kinematics: Modular Zero-Shot Robotic Manipulation. 模块化零样本机器人操作框架，桥接语义与运动学。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.22540)** PolicyTrim: Boosting Intrinsic Policy Efficiency of VLA Models. 提出内在策略效率概念与PolicyTrim方法，减少VLA模型无效动作，速度提升近6倍。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.22136)** Wh0: Generative World Models as Scalable Sources of Egocentric Human Hand Data. 利用生成式世界模型作为可扩展的自我中心人手操作数据源。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.20999)** Inductive Generalization for Robotic Manipulation. 提出归纳泛化概念与轴基评估测试，发现VLA模型在分布外任务上存在根本性失败。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.18960)** Mem-World: Memory-Augmented World Models for Persistent Robot Manipulation. 通过4D腕部视角曲面元索引内存解决操作中因遮挡导致的场景遗忘问题。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.18375)** PAIWorld: 3D-Consistent World Foundation Model for Robotic Manipulation. 提出几何感知交叉注意力与潜在3D-REPA蒸馏，解决多视图世界模型的3D不一致问题。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.17598)** MuseVLA: Adaptive Multimodal Sensing VLA for Robotic Manipulation. 提出自适应多模态感知VLA模型，将传感器作为按需工具集成，灵巧手操作成功率80.6%。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.12109)** InDex: Adapting VLA to Dexterous Manipulation via Intent-Conditioned Fine-Tuning. 提出跨形态语义继承的灵巧操作VLA适配框架，通过意图条件扩散头解码灵巧手关节。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.11396)** PLUME: Probabilistic Latent Unified World Modeling for Multi-Finger Manipulation. 提出概率潜在统一世界模型用于多指灵巧操作。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.10363)** HiMem-WAM: Hierarchical Memory-Gated World Action Models. 提出层次化记忆门控世界动作模型用于机器人操作。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30226)** BORA: Bridging Offline Reinforcement Learning and Online Residual Adaptation for Real-World Dexterous VLA Models. 提出BORA方法，结合离线强化学习和在线残差适应，实现真实世界灵巧视觉-语言-动作模型的高效训练。

- ★ **[ICML 2026年5月](https://arxiv.org/abs/2605.29937)** Fisher-Preserving Guidance: Training-Free Manifold Constraints for Safe Diffusion Control. 提出无需训练的Fisher保持引导方法，通过流形约束实现安全的扩散模型控制，适用于机器人运动规划。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.29564)** VE2VF: Vision-Enabled to Vision-Free Distillation via Real-world Reinforcement Learning. 提出VE2VF方法，通过真实世界强化学习将视觉依赖策略蒸馏为视觉无关策略，实现鲁棒的接触丰富操作。

- **[ICRA 2026年5月](https://arxiv.org/abs/2605.29298)** MonoDuo: Using One Robot Arm to Learn Bimanual Policies. 提出MonoDuo方法，通过单臂操作数据学习双臂协作策略，降低双臂机器人数据收集成本。

- ★ **[ICML 2026年5月](https://arxiv.org/abs/2605.27095)** FA-OPD: Adversarial Dual On-Policy Distillation from Expressive Flow-based Teacher. 提出FA-OPD对抗双重在线策略蒸馏方法，流匹配教师与轻量MLP学生协同训练，在六个机器人基准上超越强基线。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.26478)** Learning from Demonstrations. 研究机器人从示范中学习的方法，探讨模仿学习、行为克隆等技术在机器人操作中的应用，分析样本效率和泛化能力。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13632)** Guide, Think, Act: Interactive Embodied Reasoning in Vision-Language-Action Models (GTA-VLA). 交互式VLA框架，用户通过视觉线索引导策略，模型生成空间视觉思维链，SimplerEnv WidowX达81.2%成功率，单次视觉交互显著提升OOD性能。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13452)** CUBic: Coordinated Unified Bimanual Perception and Control Framework. 统一双手感知控制框架，学习共享token化表示桥接感知和控制，独立性与协调性从结构中涌现，真实世界Agibot双臂验证。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13117)** SECOND-Grasp: Semantic Contact-guided Dexterous Grasping. 统一灵巧抓取框架，基于VLM语义推理生成粗略接触提议，语义几何一致性细化，DexGraspNet上已见/未见类别分别达98.2%/97.7%。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00475)** MSACT: Multistage Spatial Alignment for Stable Low-Latency Fine Manipulation. 提出 MSACT：一种面向稳定低延迟精细操作的多阶段空间对齐方法，并特别关注双臂协作与扩散式建模。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00471)** Stereo Multistage Spatial Attention for Real-Time Mobile Manipulation Under Visual Scale Variation and Disturbances. 一种面向实时移动操作的视觉-语言-动作方法，针对尺度变化与干扰场景，围绕层次化空间注意力设计以增强鲁棒性。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00438)** thinking in text and images: interleaved vision--language reasoning traces for long-horizon robot manipulation. 一种面向长时程机器人操作的 VLA 风格方法，通过交错文本与视觉推理痕迹来提升规划与执行能力。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.26848)** starry: spatial-temporal action-centric world modeling for robotic manipulation. 提出 starry：一种面向机器人操作的动作中心时空世界建模方法，重点关注双臂协作与任务成功率提升。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24681)** Learning Human-Intention Priors from Large-Scale Human Demonstrations for Robotic Manipulation. 一种层次化操作方法，从大规模人类示范中学习人类意图先验，以提升机器人操作的鲁棒性。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.22615)** GazeVLA: Learning Human Intention for Robotic Manipulation. 通过视线建模人类意图作为中间表示，弥合人机形态差距。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21924)** Long-Horizon Manipulation via Trace-Conditioned VLA Planning. LoHo-Manip框架通过视觉轨迹提示与任务管理VLM，将长时程操作拆解为可恢复的局部执行与滚动式重规划.

- **[ICRA 2026年4月](https://arxiv.org/abs/2604.21914)** VistaBot: View-Robust Robot Manipulation via Spatiotemporal-Aware View Synthesis. 结合前馈几何估计与视频扩散模型，实现无需测试时相机标定的视角鲁棒闭环操作，并提出跨视角泛化评测指标.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20348)** Bimanual Robot Manipulation via Multi-Agent In-Context Learning. 利用多智能体in-context learning协调双臂高维动作空间，在复杂双手任务中提升协同决策与动作生成能力.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20347)** A Vision-Language-Action Model for Adaptive Ultrasound-Guided Needle Insertion and Needle Tracking. 将VLA用于自适应超声引导下的穿刺与针体跟踪，把视觉理解、动作决策与医疗机器人控制结合起来。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.19509)** Assessing VLM-Driven Semantic-Affordance Inference for Non-Humanoid Robot Morphologies. 研究VLM在非人形机器人形态上的语义可供性推断能力，揭示在工具使用和非常规操作场景下存在偏保守与高假阴性问题.

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.05320)** ExpressMM: Expressive Mobile Manipulation Behaviors in Human-Robot Interactions. 面向人机交互的富表达移动操作行为框架，把动作执行与社会表达结合起来提升交互自然性与可理解性。

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.17834)** Generative Control as Optimization: Time Unconditional Flow Matching for Adaptive and Robust Robotic Control. 将流匹配控制从固定步轨迹积分改为自适应优化过程，并利用速度场范数作为无训练的安全与分布外信号，提升控制效率与鲁棒性。

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.10158)** XL-VLA: Cross-Hand Latent Representation for Vision-Language-Action Models. 跨手隐式表示的VLA框架，在不同灵巧手之间共享统一的隐式动作空间，实现跨本体的灵巧操纵训练.

- **[arXiv 2026年3月](https://arxiv.org/abs/2603.00110)** Learning Physics from Pretrained Video Models: A Multimodal Continuous and Sequential World Interaction Models for Robotic Manipulation. 利用预训练视频模型学习连续与序列物理交互，构建服务机器人操作的多模态世界交互模型。

- **[arXiv 2026年1月](https://arxiv.org/abs/2601.21251)** SMP: Abstracting Robot Manipulation Skills via Mixture-of-Experts Diffusion Policies. Skill MoE Policy，学习紧凑正交技能基，使用粘性路由在每一步从小的任务相关专家子集组合动作，变分训练目标支持设计，自适应专家激活实现快速采样.

- ★ **[AAAI 2026年1月](https://arxiv.org/abs/2601.01948)** SDP: Learning Diffusion Policy from Primitive Skills for Robot Manipulation. 技能条件扩散策略SDP，将可解释的技能学习与条件行动规划相结合，抽象出跨任务的八个可复用原始技能，采用VLM提取离散表示，轻量路由网络为每个状态分配期望的原始技能.

### [H-RDT: Human Manipulation Enhanced Bimanual Robotic Manipulation](https://arxiv.org/abs/2507.23523)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用大规模自我中心人类操作数据增强双臂机器人操作的扩散基础模型。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学（朱军团队）等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>2B 参数扩散 Transformer</strong> + flow matching 建模复杂动作分布</li><li>两阶段训练：自我中心人类操作数据预训练 → 跨本体机器人数据微调</li><li><strong>模块化动作编解码器</strong>（Modular Action Encoder/Decoder）支持高效跨本体知识迁移</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>对比从零训练：仿真提升 <strong>13.9%</strong>、真实世界提升 <strong>40.5%</strong></li><li>超越 π0 与 RDT，少样本与鲁棒性评测全面占优</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">H-RDT（代码与预训练模型开源）</td></tr>
</tbody>
</table>
- **[ICRA 2025年6月](https://arxiv.org/abs/2506.20668)** DemoDiffusion: One-Shot Human Imitation using pre-trained Diffusion Policy. 利用预训练的通用扩散策略对通过运动学重定向获得的轨迹进行修正，确保其既遵循人体运动又保持在合理机器人动作分布内，实现单次人类演示的机器人操作模仿.

### [ForceVLA: Enhancing VLA Models with a Force-aware MoE for Contact-rich Manipulation](https://arxiv.org/abs/2505.22159)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">将 6 轴力觉作为一等模态引入 VLA 的力感知 MoE 框架。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 5 月（NeurIPS 2025）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">上海交通大学、复旦大学、新加坡国立大学等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>FVLMoE</strong> 力感知专家混合模块，动作解码时融合实时力反馈</li><li>力感知路由按模态/阶段分流</li><li>同步采集视觉+本体感知+力矩信号</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>较 π0 基线平均任务成功率 <strong>+23.2%</strong></li><li>插插头任务最高 <strong>80%</strong> 成功率</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">ForceVLA-Data（代码与数据开源）</td></tr>
</tbody>
</table>
- **[arXiv 2025年5月](https://arxiv.org/abs/2505.16413)** DexVLA: Plug-in Diffusion Experts for Vision-Language-Action Models. 扩散专家即插即用的VLA增强框架.

- **[arXiv 2025年4月](https://arxiv.org/abs/2504.05291)** ObjectVLA: Open-World Object Manipulation without Demonstrations. 无需演示的开放世界物体操纵VLA.

- **[arXiv 2025年1月](https://arxiv.org/abs/2501.05233)** VideoVLA: Video Generators as Generalizable Robot Manipulators. 利用视频生成模型实现通用机器人操纵.

### [Video Prediction Policy: A Generalist Robot Policy with Predictive Visual Representations](https://arxiv.org/abs/2412.14803)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以视频扩散模型的预测表征指导动作学习的通用操作策略。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 12 月（ICML 2025 Spotlight）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">清华大学、UC Berkeley、上海人工智能实验室等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>VDM 内学习隐式逆动力学模型</strong></li><li>在机器人数据 + 互联网人类操作视频上微调视频基础模型</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CALVIN ABC-D 相对 SOTA 提升 <strong>18.6%</strong></li><li>真机灵巧操作成功率提升 <strong>31.6%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VPP（代码开源，video-prediction-policy.github.io）</td></tr>
</tbody>
</table>
### [EgoMimic: Scaling Imitation Learning via Egocentric Video](https://arxiv.org/abs/2410.24221)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Aria 眼镜第一人称数据与机器人数据统一共训的模仿学习框架。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Georgia Tech</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Project Aria</strong> 采集人类具身数据 + 3D 手部追踪</li><li>低成本双臂平台缩小人机运动学鸿沟</li><li>跨域对齐 + 人机共训统一策略</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>长时程、单/双臂任务显著超 SOTA</li><li><strong>1 小时</strong>人手数据价值显著高于 1 小时机器人数据</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">EgoMimic（代码开源，egomimic.github.io）</td></tr>
</tbody>
</table>
### [ALOHA Unleashed: A Simple Recipe for Visuomotor Policies](https://arxiv.org/abs/2410.13126)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以大规模遥操作数据加扩散策略实现低成本双臂灵巧操作的可扩展配方。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford（Tony Z. Zhao、Chelsea Finn）+ Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>低成本 <strong>ALOHA 2</strong> 平台大规模遥操作数据收集 + 扩散策略 Transformer 的简单配方</li><li>预测 <strong>50 步动作块</strong></li><li>覆盖 5 个真实任务与 3 个仿真任务，共 <strong>26,000+ 演示</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>端到端策略首次自主完成<strong>系鞋带与挂衬衫</strong></li><li>5 项挑战性真实任务（挂衬衫、系鞋带、换手指、插齿轮、码厨房物品）及 3 项仿真双臂任务均显著优于 SOTA 基线</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">单任务扩散策略；26K 演示（挂衬衫 6K、系鞋带 6K 等）；开源（CoRL 2024）</td></tr>
</tbody>
</table>

### [HIL-SERL: Precise and Dexterous Robotic Manipulation via Human-in-the-Loop Reinforcement Learning](https://arxiv.org/abs/2410.21845)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">人类在环视觉 RL，1-2.5 小时训练出近完美的精密灵巧操作策略。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley BAIR（Jianlan Luo、Sergey Levine 等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>整合<strong>人类演示 + 在线纠错</strong>与高效 off-policy RL（RLPD 50/50 混合采样）</li><li>预训练视觉骨干 + <strong>二值奖励分类器</strong> + 底层阻抗控制器保证物理安全</li><li>系统级设计让真实世界 RL 训练仅需 <strong>1-2.5 小时</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>动态操作、精密装配、双臂协调等任务<strong>近完美成功率</strong></li><li>对比模仿学习基线平均成功率提升约 <strong>2 倍</strong>、执行速度快 <strong>1.8 倍</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">HIL-SERL（代码开源，项目页 hil-serl.github.io）</td></tr>
</tbody>
</table>
- **[CoRL 2024年6月](https://arxiv.org/abs/2406.09288)** ManiWAV: Learning Robot Manipulation from In-the-Wild Audio-Visual Data. 从真实世界视听数据学习机器人操纵.

- **[RSS 2024年3月](https://arxiv.org/abs/2403.07788)** DexCap: Scalable and Portable Mocap Data Collection System for Dexterous Manipulation. 可扩展、便携的灵巧操作动作捕捉系统.

- **[CoRL 2024年2月](https://arxiv.org/abs/2402.10329)** UMI: Universal Manipulation Interface: In-The-Wild Robot Teaching Without In-The-Wild Robots. 通用操纵接口，无需真实机器人即可教授.

- **[CoRL 2023年7月](https://arxiv.org/abs/2307.16677)** AnyTeleop: A General Vision-Based Teleoperation System for Robotic Manipulation. 通用视觉遥操作系统.

- **[RSS 2023年4月](https://arxiv.org/abs/2304.13705)** ACT: Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware. 低成本硬件的精细双手操作学习.

- **[RSS 2023年3月](https://arxiv.org/abs/2303.04137)** Diffusion Policy: Visuomotor Policy Learning via Action Diffusion. 基于扩散模型的机器人策略学习，在灵巧操作上表现优异.

- ★ **[ICLR 2023年2月](https://arxiv.org/abs/2302.12422)** MimicPlay: Long-Horizon Imitation Learning by Watching Human Play. 通过观看人类玩游戏的长时间模仿学习.

### [MimicPlay: Long-Horizon Imitation Learning by Watching Human Play](https://arxiv.org/abs/2302.12422)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用人类玩耍视频做分层长时程模仿学习：高层看手、低层学操作。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 2 月（CoRL 2023 Oral）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford、NVIDIA、Georgia Tech、UT Austin、Caltech</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>高层潜规划器预测未来 <strong>3D 人手轨迹</strong></li><li>低层视觉运动控制仅用少量遥操作数据</li><li>人机双数据源分层解耦</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>14 个</strong>真实长时程任务，成功率超 SOTA <strong>50%+</strong></li><li>未见任务泛化提升 <strong>40%+</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">MimicPlay（代码开源，mimic-play.github.io）</td></tr>
</tbody>
</table>
- **[CoRL 2022年11月](https://arxiv.org/abs/2211.07636)** RVT: Robotic View Transformer for 3D Object Manipulation. 3D物体操纵的机器人视图Transformer.

- **[CoRL 2022年9月](https://arxiv.org/abs/2209.05451)** Perceiver-Actor: A Multi-Task Transformer for Robotic Manipulation. 语言条件的多任务机器人操纵 Transformer，通常也以 PerAct 名称被引用.

- **[ICRA 2022年3月](https://arxiv.org/abs/2203.08745)** C2F-ARM: Coarse-to-Fine Imitation Learning for Robot Manipulation. 粗到细的模仿学习框架.

- **[CoRL 2022年2月](https://arxiv.org/abs/2202.02005)** BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning. 零样本任务泛化的模仿学习方法，通过语言指令条件化，使机器人能在测试时执行训练中未见过的任务.

- **[CoRL 2021年9月](https://arxiv.org/abs/2109.12098)** CLIPort: What and Where Pathways for Robotic Manipulation. 结合CLIP视觉理解与端到端模仿学习的机器人操纵方法，实现开放词汇的物体操纵和泛化.

- **[ICRA 2021年3月](https://arxiv.org/abs/2103.02245)** Form2Fit: Learning Shape Priors for Generalizable Manipulation. 学习形状先验的通用操作.

- ★ **[ICCV 2021年1月](https://arxiv.org/abs/2101.09555)** Where2Act: From Pixels to Actions for Articulated Objects. 从像素到动作的铰接物体操作.

- ★ **[CVPR 2018年12月](https://arxiv.org/abs/1812.02713)** PartNet: A Large-Scale Benchmark for Fine-Grained and Hierarchical Part-Level 3D Object Understanding. 细粒度部件级3D物体理解基准.
<a id="locomotion" name="locomotion"></a>
## Locomotion

### [SleepWalking: Privileged Representation Shaping for End-to-End Blind Locomotion in Legged Robots](https://arxiv.org/abs/2608.30883)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">训练时用特权物理重建塑造循环表征，端到端无感知腿足行走更稳且省算力。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">西北工业大学 + 上海交通大学 + 云幕智能制造</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>把部分可观测运动问题重新定义为<strong>“信息保持”问题</strong>：关键不是信息如何进入网络，而是内部状态能否留住它</li><li><strong>SWAQ 单阶段端到端框架</strong>：仅训练期用 next-step 特权重建（速度、无噪观测、地形高度）塑造循环历史表征，部署时只保留 history→action 通路</li><li>给出特权变量可恢复性与可达回报差的理论界</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>对齐训练设置下峰值平均地形等级较最强无外感基线 DWAQ 高 <strong>15.0%</strong></li><li>单控制步推理 MAC 少 <strong>44.4%</strong>；跨形态 sim2real（四足 Go1 与人形）一致通过楼梯地形</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">SWAQ 框架</td></tr>
</tbody>
</table>

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.14417)** Before the Body Moves: Learning Anticipatory Joint Intent for Language-Conditioned Humanoid Control (DAJI). 面向语言条件人形机器人控制的层次化框架，学习预期性联合意图表征，显式编码 upcoming 接触变化与平衡准备，实现稳定的全身动作生成。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.19734)** UniT: Toward a Unified Physical Language for Human-to-Humanoid Policy Learning and World Modeling. 统一人类到人形机器人的物理语言框架，通过视觉锚定的潜在动作分词器连接跨本体策略学习与世界建模.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.08509)** Visually-grounded Humanoid Agents. 一种面向人形智能体的视觉接地方法，关注具身智能能力。
### [MIRROR: Visual Motion Imitation via Real-time Retargeting and Teleoperation with Parallel Differential Inverse Kinematics](https://arxiv.org/abs/2603.23995)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GPU 并行差分逆运动学实现实时、安全的人形视觉运动模仿遥操作。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 3 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">California Institute of Technology（Caltech）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>GPU 并行 continuation-based 差分 IK</strong>：并行求解多个约束 QP，逃离关节极限/奇异点/碰撞边界的局部极小</li><li>自碰撞避免<strong>控制屏障函数（CBF）</strong> + Lyapunov 进展准则选择全局最优更新</li><li>视觉骨骼姿态估计流水线实现 <strong>单目相机实时上半身遥操作</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>在 THEMIS 人形机器人硬件上完成真实世界任务，保持实时性与安全性</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">MIRROR（代码开源，junhengl/mirror）</td></tr>
</tbody>
</table>
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.17927)** RoboForge: Physically Optimized Text-guided Whole-Body Locomotion for Humanoids. 物理优化的人形机器人全身运动生成框架，通过PP-Opt模块双向联合优化运动生成和物理执行，实现文本到物理可行运动的端到端转换.
- **[arXiv 2025年4月](https://arxiv.org/abs/2504.09532)** Humanoid-COA: Humanoid Agent via Embodied Chain-of-Action Reasoning with Multimodal Foundation Models for Zero-Shot Loco-Manipulation. 首个将基础模型推理与具身动作链机制相结合的人形智能体框架，用于零样本移动操纵.
- **[arXiv 2025年2月](https://arxiv.org/abs/2502.09247)** Humanoid-VLA: Vision-Language-Action Models for Humanoid Control. 专为人形机器人设计的VLA模型.
### [HumanPlus: Humanoid Shadowing and Imitation from Humans](https://arxiv.org/abs/2406.10454)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">人形"影子跟随"遥操作 + 自我中心视觉模仿学习的全栈系统。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 6 月（CoRL 2024 Best Paper Finalist）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford University（Chelsea Finn 团队）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Shadowing</strong>：用 40 小时人类运动数据（AMASS）RL 训练低级策略，仅凭 RGB 相机实时跟踪人体与手部</li><li>通过影子遥操作采集全身数据，再用<strong>自我中心视觉行为克隆</strong>训练技能策略</li><li>33-DoF 180cm 定制人形平台</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>穿鞋站立行走、仓库卸货、叠衣服、打字、打招呼等任务 <strong>60-100% 成功率</strong>（最多 40 个演示）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">HumanPlus（代码、数据集、硬件材料清单全开源，humanoid-ai.github.io）</td></tr>
</tbody>
</table>
### [OmniH2O: Universal and Dexterous Human-to-Humanoid Whole-Body Teleoperation and Learning](https://arxiv.org/abs/2406.08858)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以运动学位姿为通用接口的全身人形遥操作与自主学习系统。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CMU（Kris Kitani 团队）等</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>以<strong>运动学位姿为通用控制接口</strong>，支持 VR 头显、语音指令、RGB 相机多种人机交互方式</li><li><strong>RL sim-to-real</strong> 流水线：大规模人形运动数据重定向扩增 + 特权教师策略蒸馏</li><li>可接 GPT-4 等前沿模型实现完全自主</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>真实全身任务：运动、物体搬运与操作、人机交互等</li><li>发布首个<strong>人形全身控制数据集 OmniH2O-6</strong>（6 个日常任务）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">OmniH2O-6 数据集（omni.human2humanoid.com）</td></tr>
</tbody>
</table>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>

## Navigation & Spatial Intelligence

### [CrossTracer: Cross-Embodiment Navigation via VLA Model Reasoning and Trace Residuals Adapting](https://arxiv.org/abs/2608.06688)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VLA 语义推理 + 按本体残差适配的层级跨本体导航框架，图像平面路点为统一接口。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">鹏城实验室 + 南方科技大学</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>以<strong>归一化图像平面路点</strong>表示导航计划，形成语义推理与物理落地间的统一像素空间接口</li><li>两级结构：<strong>VL-Tracer</strong>（预训练 VLA 出初始轨迹）+ <strong>CE-Adapter</strong>（预测本体条件残差修正）</li><li><strong>CE-RRT*</strong> 把全景分割转为机器人条件代价图并自动生成训练标注，免人工标注</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>NaviTrace 基准总分 <strong>45.68</strong>，超过 Gemini-2.5-Pro（35.67）<strong>10.01 分、相对提升 28.1%</strong></li><li>轮式与足式机器人真机部署进一步提升导航成功率与执行效率</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CrossTracer 框架；评测于 NaviTrace 基准</td></tr>
</tbody>
</table>

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.09716)** RoboNav-Arm: Agentic AI Navigation and Obstacle Avoidance for Manipulator. 面向机械臂的智能体AI导航与避障。
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.05122)** Green for Go, Red for No: Visual Grounding for VLA Navigation Policies. 通过语义分割实现VLA导航策略的视觉接地，降低航点误差27-44%。
- **[arXiv 2026年7月](https://arxiv.org/abs/2607.03146)** Exp2VLA: Enabling VLA for Drone Navigation from Expert Demonstrations. 从专家演示中学习VLA无人机导航。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.26265)** NavIsaacLab: Generating Realistic Crowd for Human-aware Navigation. 利用物理仿真和轨迹扩散模型生成逼真人群用于训练人感知导航策略。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.12956)** SERF: Spatiotemporal Environment and Robot Feature Map for Mobile Manipulation. 提出时空环境与机器人特征地图用于长时程移动操作。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.10495)** Act on What You See: Safe Social Navigation in VLA Models. 在VLA模型中实现安全社交导航。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.06836)** Think Like a Pilot: Fine-Grained Long-Horizon UAV Navigation. 提出细粒度长时程无人机导航框架。
- ★ **[CVPR 2026年5月](https://arxiv.org/abs/2605.30342)** GAVIS: Uncertainty-driven 3D Gaussian Splatting Active Mapping via Anisotropic Visibility Field. 提出GAVIS框架，通过各向异性可见场实现3D高斯溅射的不确定性量化和主动建图，支持实时200FPS的不确定性量化。
- **[ICRA 2026年5月](https://arxiv.org/abs/2605.29773)** Energy-Aware NECO for Single-Pass Pixel-wise Out-of-Distribution Detection in Semantic Segmentation. 提出能量感知的NECO方法，实现语义分割中的高效像素级分布外检测，提升机器人感知系统的鲁棒性。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.27952)** Con-DSO: Learning Short-Horizon Consistency Priors for RGB-D Direct Sparse Odometry. 提出一致性感知的RGB-D直接稀疏里程计框架，通过预测光度和深度几何一致性不确定性，在多个基准上实现20%-80%的轨迹误差降低。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.27178)** Domain Adaptation for Robot Vision. 研究机器人视觉中的域适应问题，提出改进的对抗学习和自监督方法，提升模型在新环境中的泛化能力。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.26949)** DinoComplete: 3D Shape Completion with Distilled Semantic Priors and State Space Models. 提出DinoComplete形状补全框架，利用DINO特征蒸馏的体素对齐语义先验，结合多尺度体素Mamba模块实现高效长程推理。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.25832)** Visual-Inertial Odometry. 研究视觉惯性里程计技术，融合相机和IMU数据实现鲁棒的机器人定位，在挑战性环境下保持高精度。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13775)** RoboEvolve: Co-Evolving Planner-Simulator for Robotic Manipulation with Limited Data. VLM规划器和VGM模拟器耦合为共同进化循环，认知启发双阶段机制：白天探索+夜间巩固，仅500个无标签种子超越全监督基线(50倍数据减少)。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12735)** Toward a Blueprint for Generalizable Robot Autonomy (Unified Autonomy Stack). 开源统一自主栈，融合LiDAR/雷达/视觉/惯性感知，实现因子图定位、语义场景理解和多层安全导航，支持多种空中和地面机器人形态。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12625)** Driving Intents Amplify Planning-Oriented Reinforcement Learning (DIAL). 通过意图条件CFG扩展采样分布打破模式坍塌，结合多意图GRPO进行偏好RL，在WOD-E2E上RFS达9.14，首次超越人类演示和先前最佳。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12624)** MindVLA-U1: VLA Beats VA with Unified Streaming Architecture for Autonomous Driving. 首个统一流式VLA自动驾驶架构，单次前向传播同时生成语言token和流匹配轨迹，在WOD-E2E上首次超越人类驾驶员(RFS 8.20 vs 8.13)。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12622)** Action Emergence from Streaming Intent. 提出流式意图机制实现端到端自动驾驶中的动作涌现，VLA模型SI通过四步思维链解码意图token，驱动CFG引导流匹配动作头，首次在VLA中实现意图可控性。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12620)** VeGAS: Verifier-Guided Action Selection For Embodied Agents. 测试时框架，采样候选动作并用生成式验证器识别最可靠选择，LLM驱动的数据合成构建失败案例课程，在Habitat/ALFRED上最高提升36%相对性能。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.09387)** NEXUS: Continual Learning of Symbolic Constraints for Safe and Robust Embodied Planning. 面向安全鲁棒具身规划的符号约束持续学习框架。
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24707)** Passage-Aware Structural Mapping for RGB-D Visual SLAM. 一种用于 RGB-D Visual SLAM 的导航与空间建图感知方法。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.22851)** EgoDyn-Bench: Evaluating Ego-Motion Understanding in Vision-Centric Foundation Models for Autonomous Driving. 提出 EgoDyn-Bench：一个用于评估自动驾驶中视觉中心基础模型自我运动理解能力的统一基准。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.22339)** flow4dgs-slam: optical flow-guided 4d gaussian splatting slam. 一种用于导航与建图的感知方法，通过光流引导的 4D Gaussian Splatting 实现更高效且更鲁棒的 SLAM。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21894)** Task-Driven Co-Design of Heterogeneous Multi-Robot Systems. 面向异构多机器人系统的任务驱动协同设计框架，统一考虑机器人设计、编队组成、规划与执行之间的耦合权衡.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21707)** Effects of Swarm Size Variability on Operator Workload. 研究群体机器人规模动态变化对人类操作者负荷与表现的影响，为真实部署中的人群协同与任务分配提供依据.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21693)** SLAM as a Stochastic Control Problem with Partial Information: Optimal Solutions and Rigorous Approximations. 将主动SLAM重写为部分信息下的随机控制问题，并给出带探索代价的统一建模与严格近似分析.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21640)** Task-specific Subnetwork Discovery in Reinforcement Learning for Autonomous Underwater Navigation. 面向自主水下导航的多任务强化学习可解释框架，通过任务相关子网络发现提升策略适应性与内部决策可读性.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21453)** Instance-level Visual Active Tracking with Occlusion-Aware Planning. 面向遮挡场景的实例级主动视觉跟踪方法，把目标跟踪与遮挡感知规划结合起来提升持续跟踪稳定性。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21363)** A Deployable Embodied Vision-Language Navigation System with Hierarchical Cognition and Context-Aware Exploration. 面向真实部署的VLN系统，通过分层认知与上下文感知探索在算力、时延和导航性能之间取得平衡.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21138)** Navigating the Clutter: Waypoint-Based Bi-Level Planning for Multi-Robot Systems. 面向拥挤环境多机器人控制的双层规划框架，通过路点表示和可行性反馈联合优化任务规划与运动规划。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20305)** AdaTracker: Learning Adaptive In-Context Policy for Cross-Embodiment Active Visual Tracking. 面向跨本体主动视觉跟踪的自适应in-context策略学习框架，尝试用统一模型适配不同机器人形态下的物理约束与运动动态.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.19536)** LiveVLN: Breaking the Stop-and-Go Loop in Vision-Language Navigation. 针对视觉语言导航中的停走式阻塞决策循环，引入更连续的感知-推理-执行机制，提升真实环境中的运动流畅性.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.08232)** HiRO-Nav: Hybrid ReasOning Enables Efficient Embodied Navigation. 首个基于动作熵自适应决定是否在每个步骤进行思考的导航智能体，通过混合监督微调冷启动和在线强化学习，仅在熵高的关键动作上激活显式推理.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.07973)** UrbanNav Benchmark: How Far Are Large Multimodal Models from Human-Level Spatial Action. 首个针对城市场景目标导向导航的具身空间动作基准，包含5037个高质量样本，强调3D垂直行动和丰富城市场景语义信息.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.07957)** WorldMAP: Bootstrapping Vision-Language Navigation Trajectory Prediction with Generative World Models. 教师-学生框架，世界模型驱动的教师从生成视频构建语义空间记忆，通过显式规划产生轨迹伪标签，轻量学生直接训练预测导航轨迹.
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.28032)** CARLA-Air: Fly Drones Inside a CARLA World -- A Unified Infrastructure for Air-Ground Embodied Intelligence. 在CARLA中统一空地机器人仿真，支持无人机与地面智能体的协同训练、感知和评测。
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.16947)** EmergeNav: Structured Embodied Inference for Zero-Shot Vision-and-Language Navigation in Continuous Environments. 结构化具身推理的零样本VLN-CE框架，无需训练实现37%的成功率.
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.16413)** OpenDriveVLA: Towards End-to-end Autonomous Driving with Large Vision Language Action Model. 面向自动驾驶的端到端VLA模型，将视觉-语言-动作统一建模，实现驾驶场景的感知-决策-控制一体化.
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.14669)** RenderMem: Rendering as Spatial Memory Retrieval. 将渲染作为3D世界表示与空间推理之间接口的空间记忆框架，维护3D场景表示，通过从查询隐含的视点渲染场景来生成查询条件化的视觉证据.
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.09163)** SPAN-Nav: Generalized Spatial Awareness for Versatile Vision-Language Navigation. 端到端基础模型，通过占用预测任务从大规模室内外场景中提取空间先验，采用紧凑的单token表示封装粗粒度导航线索，利用CoT机制显式注入空间线索到动作推理.
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.06914)** SysNav: Multi-Level Systematic Cooperation Enables Real-World, Cross-Embodiment Object Navigation. 三层系统级对象导航框架，解耦语义推理、导航规划和运动控制，部署于轮式机器人、Unitree Go2四足和Unitree G1人形三种具身平台，190次真实实验验证.

- **[ICRA 2026年2月](https://arxiv.org/abs/2510.08173)** NavSpace: Spatial Intelligence Navigation Benchmark. 首个空间智能导航评测基准，涵盖六大类超1200条动态空间指令，将评估从静态感知推向持续推理.
- **[arXiv 2025年9月](https://arxiv.org/abs/2509.14000)** JaGuard: Position Error Correction of GNSS Jamming with Deep Temporal Graphs. 将GNSS干扰校正建模为动态图回归问题，利用深度时序图网络融合卫星几何与短时动态，修正固定接收机在干扰条件下的位置漂移。
- **[arXiv 2025年6月](https://arxiv.org/abs/2506.15518)** Real-Time Initialization of Unknown Anchors for UWB-aided Navigation. 面向UWB辅助导航的未知锚点实时初始化方法，在无需先验锚点布局的情况下提升定位可用性。
- **[arXiv 2025年5月](https://arxiv.org/abs/2505.08912)** CoW: Chain-of-Thought Walking for Embodied Navigation. 具身导航的思维链行走方法.
- **[arXiv 2025年4月](https://arxiv.org/abs/2504.08962)** TrackVLA: Embodied Visual Tracking with Vision-Language-Action Models. 具身视觉跟踪的VLA模型.
- **[arXiv 2025年1月](https://arxiv.org/abs/2501.07399)** Efficiently Closing Loops in LiDAR-Based SLAM Using Point Cloud Density Maps. 利用点云密度图高效完成激光SLAM回环检测与验证，在保证精度的同时降低计算开销。

- **[arXiv 2024年7月](https://arxiv.org/abs/2407.00848)** EgoExo++: Integrating On-demand Exocentric Visuals with 2.5D Ground Surface Estimation for Interactive Teleoperation of Underwater ROVs. 用于水下ROV交互遥操作的自我中心与外部视角融合框架，结合2.5D地面估计提升复杂水下环境感知与操控安全性。
- **[ICRA 2024年2月](https://arxiv.org/abs/2402.09466)** VLFM: Vision-Language Frontier Maps for Zero-Shot Semantic Navigation. 零样本语义导航的视觉语言边界地图.
- ★ **[CVPR 2024年1月](https://arxiv.org/abs/2401.04567)** EgoVLPv2: Egocentric Video-Language Pre-training. 第一人称视频-语言预训练.
- **[arXiv 2023年8月](https://arxiv.org/abs/2308.00513)** UVIO: An UWB-Aided Visual-Inertial Odometry Framework with Bias-Compensated Anchors Initialization. UWB辅助的视觉惯性里程计框架，通过偏置补偿的锚点初始化提升定位收敛速度与稳定性。
- ★ **[AAAI 2023年5月](https://arxiv.org/abs/2305.16986)** NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models. 大语言模型在视觉-语言导航中的显式推理.
- **[RSS 2022年10月](https://arxiv.org/abs/2210.05663)** CLIP-Fields: Weakly Supervised Semantic Fields for Robotic Memory. 弱监督语义场用于机器人记忆.
- ★ **[CVPR 2022年3月](https://arxiv.org/abs/2203.06789)** PONI: Potential Functions for ObjectGoal Navigation with Interaction-free Learning. 无交互学习的物体目标导航势函数.
- ★ **[ICCV 2021年4月](https://arxiv.org/abs/2104.03456)** SOON: Scenario Oriented Object Navigation. 场景导向的物体导航.
- **[ICRA 2021年3月](https://arxiv.org/abs/2103.07086)** ViNG: Learning Open-World Navigation with Visual Goal Representations. 视觉目标表示的开放世界导航.
- **[CoRL 2020年10月](https://arxiv.org/abs/2010.15044)** Semantic MapNet: Building Allocentric Semantic Maps and Representations. 异中心语义地图构建.
- ★ **[ECCV 2020年7月](https://arxiv.org/abs/2007.00643)** ObjectNav: Object Goal Navigation using Goal-Oriented Semantic Exploration. 目标驱动的语义探索导航.
- ★ **[CVPR 2020年6月](https://arxiv.org/abs/2006.13979)** VLN-BERT: A Recurrent BERT for Vision-and-Language Navigation. 视觉-语言导航的循环BERT模型.
- ★ **[ICLR 2020年6月](https://arxiv.org/abs/2006.04884)** Active Neural SLAM. 主动神经SLAM框架.
- ★ **[ICML 2019年6月](https://arxiv.org/abs/1906.09518)** Neural SLAM: Learning to Explore with External Memory. 神经SLAM，学习用外部记忆进行探索.
- ★ **[NeurIPS 2018年4月](https://arxiv.org/abs/1804.00168)** PointNav: Learning to Navigate in Cities Without a Map. 无地图的城市导航学习.
- ★ **[CVPR 2017年2月](https://arxiv.org/abs/1702.04405)** ScanNet: Richly-Annotated 3D Reconstructions of Indoor Scenes. 富标注的室内场景 3D 重建数据集.
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>

## Simulators & Sim2Real

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.15065)** DriftWorld: Fast World Modeling through Drifting. 通过漂移实现快速世界建模。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.06699)** RoboSnap: One-Shot Real-to-Sim Scene Generation. 将单张RGB图像转换为物理稳定的模拟场景。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.02205)** Actuator Reality Shaping for Zero-Shot Sim-to-Real Robot Learning. 提出执行器现实塑造范式，匹配物理执行器与仿真理想参考动力学。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.01410)** BIFROST: Sim2Real Transfer via Invariant Feature Representation. 通过跨域双模拟目标学习共享历史编码器实现零样本Sim2Real迁移。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.00678)** ABot-M0.5: Unified Mobility-and-Manipulation World Action Model. 统一移动与操作的世作动作模型。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.25939)** DeformGen: Dynamics-Based Topology Augmentation for Deformable Manipulation. 通过局部物理扰动和动力学前向模拟生成拓扑一致的可变形状态。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.20389)** CoLI: Continuum Robot Learning via Monolithic 3D Printing. 提出基于多材料3D打印和同构遥操作的连续体机器人平台。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.17030)** Qwen-RobotWorld: Unifying Embodied World Modeling through Language-Conditioned Video Generation. 通义提出通过语言条件视频生成统一具身世界建模。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.16470)** Decoupled Object-Centric Video Understanding for Manipulation Commands. 解耦对象中心视频理解用于生成机器人操作指令。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.11372)** HiPi: Reproducible High-Fidelity Piezoresistive Sensors. 可复现的高保真压阻传感器用于机器人操作。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.11184)** TacForeSight: Force-Guided Tactile World Model for Contact-Rich Manipulation. 力引导的触觉世界模型用于丰富接触操作。

- ★ **[ICML 2026年5月](https://arxiv.org/abs/2605.29032)** Theoretical Foundations and Effective Algorithms for Policy-Aware Simulator Learning. 提出策略感知模拟器学习方法，将模拟器学习目标从预测准确性转向策略鲁棒性，通过零和博弈框架解决模拟器利用问题。

- **[GECCO 2026年5月](https://arxiv.org/abs/2605.28812)** Beyond Binary: Sim-to-Real Dexterous Manipulation with Physics-Grounded Contact Representation. 提出基于压力中心的触觉表示方法，保留密集接触信息的同时保持sim-to-real迁移的鲁棒性，实现零样本真实机器人迁移。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.28312)** Sim-to-Real Transfer for Robotic Manipulation. 研究机器人操作中的sim-to-real迁移问题，提出改进的域随机化和适应技术，提升仿真到真实环境的策略迁移效果。

- **[Neutrosophic Sets and Systems 2026年5月](https://arxiv.org/abs/2605.26114)** MobileGym: A Verifiable and Highly Parallel Simulation Platform for Mobile GUI Agent Research. 提出MobileGym平台，支持可验证的结果信号和大规模并行在线强化学习，在Sim-to-Real案例中实现95.1%的训练增益保持。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.14625)** Digital Twin Synchronization Over Mobile Embodied AI Network With Agentic Intelligence. 面向移动具身AI网络的数字孪生同步框架，通过智能体智能实现高保真虚拟表征与低信息年龄。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.13315)** Embodied Neurocomputation: A Framework for Interfacing Biological Neural Cultures with Scaled Task-Driven Validation. 面向生物神经培养与任务驱动验证的具身神经计算框架。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12654)** COSMIC: Concurrent Optimization of Structure, Material, and Integrated Control for robotic systems. 梯度共设计框架同时优化拓扑、材料分布和控制策略，嵌入混合拓扑变量到连续设计空间，在可微仿真器中集成神经网络控制器，发现超越分离设计的多样化运动策略。

- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12038)** OmniHumanoid: Streaming Cross-Embodiment Video Generation with Paired-Free Adaptation. 流式跨本体视频生成框架，无需配对数据即可适配不同机器人形态，支持连续视频生成。

- **[arXiv 2026年4月](https://arxiv.org/abs/2604.25459)** GS-Playground: A High-Throughput Photorealistic Simulator for Vision-Informed Robot Learning. 一个面向机器人操作与视觉知情学习的高吞吐量、照片级真实感仿真器。

### [RoboCasa365: A Large-Scale Simulation Framework for Training and Benchmarking Generalist Robots](https://arxiv.org/abs/2603.04356)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">365 任务、2500 场景的厨房移动操作大规模仿真基准。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 3 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">University of Texas at Austin、NVIDIA Research</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>基于 RoboCasa 平台扩展至 <strong>365 个日常任务 × 2500 厨房场景</strong></li><li>含 <strong>600 小时人类演示 + 1600 小时合成演示</strong>（共 2200+ 小时交互数据）</li><li>系统支持多任务学习、机器人基础模型训练与终身学习评测</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>系统分析任务多样性、数据规模、环境变化对泛化的影响</li><li>用 SOTA 方法在多任务/基础模型/终身学习设定下评测并给出新洞察</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboCasa365 仿真平台与数据</td></tr>
</tbody>
</table>
- **[arXiv 2026年3月](https://arxiv.org/abs/2603.22039)** RAFL: Generalizable Sim-to-Real of Soft Robots with Residual Acceleration Field Learning. 残差加速度场学习框架，用可迁移的单元级校正动力学场增强基础模拟器，基于共享局部特征运行，与全局网格拓扑和离散化无关.

- **[arXiv 2025年11月](https://arxiv.org/abs/2511.02345)** Sim2Real 2.0: A Survey and Benchmark. Sim2Real综述与基准.

- **[arXiv 2025年10月](https://arxiv.org/abs/2510.09876)** UniSim: A Universal Simulator for Robotics and Embodied AI. 机器人具身AI通用仿真器.

- **[OpenReview 2025年10月](https://openreview.net/forum?id=P7tg7VowVX)** RoboSimGS: High-Fidelity Simulated Data Generation for Real-World Zero-Shot Transfer. Real2Sim2Real框架，将多视角真实图像转换为可扩展、高保真、物理交互的仿真环境，采用3DGS捕捉照片级外观、网格基元确保精确物理仿真，MLLM自动化创建物理合理关节资产.

- **[arXiv 2025年9月](https://arxiv.org/abs/2509.24948)** World-Env: Leveraging World Model as a Virtual Environment for VLA Post-Training. 利用世界模型构建低成本虚拟环境，为VLA后训练提供连续奖励与动作终止信号，在少样本机器人操作任务中替代高成本真实交互。

- **[ICRA 2025年9月](https://arxiv.org/abs/2509.14687)** RealMirror: Vision-Language-Action Platform for Embodied AI. 开源端到端仿真基座，提供高视觉保真度和物理交互真实性的仿真平台.

- **[arXiv 2025年9月](https://arxiv.org/abs/2509.12372)** Sym2Real: Symbolic Dynamics with Residual Learning for Data-Efficient Adaptive Control. 数据驱动框架，结合符号动力学与残差学习，仅用约10条轨迹就能在现实世界中实现鲁棒控制.

- **[arXiv 2025年6月](https://arxiv.org/abs/2506.10600)** EmbodiedGen: Generative 3D Worlds for Embodied AI. 生成式3D世界用于具身AI.

### [V-JEPA 2: Self-Supervised Video Models for Understanding, Prediction and Planning](https://arxiv.org/abs/2506.09985)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">纯自监督潜空间视频世界模型，兼具理解、预测与零样本规划。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 6 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Meta FAIR（Yann LeCun 等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>JEPA 架构</strong>：在潜空间预测未来而非重建像素</li><li>ViT-g <strong>1B 参数</strong>编码器 + 3D-RoPE，预训练于 100 万小时以上互联网视频</li><li>后接 300M 参数动作条件世界模型 V-JEPA 2-AC</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Something-Something v2 运动理解 <strong>77.3 top-1</strong>；EK-100 动作预测 39.7 R@5（相对提升 44%）</li><li>V-JEPA 2-AC 以 <62 小时 Droid 数据训练，零样本在 Franka 双臂上完成抓取放置</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 V-JEPA 2 / V-JEPA 2-AC；训练数据互联网视频 + Droid 数据集；模型与权重开源</td></tr>
</tbody>
</table>

### [Cosmos: World Foundation Model Platform for Physical AI](https://arxiv.org/abs/2501.03575)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA 面向 Physical AI 的世界基础模型开放平台。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2025 年 1 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>含视频整理管线、预训练 WFM、后训练示例与<strong>视频分词器</strong></li><li>初始 Cosmos-Predict1：自回归 5B + 扩散 7B 两种模型</li><li>分词器最高 <strong>2048x 压缩</strong>（空间 8/16x、时间 4/8x）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>训练数据约 <strong>20M 小时视频</strong>（约 45PB、9000 万亿 tokens）</li><li>分词器比同期 SOTA 快约 <strong>12x</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Cosmos-Predict1/2.5、Transfer2.5、Reason；开源（NVIDIA Open Model License）</td></tr>
</tbody>
</table>

### [Genie 2: A Large-Scale Foundation World Model](https://deepmind.google/discover/blog/genie-2-a-large-scale-foundation-world-model/)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">单图生成可玩 3D 世界的大规模基础世界模型。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 12 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind（Generalist Agents 团队）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>自回归潜在扩散世界模型</strong>，训练于大规模视频数据集</li><li>以单张图像为提示生成可玩 3D 世界</li><li>涌现重力 / 水 / 烟等物理、复杂角色动画、物体交互与长时程记忆</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>一致世界生成最长约 <strong>1 分钟</strong>（示例多为 10-20 秒）</li><li>支持第一/第三人称、等距等多视角；蒸馏版可实时交互</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Genie 2；提示图由 Imagen 3 生成；未开源</td></tr>
</tbody>
</table>

- **[CoRL 2024年6月](https://arxiv.org/abs/2406.02523)** RoboCasa: Large-Scale Simulation of Everyday Tasks for Generalist Robots. 大规模日常任务仿真.

### [Genesis: A Generative and Universal Physics Engine](https://arxiv.org/abs/2406.19481)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">开源生成式物理引擎，超实时 43 万倍模拟，支持语言生成 4D 世界。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 6 月（物理引擎 2024 年 12 月开源）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CMU 牵头 20+ 高校（MIT、Stanford、清华、北大等）与 NVIDIA、太极图形联合</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>从底层重建的<strong>通用物理引擎</strong>，统一多类物理求解器</li><li>原生 Python + <strong>Taichi GPU 加速</strong>，支持可微模拟与可微触觉</li><li>VLM 生成智能体可将自然语言转化为 4D 世界、策略、轨迹与视频</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Franka 操作场景达 <strong>4300 万 FPS</strong>（约实时 43 万倍）</li><li>比 Isaac Gym / MJX 快约 10-80 倍；单张 RTX 4090 上 26 秒训出可迁移真实世界的运动策略</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Genesis 物理引擎与模拟平台开源；生成式框架逐步开放</td></tr>
</tbody>
</table>

### [Genie: Generative Interactive Environments](https://arxiv.org/abs/2402.15391)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">110 亿参数无监督世界模型，单图生成可玩 2D 世界。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 2 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind（联合 UBC）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>ST-transformer 视频分词器 + 自回归动力学模型 + 潜在动作模型</li><li><strong>无需动作标签</strong>，完全无监督训练于互联网视频</li><li>单张图像 / 草图 / 照片生成可控 2D 交互世界</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>11B 参数</strong>，训练于约 3 万小时、6800 万段 2D 游戏视频</li><li>逐帧生成可玩世界（单次 16 帧窗口）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 Genie（11B）；训练数据互联网 2D 游戏视频；未开源</td></tr>
</tbody>
</table>

### [RoboGen: Towards Unleashing Infinite Data for Automated Robot Learning via Generative Simulation](https://arxiv.org/abs/2311.01455)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">生成式仿真自动产出技能训练数据：propose-generate-learn 自引导闭环。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 11 月（ICML 2024）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CMU、清华大学 IIIS、MIT、UMass</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>propose-generate-learn</strong> 闭环：LLM 提议任务 → 自动生成场景资产 → 自动生成奖励/监督 → 学习</li><li>基于 Genesis 引擎构建</li><li>覆盖刚体、铰接、可变形物体与足式运动</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>可无限产出多样化技能演示与训练数据</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboGen（代码开源，robogen-ai.github.io）</td></tr>
</tbody>
</table>
### [UniSim: Learning Interactive Real-World Simulators](https://arxiv.org/abs/2310.06114)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">编排多模态真实数据学习交互式世界模拟器，模拟训练零样本部署真机。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley + Google DeepMind + MIT</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>以<strong>视频扩散模型</strong>为核心</li><li>编排多轴互补真实数据：图像对象、机器人动作、导航运动、语言</li><li>统一支持高层语言指令与低层控制，推理类似 POMDP 滚动</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>获 <strong>ICLR 2024 杰出论文奖</strong></li><li>纯模拟训练的 VLM 规划器与 RL 策略零样本迁移到真实机器人</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">训练数据组合 Ego4D、Something-Something、Bridge、RH20T、RT-1 等；未开源</td></tr>
</tbody>
</table>

### [TD-MPC2: Scalable, Robust World Models for Continuous Control](https://arxiv.org/abs/2310.16828)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">单一超参数横扫 104 项在线 RL 任务的可扩展鲁棒世界模型算法。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UCSD + CMU（Nicklas Hansen、Hao Su、Xiaolong Wang）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>基于 <strong>TD-MPC 的改进</strong>：在隐式（无解码器）世界模型的潜在空间做局部轨迹优化</li><li><strong>单一超参数</strong>跨 104 个任务稳定</li><li>单个 <strong>317M 参数</strong>智能体同时执行 80 个任务（多域、多本体、多动作空间）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>104 项在线 RL 任务（4 大域）显著超越基线</li><li>智能体能力随模型与数据规模<strong>可扩展</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 TD-MPC2（最大 317M，开源）；评测域 DMControl、Meta-World、Manipulation、Humanoid（ICLR 2024）</td></tr>
</tbody>
</table>

- **[ICRA 2023年3月](https://arxiv.org/abs/2303.15482)** OmniGibson: A Modular Simulation Environment for Embodied AI. 模块化具身AI仿真环境.

### [DreamerV3: Mastering Diverse Skills through World Models](https://arxiv.org/abs/2301.04104)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">固定超参数横扫 150+ 任务的通用世界模型强化学习，首次从零挖到 Minecraft 钻石。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2023 年 1 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind + 多伦多大学（Danijar Hafner 等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>RSSM 离散潜状态世界模型</strong></li><li>symlog 变换、two-hot 奖励回归、KL balancing 等鲁棒性技术，单一超参数通用</li><li>actor-critic 完全在世界模型想象轨迹中训练</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>固定超参数在 <strong>150+ 任务</strong>上超越专用算法；Atari 100K 均值 2.01x 人类水平</li><li>首个从零（无人类数据）在 100M 步内于 Minecraft 收集钻石的算法</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型开源（danijar/dreamerv3，MIT）；评测域 Atari、DMControl、DMLab、Minecraft 等</td></tr>
</tbody>
</table>

- ★ **[NeurIPS 2021年8月](https://arxiv.org/abs/2108.10470)** Isaac Gym: High Performance GPU-Based Physics Simulation for Robot Learning. 高性能GPU物理仿真平台.

### [DayDreamer: World Models for Physical Robot Learning](https://arxiv.org/abs/2206.14176)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">将 Dreamer 世界模型直接用于真实机器人在线强化学习，摆脱模拟器。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2022 年 6 月（CoRL 2022）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley（Danijar Hafner、Sergey Levine、Pieter Abbeel 等）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>RSSM 世界模型</strong> + 想象空间中 actor-critic 训练</li><li><strong>4 种机器人</strong>（四足/双臂/轮式）统一超参</li><li>开源全部基础设施</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>四足从零学会翻滚-站立-行走仅 <strong>1 小时</strong></li><li>被推后 <strong>10 分钟</strong>内适应扰动</li><li>机械臂视觉抓放接近人类水平</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">DayDreamer（代码开源，danijar.com/daydreamer）</td></tr>
</tbody>
</table>
- **[IROS 2020年12月](https://arxiv.org/abs/2012.02924)** iGibson 1.0: A Simulation Environment for Interactive Tasks in Large Realistic Scenes. 大型真实场景交互任务仿真环境.

- **[CoRL 2020年9月](https://arxiv.org/abs/2009.12293)** robosuite: A Modular Simulation Framework and Benchmark for Robot Learning. 面向机器人学习的模块化仿真框架与基准套件.

- ★ **[NeurIPS 2020年7月](https://arxiv.org/abs/2007.04954)** ThreeDWorld: A Platform for Interactive Multi-Modal Physical Simulation. 交互式多模态物理仿真平台.

- ★ **[CVPR 2020年3月](https://arxiv.org/abs/2003.08515)** SAPIEN: A SimulAted Part-based Interactive ENvironment. 基于部件的交互式仿真环境.

### [Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model](https://arxiv.org/abs/1911.08265)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用学习到的世界模型做规划，无环境动力学知识达到超人水平。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2019 年 11 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>MuZero 算法</strong>：树搜索 + 学习模型结合</li><li>学习模型迭代预测<strong>奖励、策略与价值</strong>三个规划关键量</li><li>无需环境动力学 / 游戏规则知识</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>57 个 Atari 游戏达新 SOTA</li><li>在围棋、国际象棋、将棋上<strong>匹敌 AlphaZero</strong>（AlphaZero 需游戏规则，MuZero 不需要）</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">模型 MuZero（未开源）；评测域 Atari、Go、Chess、Shogi（Nature 2020）</td></tr>
</tbody>
</table>

- **[CoRL 2019年10月](https://arxiv.org/abs/1910.10897)** Meta-World: A Benchmark and Evaluation for Multi-Task and Meta Reinforcement Learning. 多任务元强化学习基准.

- ★ **[ICCV 2019年4月](https://arxiv.org/abs/1904.01201)** Habitat: A Platform for Embodied AI Research. 具身AI研究平台，包含仿真器和数据集.

- **[ICRA 2019年3月](https://arxiv.org/abs/1903.00742)** PyBullet: A Fast Physics Simulation for Robotics. 快速物理仿真库.

### [World Models](https://arxiv.org/abs/1803.10122)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VAE + MDN-RNN + 控制器三段式世界模型，开创在"梦境"中训练智能体的范式。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2018 年 3 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google Brain（David Ha）+ NNAISENSE / IDSIA（Jürgen Schmidhuber）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>三段式：<strong>VAE 视觉压缩 + MDN-RNN 时序记忆 + 控制器</strong></li><li>V/M 模块无监督训练</li><li>控制器可完全在世界模型"梦境"中训练再迁移回真实环境</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CarRacing-v0 平均 <strong>906±21 分</strong>，首个解决该环境的方法</li><li>ViZDoom 纯梦境训练策略迁移回真实环境达 1092±556 生存步</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">代码开源（worldmodels）；评测环境 OpenAI Gym（CarRacing、ViZDoom）</td></tr>
</tbody>
</table>

- **[arXiv 2018年1月](https://arxiv.org/abs/1801.00690)** DMControl: DeepMind Control Suite. 连续控制任务基准.

- ★ **[CVPR 2017年12月](https://arxiv.org/abs/1712.05474)** AI2-THOR: An Interactive 3D Environment for Visual AI. 交互式3D环境，经典仿真平台.

- **[IROS 2012年10月](https://homes.cs.washington.edu/~todorov/papers/TodorovIROS12.pdf)** MuJoCo: A Physics Engine for Model-Based Control. 模型控制物理引擎，经典工作.

<a id="datasets" name="datasets"></a>
## Datasets

### [RynnWorld-Teleop: An Action-Conditioned World Model for Digital Teleoperation](https://arxiv.org/abs/2607.06558)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">用生成式世界模型替代真实机器人，实现"数字遥操作"数据引擎。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 7 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Rynn（睿恩新）团队</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>数字遥操作</strong>：操作者手部姿态流驱动世界模型，从单张参考图合成高保真自我中心视频，解耦数据采集与物理硬件</li><li>深度感知骨骼条件 + 视频扩散 Transformer 渐进式人机训练 + <strong>流式自回归蒸馏</strong></li><li>单张 H100 上 <strong>40+ FPS</strong> 实时交互生成</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>仅用生成数据训练的策略实现<strong>零样本 Sim2Real</strong> 迁移</li><li>用数字遥操作数据增强真实数据集可稳定提升成功率</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RynnWorld-Teleop 数据引擎</td></tr>
</tbody>
</table>
- **[arXiv 2026年7月](https://arxiv.org/abs/2607.04367)** A Perception-Manipulation Robotics System for Food Cutting. 面向食物切割的感知-操作机器人系统。

- **[arXiv 2026年6月](https://arxiv.org/abs/2606.22142)** RoboLineage: Agent-Native Data Lifecycle Governance Across Robot Policy Iterations. 将数据收集训练等步骤表示为类型化谱系工件实现生命周期管理。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.20990)** Duet: Dual-Robot Understanding via Efficient Teaching. 利用VR遥操作和人类协作先验实现双机器人高效学习。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.17385)** EgoInfinity: Web-Scale 4D Hand-Object Interaction Data Engine. 从互联网视频自动生成4D手物交互数据，实现跨形态动作重定向。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.14665)** EgoGuide: Egocentric Guidance for Efficient Robot-Free Demo Collection. 通过同步腕部和头部视角及在线视觉-几何质量引导提升数据效率。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.29462)** CFMME: A Comprehensive Chinese Financial Multimodal Evaluation Dataset. 提出CFMME中文金融多模态评估基准，包含6052个实例覆盖八种金融图像模态，为具身智能金融应用提供评估工具。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21017)** Open-H-Embodiment: A Large-Scale Dataset for Enabling Foundation Models in Medical Robotics. 面向医疗机器人基础模型的大规模具身数据集，缓解医疗场景下数据小规模、单本体和难共享的问题.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20444)** VTouch++: A Multimodal Dataset with Vision-Based Tactile Enhancement for Bimanual Manipulation. 融合视觉增强触觉信号的多模态双手操作数据集，为接触密集型双臂操控提供更高保真的物理交互监督.

- **[arXiv 2026年2月](https://arxiv.org/abs/2602.01693)** Manip-Cognition-1.6M: GSR: Learning Structured Reasoning for Embodied Manipulation. 大规模数据集，联合监督世界理解、行动规划和目标解释，用于结构化推理学习.
- **[arXiv 2025年10月](https://arxiv.org/abs/2510.11027)** Vlaser-6M: Vlaser: Vision-Language-Action Model with Synergistic Embodied Reasoning. 高质量具身推理数据集，支持空间推理、具身接地、具身QA和任务规划四个维度的评测.
- **[arXiv 2025年8月](https://arxiv.org/abs/2508.12378)** Embodied-Points-200K: Embodied-R1: Reinforced Embodied Reasoning for General Robotic Manipulation. 通过结合具身和通用视觉推理数据集构建的大规模数据集，支持关键的具身指向能力.

### [DexMimicGen: Automated Data Generation for Bimanual Dexterous Manipulation via Imitation Learning](https://arxiv.org/abs/2410.24185)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">从少量人类演示自动生成大规模双臂灵巧操作仿真数据。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2024 年 10 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA、Stanford University</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>从 <strong>60 个源人类演示</strong>自动合成 <strong>21K 条演示</strong>，覆盖双臂灵巧操作多种协调模式</li><li>提供真实到仿真再到真实（real-to-sim-to-real）流水线</li><li>针对灵巧手人形机器人的双臂数据生成</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>在真实世界人形机器人罐子分拣任务上验证可行性</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">DexMimicGen（项目页 dexmimicgen.github.io）</td></tr>
</tbody>
</table>
- **[RSS 2024年3月](https://arxiv.org/abs/2403.12945)** DROID: A Large-Scale In-the-Wild Robot Manipulation Dataset. 真实世界大规模机器人操纵数据集.
- **[ICRA 2023年11月](https://arxiv.org/abs/2311.12032)** RH20T: A Comprehensive Robotic Dataset for Learning Diverse Skills in Real-World. 真实世界多样化技能学习数据集.
- **[arXiv 2023年10月](https://arxiv.org/abs/2310.08864)** Open X-Embodiment Dataset: Robotic Learning Datasets and RT-X Models. 最大规模多机器人数据集，22种机器人、100万+轨迹.
- **[CoRL 2023年8月](https://arxiv.org/abs/2308.12952)** BridgeData V2: A Dataset for Robot Learning at Scale. 大规模机器人学习数据集.
- ★ **[CVPR 2021年10月](https://arxiv.org/abs/2110.07058)** Ego4D: Around the World in 3,000 Hours of Egocentric Video. 大规模第一人称视频数据集.
- ★ **[NeurIPS 2021年9月](https://arxiv.org/abs/2109.08238)** HM3D: Habitat-Matterport 3D Dataset (HM3D): 1000 Large-scale 3D Environments for Embodied AI. 大规模3D环境数据集.
- **[ICRA 2020年3月](https://arxiv.org/abs/2003.06789)** GraspNet: A Large-Scale Cluttered Scene Dataset for Robotic Grasping. 大规模杂乱场景抓取数据集.
- ★ **[ICCV 2019年4月](https://arxiv.org/abs/1904.03278)** AMASS: Archive of Motion Capture as Surface Shapes. 大型人体运动数据集.
- ★ **[TPAMI 2017年5月](https://arxiv.org/abs/1705.09155)** Human3.6M: Large Scale Datasets and Predictive Methods for 3D Human Sensing. 大型人体3D姿态数据集.
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>

## Benchmarks & Evaluation

### [GAUGE: A Measurement-Grounded Benchmark for Physical Fidelity in Simulation Engines and Video World Models](https://arxiv.org/abs/2608.05948)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">一句话摘要</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">以真实测量为锚，统一诊断物理引擎与视频世界模型物理保真度的基准。</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">发布时间</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">2026 年 8 月</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">机构</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">上海人工智能实验室 InternRobotics 团队（联合多家单位）</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">特点</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>首个<strong>同时评测数值物理引擎与生成式视频世界模型</strong>物理保真的真实世界诊断基准</li><li><strong>22 个受控任务族</strong>覆盖刚体、柔性线缆、织物、体积形变物体</li><li>锚定真实轨迹并配<strong>标定物理元数据与不确定性标注</strong>，可定位“违背了哪条物理原理”</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">实验结论</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>在 14 个任务族上评测 <strong>Isaac Sim、Genesis、Newton</strong>：不存在统一保真的物理引擎，最大偏差在冲击接触、快速织物与体积形变</li><li>6 个图生视频模型在刚体任务上可生成<strong>方程形式正确但加速度/动量/振荡时序错误</strong>的轨迹</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">数据 / 模型</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GAUGE 基准（22 个任务族）</td></tr>
</tbody>
</table>

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.26789)** CheckVLA: Execution-Time Verification for Long-Horizon Mobile Manipulation. 基于动作条件世界模型的长时程移动操作执行时验证。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.23108)** The Curse of Precision: A Data Scaling Law for High-Precision Manipulation. 已在前面列出
- **[arXiv 2026年7月](https://arxiv.org/abs/2607.14609)** Representation-Aligned Tactile Grounding for Contact-Rich Manipulation. 表示对齐的触觉接地用于丰富接触操作。
- **[arXiv 2026年7月](https://arxiv.org/abs/2607.13818)** Learning Robust Execution with Agentic Reinforcement Learning. 通过智能体强化学习学习鲁棒操作执行。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.31494)** Robustness of Robotic Manipulation: Foundations and Frontiers (Survey). 系统研究机器人操作鲁棒性的定义、框架与评估方法。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.25503)** AISPO: Enhancing Depth Reliability for Non-Lambertian Object Manipulation. 提出深度补全框架提升透明高反光物体的深度可靠性。
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.20999)** Inductive Generalization for Robotic Manipulation. 已在前面列出
- **[arXiv 2026年6月](https://arxiv.org/abs/2606.18610)** SC3-Eval: Evaluating Robot Foundation Models via Self-Consistent Video Generation. 通过自一致性视频生成评估机器人基础模型。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.30326)** RoboWits: Unexpected Challenges for Robotic Creative Problem Solving. 提出RoboWits双臂机器人基准测试，系统评估认知推理、创造性工具使用和应对意外条件的鲁棒性，为具身智能创造性问题解决提供新视角。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.28805)** OmniVerifier-M1: Multimodal Meta-Verifier with Explicit Structured Recalibration. 提出OmniVerifier-M1多模态元验证器，利用符号元验证和解耦强化学习实现细粒度错误定位，支持动态区域级自校正。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.27932)** When Think-with-Image Meets Safety: What Determines Multimodal Jailbreak Robustness? 研究多模态大模型的安全性，发现显式图像工具交互可将越狱成功率降低约30%，为具身智能安全提供新见解。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12674)** Revealing Interpretable Failure Modes of VLMs (REVELIO). 系统发现VLM可解释失效模式的框架，结合多样性感知束搜索和高斯过程Thompson采样，在自动驾驶和室内机器人中揭示SOTA VLM的未报告漏洞。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.00397)** MiniVLA-Nav v1: A Multi-Scene Simulation Dataset for Language-Conditioned Robot Navigation. 面向语言条件目标接近导航的多场景仿真数据集，提供RGB、深度、实例分割和专家动作标签，并包含同分布、模板改写与OOD类别等评测划分。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.25161)** Capability-Oriented Failure Attribution for Vision-and-Language Navigation Agents. 一项面向视觉语言导航智能体的评估研究，从能力导向视角归因失败模式，并重点关注安全约束。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24086)** AsyncShield: A Plug-and-Play Edge Adapter for Asynchronous Cloud-based VLA Navigation. 面向云端VLA导航的异步控制适配器，通过时空位姿缓冲和运动学映射修正延迟意图，并以约束MDP在目标跟踪与避障安全之间动态权衡。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.24033)** Event-based SLAM Benchmark for High-Speed Maneuvers. 提出面向高速机动场景的事件相机SLAM基准EvSLAM，覆盖多平台、极端光照与复杂运动模式，并设计衡量系统极限能力的统一评测指标。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.23775)** Vision-Language-Action Safety: Threats, Challenges, Evaluations, and Mechanisms. 系统梳理VLA系统面临的安全威胁、开放挑战、评测方式与缓解机制，重点讨论长时程执行中的风险来源与安全保障路径。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21686)** WorldMark: A Unified Benchmark Suite for Interactive Video World Models. 统一评测交互式视频世界模型的基准套件，用于比较世界模型在预测、交互和可控生成上的能力。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21568)** A Bayesian Reasoning Framework for Robotic Systems in Autonomous Casualty Triage. 融合多种视觉算法输出与贝叶斯网络推理，在缺失或冲突感知输入下完成自动化伤员分诊与风险判断.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.21192)** How VLAs (Really) Work In Open-World Environments. 系统分析VLA在开放世界环境中的真实工作机制，重点观察其空间感知、任务分解与执行失效模式。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20472)** Temporal Difference Calibration in Sequential Tasks: Application to Vision-Language-Action Models. 将时序差分校准引入VLA训练与评估，用于减轻长序列决策中的误差累积和价值偏移。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20193)** LLM-Guided Safety Agent for Edge Robotics with an ISO-Compliant Perception-Compute-Control Architecture. 面向边缘机器人安全控制的ISO合规架构，将自然语言安全规范转为可执行谓词并部署到低时延闭环控制中.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.20151)** Toward Safe Autonomous Robotic Endovascular Interventions using World Models. 面向血管介入机器人的世界模型安全控制框架，提升在多样化患者解剖条件下的自主导航鲁棒性与长期稳定性.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.19638)** SafetyALFRED: Evaluating Safety-Conscious Planning of Multimodal Large Language Models. 在ALFRED基础上扩展六类厨房危险场景，评估多模态大模型在交互环境中是否会主动规避安全风险.
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.19133)** baltic: a benchmark and cross-domain strategy for 3d reconstruction across air and underwater domains under varying illumination. 构建跨空气与水下、不同照明条件的三维重建基准，并评估SfM、NeRF与3DGS在跨域场景中的几何精度和感知质量。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.17969)** E3VS-Bench: A Benchmark for Viewpoint-Dependent Active Perception in 3D Gaussian Splatting Scenes. 面向3D高斯场景主动感知的评测基准，专门测试视角相关任务中的探索、观察与决策能力。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.03956)** VLA-Forget: Vision-Language-Action Unlearning for Embodied Foundation Models. 面向具身基础模型的遗忘方法，研究如何安全移除VLA中的特定知识或行为能力，同时尽量保持整体性能。
- ★ **[AAAI 2026年3月](https://ojs.aaai.org/index.php/AAAI/article/view/40880)** IS-Bench: Evaluating Interactive Safety of VLM-Driven Embodied Agents in Daily Household Tasks. 首个多模态交互安全基准，包含161个挑战性场景和388个独特安全风险，采用新颖的过程导向评估验证风险缓解步骤是否在特定风险步骤前后正确执行.
- **[arXiv 2026年1月](https://arxiv.org/abs/2601.15282)** RBench: Rethinking Video Generation Model for the Embodied World. 面向机器人视频生成的综合基准，涵盖五个任务领域和四种不同具身，评估任务级正确性和视觉保真度，与人类评估Spearman相关系数达0.96.

- **[arXiv 2026年1月](https://arxiv.org/abs/2601.04137)** WoW-World-Eval: Wow, wo, val. A Comprehensive Embodied World Model Evaluation Turing Test. 具身图灵测试基准，基于609个机器人操作数据，考察感知、规划、预测、泛化和执行五大核心能力，22个指标的综合评估协议与人类偏好Pearson相关性>0.93.
- **[arXiv 2026年1月](https://arxiv.org/abs/2601.03136)** Limited Linguistic Diversity in Embodied AI Datasets. 分析具身 AI 数据集中语言多样性受限的问题及其对训练与评测的影响。
- **[arXiv 2025年12月](https://arxiv.org/abs/2512.24125)** ERIQ: Unified Embodied VLM Reasoning with Robotic Action via Autoregressive Discretized Pre-training. 大规模具身推理基准，包含6K+问答对，涵盖四个推理维度，通过解耦推理与执行实现系统评估，揭示具身推理能力与端到端VLA泛化之间的强正相关.
- **[arXiv 2025年11月](https://arxiv.org/abs/2511.20937)** ENACT: Evaluating Embodied Cognition with World Modeling of Egocentric Interaction. 通过自我中心交互世界建模评估具身认知能力的基准，用重排任务考察动作效果推理、具身意识与长程记忆.
- **[arXiv 2025年7月](https://arxiv.org/abs/2507.12385)** OmniEAR: Benchmarking Agent Reasoning in Embodied Tasks. 综合框架，评估语言模型在具身任务中关于物理交互、工具使用和多智能体协作的推理能力.

- **[arXiv 2025年5月](https://arxiv.org/abs/2505.12388)** StaticEmbodiedBench: A Plug-and-Play Benchmark for Embodied AI. 即插即用的基准测试，利用静态场景表示进行统一评估，避免交互式仿真或真实世界设置的高成本和碎片化问题.
- **[arXiv 2025年2月](https://arxiv.org/abs/2502.07712)** SafeVLA: Safety Alignment for Vision-Language-Action Models. VLA模型的安全对齐方法.
- **[CoRL 2024年6月](https://arxiv.org/abs/2406.03456)** CRAM: A Benchmark for Compositional Reasoning and Action in Manipulation. 组合推理与操作基准.
- **[arXiv 2024年3月](https://arxiv.org/abs/2403.10510)** EmbSpatial-Bench: Benchmarking Spatial Reasoning for Embodied AI. 具身空间推理基准.
- ★ **[CVPR 2024年1月](https://arxiv.org/abs/2401.08912)** OpenEQA: Embodied Question Answering in the Era of Foundation Models. 基础模型时代的具身问答基准.
- ★ **[ICLR 2023年2月](https://arxiv.org/abs/2302.04659)** ManiSkill2: A Unified Benchmark for Generalizable Manipulation Skills. 通用操纵技能统一基准.
- ★ **[NeurIPS 2022年11月](https://arxiv.org/abs/2211.03745)** BEHAVIOR Challenge: Benchmarking Everyday Activities. 日常活动基准挑战.
- ★ **[CVPR 2022年3月](https://arxiv.org/abs/2203.09811)** BEHAVIOR-1K: A Benchmark for Embodied AI with 1,000 Everyday Activities. 1000种日常活动基准.
- ★ **[ICLR 2021年12月](https://arxiv.org/abs/2112.03227)** CALVIN: A Benchmark for Language-Conditioned Policy Learning. 语言条件策略学习基准.
- ★ **[NeurIPS 2021年6月](https://arxiv.org/abs/2106.09876)** Franka Kitchen: A Benchmark for Long-Horizon Manipulation. 长时程操纵基准.
- ★ **[CVPR 2021年4月](https://arxiv.org/abs/2104.04631)** DexYCB: A Benchmark for Capturing Hand Grasping of Objects. 手部抓取物体基准.
- **[ICRA 2019年9月](https://arxiv.org/abs/1909.12271)** RLBench: The Robot Learning Benchmark & Learning Environment. 机器人学习基准.
<a id="survey" name="survey"></a>
<a id="survey" name="survey"></a>
<a id="survey" name="survey"></a>
<a id="survey" name="survey"></a>

## Survey

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.21655)** Progress Reward Modeling for Robotic Learning: A Comprehensive Survey. 从接口、构建方法、数据基准三方面统一进度奖励建模研究。

- **[arXiv 2026年7月](https://arxiv.org/abs/2607.06706)** VLA Models for Unmanned Aerial Robotics and Bimanual Manipulation: A Review. 全面综述VLA模型在无人机与双臂操作中的应用与挑战。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.27817)** Deep Learning for Robot Vision. 综述深度学习在机器人视觉中的应用，涵盖目标检测、语义分割、深度估计等关键任务，为具身智能感知提供系统参考。
- **[arXiv 2026年5月](https://arxiv.org/abs/2605.12090)** World Action Models: The Next Frontier in Embodied AI. 首个系统综述世界动作模型(WAM)的综述论文，提出将预测状态建模与动作生成统一的分类体系，涵盖级联式和联合式两大范式。
- **[arXiv 2026年4月](https://arxiv.org/abs/2604.23001)** Vision-Language-Action in Robotics: A Survey of Datasets, Benchmarks, and Data Engines. 一篇关于机器人 VLA 数据集、评测基准与数据引擎的综述，重点关注长时程任务。
- **[arXiv 2026年2月](https://arxiv.org/abs/2602.04567)** Benchmarking Vision-Language-Action Models: A Survey. VLA模型基准测试综述.
- **[Authorea 2026年2月](https://flamechallenge.authorea.com/doi/full/10.22541/au.177023340.02874343)** Embodied AI Evaluation: A Survey on Evaluation of Embodied AI. 围绕感知-认知-规划-行动完整循环建立系统评估框架，系统总结代表性模拟器、数据集和基准，分析从结果导向到多维度过程质量与物理安全评估的转变.
- **[arXiv 2026年1月](https://arxiv.org/abs/2601.09876)** Generative AI for Robotics: A Survey. 生成式AI在机器人中的应用综述.
- **[arXiv 2026年1月](https://arxiv.org/abs/2601.03456)** Embodied Foundation Models Survey: Embodied Foundation Models: A Survey. 具身基础模型综述.
- **[TechRxiv 2026年1月](https://www.techrxiv.org/doi/full/10.36227/techrxiv.176948355.54623875/v1)** World Models for VLA Agents: Towards Generalist Embodied AI: A Survey on World Models for VLA Agents. 首个专门针对VLA智能体的世界模型综述，提出统一分类法，将现有方法组织为世界规划器、世界行动模型、世界合成器和世界模拟器四个范式.
- **[TechRxiv 2026年1月](https://www.techrxiv.org/doi/full/10.36227/techrxiv.176739762.23746519/v1)** Physical AI: A Comprehensive Review of Physical Artificial Intelligence. 全面分析生成式物理AI系统，引入五类方法的分类法：机器人基础模型RFM、VLA、大行为模型LBM、扩散策略模型DPM和世界基础模型WFM.
- **[arXiv 2025年11月](https://arxiv.org/abs/2511.03456)** Data-Centric Embodied AI: A Survey. 数据驱动的具身智能综述.
- **[arXiv 2025年10月](https://arxiv.org/abs/2510.12390)** Efficient VLA: Efficient Vision-Language-Action Models for Embodied Manipulation: A Systematic Survey. 系统回顾提高VLA效率的方法，重点在于减少延迟、内存占用以及训练和推理成本.
- **[arXiv 2025年10月](https://arxiv.org/abs/2510.04567)** Embodied Agents with LLMs: A Survey. 大语言模型驱动的具身智能体综述.
- **[arXiv 2025年4月](https://arxiv.org/abs/2504.06789)** Open-Source Robotics: A Survey. 开源机器人综述.
- **[arXiv 2025年3月](https://arxiv.org/abs/2503.08912)** Humanoid Robots: A Survey of Technologies and Challenges. 人形机器人技术与挑战综述.
- **[arXiv 2025年3月](https://arxiv.org/abs/2503.04734)** Vision-Language-Action Models: A Survey. VLA模型综述.
- **[arXiv 2024年7月](https://arxiv.org/abs/2407.06886)** Embodied AI: A Survey. 具身AI全面综述.

- **[arXiv 2023年11月](https://arxiv.org/abs/2311.08923)** Robot Learning in Era of Foundation Models: Robot Learning in the Era of Foundation Models. 基础模型时代的机器人学习综述.
- **[arXiv 2022年12月](https://arxiv.org/abs/2212.04567)** Sim-to-Real Transfer for Robotics: A Survey. Sim2Real迁移综述.
- **[arXiv 2022年5月](https://arxiv.org/abs/2205.09876)** A Survey of Embodied Navigation. 具身导航综述.
- **[arXiv 2021年9月](https://arxiv.org/abs/2109.06789)** A Survey of Imitation Learning: Algorithms, Applications, and Challenges. 模仿学习综述.
- **[T-RO 2021年3月](https://arxiv.org/abs/2103.04567)** Robotic Manipulation: A Survey. 机器人操纵综述.
- **[IJRR 2020年4月](https://arxiv.org/abs/2004.09876)** Reinforcement Learning for Robotics: A Survey. 机器人强化学习综述.
