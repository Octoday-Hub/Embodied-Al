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
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Factorizes a single human interaction and recombines it into diverse robot-native data for embodiment-agnostic scaling without paired demonstrations.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">XPENG Robotics (with Tencent and NTU collaborators)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Factorized world model</strong>: decomposes an interaction into independent action / camera / embodiment controls, recombining factors to expand a single human video into diverse robot-native data</li><li>Pretrains on <strong>human egocentric video at scale + mixed-embodiment finetuning</strong>, no paired human-robot demonstrations needed</li><li>Recombined video-action pairs can target policy weaknesses (e.g., fixing "false completion" priors, grounding language-anchored goal selection)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Controllability avg <strong>0.778</strong> vs Cosmos-Predict2.5 0.417, WAN Fun-Control 0.609</li><li>RoboCasa GR1 tabletop success 49.8% to <strong>54.6%</strong>; XPENG IRON humanoid real-robot grasp 20.0% to <strong>55.0%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">AnyWorld (open-source, xpeng-robotics/AnyWorld); egocentric interaction video corpus</td></tr>
</tbody>
</table>

### [Beyond Data Scaling: Representation-Centric Continued Pre-training for Vision-Language-Action Models](https://arxiv.org/abs/2608.27550)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shifts VLA continued pretraining from data scaling to representation learning; beats full-data baselines with a small data budget.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">StarVLA team (VLAct; incl. Hengshuang Zhao, Bei Yu, Jiaya Jia)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Introduces <strong>representation-centric continued pretraining</strong> as an axis independent of data scale, converting a fixed robot-data budget into transferable vision-action knowledge</li><li><strong>Three action heads (OFT / PI / GR00T) jointly supervise one backbone</strong>; heads are discarded after pretraining, task-specific heads attached downstream</li><li>Qwen3-VL-4B base, trained with only <strong>16 GPUs and fully open data</strong>; weights/checkpoints/pipeline released</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO-Plus <strong>82.6%</strong>, RoboTwin 2.0 <strong>92.5%</strong>, surpassing ABot-M0 and LingBot-VLA</li><li>On unseen humanoid RoboCasa-GR1, <strong>20%</strong> of downstream data reaches <strong>49.5%</strong>, above full-data GR00T-N1.6 (47.6%)</li><li>Real-robot avg success <strong>92.5%</strong> across 4 in-domain tasks (77.5% without continued pretraining)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VLAct (Qwen3-VL-4B backbone)</td></tr>
</tbody>
</table>

### [Riemann-1.0: An Embodied World Action Model for Physical AI](https://arxiv.org/abs/2608.27033)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A fully causal autoregressive World Action Model that acts as both an executable robot policy and a world simulator.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Riemann Dynamics (robot company incubated by Kunlun Wanwei)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Fully causal autoregressive WAM</strong>: actions sit in the causal chain of visual state transitions (action before vision), unlike joint-generation / video-first / decoupled routes</li><li>One model, dual use: <strong>closed-loop robot policy</strong> plus <strong>action-conditioned multi-embodiment visual world simulator</strong></li><li><strong>Three-stage progressive embodied pretraining</strong>: LAM latent-action bootstrap on human video to UMI/exoskeleton alignment to robot-policy enhancement</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO <strong>99.0%</strong>, RoboTwin 2.0 <strong>94.3%</strong>, long-horizon RoboCasa-365 <strong>62.6%</strong> (+8.4 pp over prior best)</li><li>Real-robot (Tianji dual-arm) household tasks: avg SR <strong>85.0%</strong>, PSR <strong>94.4%</strong>, leading strongest open baseline by 15 SR points on average</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Riemann-1.0; 232K hours of multisource data (200K+ h human egocentric video, 12K+ h UMI/exoskeleton demos, 20K+ h robot trajectories, 41 embodiments)</td></tr>
</tbody>
</table>

### [One Policy, Many Embodiments: Unified Camera-Centric Action Geometry Pre-training for Heterogeneous Embodied Manipulation](https://arxiv.org/abs/2608.26058)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A unified camera-centric action geometry lets arms, humanoids, and hands share one VLA policy's action schema.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Xiaomi Embodied Intelligence Team + University of Macau</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Introduces <strong>UCAG-P, a camera-centric unified action formulation</strong>: observable end-effector anchor motion as the shared learning target, bypassing explicit action retargeting and data-specific branches</li><li>A <strong>geometry-conditioned action translator</strong> converts shared predicted motion into executable control given target-embodiment kinematics</li><li>Decoupled design lets a shared VLA learn transferable manipulation geometry while keeping embodiment-specific controllability</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Single checkpoint, no benchmark-specific finetuning: LIBERO <strong>98.3%</strong>, RoboTwin Easy <strong>88.7%</strong> / Hard <strong>89.2%</strong></li><li>LIBERO-Plus zero-shot <strong>82.0%</strong>, RoboCasa GR-1 <strong>62.0%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UCAG-P; 4.03K hours robot+sim data and 2.34K hours human demos</td></tr>
</tbody>
</table>

### [τ0-VLA: a Hierarchical Robot Foundation Model with World-Model-Guided Test-Time Computation](https://arxiv.org/abs/2608.16885)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A slow-think/fast-exec hierarchical VLA with world-model-guided test-time computation that doubles long-horizon real-robot success.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shanghai Frontier Innovation Institute (Luo Jianlan's team) + Agibot + CUHK</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Two-policy hierarchical architecture</strong>: a high-level policy proposes semantic subtasks ("slow thinking") while a low-level policy executes actions at higher frequency ("fast execution"), running asynchronously</li><li>First to bring <strong>test-time computation into embodied high-level decisions</strong>: low-confidence choices trigger a candidate-subtask -> world-model rollout -> value scoring -> beam search loop</li><li>Ships <strong>execution memory, world model, value model, and reflection model</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Avg success <strong>45.0%</strong> across four 13-25-step long-horizon real-robot tasks vs π0.5 22.5%, GR00T N1.7 2.5%</li><li>Under unseen layouts, TTC lifts next-subtask prediction from 50.0% to <strong>74.0%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">τ0-VLA (open-source, Apache-2.0); 40,115 hours heterogeneous real-world robot data</td></tr>
</tbody>
</table>

### [StellaVLA: In-Context Structured Demonstration for Generalizable Vision-Language-Action Models](https://arxiv.org/abs/2608.11671)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Conditioning on one retrieved structured demonstration lets a VLA adapt to out-of-distribution scenes without finetuning.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">University of Sydney (Chang Xu lab) + StellarEdge AI</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>An offline pipeline converts raw trajectories into <strong>structured demonstrations</strong> (task plan, sub-goal descriptions, verbalized 3D motion) at zero annotation cost</li><li><strong>Parallel dual training</strong>: an action expert and the native language head supervise one shared backbone; inference uses the action expert alone with <strong>no added latency</strong></li><li>Cross-embodiment transfer: real-robot, human-hand, and XR demonstrations all work as context</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Ranks first on VLA-Arena (Aug 1, 2026) with <strong>0.63</strong> overall vs π0.5 0.44 and LingBot-VLA 0.22</li><li>LIBERO avg success <strong>98.8%</strong>; LIBERO-Plus zero-shot <strong>85.1%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">StellaVLA; structured demos auto-generated with Qwen3-VL, validated on AgileX Piper</td></tr>
</tbody>
</table>

### [Harness VLA: Steering Frozen VLAs into Reliable Manipulation Primitives via Memory-Guided Agent](https://arxiv.org/abs/2607.08448)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A system-level Harness steers frozen VLAs into reliable manipulation primitives via memory-guided agents.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jul 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University (Prof. Chao Yu's team) with Zhengxing Innovation and Infinigence-AI</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>First to introduce the <strong>Harness Layer</strong> (an execution-organizing system layer) into embodied AI, letting the frozen underlying VLA focus on contact-rich manipulation</li><li>Harness learns how to <strong>organize, invoke, and reuse</strong> foundation models without ever updating VLA weights</li><li>General system-layer framework, combinable with <strong>WAMs</strong> and other embodied foundation models</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>82.4%</strong> success on LIBERO-Pro perturbation evaluation (Pi_RLinf 50%, NVIDIA Cap-X 18.2%, Berkeley RATS 43.8%)</li><li>Significant gains on task success under complex perturbations</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Harness VLA framework (project page harnessvla.github.io)</td></tr>
</tbody>
</table>

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.10655)** Foveated Perception for Shortcut Learning. Proposes foveated perception mechanisms to mitigate shortcut learning in robotic foundation models.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.09818)** TS-Mask VLA: Temporal-Spatial Masking. Proposes 2D temporal-spatial masking with Bridge Attention, achieving 95.7% on LIBERO with only 0.5B parameters.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.06564)** Lift3D-VLA: 3D Geometry VLA. Elevates VLA models with 3D geometric features and physical dynamics modeling.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.03941)** WSA1: 3D World-Spatial-Action Model. Proposes a 3D-centric world-spatial-action model for generalizable robot control via 3D scene understanding.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.02865)** DREAMSTEER: Latent World Models for VLA. Uses latent world models to steer VLA policies at deployment time without any finetuning.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.02501)** Embodied.cpp: Portable Inference Runtime. A portable inference runtime for embodied AI models similar to llama.cpp but for robotics.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.01088)** ROSA: Foundation Model Serving System. A serving system for robotics foundation models supporting multi-model deployment and heterogeneous robot coordination.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.01002)** Hy-Embodied-RxBrain-1.0: A Cognitive World Model with Unified Textual Reasoning and Visual Imagination. Tencent's embodied native world cognition model released at WAIC 2026, pioneering deep synergy between textual reasoning and visual imagination in continuous cognitive sequences for high-level robot decision guidance.

### [Xiaomi-Robotics-1: Scaling VLA Models with over 100K Hours of Real-World Trajectories](https://arxiv.org/abs/2607.15330)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A VLA trained on 100K hours of real-world trajectories, reaching 57.4% on RoboCasa365.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">July 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Xiaomi (Xiaomi Robotics)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>MoT (Mixture-of-Transformers) architecture</strong>: the Qwen3-VL vision-language model handles semantic understanding while a Diffusion Transformer (DiT) generates action chunks via flow matching; VLM-side action tokens do not participate in DiT attention</li><li><strong>Two-stage training</strong>: pretraining on 100K hours of UMI real-world trajectories + post-training on ~10K hours of cross-embodiment data (self-collected mobile/dual-arm robot data, instruction-annotated UMI and open-source datasets)</li><li><strong>Scalable automatic annotation pipeline</strong>: the VLM automatically generates language descriptions of scene state transitions, completing full annotation in about 2 weeks</li><li>Provides <strong>2B / 5B / 10B</strong> model scales; cross-embodiment action spaces unified via end-effector coordinate-frame increments, with missing dimensions masked by loss masking</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Average success rate of <strong>57.4%</strong> on RoboCasa365, surpassing the previous SOTA (46.6%)</li><li>Average score of <strong>20.07</strong> on RoboDojo, vs 13.07 for the prior SOTA</li><li>Average <strong>75%</strong> on 4 out-of-the-box household tasks on real robots; finetuning for new tasks requires on average less than 10 hours of data</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Xiaomi-Robotics-1 (2B / 5B / 10B); dataset Xiaomi-Robotics-1 Dataset (100K hours of UMI real-world manipulation trajectories); open-source (Apache-2.0)</td></tr>
</tbody>
</table>

### [Cortex: A Bidirectionally Aligned Embodied Agent Framework for Long-horizon Manipulation](https://arxiv.org/abs/2607.05377)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A two-system bidirectional alignment framework combining VLM planning with VLA execution, reaching 95.5% zero-shot on LIBERO-Long.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">July 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University, Shanghai AI Lab</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Two-system architecture</strong>: a high-level VLM tracks task progress through text semantic memory and dispatches sub-tasks one by one, while a low-level VLA executes reactively</li><li><strong>Bidirectionally aligned sub-task interface</strong>: manipulation sub-tasks are normalized into 32 canonical skill primitives with strict language templates, constraining planner outputs to executable, processable sub-tasks</li><li><strong>Event-balanced sampling</strong>: oversampling samples near sub-task transition boundaries to alleviate planning ambiguity in long-horizon tasks</li><li>Training data: 4000+ hours of auto-annotated open-source video + 30 hours of simulation data; inference-side harness supports language normalization and timeout reset</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Zero-shot success rate of <strong>95.5%</strong> on LIBERO-Long, 3.1% higher than the single-agent baseline</li><li><strong>86.8%</strong> on RoboTwin, 4.1% higher than the single-agent baseline</li><li>Zero-shot completion of an unseen 14-step chemistry experiment on a real robot at <strong>65%</strong> success (0% for end-to-end VLA finetuning)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Cortex; training data 4000+ hours of auto-annotated open-source video + 30 hours of simulation data</td></tr>
</tbody>
</table>

### [Hy-Embodied-VLA-0.5: A Scalable Vision-Language-Action Model for Cross-Embodiment Deployment](https://arxiv.org/abs/2607.01001)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tencent's embodied VLA foundation model, trained on 10K+ hours of data, supporting cross-embodiment deployment.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">July 2026 (released at WAIC 2026)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tencent (Robotics X / Hunyuan)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Forms a <strong>three-layer "Perception-Cognition-Action" model stack</strong> with Hy-Embodied-VLM-1.0 and Hy-Embodied-RxBrain-1.0; the VLA converts high-level goals into continuous, correctable low-level actions</li><li><strong>Designed for high-frequency continuous action generation</strong>, matching the multi-timescale physical world by frequency layering</li><li><strong>Chemical plant trial production</strong>: single-unit takt time under 6 seconds; new SKUs require only ~8 hours of data collection and finetuning for adaptation</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Unified modeling and cross-embodiment capability performed excellently in release evaluations</li><li>Factory trial production validated industrial deployment for high-mix, low-volume production lines</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Hy-Embodied-VLA-0.5; training data 10K+ hours of high-precision data; open-source</td></tr>
</tbody>
</table>

### [MiniCPM-RobotManip: A 1.5B General-Purpose VLA Model with Native Context Memory](https://github.com/OpenBMB/MiniCPM-Robot)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A 1.5B lightweight VLA with streaming native memory, single-step inference at 120ms.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">July 2026 (released at WAIC 2026)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">ModelBest (OpenBMB)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Architecture</strong>: SigLIP vision tower + Qwen3.5 language backbone + 16-layer DiT action head, generating 30-step 80-dim action chunks at once</li><li><strong>Streaming memory</strong>: inherits MiniCPM-V 4.6's visual token compression (256→64 per frame), incrementally caches historical observations, and retains up to ~1 minute of context with inference cost on par with a single frame</li><li><strong>1.5B-parameter generalist policy</strong>, 120ms forward pass per decision step (H100 BF16), vs ~234ms for π0.5</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">LIBERO <strong>97.5</strong>, Calvin ABC→D 4.1, RoboTwin2 easy/hard 91.3/91.6, RMBench <strong>53.3</strong> (π0.5 only 10.4, ~5x)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model MiniCPM-RobotManip (1.5B); open-source (Apache-2.0, repo MiniCPM-Robot)</td></tr>
</tbody>
</table>

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.26025)** In-Context World Modeling. Proposes in-context world modeling for robotic control without explicit world model training.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.24049)** SPACE: Cross-Robot Data Learning. Proposes Cartesian state increments as a universal action representation for cross-embodiment policy learning.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.22174)** OpenHLM: Whole-Body Humanoid Loco-Manipulation. Open-source VLA recipe for whole-body humanoid loco-manipulation supporting squatting, pedal-pressing, etc.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.17846)** Qwen-RobotManip: Alignment Unlocks Scale. Proposes unified alignment framework for multi-source heterogeneous manipulation data, ~38,100h pretraining corpus with emergent zero-shot generalization.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.17200)** ACE-Ego-0: Unifying Egocentric Human and Robotic Data. Unifies egocentric human video and robot data for cross-embodiment VLA pretraining via camera-space action mapping and temporal alignment.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.13886)** PhysVLA: Physically-Grounded VLA. Introduces physical reasoning into VLA models for enhanced understanding of object physical properties.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.13769)** μ0: A Scalable 3D Interaction-Trace World Model. Proposes a scalable 3D interaction-trace world model for cross-embodiment robot learning via interaction point trajectory prediction, without action labels.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.11270)** Lumo-2: Predictive, Aligned Robot Learning. Introduces a latent world-action model with multi-stage modality pre-alignment strategy.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.08530)** GEAR-VLA: Geometry-Aware Action Representations. Proposes coarse-to-fine action learning with embodiment canonicalization, achieving SOTA on LIBERO, zero-shot LIBERO-Plus, and cross-embodiment transfer.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.08242)** Light-WAM: Efficient World Action Models. Lightweight world action model with compact video backbone and reduced latent space.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.06556)** Robots Need More than VLA and World Models. Systematically analyzes limitations of VLA and world models, proposing additional capabilities needed for robotic systems.

### [Galaxea G0.5: Open-Sourced Generalist VLA with Unified Autoregressive Action Generation](https://arxiv.org/abs/2608.11739)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">The 2026 WRC flagship open-source VLA, unifying reasoning and action generation in a single autoregressive stream.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">June 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Galaxea (founded by the Zhao Xing team from Tsinghua University)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Unified autoregressive VLA</strong>: visual, language, reasoning, and action tokens are generated in the same stream by a single Transformer Decoder (initially from Qwen3.5-2B) via next-token prediction</li><li><strong>ActionCodec</strong> structured residual quantization compresses cross-embodiment actions into a 27-dimensional shared component space (9 each for left/right arms, 1 each for grippers, 7 for the lower body)</li><li>Native CoT (subtask / BBox / trajectory / action prompts) optional; pretrained on <strong>14 embodiments</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Average success rate <strong>76.7%</strong> on real robots R1-Lite/R1-Pro (π0.5: 53.3%, GR00T-N1.7: 24.4%)</li><li>DROID zero-shot <strong>82.5%</strong> (π0.5: 57.5%); LIBERO 98.9%, RoboTwin 2.0 93.3%</li><li>AR+CoT inference ~<strong>192 ms</strong>; BEHAVIOR Challenge Task Success 0.3136 (champion 0.2605)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model G0.5 (weights and code open-sourced, HuggingFace OpenGalaxea/G05); pretraining data across 14 embodiments; Fast-WAM world model released alongside</td></tr>
</tbody>
</table>

### [WeaveLA: Event-Driven Latent Memory for VLA Long-Horizon Manipulation](https://arxiv.org/abs/2606.17463)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Uses event-driven latent memory to address the cross-subtask information disconnection of VLAs in repetitive long-horizon tasks.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">June 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Fudan University (with CUHK-Shenzhen, etc.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Event-driven cross-subtask latent memory interface</strong>: on top of the frozen VLA backbone (π0.5), compresses each completed subtask segment into 8 latent tokens via query-driven attention pooling</li><li>Routed into the action generation path of the next subtask; triggered only on subtask-completion events, <strong>not written frame-by-frame</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Success rate on the hardest repetitive task subset of the RoboMME benchmark (SwingXtimes, N=3) improves from <strong>0% to 47.8%</strong></li><li>Performance on single-shot tasks unchanged; per-episode paired analysis confirms the gains concentrate on tasks requiring cross-subtask causal structure</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model WeaveLA; evaluated on the π0.5 backbone and the RoboMME benchmark</td></tr>
</tbody>
</table>

- **[arXiv May 2026](https://arxiv.org/abs/2605.30350)** DynaFLIP: Rethinking Robotics Perception via Tri-Modal-Dynamics Guided Representation. A dynamics-aware multimodal pretraining framework that integrates vision, language, and dynamics information to enhance scene understanding and motion execution in robotic manipulation.

- **[arXiv May 2026](https://arxiv.org/abs/2605.30311)** Archon: A Unified Multimodal Model for Holistic Digital Human Generation. Proposes Archon, a unified multimodal model integrating seven modalities for holistic digital human generation with an intra-modal thinking approach for enhanced fidelity and controllability.

- **[arXiv May 2026](https://arxiv.org/abs/2605.30263)** minWM: A Full-Stack Open-Source Framework for Real-Time Interactive Video World Models. A full-stack open-source framework that converts bidirectional video diffusion models into camera-controllable few-step autoregressive world models, supporting real-time low-latency rollout.

- **[arXiv May 2026](https://arxiv.org/abs/2605.30260)** How LoRA Remembers? A Parametric Memory Law for LLM Finetuning. Proposes a parametric memory law that quantifies the memory capacity limits of LoRA in LLM finetuning, discovering that p>0.5 is sufficient for verbatim recall, providing theoretical guidance for embodied intelligence model finetuning.

- **[arXiv May 2026](https://arxiv.org/abs/2605.30248)** GenClaw: Code-Driven Agentic Image Generation. Proposes GenClaw, a code-driven agentic image generation paradigm where agents first conceptualize, then render visual sketches with code, and finally add textures with generative models for highly controllable visual generation.

- **[arXiv May 2026](https://arxiv.org/abs/2605.30056)** Sample-Efficient Diffusion-based Reinforcement Learning with Critic Guidance. A sample-efficient diffusion-based RL method combining critic guidance to improve learning efficiency, demonstrating excellent performance in robotic control tasks.

- **[arXiv May 2026](https://arxiv.org/abs/2605.29488)** AnyMo: Scaling Any-Modality Conditional Motion Generation with Masked Modeling. Proposes AnyMo, a unified multimodal framework combining residual FSQ motion tokenizer and scalable masked modeling Transformer for high-quality motion synthesis from any modality combination.

- **[arXiv May 2026](https://arxiv.org/abs/2605.28548)** GEM: Generative Supervision Helps Embodied Intelligence. A generative supervision embodied vision-language model that integrates depth map generation into VLM pretraining, demonstrating superior task execution in both simulation and real-world evaluations.

- **[arXiv May 2026](https://arxiv.org/abs/2605.28272)** EchoAvatar: Real-time Generative Avatar Animation from Audio Streams. Proposes a unified streaming architecture synthesizing continuous full-body motion from incremental audio input, supporting seamless speech and music generalization with explicit LLM semantic control.

- **[arXiv May 2026](https://arxiv.org/abs/2605.26933)** Diff-Tracking: Leveraging Text-to-Image Diffusion Models for Unsupervised Visual Object Tracking. Proposes Diff-Tracking, leveraging rich semantic knowledge from pretrained text-to-image diffusion models for unsupervised visual object tracking via cross-attention mechanisms.

- **[arXiv May 2026](https://arxiv.org/abs/2605.15153)** Pelican-Unified 1.0: A Unified Embodied Intelligence Model for Understanding, Reasoning, Imagination and Action. The Beijing Humanoid Robot Innovation Center's first embodied foundation model, trained under a unified training paradigm, integrates understanding, reasoning, imagination, and action generation into a single architecture and ranks first on the WorldArena imagination benchmark.

- **[arXiv May 2026](https://arxiv.org/abs/2605.14211)** ASH: Agents that Self-Hone via Embodied Learning. A self-improving embodied agent framework that learns inverse dynamics from self-generated trajectories and extracts supervision from unlabeled web videos for long-horizon embodied learning.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13778)** Realtime-VLA FLASH: Speculative Inference Framework for Diffusion-based VLAs. A speculative inference framework that introduces a lightweight draft model and parallel verification with the main model, reducing average task-level latency to 19.1 ms and achieving a 3x speedup, with real conveyor-belt sorting validation.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13757)** FrameSkip: Learning from Fewer but More Informative Frames in VLA Training. A data-layer frame selection framework that scores frames using action change, visual consistency, and task progress, retaining only 20% of frames while still reaching a 76.15% macro-average success rate.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13548)** AttenA+: Rectifying Action Inequality in Robotic Foundation Models. A speed-aware action-attention framework that prioritizes kinematically critical motion segments; as a plug-in method it raises OpenVLA-OFT to 98.6% and shows robust results on Franka.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13403)** RotVLA: Rotational Latent Action for Vision-Language-Action Model. A VLA framework built on SO(n) rotational latent actions that provides continuity, compositionality, and geometric alignment with real action dynamics, reaching 98.2% on LIBERO with only 1.7B parameters.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13382)** BlockVLA: Accelerating Autoregressive VLA via Block Diffusion Finetuning. A block-diffusion approach that adapts autoregressive backbones into efficient discrete diffusion policies, enabling within-block parallel denoising and delivering 3.3x faster inference on LIBERO and SimplerEnv.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13276)** D-VLA: A High-Concurrency Distributed Asynchronous Reinforcement Learning Framework for Vision-Language-Action Models. A high-concurrency distributed asynchronous RL framework for VLAs that isolates simulation and optimization through “planar decoupling” and uses a four-thread asynchronous swimlane pipeline to preserve linear scaling at trillion-parameter scale.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13119)** Towards Long-horizon Embodied Agents with Tool-Aligned Vision-Language-Action Models (VLAs-as-Tools). A framework that assigns long-horizon tasks to a high-level VLM plus a family of specialized VLA tools; tool-aligned post-training improves pi_0.5 by 4.8 points on LIBERO-Long and by 23.1 points on RoboTwin.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13105)** What to Ignore, What to React: Visually Robust RL Fine-Tuning of VLA Models (PAIR-VLA). PAIR-VLA addresses visual shift with invariance terms and sensitivity objectives, improving average performance by 16.62% on ManiSkill3 for pi_0.5 and by 9.10% for OpenVLA.

- **[arXiv May 2026](https://arxiv.org/abs/2605.10332)** EmbodiSkill: Skill-Aware Reflection for Self-Evolving Embodied Agents. A skill self-evolution framework for embodied agents that distinguishes skill-content errors from execution failures through skill-aware reflection, reaching a 93.28% task success rate on ALFWorld.

- **[arXiv May 2026](https://arxiv.org/abs/2605.00416)** Learning while Deploying: Fleet-Scale Reinforcement Learning for Generalist Robot Policies. Introduces Learning while Deploying, a fleet-scale reinforcement learning framework for generalist robot policies.

- **[arXiv May 2026](https://arxiv.org/abs/2605.00321)** Embodied Interpretability: Linking Causal Understanding to Generalization in Vision-Language-Action Models. A study of VLA interpretability that examines how causal understanding connects to generalization.

- **[arXiv May 2026](https://arxiv.org/abs/2605.00078)** Being-H0.7: A Latent World-Action Model from Egocentric Videos. Introduces Being-H0.7, a latent world-action model that incorporates world modeling with real-world deployment in mind.

### [Qwen-VLA: A Unified Embodied Foundation Model](https://arxiv.org/abs/2605.30280)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A unified embodied foundation model spanning manipulation, navigation and trajectory prediction in a single model.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">May 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Alibaba Qwen (Tongyi Qianwen) team</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Qwen3.5-4B VLM + 1.15B DiT flow-matching action decoder</strong> (~5.1B total)</li><li>Four-stage training: T2A text-to-action pretraining → CPT → SFT → RL</li><li>Unifies manipulation, navigation and trajectory prediction into an action-trajectory framework</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO <strong>97.9%</strong>, Simpler-WidowX <strong>73.7%</strong>, RoboTwin Easy/Hard 86.1%/87.2%</li><li>Average real-robot ALOHA OOD success rate <strong>76.9%</strong>, outperforming GR00T N1.6 and π0.5</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Qwen-VLA-Base / Instruct; training data 10K+ hours from multiple sources (manipulation trajectories, human demonstrations such as Ego4D, simulation, VLN, VL); open-source (QwenLM/Qwen-VLA)</td></tr>
</tbody>
</table>

- **[arXiv April 2026](https://arxiv.org/abs/2604.27792)** MotuBrain: An Advanced World Action Model for Robot Control. Introduces MotuBrain, a world-action model focused on long-horizon tasks that leverages heterogeneous data to improve task success.

- **[arXiv April 2026](https://arxiv.org/abs/2604.24921)** libra-vla: achieving learning equilibrium via asynchronous coarse-to-fine dual-system. Introduces libra-vla, an asynchronous coarse-to-fine dual-system architecture for open-world settings that aims to improve robustness.

- **[arXiv April 2026](https://arxiv.org/abs/2604.24622)** CF-VLA: Efficient Coarse-to-Fine Action Generation for Vision-Language-Action Policies. A coarse-to-fine action generation method for VLA policies that targets multi-step execution and improved task success.

- **[arXiv April 2026](https://arxiv.org/abs/2604.24447)** Characterizing Vision-Language-Action Models across XPUs: Constraints and Acceleration for On-Robot Deployment. A study of deploying VLA models across XPUs, focusing on hardware constraints, efficiency, and acceleration for on-robot use.

- **[arXiv April 2026](https://arxiv.org/abs/2604.24182)** $M^2$-VLA: Boosting Vision-Language Models for Generalizable Manipulation via Layer Mixture and Meta-Skills. A manipulation-oriented VLA approach that improves generalization through layer mixture and meta-skills.

- **[arXiv April 2026](https://arxiv.org/abs/2604.23272)** Modular Sensory Stream for Integrating Physical Feedback in Vision-Language-Action Models. A VLA extension that integrates physical feedback through a modular sensory stream to better support tactile interaction.

- **[arXiv April 2026](https://arxiv.org/abs/2604.23121)** Breaking Lock-In: Preserving Steerability under Low-Data VLA Post-Training. Addresses the lock-in effect in low-data VLA post-training by preserving visual grounding and adding contrastive prompt guidance at test time to reduce overfitting to training objects and spatial targets.

- **[arXiv April 2026](https://arxiv.org/abs/2604.23073)** RL Token: Bootstrapping Online RL with Vision-Language-Action Models. Introduces RL Token, an efficiency-oriented method that constrains action generation with sparse spatial anchors to improve task success.

- **[arXiv April 2026](https://arxiv.org/abs/2604.21741)** Hi-WM: Human-in-the-World-Model for Scalable Robot Post-Training. Uses an action-conditioned world model to post-train general robot policies inside a closed-loop imagined environment, moving human correction from costly real execution to reusable model-internal revisions.

- **[arXiv April 2026](https://arxiv.org/abs/2604.21391)** From Noise to Intent: Anchoring Generative VLA Policies with Residual Bridges. Introduces the ResVLA residual-bridge architecture, creating an explicit transition between high-level semantic understanding and low-level physical control to improve alignment and representation efficiency in generative VLAs.

- **[arXiv April 2026](https://arxiv.org/abs/2604.21241)** CorridorVLA: Explicit Spatial Constraints for Generative Action Heads via Sparse Anchors. Adds sparse spatial anchors and explicit tolerance corridors to generative action heads, using interpretable physical constraints to improve action alignment and task success in VLA policies.

- **[arXiv April 2026](https://arxiv.org/abs/2604.21232)** ReCAPA: Hierarchical Predictive Correction to Mitigate Cascading Failures. A hierarchical predictive-correction framework for multi-step VLA execution that uses anticipatory alignment and planning to reduce cascading failures.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20834)** PokeVLA: Empowering Pocket-Sized Vision-Language-Action Model with Comprehensive World Knowledge Guidance. A compact VLA model for lightweight deployment that uses world-knowledge guidance to strengthen high-level understanding, spatial perception, and manipulation under tight parameter budgets.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20627)** Occupancy Reward Shaping: Improving Credit Assignment for Offline Goal-Conditioned Reinforcement Learning. A reward shaping method for offline goal-conditioned RL that extracts temporal geometric structure from world-model occupancy measures to ease sparse-reward credit assignment.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20246)** Cortex 2.0: Grounding World Models in Real-World Industrial Deployment. A world-model framework for long-horizon industrial manipulation that shifts from reactive control to plan-and-act, improving cross-task and cross-embodiment execution stability by generating candidate futures.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20100)** JoyAI-RA 0.1: A Foundation Model for Robotic Autonomy. A VLA foundation model for open-world robotic autonomy that organizes multi-embodiment data and cross-embodiment training to mitigate insufficient data diversity and poor generalization.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20012)** EmbodiedMidtrain: Bridging the Gap between Vision-Language Models and Vision-Language-Action Models via Mid-training. Introduces a mid-training stage between VLMs and VLAs to reduce distribution mismatch and improve downstream action modeling.

- **[arXiv April 2026](https://arxiv.org/abs/2604.19683)** Mask World Model: Predicting What Matters for Robust Robot Policy Learning. A masked world model for robot policy learning that predicts only the state changes most relevant to decision-making, improving both training efficiency and policy robustness.

- **[arXiv Apr 2026](https://arxiv.org/abs/2604.16484)** DexWorldModel: Causal Latent World Modeling towards Automated Learning of Embodied Tasks. Proposes CLWM using DINOv3 features as generative targets to disentangle interaction semantics from visual noise, with dual-state TTT memory for O(1) long-horizon footprint and speculative asynchronous inference cutting blocking latency by ~50%.

- ★ **[ICML May 2025](https://arxiv.org/abs/2505.06412)** DiffusionVLA: Scaling Robot Foundation Models via Unified Diffusion and Autoregression. A unified diffusion-and-autoregression framework that scales robot foundation models and reaches 63.7% zero-shot pick accuracy on 102 unseen objects.

- **[arXiv April 2026](https://arxiv.org/abs/2604.08168)** ViVa: A Video-Generative Value Model for Robot Reinforcement Learning. A video-generative value model that uses spatiotemporal priors from pretrained video generators for value estimation, delivering strong gains on real-world box assembly tasks.

- **[arXiv April 2026](https://arxiv.org/abs/2604.07799)** Learning Without Losing Identity: Capability Evolution for Embodied Agents. A new capability-centric evolution paradigm for embodied agents that introduces modular capability blocks for continual learning, raising success rate from 32.4% to 91.3% over 20 iterations with zero policy drift.

- ★ **[CVPR April 2026](https://arxiv.org/abs/2604.07774)** RoboAgent: Chaining Basic Capabilities for Embodied Task Planning. A VLM capability-chaining framework for embodied task planning that decomposes complex planning into sequences of basic vision-language questions for more transparent and controllable reasoning.

- **[arXiv April 2026](https://arxiv.org/abs/2604.07430)** HY-Embodied-0.5: Embodied Foundation Models for Real-World Agents. A VLM family designed for real-world embodied agents, built with a MoE architecture and available in 2B and 32B sizes, with strong results across 22 benchmarks.

- **[arXiv March 2026](https://arxiv.org/abs/2603.29844)** DIAL: Decoupling Intent and Action via Latent World Modeling for End-to-End VLA. Introduces DIAL, a latent-world-modeling approach for end-to-end VLAs focused on real-world deployment and stronger generalization.

- **[arXiv March 2026](https://arxiv.org/abs/2603.27670)** ProgressVLA: Progress-Guided Diffusion Policy for Vision-Language Robotic Manipulation. A progress-guided diffusion-policy VLA that uses a pretrained progress estimator and differentiable progress guidance to become progress-aware on long-horizon manipulation tasks.

- **[arXiv March 2026](https://arxiv.org/abs/2603.20711)** RoboECC: Multi-Factor-Aware Edge-Cloud Collaborative Deployment for VLA Models. An edge-cloud collaborative deployment framework for VLA models that co-optimizes model partitioning and network awareness to balance real-time performance with inference quality under bandwidth fluctuations.

- **[arXiv March 2026](https://arxiv.org/abs/2603.17573)** HeiSD: Hybrid Speculative Decoding for Embodied Vision-Language-Action Models with Kinematic Awareness. Introduces HeiSD, a kinematics-aware hybrid speculative decoding method for embodied VLAs aimed at more efficient inference.

- **[arXiv March 2026](https://arxiv.org/abs/2603.17192)** Not All Features Are Created Equal: A Mechanistic Study of Vision-Language-Action Models. A mechanistic interpretability study of VLA internals that analyzes how different attention heads specialize in instruction following, object interaction, and robot control.

- **[arXiv March 2026](https://arxiv.org/abs/2603.01581)** KERV: Kinematic-Rectified Speculative Decoding for Embodied VLA Models. Injects robot kinematics into speculative decoding for VLAs, using kinematic prediction and threshold-based correction to reduce re-inference overhead while preserving success rate.

- **[arXiv March 2026](https://arxiv.org/abs/2603.00376)** NeuroHex: A Brain-Inspired Hex Coordinate System to Enable Highly Computationally-Efficient World Models for Continuous Online-Adaptive Learning. Introduces NeuroHex, a highly efficient, hierarchically designed world modeling approach inspired by brain-like hex coordinates.

- **[arXiv February 2026](https://arxiv.org/abs/2602.14979)** RynnBrain: Open Embodied Foundation Models. Open embodied spatiotemporal foundation models that unify egocentric understanding, spatiotemporal localization, physical reasoning, and physically grounded planning inside one framework.

- **[arXiv February 2026](https://arxiv.org/abs/2602.11075)** RISE: Self-Improving Robot Policy with Compositional World Model. A self-improving robot policy framework driven by a compositional world model that generates experience internally and iteratively improves policies for better generalization and adaptation.

- **[arXiv February 2026](https://arxiv.org/abs/2602.09971)** VLA-JEPA: Enhancing Vision-Language-Action Model with Latent World Model. Integrates JEPA into VLA models so world dynamics can be predicted in latent space, improving generalization and robustness.

- **[arXiv February 2026](https://arxiv.org/abs/2602.04315)** GeneralVLA: Generalizable Vision-Language-Action Models with Knowledge-Guided Trajectory Planning. A hierarchical VLA model with knowledge-guided trajectory planning that enables zero-shot manipulation and automatic data generation without real robot data.

- **[arXiv January 2026](https://arxiv.org/abs/2601.18692)** A Pragmatic VLA Foundation Model. This paper presents LingBot-VLA, trained on about 20,000 hours of real-world data across nine dual-arm setups, with an emphasis on training efficiency and real-world generalization.

- **[arXiv January 2026](https://arxiv.org/abs/2601.12993)** Being-H0.5: Scaling Human-Centric Robot Learning for Cross-Embodiment Generalization. A human-centric cross-embodiment VLA foundation model trained on a 35,000-hour multimodal dataset spanning 30 embodiments, reaching 98.9% success on LIBERO.

- **[arXiv January 2026](https://arxiv.org/abs/2601.04052)** Stable Language Guidance for Vision-Language-Action Models. Introduces a residual semantic-guidance framework that decouples physical affordance from semantic execution to stabilize language guidance in VLA models.

- **[arXiv November 2025](https://arxiv.org/abs/2511.18112)** EchoVLA: Vision-Language-Action Model with Synergistic Declarative Memory. A VLA model augmented with declarative memory that reduces forgetting in long-horizon tasks through an external memory module.

- **[arXiv November 2025](https://arxiv.org/abs/2511.17502)** RynnVLA-002: A Unified Vision-Language-Action and World Model. A unified VLA-and-world-model framework in which the world model predicts future image states from actions and visual inputs to refine action generation.

- **[arXiv November 2025](https://arxiv.org/abs/2511.01718)** Unified Diffusion VLA: Vision-Language-Action Model via Joint Discrete Denoising Diffusion Process. A VLA model that unifies understanding, generation, and action through a joint discrete denoising diffusion process.

### [π_RL: Online RL Fine-tuning for Flow-based Vision-Language-Action Models](https://arxiv.org/abs/2510.25889)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Online RL fine-tuning framework for flow-based VLAs (π0 / π0.5).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Oct 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University, Peking University, et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Flow-Noise</strong>: models the denoising process as a discrete-time MDP with a learnable noise network for exact log-likelihood computation</li><li><strong>Flow-SDE</strong>: couples denoising with agent-environment interaction as a two-layer MDP, using ODE-to-SDE conversion for efficient RL exploration</li><li>Tackles the intractable action log-likelihood of flow matching, enabling online RL for large-scale flow-based VLAs</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>RL fine-tuning yields significant improvements in both <strong>in-distribution and out-of-distribution</strong> settings across benchmarks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">πRL fine-tuning framework (built on open models such as π0 / π0.5)</td></tr>
</tbody>
</table>

- **[arXiv October 2025](https://arxiv.org/abs/2510.25122)** NanoVLA: Routing Decoupled Vision-Language Understanding for Nano-sized Generalist Robotic Policies. A lightweight VLA architecture that combines decoupled vision-language understanding with dynamic routing, delivering up to 52x faster edge inference while reducing parameters by 98%.

- **[arXiv October 2025](https://arxiv.org/abs/2510.12710)** Reflection-Based Task Adaptation for Self-Improving VLA. Uses a two-path design with failure-driven reflective RL and success-driven quality-guided SFT to enable fast autonomous task adaptation in VLA models.

- **[arXiv October 2025](https://arxiv.org/abs/2510.10274)** X-VLA: The First Soft-Prompted Robot Foundation Model for Any Robot, Any Task. A soft-prompt-based robot foundation model that generalizes across robots and tasks through parameter-efficient adaptation.

- **[arXiv October 2025](https://arxiv.org/abs/2510.07778)** IntentionVLA: Embodied Intention Reasoning for Human-Robot Interaction. A VLA model for embodied intention reasoning that improves fluency and safety in human-robot collaboration.

- **[arXiv October 2025](https://arxiv.org/abs/2510.01623)** VLA-R1: Enhancing Reasoning in Vision-Language-Action Models. A reasoning-enhanced VLA that uses RLVR and GRPO to optimize reasoning and execution jointly, and releases the VLA-CoT-13K chain-of-thought supervision dataset.

- **[arXiv September 2025](https://arxiv.org/abs/2509.15293)** FoMER: How Good are Foundation Models in Step-by-Step Embodied Reasoning. Introduces the FoMER benchmark to evaluate step-by-step reasoning by large language models in complex embodied decision-making settings.

- **[arXiv September 2025](https://arxiv.org/abs/2509.11767)** WALL-OSS: Igniting VLMs toward the Embodied Space. An end-to-end embodied foundation model that uses large-scale multimodal pretraining to improve embodied perception, language-action association, and robust manipulation.

- ★ **[ICLR September 2025](https://arxiv.org/abs/2509.09332)** OmniEVA: Embodied Versatile Planner via Task-Adaptive 3D-Grounded and Embodiment-aware Reasoning. Introduces task-adaptive 3D grounding and embodiment-aware reasoning, using a gated router to selectively regulate 3D fusion based on context for context-aware grounding and planning.

- ★ **[NeurIPS September 2025](https://arxiv.org/abs/2509.08844)** EfficientVLA: Training-Free Acceleration and Compression for Vision-Language-Action Models. A training-free acceleration framework for VLA inference that achieves 1.93x speedup and a 28.9% reduction in FLOPs.

- **[arXiv July 2025](https://arxiv.org/abs/2507.08421)** SwitchVLA: Execution-Aware Task Switching for Vision-Language-Action Models. A VLA framework for execution-aware task switching.

- **[arXiv July 2025](https://arxiv.org/abs/2507.01424)** TriVLA: A Triple-System Vision-Language-Action Model with Episodic World Modeling. A triple-system VLA architecture spanning perception, world modeling, and action, where episodic world models strengthen long-horizon task planning.

### [SmolVLA: A Vision-Language-Action Model for Affordable and Efficient Robotics](https://arxiv.org/abs/2506.01844)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A community-driven, low-cost compact VLA trainable on a single GPU and deployable on consumer hardware.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jun 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Hugging Face, Sorbonne University</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Trainable on a single GPU</strong>, deployable on consumer GPUs/CPUs</li><li>An asynchronous inference stack decouples perception from action execution</li><li>Trained with community-crowdsourced data (LeRobot ecosystem)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Matches VLAs <strong>10×</strong> its size across simulation and real-robot benchmarks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">SmolVLA (integrated into LeRobot, open-sourced)</td></tr>
</tbody>
</table>
### [WorldVLA: Towards Autoregressive Action World Model](https://arxiv.org/abs/2506.21539)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Unifies VLA and world models in a single autoregressive framework for bidirectional image-action understanding and generation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jun 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Alibaba DAMO Academy, Hupan Lab, Zhejiang University</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Three tokenizers (image/text/action) sharing one vocabulary</strong></li><li>An <strong>action attention masking</strong> strategy suppresses error accumulation in action-chunk generation</li><li>Outperforms OpenVLA without large-scale pretraining</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LIBERO grasp success rate <strong>+4%</strong> over an action-only model with the same backbone</li><li>Video generation FVD reduced by <strong>10%</strong></li><li>Masking strategy lifts action-chunk success by <strong>4%~23%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">WorldVLA (code open-sourced, alibaba-damo-academy)</td></tr>
</tbody>
</table>
- **[arXiv June 2025](https://arxiv.org/abs/2506.04500)** Don't Do That. Guiding Embodied Systems through Large Language Model-based Constraint Generation. Introduces the STPR constraint-generation framework, using LLMs to translate natural-language constraints into executable Python functions for point-cloud representations and classical search-based navigation.

- **[arXiv June 2025](https://arxiv.org/abs/2506.00411)** LoHoVLA: Vision-Language-Action Model for Long-Horizon Embodied Tasks. A VLA model tailored for long-horizon embodied tasks, using hierarchical action prediction to mitigate error accumulation in compound tasks.

### [Knowledge Insulating Vision-Language-Action Models: Train Fast, Run Fast, Generalize Better](https://arxiv.org/abs/2505.23705)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Fixes action experts destroying VLM pretrained knowledge — the π0.5 + KI training recipe.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">May 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence (π0 team)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>3B</strong> VLM backbone + <strong>300M</strong> flow-matching action expert</li><li>Action-expert gradients <strong>do not flow back</strong> to the backbone (stop-gradient insulation)</li><li>Backbone quickly acquires motion representations via FAST discrete action tokens, co-trained with web-scale VLM data</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>7.5×</strong> fewer training steps than π0</li><li>Retains flow-matching inference speed; best language following and OOD generalization (shirt folding, bussing real-robot tasks)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">π0.5 + KI (weights released via PI)</td></tr>
</tbody>
</table>
- **[arXiv May 2025](https://arxiv.org/abs/2505.03500)** VLAs are Confined yet Capable of Generalizing to Novel Instructions. A study of VLA models that evaluates how they remain constrained while still generalizing to novel instructions under a unified setup.

### [GR00T N1.5: World Model-Enhanced VLA](https://research.nvidia.com/labs/gear/gr00t-n15/)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GR00T N1 upgrade with a frozen VLM plus world modeling and synthetic neural trajectories, doubling the language-following rate.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">May 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA GEAR Lab</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>World model + action expert fusion</strong>: the VLM (Eagle 2.5) is trained frozen to preserve language capability, while a DiT action expert outputs continuous actions</li><li><strong>FLARE future latent representation alignment</strong> (implicit world modeling), unlocking learning from human first-person videos</li><li>DreamGen / Cosmos generate neural trajectories as synthetic data</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Real-robot GR-1 language instruction following <strong>46.6% → 93.3%</strong> (overall success 43.3% → 83.0%)</li><li>Language Table 52.8% → <strong>93.2%</strong>; success on 12 DreamGen new tasks 13.1% → 38.3%</li><li>Upgrade completed with synthetic data in just <strong>36 hours</strong> (nearly 3 months of human effort)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model GR00T-N1.5-3B; datasets Open X-Embodiment, AgiBot-Beta, DexMG, DreamGen neural trajectories, NVIDIA Physical AI data (24,000 simulated trajectories); open-source</td></tr>
</tbody>
</table>

### [π0.5: Scaling VLA with Heterogeneous Data](https://arxiv.org/abs/2504.16054)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">π0's open-world upgrade, co-training on heterogeneous data enables robots to complete long-horizon household tasks.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">April 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Heterogeneous data co-training</strong>: multi-robot data + high-level sub-task labels + verbal instructions + web VL data</li><li>Pretraining with <strong>FAST discrete action tokens</strong>, post-training with a flow matching continuous action expert</li><li>Two-level inference, ~3.3B parameters (SigLIP 400M + Gemma 2B + 300M expert)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>First time an end-to-end system performs <strong>10-15 minute long-horizon tasks</strong> in a new home (cleaning kitchen/bedroom)</li><li>OOD sub-task success rate <strong>94%</strong>, close to the control group in seen test environments</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model π0.5; training data ~400 hours of mobile manipulation (across ~100 homes) + cross-embodiment and web data; partially open-sourced in openpi</td></tr>
</tbody>
</table>

### [Gemini Robotics: Bringing AI into the Physical World](https://arxiv.org/abs/2503.20020)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A VLA generalist family built on Gemini 2.0, bringing multimodal reasoning to real-robot control.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Mar 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind (Gemini Robotics Team)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Two models: the VLA main model and the <strong>Gemini Robotics-ER</strong> embodied reasoning variant</li><li><strong>3D understanding</strong>: multi-view correspondence, 3D bounding boxes, grasp detection</li><li>New short-horizon tasks learned from only <strong>100 demonstrations</strong></li><li>Adaptable to new embodiments (dual-arm platforms, high-DoF humanoids)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Solves long-horizon dexterous tasks (origami fox, card games)</li><li>ER model enables zero-shot robot code generation and few-shot in-context adaptation</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Gemini Robotics (closed-source, API access)</td></tr>
</tbody>
</table>
- **[arXiv March 2025](https://arxiv.org/abs/2503.12438)** ChatVLA: Multimodal Understanding and Robot Control. Conversational multimodal understanding and robot control.

- **[arXiv March 2025](https://arxiv.org/abs/2503.04123)** SmolVLA: Efficient Vision-Language-Action Models for Robotics. A lightweight VLA model for robotics that is suitable for edge deployment.

### [AgiBot GO-1: Open-Sourced Generalist Embodied Agent](https://arxiv.org/abs/2503.06669)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">AgiBot's open-sourced generalist embodied foundation model, with million-scale real-robot data and latent action representations.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">March 2025 (released at WRC 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">AgiBot + OpenDriveLab (Shanghai AI Lab)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>ViLLA architecture</strong>: InternVL-2B VLM + Latent Planner + diffusion Action Expert</li><li>Companion <strong>AgiBot World</strong> million-scale real-robot dataset (1M+ trajectories, 217 tasks, 5 scenarios)</li><li>Latent action representation scales predictably with data volume</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Pretraining on AgiBot World improves over Open X-Embodiment by an average <strong>30%</strong></li><li>GO-1 exceeds <strong>60%</strong> success on complex tasks, a 32% improvement over RDT</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model GO-1; datasets AgiBot World (1M+ trajectories) and AgiBot Digital World simulation data; datasets and model fully open-sourced</td></tr>
</tbody>
</table>

### [GR00T N1: An Open Foundation Model for Generalist Humanoid Robots](https://arxiv.org/abs/2503.14734)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">The first open humanoid VLA foundation model, with fast-slow dual systems supporting multi-step manipulation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">March 2025 (released at GTC 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA GEAR Lab (led by Jim Fan and Yuke Zhu)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Dual-system architecture</strong>: System 2 is a VLM (Eagle-2, 10Hz planning), System 1 is a diffusion Transformer action expert (120Hz closed-loop control)</li><li><strong>LAPA latent action pretraining</strong>, learning from unlabeled human videos</li><li>Data pyramid: a mixture of real teleoperation + synthetic + internet data</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>The public GR00T-N1-2B has ~<strong>2.2B parameters</strong>; 63.9ms to sample 16 actions on an L40 GPU</li><li>Pretraining ~50K H100 GPU hours; surpasses SOTA imitation baselines across embodied simulation benchmarks, deployed on Fourier GR-1</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model GR00T-N1-2B; datasets Open X-Embodiment, AgiBot-Alpha, 181,000+ unlabeled internet videos; open-source (Apache 2.0)</td></tr>
</tbody>
</table>

### [DexVLA: Vision-Language Model with Plug-In Diffusion Expert for General Robot Control](https://arxiv.org/abs/2502.05855)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A billion-parameter diffusion action expert with embodied curriculum learning for cross-embodiment VLA.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Feb 2025 (CoRL 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Midea Group, East China Normal University</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>1B-parameter</strong> multi-head diffusion expert, one head per embodiment</li><li>Three-stage curriculum: cross-embodiment pretraining → embodiment alignment → task post-training</li><li>Sub-step reasoning autonomously decomposes long-horizon tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Outperforms OpenVLA, Octo, Diffusion Policy across single-arm / bimanual / dexterous embodiments</li><li>New embodiments learn complex skills from only <strong>100 demos</strong></li><li>Pretrained on just <strong>100 hours</strong> of demonstrations; completes 2-minute+ laundry-folding long-horizon tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">DexVLA (code open-sourced, dex-vla.github.io)</td></tr>
</tbody>
</table>
### [Helix: A Vision-Language-Action Model for Generalist Humanoid Control](https://www.figure.ai/news/helix)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">The first dual-system end-to-end VLA achieving whole-body high-speed dexterous control on humanoids.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">February 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Figure AI</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>System 1 / System 2 dual-system architecture</strong>: S2 is a 7B internet-pretrained VLM (7-9 Hz scene understanding), S1 is an 80M visuomotor Transformer (200 Hz continuous control), jointly trained and asynchronously deployed</li><li>Directly outputs <strong>35-DoF whole-upper-body continuous control</strong></li><li>Only ~<strong>500 hours</strong> of multi-robot teleoperation data (less than 5% of previous VLA datasets)</li><li>Runs entirely on <strong>onboard low-power GPU</strong> (no cloud needed)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Two robots sharing the same weights perform <strong>zero-shot collaboration</strong> on grocery stocking</li><li>Zero-shot grasping of thousands of unseen small objects under natural language prompts</li><li>Coordinates the whole-body 35-DoF action space at 200 Hz</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Helix (weights not open-sourced); self-collected ~500 hours of teleoperation data; S2 based on an open-source, open-weight VLM</td></tr>
</tbody>
</table>

### [Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models](https://arxiv.org/abs/2502.19417)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A hierarchical VLM+VLA framework that enables robots to follow complex instructions in the open world and respond to real-time feedback.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">February 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence + Stanford + Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Hierarchical VLA</strong>: a high-level VLM reasons over complex open-ended instructions and outputs atomic language commands, executed by a low-level π0 VLA (PaliGemma-3B + flow matching action expert)</li><li>Uses a large VLM to <strong>backward-synthesize</strong> complex instruction / human-robot interjection data for training the high-level policy</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Validated on three platforms: single-arm, dual-arm, and dual-arm mobile</li><li>On complex-prompt and in-execution feedback tasks, instruction accuracy and task progress significantly surpass the GPT-4o high-level approach and flat VLA baselines</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Hi Robot; low-level policy π0; synthetic data generation scheme; full weights not released (ICML 2025)</td></tr>
</tbody>
</table>

### [UP-VLA: A Unified Understanding and Prediction Model for Embodied Agent](https://arxiv.org/abs/2501.18867)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A VLA pretraining paradigm unifying multimodal understanding and future prediction objectives.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jan 2025 (ICML 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University, Shanghai Qi Zhi Institute</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Dual visual pathways: <strong>CLIP-ViT continuous + VQ-GAN discrete</strong> encodings (Phi-1.5 backbone)</li><li>Understanding-enhanced prompting mechanism</li><li>Mixed pretraining on Bridge data + LLaVA-665k</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CALVIN ABC→D <strong>+33%</strong> over prior SOTA</li><li>Marked gains on real-world tasks requiring precise spatial information</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UP-VLA (code open-sourced)</td></tr>
</tbody>
</table>
- **[arXiv January 2025](https://arxiv.org/abs/2409.20537)** HPT: Hierarchical Pre-trained Transformer for Robot Learning. A hierarchical pretraining transformer architecture that uses layered representations to support efficient transfer across robot tasks.

- ★ **[CVPR January 2025](https://arxiv.org/abs/2501.10105)** UniAct: Universal Actions for Enhanced Embodied Foundation Models. Introduces a universal action space that maps low-level controls from different robots into normalized action representations, improving cross-platform generalization.

- **[arXiv January 2025](https://arxiv.org/abs/2501.08132)** HiMoE-VLA: Hierarchical Mixture-of-Experts for Vision-Language-Action Policies. A hierarchical mixture-of-experts architecture for VLA policies.

### [SpatialVLA: Exploring Spatial Representations for Visual-Language-Action Model](https://arxiv.org/abs/2501.15830)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A generalist manipulation model that endows VLA with 3D spatial intelligence via Ego3D position encoding and an adaptive action grid.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">January 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shanghai AI Laboratory (with Fudan University, Shanghai Jiao Tong University, Zhejiang University, etc.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Proposes <strong>Ego3D position encoding</strong>: injects depth 3D information in the egocentric camera coordinate frame, avoiding robot-camera extrinsic calibration</li><li>Uses an <strong>adaptive action grid</strong> to discretize continuous actions into spatial action tokens, supporting cross-embodiment alignment</li><li>Pretrains a generalist policy on <strong>1.1M real robot episodes</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Comprehensive evaluation across a 7-task suite, 16 real-world tasks, and 48 simulated setups</li><li><strong>73%</strong> spatial-prompt task understanding accuracy on Franka, surpassing RT-1-X, Octo, and OpenVLA zero-shot</li><li>Fewer action tokens and faster inference than baselines</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model SpatialVLA (open-sourced); based on 1.1M episodes of mixed data such as Fractal + Bridge (RSS 2025)</td></tr>
</tbody>
</table>

### [Moto: Latent Motion Token as the Bridging Language for Learning Robot Manipulation from Videos](https://arxiv.org/abs/2412.04445)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Unsupervised "latent motion tokens" bridge video pretraining to real robot control.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Dec 2024 (ICCV 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">University of Hong Kong, Tencent AI Lab</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>A VQ-VAE-style <strong>Latent Motion Tokenizer</strong> compresses inter-frame motion into discrete tokens</li><li>Moto-GPT autoregressively predicts the next motion token</li><li>Co-fine-tuning connects motion priors to real control</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Only <strong>98M parameters</strong>, matches <strong>55B</strong> models (RT-2-X) on SIMPLER and CALVIN</li><li>Human-video pretraining further boosts manipulation performance</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Moto (code open-sourced)</td></tr>
</tbody>
</table>
### [CogACT: A Foundational VLA Model for Synergizing Cognition and Action in Robotic Manipulation](https://arxiv.org/abs/2411.19650)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A componentized VLA: the VLM handles cognition while a DiT diffusion module specializes in action generation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Nov 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University, Microsoft Research Asia, et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>DINOv2+SigLIP vision, LLaMA-2 language, DiT action module (up to <strong>300M parameters</strong>, 7B total)</li><li>Adaptive Action Ensemble (AAE) strategy</li><li>Pretrained on <strong>0.4M trajectories</strong> (OXE subset)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Beats OpenVLA by <strong>35%</strong> in simulation and <strong>55%</strong> on real robots</li><li>Surpasses RT-2-X (55B) by <strong>18%</strong> absolute success in simulation</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CogACT (code and models open-sourced, cogact.github.io)</td></tr>
</tbody>
</table>
### [GR-2: A Generative Video-Language-Action Model with Web-Scale Knowledge for Robot Manipulation](https://arxiv.org/abs/2410.06158)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VLA generatively pretrained on 38M web videos, averaging 97.7% success on 100+ real manipulation tasks.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Oct 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">ByteDance Seed</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Pretrained on <strong>38M video clips / 50B+ tokens</strong> of web video (47× GR-1's 0.8M)</li><li>Joint fine-tuning for video generation and action prediction</li><li>Strong model-size scaling behavior</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>97.7%</strong> average success across <strong>100+ real tabletop tasks</strong></li><li>End-to-end bin picking: 33.3% → <strong>79.0%</strong> (vs GR-1)</li><li>CALVIN 5-task success 73.1% → <strong>85.9%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GR-2 (tech report, gr2-manipulation.github.io)</td></tr>
</tbody>
</table>
### [RoboDual: Towards Synergistic, Generalized, and Efficient Dual-System for Robotic Manipulation](https://arxiv.org/abs/2410.08001)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A synergistic dual system pairing a VLA generalist (slow) with a diffusion-transformer specialist (fast).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Oct 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shanghai AI Laboratory, Shanghai Jiao Tong University, HKU, AgiBot</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>The generalist provides high-level understanding and discrete actions; the specialist unrolls multi-step actions</li><li>The specialist has only <strong>20M trainable parameters</strong></li><li>~4Hz generalist inference, <strong>20Hz</strong> specialist execution</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Real-world success rate <strong>+26.7%</strong> over OpenVLA, <strong>+12%</strong> on CALVIN</li><li>Strong performance with only <strong>5% of demonstration data</strong></li><li><strong>3.8×</strong> control frequency</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboDual (code open-sourced)</td></tr>
</tbody>
</table>
### [π0: A Vision-Language-Action Flow Model](https://arxiv.org/abs/2410.24164)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence's first generalist policy, flow matching continuous actions enable dexterous manipulation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">October 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Physical Intelligence (π)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>PaliGemma 3B VLM + 300M action expert</strong> (~3.3B total)</li><li><strong>flow matching</strong> generates continuous actions, 50Hz high-frequency control, 50-step action chunks</li><li>10K+ hours, 8 robot platforms, 68 tasks, pretraining + post-training paradigm</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Zero-shot: tidying a table <strong>0.971</strong>, folding shirts <strong>1.0</strong>, bagging groceries <strong>0.786</strong></li><li>OpenVLA / Octo near 0 on these tasks; more than 2x improvement over π0-small</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model π0 (~3.3B) / π0-small (470M); training data proprietary 10K+ hours + Open X-Embodiment; openpi open-sourced (2025-02)</td></tr>
</tbody>
</table>

### [RDT-1B: A Diffusion Foundation Model for Bimanual Manipulation](https://arxiv.org/abs/2410.07864)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A 1.2B-parameter diffusion bimanual foundation model; cross-embodiment pretraining enables zero-shot and few-shot generalization.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">October 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University (Zhu Jun & Su Hang team)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Diffusion Transformer-based <strong>bimanual manipulation foundation model</strong>, 1.2B parameters (the largest diffusion robot foundation model at the time)</li><li>Proposes a 128-dimensional <strong>physically interpretable unified action space</strong> for cross-embodiment training</li><li><strong>Alternating Condition Injection (ACI)</strong> to balance image and language conditions</li><li>Pretraining on 46 multi-robot datasets with <strong>1M+ trajectories / ~21TB</strong>, plus fine-tuning on 66K+ self-collected bimanual trajectories</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Zero-shot cup washing with unseen cups <strong>50%</strong> (87.5% for seen cups, baseline near 0)</li><li>Cross-scene water pouring <strong>62.5%</strong> (best baseline 37.5%); instruction following 100%</li><li>Onboard RTX 4090 achieves ~6 Hz action chunks / 381 Hz action inference</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Models RDT-1B (1.2B) and RDT-170M; pretraining includes RT-1, RH20T, DROID, BridgeData V2, Open X-Embodiment subsets; fine-tuning data rdt-ft-data open-sourced (MIT)</td></tr>
</tbody>
</table>

### [TinyVLA: Towards Fast, Data-Efficient Vision-Language-Action Models for Robotic Manipulation](https://arxiv.org/abs/2409.12514)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A compact VLA family with no pretraining stage — fast and data-efficient.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Sep 2024 (RA-L 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Midea Group, East China Normal University, Beijing Humanoid Robot Innovation Center, et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Policy backbone <strong>initialized from fast multimodal models</strong> (no robot-data pretraining)</li><li>A <strong>diffusion-policy decoder</strong> attached during fine-tuning</li><li>Compact family; notably faster and more data-efficient than OpenVLA</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Comparable or better performance with strong generalization across language, novel objects, and positions</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">TinyVLA (code open-sourced, tiny-vla.github.io)</td></tr>
</tbody>
</table>
### [RoboPoint: A Vision-Language Model for Spatial Affordance Prediction for Robotics](https://arxiv.org/abs/2406.10721)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A VLM predicting spatial-affordance key points, with a fully automated data pipeline requiring no real-robot collection.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jun 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">University of Washington, NVIDIA, Allen Institute for AI (AI2)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Fully automated synthetic data pipeline</strong> — no real-robot collection needed</li><li>Point-level action space with depth-based 3D lifting</li><li>Supports navigation, manipulation, and AR downstream tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Spatial affordance accuracy beats GPT-4o/PIVOT by <strong>21.8%</strong></li><li>Downstream task success rate improved by <strong>30.5%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboPoint, Where2Place benchmark (open-sourced)</td></tr>
</tbody>
</table>
- **[arXiv June 2024](https://arxiv.org/abs/2406.06833)** RoboMatrix: Skill-Centric Robot Task Planning. A skill-centric framework for robot task planning.

### [OpenVLA: An Open-Source Vision-Language-Action Model](https://arxiv.org/abs/2406.09246)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A 7B open-source VLA that outperforms a 55B closed-source model on open data.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">June 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford + UC Berkeley + TRI + Google DeepMind + Physical Intelligence + MIT</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Based on Prismatic-7B VLM: <strong>SigLIP + DINOv2 dual vision encoders</strong> + Llama 2 7B</li><li>Finetuned on <strong>Open X-Embodiment 970K trajectories</strong></li><li>Weights / training pipeline fully open-sourced, supporting LoRA and quantization-based efficient finetuning</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Absolute <strong>16.5%</strong> improvement in success rate over RT-2-X (55B) across 29 evaluation tasks, with 7x fewer parameters</li><li>Zero-shot outperforms RT-1-X and Octo</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model OpenVLA (7B); dataset Open X-Embodiment (970K trajectories); weights and code open-sourced</td></tr>
</tbody>
</table>

### [RoboMamba: Multimodal State Space Model for Efficient Robot Reasoning and Manipulation](https://arxiv.org/abs/2406.04339)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">An efficient multimodal robot large model built on Mamba linear attention, acquiring manipulation ability with low-cost fine-tuning.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">June 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Peking University, Beijing Academy of Artificial Intelligence (BAAI)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>First to introduce the <strong>Mamba state space model</strong> into robot MLLMs, enabling linear-complexity long-sequence reasoning</li><li>End-to-end integration of a CLIP vision encoder with a Mamba language model</li><li>Fine-tuning only <strong>0.1% of parameters</strong> (3.7M policy head, ~20 minutes on a single A100) yields end-effector pose prediction</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Achieves <strong>36.3 BLEU-4</strong> on RoboVQA with 3.2B parameters</li><li>Reaches the then-SOTA in SAPIEN simulated manipulation (policy head only 7MB)</li><li>Inference ~<strong>7x</strong> faster than robot MLLMs at the time</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model RoboMamba (3.2B, open-sourced); no public dedicated dataset</td></tr>
</tbody>
</table>

- **[CoRL May 2024](https://arxiv.org/abs/2405.16789)** MC-Skill: Multi-Context Skill Learning for Vision-Language-Action. A multi-context skill-learning VLA framework that supports generalization in complex scenes.

### [Octo: An Open-Source Generalist Robot Policy](https://arxiv.org/abs/2405.12213)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">An open-source generalist robot diffusion policy, flexibly adapting to multiple sensors and action spaces.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">May 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley + Stanford + CMU + Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Transformer backbone + diffusion action decoding</strong>, supporting language / goal-image dual conditioning</li><li>First fully open-source generalist robot policy (weights, training pipeline, data)</li><li>Finetunable to new sensors (force sensing) and new action spaces</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Pretrained on Open X-Embodiment <strong>800K trajectories</strong>, evaluated on 9 real-robot platforms</li><li>Zero-shot surpasses RT-1-X and rivals RT-2-X (55B); finetuning beats suboptimal baselines by an average <strong>52%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Octo-Small (27M) / Octo-Base (93M); dataset Open X-Embodiment (800K trajectories); fully open-sourced</td></tr>
</tbody>
</table>

### [3D-VLA: A 3D Vision-Language-Action Generative World Model](https://arxiv.org/abs/2403.09631)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A generative world model connecting 3D perception, reasoning, and action for embodied AI.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Mar 2024 (ICML 2024)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UMass Amherst, Shanghai Jiao Tong University, MIT-IBM Watson AI Lab, et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Built on <strong>3D-LLM</strong> with interaction tokens</li><li>An embodied diffusion model generates target images and point clouds</li><li>Curates a <strong>2M-pair</strong> 3D-language-action instruction dataset</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Substantially outperforms baselines on held-in sets in reasoning, multimodal generation, and planning</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">3D-VLA (code and diffusion weights open-sourced on Hugging Face)</td></tr>
</tbody>
</table>
- **[arXiv February 2024](https://arxiv.org/abs/2402.06149)** GR-2: A Generative Video-Language-Action Model for Robot Manipulation. A generative video-language-action model that learns general visual representations through large-scale video pretraining before fine-tuning on robot manipulation tasks.

- **[arXiv January 2024](https://arxiv.org/abs/2401.12963)** AutoRT: Embodied Foundation Models for Large-Scale Robot Orchestration. A system for large-scale robot orchestration with foundation models, combining LLM-based task decomposition with VLM-based environment understanding to collect data across multiple robots in parallel.

### [GR-1: Unleashing Large-Scale Video Generative Pre-training for Visual Robot Manipulation](https://arxiv.org/abs/2312.13139)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">The pioneering GPT-style video generative pretraining transferred to robot manipulation (GR-2's predecessor).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Dec 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">ByteDance Seed</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>GPT-style unified Transformer: language + image sequences + robot state as input</li><li>End-to-end prediction of actions and future frames</li><li>Video pretraining on <strong>~8M Ego4D frames</strong> before fine-tuning</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CALVIN success rate <strong>88.9% → 94.9%</strong></li><li>Zero-shot unseen scenes <strong>53.3% → 85.4%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GR-1 (code open-sourced, GR1-Manipulation.github.io)</td></tr>
</tbody>
</table>
- **[arXiv November 2023](https://arxiv.org/abs/2311.01355)** RoboFlamingo: A Vision-Language Model for Open-Vocabulary Robot Control. An open-source VLA model based on Flamingo that achieves open-vocabulary robot control through vision-language model fine-tuning and few-shot learning.

- **[CoRL July 2023](https://arxiv.org/abs/2307.06135)** SayPlan: Grounding Large Language Models using 3D Scene Graphs for Scalable Robot Task Planning. Improves robot task planning by grounding large language models in 3D scene graphs.

### [RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control](https://arxiv.org/abs/2307.15818)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Actions tokenized and integrated into a VLM for co-finetuning, transferring internet knowledge to robot control for the first time.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">July 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>First to propose the <strong>VLA paradigm</strong>: actions encoded as text tokens, co-finetuned with internet vision-language data</li><li>Backbones are <strong>PaLI-X-55B</strong> and <strong>PaLM-E-12B</strong></li><li>Supports chain-of-thought multi-step reasoning</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>~6000 real-robot evaluations; average success on unseen scenes raised from 32% for RT-1 to <strong>62%</strong></li><li>Emergent capabilities (symbol / reasoning / person recognition) average <strong>60%</strong>, vs 17% for RT-1</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model RT-2 (PaLI-X-55B / PaLM-E-12B); training data robot trajectories + internet VL data; weights not released</td></tr>
</tbody>
</table>

### [VoxPoser: Composable 3D Value Maps for Robotic Manipulation with Language Models](https://arxiv.org/abs/2307.05973)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">LLM + VLM compose 3D value maps to directly plan manipulation trajectories, zero-training and zero-shot.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">July 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford (Wenlong Huang, Fei-Fei Li, Jiajun Wu team)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>LLM writes code to call the VLM, <strong>composing 3D value maps</strong> (affordance + constraint) as the objective function for motion planning</li><li><strong>Zero-training, zero-shot</strong> synthesis of 6-DoF trajectories, supporting open instructions and open objects</li><li>MPC closed-loop replanning robust to disturbances</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Average success <strong>88%</strong> across 5 real-robot task categories (70% with disturbances), vs only 24% for the LLM + action primitive baseline</li><li>Online learning reduces contact task dynamics learning from >12 hours to ~<strong>3 minutes</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Uses off-the-shelf LLM (GPT-4) + VLM (CLIP); no proprietary training data; code open-sourced (huangwl18/VoxPoser)</td></tr>
</tbody>
</table>

- **[arXiv June 2023](https://arxiv.org/abs/2306.11706)** RoboCat: A Self-Improving Foundation Agent for Robotic Manipulation. A self-improving robot foundation model that aggregates data and fine-tunes on new tasks, creating a self-improvement loop.

- **[arXiv May 2023](https://arxiv.org/abs/2305.16291)** Voyager: An Open-Ended Embodied Agent with Large Language Models. An LLM-driven framework for open-ended embodied agents in open-world environments.

- **[ICRA March 2023](https://arxiv.org/abs/2303.08734)** PromptCraft: Zero-Shot Task Planning with Large Language Models. A prompt-engineering framework for zero-shot task planning with large language models.

- ★ **[ICLR December 2022](https://arxiv.org/abs/2212.04088)** LLM-Planner: Few-Shot Grounded Planning for Embodied Agents with Large Language Models. An LLM-based method for few-shot grounded planning in embodied agents.

- ★ **[ICLR October 2022](https://arxiv.org/abs/2210.03629)** ReAct: Synergizing Reasoning and Acting in Language Models. A framework for coupling reasoning and action in language models.

- ★ **[NeurIPS October 2022](https://arxiv.org/abs/2210.03094)** VIMA: General Robot Manipulation with Multimodal Prompts. A general robot manipulation model built around multimodal prompting.

### [PaLM-E: An Embodied Multimodal Language Model](https://arxiv.org/abs/2303.03378)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">The first embodied multimodal language model, connecting continuous sensor signals into an LLM for unified planning and QA.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">March 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google Robotics + Google Research + TU Berlin</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Continuous observations such as images / robot states are encoded as vectors and injected into the pretrained PaLM embedding space</li><li>A single model unifies <strong>robot planning, VQA and captioning</strong></li><li>Cross-domain joint training enables positive transfer</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Largest model <strong>PaLM-E-562B</strong></li><li>Achieved SOTA on OK-VQA</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model PaLM-E (12B / 84B / 562B); training data RT-series robot data + internet vision-language data; not open-sourced</td></tr>
</tbody>
</table>

### [RT-1: Robotics Transformer for Real-World Control at Scale](https://arxiv.org/abs/2212.06817)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">The first large-scale multi-task real-robot Transformer policy, validating the scalability of robot policies.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">December 2022</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google (Robotics at Google / Everyday Robots)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Inputs 6 frames of images + language instructions, outputs <strong>11-dim discrete actions</strong></li><li>Lightweight architecture <strong>EfficientNet-B3 (FiLM) + TokenLearner</strong>, only 35M parameters</li><li>Collected and trained on 700+ real tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>97%</strong> success across 700+ real-robot tasks</li><li>Significant zero-shot generalization to new objects and new environments</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model RT-1 (35M); dataset RT-1 dataset; code open-sourced (google-research/robotics_transformer)</td></tr>
</tbody>
</table>

- **[CoRL September 2022](https://arxiv.org/abs/2209.07753)** Code as Policies: Language Model Programs for Embodied Control. Uses code generated by language models as policies for embodied robot control.

- **[CoRL July 2022](https://arxiv.org/abs/2207.05608)** Inner Monologue: Embodied Reasoning through Planning with Language Models. A framework for embodied reasoning and planning assisted by language models.

- **[arXiv May 2022](https://arxiv.org/abs/2205.06175)** GATO: A Generalist Agent. A single transformer model that handles 600+ tasks spanning robot control, games, and dialogue, offering one of the earliest demonstrations of a generalist agent.

- **[CoRL April 2022](https://arxiv.org/abs/2204.01691)** SayCan: Do As I Can, Not As I Say: Grounding Language in Robotic Affordances. Grounds language models in robotic affordances to execute natural-language instructions.

- **[CoRL March 2022](https://arxiv.org/abs/2203.12601)** R3M: A Universal Visual Representation for Robot Manipulation. A universal visual representation for robot manipulation pretrained on large-scale Ego4D human video, transferable to a wide range of downstream robot manipulation tasks.

<a id="manipulation" name="manipulation"></a>

## Manipulation & Teleoperation

### [Gripper-aware Vision Language Action Models](https://arxiv.org/abs/2608.24603)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Makes VLAs explicitly gripper-aware via a multi-gripper tokenizer and adapter routing for cross-gripper manipulation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">University of Liverpool AIRV Lab (with IISc, ZHAW, HUST, Physical Intelligence, et al.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Challenges VLAs' implicit <strong>"gripper-invariance" assumption</strong>: suction cups and parallel jaws are naturally different for the same goal policy</li><li>Introduces <strong>MiGA, a multi-gripper dataset</strong>: 5 gripper types, 103K demos, 36 tasks, ~5% failure demos included</li><li>GVLA adds <strong>three-layer soft-prompt multi-gripper tokenization</strong> plus <strong>dual Mixture-of-Adapters routing</strong>, balancing shared parameters and per-gripper specialization</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Avg sim success <strong>66.0%</strong> across four task suites (π0.5 base), +<strong>7.62 pp</strong> over best baseline</li><li>Unseen gripper (Robotiq 2F-85) adapts with only <strong>10 demos + 20K steps</strong>, success <strong>0.92</strong> (drops to 0.52 without adapters)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GVLA model; MiGA dataset (open on HuggingFace)</td></tr>
</tbody>
</table>

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.23108)** Curse of Precision: Scaling Law. Discovers a new scaling law for precision tasks: log(N) ∝ 1/(P - c), revealing the emergent property of precision ceiling.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.22530)** ViTacWorld: Visuo-Tactile World Models. Scales visuo-tactile world models using real and simulated data for contact-rich manipulation.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.18231)** FM-VLA: Force-based Memory. Proposes force-based memory for VLA models in contact-rich manipulation tasks.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.15641)** IMBench: Intuitive Manipulation Benchmark. A benchmark for intuitive robotic manipulation.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.11427)** EDAR: Environment-Dependent Action Representations. Associates action tokens with executable control structures and anticipated visual outcomes.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.10172)** LoRA Fine-Tuning for VLA in Industry. Studies the efficiency of LoRA fine-tuning for VLA models in industrial manipulation.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.08354)** SkillPlug: Unsupervised Skill Mining. Mines shared transferable skill libraries via skill conditioning modules for few-shot adaptation.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.04234)** SoftVTBench: Visuo-Tactile Benchmark. Safety-aware visuo-tactile benchmark for physically constrained deformable object manipulation.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.02322)** LionRock: Dynamic Data Collection. Identifies shortcut learning in VLA and proposes hybrid dynamic data collection. Accepted at IROS 2026.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.27036)** RelAfford6D: Relational Affordance Graphs. Proposes relational 6D affordance graphs for constraint-driven robotic manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.26800)** SSI-Policy: Structured Scene Interfaces. Learns structured scene interfaces for vision-language robotic manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.24742)** World Value Models. Fuses world models with value estimation for data quality assessment via temporal modeling.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.23420)** Flowing With Purpose: Latent Action Flow. Latent action guided flow matching policies for robotic manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.23157)** Bridging Semantics and Kinematics. Modular framework bridging semantics and kinematics for zero-shot manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.22540)** PolicyTrim: Policy Efficiency. Boosts intrinsic policy efficiency, reducing ineffective actions by ~50% and increasing speed by 6x.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.22136)** Wh0: Generative World Models for Hand Data. Generative world models as scalable sources of egocentric human hand manipulation data.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.20999)** Inductive Generalization for Manipulation. Proposes inductive generalization evaluation, revealing fundamental failures of VLA models on OOD tasks.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.18960)** Mem-World: Memory-Augmented World Models. Proposes 4D wrist-view memory to solve scene forgetting caused by occlusion in manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.18375)** PAIWorld: 3D World Foundation Model. Addresses 3D inconsistency in multi-view world models via geometry-aware cross-attention.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.17598)** MuseVLA: Adaptive Multimodal Sensing. Proposes adaptive multimodal sensing VLA integrating sensors as on-demand tools, achieving 80.6% on dexterous tasks.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.12109)** InDex: VLA to Dexterous Manipulation. Cross-morphology semantic inheritance framework for adapting VLA to dexterous hands via intent-conditioned diffusion.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.11396)** PLUME: Probabilistic World Modeling. Probabilistic latent unified world modeling for multi-finger dexterous manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.10363)** HiMem-WAM: Hierarchical Memory World Models. Hierarchical memory-gated world action models for robotic manipulation.

- **[arXiv May 2026](https://arxiv.org/abs/2605.30226)** BORA: Bridging Offline Reinforcement Learning and Online Residual Adaptation for Real-World Dexterous VLA Models. Combines offline reinforcement learning with online residual adaptation for efficient training of real-world dexterous vision-language-action models.

- ★ **[ICML May 2026](https://arxiv.org/abs/2605.29937)** Fisher-Preserving Guidance: Training-Free Manifold Constraints for Safe Diffusion Control. A training-free Fisher-preserving guidance method using manifold constraints for safe diffusion model control, applicable to robot motion planning.

- **[arXiv May 2026](https://arxiv.org/abs/2605.29564)** VE2VF: Vision-Enabled to Vision-Free Distillation via Real-world Reinforcement Learning for Robust Contact-Rich Manipulation. Distills vision-dependent policies into vision-free policies through real-world RL, achieving robust contact-rich manipulation.

- **[ICRA May 2026](https://arxiv.org/abs/2605.29298)** MonoDuo: Using One Robot Arm to Learn Bimanual Policies. Enables bimanual collaboration policies learning from single-arm manipulation data, reducing bimanual robot data collection costs.

- ★ **[ICML May 2026](https://arxiv.org/abs/2605.27095)** FA-OPD: Adversarial Dual On-Policy Distillation from Expressive Flow-based Teacher. Proposes FA-OPD, an adversarial dual on-policy distillation method with flow-matching teacher and lightweight MLP student co-training, surpassing strong baselines on six robot benchmarks.

- **[arXiv May 2026](https://arxiv.org/abs/2605.26478)** Learning from Demonstrations. Studies robot learning from demonstrations, exploring the application of imitation learning and behavioral cloning techniques in robot manipulation, analyzing sample efficiency and generalization capability.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13632)** Guide, Think, Act: Interactive Embodied Reasoning in Vision-Language-Action Models (GTA-VLA). An interactive VLA framework where users guide the policy with visual cues and the model generates spatial visual chains of thought, reaching 81.2% success on SimplerEnv WidowX and significantly improving OOD performance with a single visual interaction.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13452)** CUBic: Coordinated Unified Bimanual Perception and Control Framework. A unified bimanual perception-and-control framework that learns shared tokenized representations bridging perception and control, with independence and coordination emerging from the structure itself, validated on a real-world Agibot dual-arm platform.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13117)** SECOND-Grasp: Semantic Contact-guided Dexterous Grasping. A unified dexterous grasping framework that uses VLM-based semantic reasoning for coarse contact proposals and refines them with semantic-geometric consistency, reaching 98.2% and 97.7% on seen and unseen categories in DexGraspNet.

- **[arXiv May 2026](https://arxiv.org/abs/2605.00475)** MSACT: Multistage Spatial Alignment for Stable Low-Latency Fine Manipulation. Introduces MSACT, a multi-stage spatial alignment method for stable low-latency fine manipulation, with a particular focus on bimanual coordination and diffusion-based modeling.

- **[arXiv May 2026](https://arxiv.org/abs/2605.00471)** Stereo Multistage Spatial Attention for Real-Time Mobile Manipulation Under Visual Scale Variation and Disturbances. A vision-language-action method for real-time mobile manipulation under scale variation and disturbances, designed around hierarchical spatial attention for stronger robustness.

- **[arXiv May 2026](https://arxiv.org/abs/2605.00438)** thinking in text and images: interleaved vision--language reasoning traces for long-horizon robot manipulation. A vision-language-action approach for long-horizon robot manipulation that interleaves textual and visual reasoning traces to improve planning and execution.

- **[arXiv April 2026](https://arxiv.org/abs/2604.26848)** starry: spatial-temporal action-centric world modeling for robotic manipulation. Introduces starry, an action-centric spatiotemporal world-modeling approach for robotic manipulation with a focus on bimanual coordination and stronger task success.

- **[arXiv April 2026](https://arxiv.org/abs/2604.24681)** Learning Human-Intention Priors from Large-Scale Human Demonstrations for Robotic Manipulation. A hierarchical manipulation method that learns human-intention priors from large-scale demonstrations to improve robustness.

- **[arXiv Apr 2026](https://arxiv.org/abs/2604.22615)** GazeVLA: Human Intention for Manipulation. Models human intention through gaze as an intermediate representation to bridge the embodiment gap.

- **[arXiv April 2026](https://arxiv.org/abs/2604.21924)** Long-Horizon Manipulation via Trace-Conditioned VLA Planning. The LoHo-Manip framework uses visual trace prompts and a task-managing VLM to decompose long-horizon manipulation into recoverable local execution and rolling replanning.

- **[ICRA April 2026](https://arxiv.org/abs/2604.21914)** VistaBot: View-Robust Robot Manipulation via Spatiotemporal-Aware View Synthesis. Combines feed-forward geometric estimation with video diffusion models to enable view-robust closed-loop manipulation without test-time camera calibration, while also introducing cross-view generalization metrics.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20348)** Bimanual Robot Manipulation via Multi-Agent In-Context Learning. Uses multi-agent in-context learning to coordinate the high-dimensional action space of dual arms, improving cooperative decision-making and action generation for complex bimanual tasks.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20347)** A Vision-Language-Action Model for Adaptive Ultrasound-Guided Needle Insertion and Needle Tracking. Applies VLA models to adaptive ultrasound-guided puncture and needle tracking, tightly coupling visual understanding, action decisions, and medical robot control.

- **[arXiv April 2026](https://arxiv.org/abs/2604.19509)** Assessing VLM-Driven Semantic-Affordance Inference for Non-Humanoid Robot Morphologies. Studies semantic affordance inference by VLMs on non-humanoid robot morphologies and shows that models remain overly conservative and yield many false negatives in tool-use and unconventional manipulation scenarios.

- **[arXiv April 2026](https://arxiv.org/abs/2604.05320)** ExpressMM: Expressive Mobile Manipulation Behaviors in Human-Robot Interactions. A mobile manipulation framework for human-robot interaction that combines task execution with social expressiveness to improve naturalness and interpretability.

- **[arXiv March 2026](https://arxiv.org/abs/2603.17834)** Generative Control as Optimization: Time Unconditional Flow Matching for Adaptive and Robust Robotic Control. Reformulates flow-matching control from fixed-step trajectory integration into an adaptive optimization process and uses velocity-field norms as training-free safety and OOD signals.

- **[arXiv March 2026](https://arxiv.org/abs/2603.10158)** XL-VLA: Cross-Hand Latent Representation for Vision-Language-Action Models. A cross-hand latent representation framework for VLAs that shares a unified implicit action space across different dexterous hands, enabling cross-embodiment dexterous manipulation training.

- **[arXiv March 2026](https://arxiv.org/abs/2603.00110)** Learning Physics from Pretrained Video Models: A Multimodal Continuous and Sequential World Interaction Models for Robotic Manipulation. Learns continuous and sequential physical interaction from pretrained video models to build multimodal world-interaction models for service robot manipulation.

- **[arXiv January 2026](https://arxiv.org/abs/2601.21251)** SMP: Abstracting Robot Manipulation Skills via Mixture-of-Experts Diffusion Policies. A skill-MoE policy that learns compact orthogonal skill bases and uses sticky routing to compose actions from small task-relevant expert subsets, enabling adaptive expert activation and fast sampling.

- ★ **[AAAI January 2026](https://arxiv.org/abs/2601.01948)** SDP: Learning Diffusion Policy from Primitive Skills for Robot Manipulation. A skill-conditioned diffusion policy that combines interpretable skill learning with conditional action planning, extracting eight reusable primitive skills across tasks and routing them through a lightweight network.

### [H-RDT: Human Manipulation Enhanced Bimanual Robotic Manipulation](https://arxiv.org/abs/2507.23523)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A diffusion foundation model that leverages large-scale egocentric human manipulation data for bimanual robots.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jul 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University (Jun Zhu's team), et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>2B-parameter diffusion Transformer</strong> with flow matching for complex action distributions</li><li>Two-stage training: pretraining on egocentric human manipulation data, then cross-embodiment fine-tuning on robot data</li><li><strong>Modular action encoders/decoders</strong> enable efficient knowledge transfer across embodiments</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>vs. training from scratch: <strong>+13.9%</strong> in simulation and <strong>+40.5%</strong> on real robots</li><li>Outperforms π0 and RDT; superior in few-shot and robustness evaluations</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">H-RDT (code and pretrained models open-sourced)</td></tr>
</tbody>
</table>

- **[ICRA June 2025](https://arxiv.org/abs/2506.20668)** DemoDiffusion: One-Shot Human Imitation using pre-trained Diffusion Policy. Uses a pretrained general diffusion policy to correct trajectories produced by kinematic retargeting, keeping them consistent with human motion while staying inside a valid robot action distribution.

### [ForceVLA: Enhancing VLA Models with a Force-aware MoE for Contact-rich Manipulation](https://arxiv.org/abs/2505.22159)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Introduces 6-axis force sensing as a first-class modality via a force-aware MoE framework for VLAs.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">May 2025 (NeurIPS 2025)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shanghai Jiao Tong University, Fudan University, NUS, et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>FVLMoE</strong> force-aware mixture-of-experts fuses real-time force feedback during action decoding</li><li>Force-aware routing splits experts by modality and stage</li><li>Synchronized capture of vision + proprioception + force-torque signals</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Average task success rate <strong>+23.2%</strong> over the π0 baseline</li><li>Up to <strong>80%</strong> success on plug-insertion tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">ForceVLA-Data (code and data open-sourced)</td></tr>
</tbody>
</table>
- **[arXiv May 2025](https://arxiv.org/abs/2505.16413)** DexVLA: Plug-in Diffusion Experts for Vision-Language-Action Models. A plug-in diffusion expert framework for strengthening VLA manipulation performance.

- **[arXiv April 2025](https://arxiv.org/abs/2504.05291)** ObjectVLA: Open-World Object Manipulation without Demonstrations. A VLA system for open-world object manipulation that does not rely on demonstrations.

- **[arXiv January 2025](https://arxiv.org/abs/2501.05233)** VideoVLA: Video Generators as Generalizable Robot Manipulators. Uses video generation models as the basis for generalizable robot manipulation.

### [Video Prediction Policy: A Generalist Robot Policy with Predictive Visual Representations](https://arxiv.org/abs/2412.14803)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A generalist manipulation policy guided by predictive representations from a video diffusion model.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Dec 2024 (ICML 2025 Spotlight)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Tsinghua University, UC Berkeley, Shanghai AI Laboratory, et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>An <strong>implicit inverse dynamics model learned inside the VDM</strong></li><li>Fine-tunes video foundation models on robot data + internet-scale human manipulation videos</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CALVIN ABC-D <strong>+18.6%</strong> over SOTA</li><li>Real-robot dexterous manipulation success rate <strong>+31.6%</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">VPP (code open-sourced, video-prediction-policy.github.io)</td></tr>
</tbody>
</table>
### [EgoMimic: Scaling Imitation Learning via Egocentric Video](https://arxiv.org/abs/2410.24221)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Unified co-training of Aria-glasses egocentric human data and robot data for imitation learning.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Oct 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Georgia Tech</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Project Aria</strong> glasses capture human embodied data with 3D hand tracking</li><li>A low-cost bimanual platform narrows the human-robot kinematics gap</li><li>Cross-domain alignment + human-robot co-training for a unified policy</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Substantially outperforms SOTA on long-horizon, single/dual-arm tasks</li><li><strong>1 hour</strong> of human data is far more valuable than 1 hour of robot data</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">EgoMimic (code open-sourced, egomimic.github.io)</td></tr>
</tbody>
</table>
### [ALOHA Unleashed: A Simple Recipe for Visuomotor Policies](https://arxiv.org/abs/2410.13126)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A scalable recipe for low-cost bimanual dexterous manipulation, combining large-scale teleoperation data with diffusion policies.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">October 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford (Tony Z. Zhao, Chelsea Finn) + Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>A simple recipe combining large-scale teleoperation data collection on the low-cost <strong>ALOHA 2</strong> platform with a diffusion policy Transformer</li><li>Predicts <strong>50-step action chunks</strong></li><li>Covers 5 real-world and 3 simulated tasks with <strong>26,000+ demonstrations</strong> in total</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>End-to-end policies autonomously complete <strong>shoe lacing and shirt hanging</strong> for the first time</li><li>Significantly outperforms SOTA baselines on 5 challenging real-world tasks (shirt hanging, shoe lacing, finger swapping, gear insertion, kitchen item stacking) and 3 simulated bimanual tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Single-task diffusion policies; 26K demonstrations (6K shirt hanging, 6K shoe lacing, etc.); open-sourced (CoRL 2024)</td></tr>
</tbody>
</table>

### [HIL-SERL: Precise and Dexterous Robotic Manipulation via Human-in-the-Loop Reinforcement Learning](https://arxiv.org/abs/2410.21845)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Human-in-the-loop vision-based RL trains near-perfect dexterous manipulation policies in 1-2.5 hours.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Oct 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley BAIR (Jianlan Luo, Sergey Levine, et al.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Combines <strong>human demonstrations + online corrections</strong> with sample-efficient off-policy RL (RLPD 50/50 mixed sampling)</li><li>Pretrained visual backbone + <strong>binary reward classifier</strong> + low-level impedance controller for physical safety</li><li>System-level design brings real-world RL training down to <strong>1-2.5 hours</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Near-perfect success rates</strong> on dynamic manipulation, precision assembly, and dual-arm coordination</li><li>Average <strong>2x success rate</strong> and <strong>1.8x faster execution</strong> vs. imitation learning baselines</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">HIL-SERL (code open-sourced, project page hil-serl.github.io)</td></tr>
</tbody>
</table>

- **[CoRL June 2024](https://arxiv.org/abs/2406.09288)** ManiWAV: Learning Robot Manipulation from In-the-Wild Audio-Visual Data. Learns robot manipulation from real-world audio-visual data collected in the wild.

- **[RSS March 2024](https://arxiv.org/abs/2403.07788)** DexCap: Scalable and Portable Mocap Data Collection System for Dexterous Manipulation. A scalable and portable motion-capture data collection system for dexterous manipulation.

- **[CoRL February 2024](https://arxiv.org/abs/2402.10329)** UMI: Universal Manipulation Interface: In-The-Wild Robot Teaching Without In-The-Wild Robots. A universal manipulation interface for robot teaching that avoids the need for in-the-wild robot collection.

- **[CoRL July 2023](https://arxiv.org/abs/2307.16677)** AnyTeleop: A General Vision-Based Teleoperation System for Robotic Manipulation. A general vision-based teleoperation system for robot manipulation.

- **[RSS April 2023](https://arxiv.org/abs/2304.13705)** ACT: Learning Fine-Grained Bimanual Manipulation with Low-Cost Hardware. Fine-grained bimanual manipulation learning with low-cost hardware.

- **[RSS March 2023](https://arxiv.org/abs/2303.04137)** Diffusion Policy: Visuomotor Policy Learning via Action Diffusion. A diffusion-based robot policy learning method that performs strongly on dexterous manipulation tasks.

- ★ **[ICLR February 2023](https://arxiv.org/abs/2302.12422)** MimicPlay: Long-Horizon Imitation Learning by Watching Human Play. Long-horizon imitation learning from observing humans at play.

### [MimicPlay: Long-Horizon Imitation Learning by Watching Human Play](https://arxiv.org/abs/2302.12422)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Hierarchical long-horizon imitation from human play videos: the high level watches hands, the low level learns manipulation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Feb 2023 (CoRL 2023 Oral)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford, NVIDIA, Georgia Tech, UT Austin, Caltech</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>A high-level latent planner predicts future <strong>3D human-hand trajectories</strong></li><li>Low-level visuomotor control uses only a small amount of teleoperation data</li><li>Hierarchical decoupling of human and robot data sources</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>14</strong> real long-horizon tasks with success rates beating SOTA by <strong>50%+</strong></li><li>Generalization to unseen tasks improved by <strong>40%+</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">MimicPlay (code open-sourced, mimic-play.github.io)</td></tr>
</tbody>
</table>
- **[CoRL November 2022](https://arxiv.org/abs/2211.07636)** RVT: Robotic View Transformer for 3D Object Manipulation. A robotic view transformer for 3D object manipulation.

- **[CoRL September 2022](https://arxiv.org/abs/2209.05451)** Perceiver-Actor: A Multi-Task Transformer for Robotic Manipulation. A language-conditioned multitask transformer for robotic manipulation, also widely referred to as PerAct.

- **[ICRA March 2022](https://arxiv.org/abs/2203.08745)** C2F-ARM: Coarse-to-Fine Imitation Learning for Robot Manipulation. A coarse-to-fine imitation learning framework for robot manipulation.

- **[CoRL February 2022](https://arxiv.org/abs/2202.02005)** BC-Z: Zero-Shot Task Generalization with Robotic Imitation Learning. A zero-shot task generalization approach for imitation learning that conditions on language instructions so robots can perform previously unseen tasks at test time.

- **[CoRL September 2021](https://arxiv.org/abs/2109.12098)** CLIPort: What and Where Pathways for Robotic Manipulation. A robot manipulation method that combines CLIP-based visual understanding with end-to-end imitation learning to enable open-vocabulary object manipulation and generalization.

- **[ICRA March 2021](https://arxiv.org/abs/2103.02245)** Form2Fit: Learning Shape Priors for Generalizable Manipulation. A method for generalizable manipulation through learned shape priors.

- ★ **[ICCV January 2021](https://arxiv.org/abs/2101.09555)** Where2Act: From Pixels to Actions for Articulated Objects. A method for articulated object manipulation that maps pixels directly to actions.

- ★ **[CVPR December 2018](https://arxiv.org/abs/1812.02713)** PartNet: A Large-Scale Benchmark for Fine-Grained and Hierarchical Part-Level 3D Object Understanding. A benchmark for fine-grained and hierarchical part-level 3D object understanding.
<a id="locomotion" name="locomotion"></a>

## Locomotion

### [SleepWalking: Privileged Representation Shaping for End-to-End Blind Locomotion in Legged Robots](https://arxiv.org/abs/2608.30883)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shapes recurrent representations with privileged physical reconstruction during training for more stable, cheaper end-to-end blind legged locomotion.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Northwestern Polytechnical University + Shanghai Jiao Tong University + Yunmu Intelligent Manufacturing</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Reframes partially observable locomotion as an <strong>"information retention" problem</strong>: what matters is whether internal state can keep information, not how it enters the network</li><li><strong>SWAQ single-stage end-to-end framework</strong>: privileged next-step reconstruction (velocity, noise-free observations, terrain height) shapes the recurrent history representation only during training; deployment keeps only the history-to-action path</li><li>Provides theoretical bounds on privileged-variable recoverability and attainable return gaps</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Peak average terrain level <strong>15.0%</strong> higher than the strongest exteroception-free baseline (DWAQ) under matched training</li><li>Single control-step inference uses <strong>44.4%</strong> fewer MACs; cross-embodiment sim2real (Quadruped Go1 and humanoid) passes stair terrain consistently</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">SWAQ framework</td></tr>
</tbody>
</table>

- **[arXiv May 2026](https://arxiv.org/abs/2605.14417)** Before the Body Moves: Learning Anticipatory Joint Intent for Language-Conditioned Humanoid Control (DAJI). A hierarchical framework for language-conditioned humanoid control that learns anticipatory joint-intent representations and explicitly encodes upcoming contact changes and balance preparation for stable whole-body motion generation.

- **[arXiv April 2026](https://arxiv.org/abs/2604.19734)** UniT: Toward a Unified Physical Language for Human-to-Humanoid Policy Learning and World Modeling. A unified physical language for policy learning and world modeling from humans to humanoids, using visually grounded latent action tokenization to bridge cross-embodiment learning.

- **[arXiv April 2026](https://arxiv.org/abs/2604.08509)** Visually-grounded Humanoid Agents. A visually grounded approach to humanoid agents focused on embodied AI capabilities.

### [MIRROR: Visual Motion Imitation via Real-time Retargeting and Teleoperation with Parallel Differential Inverse Kinematics](https://arxiv.org/abs/2603.23995)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GPU-parallel differential IK enables real-time, safe visual motion imitation for humanoid teleoperation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Mar 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">California Institute of Technology (Caltech)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>GPU-parallel continuation-based differential IK</strong>: solves multiple constrained QPs in parallel to escape local minima near joint limits, singularities, and collisions</li><li>Self-collision-avoidance <strong>control barrier function (CBF)</strong> + Lyapunov-based progression criterion for global error reduction</li><li>Visual skeletal pose estimation pipeline for <strong>real-time upper-body teleoperation from a single stereo camera</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Real-world tasks on the THEMIS humanoid with real-time performance and safety guarantees</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">MIRROR (code open-sourced, junhengl/mirror)</td></tr>
</tbody>
</table>

- **[arXiv March 2026](https://arxiv.org/abs/2603.17927)** RoboForge: Physically Optimized Text-guided Whole-Body Locomotion for Humanoids. A physically optimized framework for text-guided humanoid whole-body locomotion that jointly optimizes motion generation and physical execution via the PP-Opt module.

- **[arXiv April 2025](https://arxiv.org/abs/2504.09532)** Humanoid-COA: Humanoid Agent via Embodied Chain-of-Action Reasoning with Multimodal Foundation Models for Zero-Shot Loco-Manipulation. The first humanoid agent framework to combine multimodal foundation-model reasoning with embodied chain-of-action mechanisms for zero-shot loco-manipulation.

- **[arXiv February 2025](https://arxiv.org/abs/2502.09247)** Humanoid-VLA: Vision-Language-Action Models for Humanoid Control. A VLA model designed specifically for humanoid robot control.
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>
<a id="navigation-spatial-intelligence" name="navigation-spatial-intelligence"></a>

### [HumanPlus: Humanoid Shadowing and Imitation from Humans](https://arxiv.org/abs/2406.10454)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A full-stack system for humanoid shadowing teleoperation and egocentric imitation learning from humans.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jun 2024 (CoRL 2024 Best Paper Award Finalist)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Stanford University (Chelsea Finn's team)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Shadowing</strong>: low-level policy trained via RL on 40-hour human motion data (AMASS) tracks body and hands in real time from RGB camera only</li><li>Whole-body data collected via shadowing, then <strong>egocentric behavior cloning</strong> trains skill policies</li><li>Custom 33-DoF 180cm humanoid platform</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>60-100% success rates</strong> on tasks such as putting on a shoe, unloading racks, folding a sweatshirt, typing, and greeting (up to 40 demos)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">HumanPlus (code, dataset, and hardware BOM fully open-sourced, humanoid-ai.github.io)</td></tr>
</tbody>
</table>

### [OmniH2O: Universal and Dexterous Human-to-Humanoid Whole-Body Teleoperation and Learning](https://arxiv.org/abs/2406.08858)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Whole-body humanoid teleoperation and autonomous learning with kinematic pose as a universal interface.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jun 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Carnegie Mellon University (Kris Kitani's team), et al.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Kinematic pose as a universal control interface</strong>: VR headset, verbal instruction, and RGB camera control</li><li><strong>RL sim-to-real</strong> pipeline: large-scale human motion retargeting + privileged teacher distillation</li><li>Full autonomy via GPT-4 or other frontier models</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Real-world whole-body tasks: sports, object manipulation, human interaction</li><li>Releases <strong>OmniH2O-6</strong>, the first humanoid whole-body control dataset (6 daily tasks)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">OmniH2O-6 dataset (omni.human2humanoid.com)</td></tr>
</tbody>
</table>

## Navigation & Spatial Intelligence

### [CrossTracer: Cross-Embodiment Navigation via VLA Model Reasoning and Trace Residuals Adapting](https://arxiv.org/abs/2608.06688)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A hierarchical cross-embodiment navigation framework combining VLA reasoning with embodiment-specific residual adaptation over image-plane waypoints.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Peng Cheng Laboratory + Southern University of Science and Technology</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Represents navigation plans as <strong>normalized image-plane waypoints</strong>, a unified pixel-space interface between semantic reasoning and physical execution</li><li>Two-level structure: <strong>VL-Tracer</strong> (pretrained VLA proposes initial traces) + <strong>CE-Adapter</strong> (predicts embodiment-conditioned residual corrections)</li><li><strong>CE-RRT*</strong> converts panoptic segmentation into robot-conditioned cost maps and auto-generates training traces without human labels</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>NaviTrace total score <strong>45.68</strong>, beating Gemini-2.5-Pro (35.67) by <strong>10.01 points (+28.1%)</strong></li><li>Real-robot deployments on wheeled and legged robots further improve success and efficiency</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CrossTracer framework; evaluated on NaviTrace benchmark</td></tr>
</tbody>
</table>

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.09716)** RoboNav-Arm: Navigation for Manipulators. Agentic AI-driven navigation and obstacle avoidance for robotic manipulators.
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.05122)** Green for Go, Red for No. Visual grounding via semantic segmentation for VLA navigation, reducing waypoint error by 27-44%.
- **[arXiv Jul 2026](https://arxiv.org/abs/2607.03146)** Exp2VLA: Drone Navigation. Enables VLA for drone navigation from expert demonstrations.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.26265)** NavIsaacLab: Crowd Navigation. Generates realistic crowds via physics simulation for training human-aware navigation policies.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.12956)** SERF: Spatiotemporal Feature Map. Spatiotemporal environment and robot feature map for long-horizon mobile manipulation.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.10495)** Act on What You See: Safe Social Navigation. Unlocks safe social navigation in VLA models.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.06836)** Think Like a Pilot: UAV Navigation. Proposes fine-grained long-horizon UAV navigation framework.
- ★ **[CVPR May 2026](https://arxiv.org/abs/2605.30342)** Uncertainty-driven 3D Gaussian Splatting Active Mapping via Anisotropic Visibility Field (GAVIS). Proposes the GAVIS framework for uncertainty quantification and active mapping of 3D Gaussian splatting via anisotropic visibility field, supporting real-time 200FPS uncertainty quantification.
- **[ICRA May 2026](https://arxiv.org/abs/2605.29773)** Energy-Aware NECO for Single-Pass Pixel-wise Out-of-Distribution Detection in Semantic Segmentation. An energy-aware NECO method for efficient pixel-wise out-of-distribution detection in semantic segmentation, enhancing robustness of robot perception systems.
- **[arXiv May 2026](https://arxiv.org/abs/2605.27952)** Con-DSO: Learning Short-Horizon Consistency Priors for RGB-D Direct Sparse Odometry. A consistency-aware RGB-D direct sparse odometry framework that predicts photometric and depth geometric consistency uncertainty, achieving 20%-80% trajectory error reduction across multiple benchmarks.
- **[arXiv May 2026](https://arxiv.org/abs/2605.27178)** Domain Adaptation for Robot Vision. Studies domain adaptation in robot vision, proposing improved adversarial learning and self-supervised methods to enhance model generalization in new environments.
- **[arXiv May 2026](https://arxiv.org/abs/2605.26949)** DinoComplete: 3D Shape Completion with Distilled Semantic Priors and State Space Models. Proposes DinoComplete, a shape completion framework leveraging DINO feature-distilled voxel-aligned semantic priors combined with multi-scale voxel Mamba modules for efficient long-range reasoning.
- **[arXiv May 2026](https://arxiv.org/abs/2605.25832)** Visual-Inertial Odometry. Studies visual-inertial odometry technology, fusing camera and IMU data for robust robot localization, maintaining high precision in challenging environments.
- **[arXiv May 2026](https://arxiv.org/abs/2605.13775)** RoboEvolve: Co-Evolving Planner-Simulator for Robotic Manipulation with Limited Data. Couples a VLM planner and a VGM simulator in a co-evolution loop with a cognitively inspired “daytime exploration, nighttime consolidation” setup, surpassing fully supervised baselines with just 500 unlabeled seeds.
- **[arXiv May 2026](https://arxiv.org/abs/2605.12735)** Toward a Blueprint for Generalizable Robot Autonomy (Unified Autonomy Stack). An open-source unified autonomy stack that fuses LiDAR, radar, vision, and inertial sensing to support factor-graph localization, semantic scene understanding, and multilayer safe navigation across aerial and ground robots.
- **[arXiv May 2026](https://arxiv.org/abs/2605.12625)** Driving Intents Amplify Planning-Oriented Reinforcement Learning (DIAL). Uses intent-conditioned CFG to expand the sampled distribution and break mode collapse, then combines it with multi-intent GRPO for preference RL, surpassing both human demonstrations and previous best systems on WOD-E2E.
- **[arXiv May 2026](https://arxiv.org/abs/2605.12624)** MindVLA-U1: VLA Beats VA with Unified Streaming Architecture for Autonomous Driving. The first unified streaming VLA architecture for autonomous driving, generating language tokens and flow-matched trajectories in a single forward pass and surpassing human drivers for the first time on WOD-E2E.
- **[arXiv May 2026](https://arxiv.org/abs/2605.12622)** Action Emergence from Streaming Intent. Proposes a streaming-intent mechanism for end-to-end autonomous driving, where intent tokens decoded through a four-step chain of thought guide a flow-matching action head and make intent control explicit in VLA systems.
- **[arXiv May 2026](https://arxiv.org/abs/2605.12620)** VeGAS: Verifier-Guided Action Selection For Embodied Agents. A test-time framework that samples candidate actions and uses a generative verifier to identify the most reliable choice, improving relative performance by up to 36% on Habitat and ALFRED.
- **[arXiv May 2026](https://arxiv.org/abs/2605.09387)** NEXUS: Continual Learning of Symbolic Constraints for Safe and Robust Embodied Planning. A continual symbolic-constraint learning framework for safe and robust embodied planning.
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>
- **[arXiv April 2026](https://arxiv.org/abs/2604.24707)** Passage-Aware Structural Mapping for RGB-D Visual SLAM. A perception method for navigation and spatial mapping in RGB-D SLAM.
- **[arXiv April 2026](https://arxiv.org/abs/2604.22851)** EgoDyn-Bench: Evaluating Ego-Motion Understanding in Vision-Centric Foundation Models for Autonomous Driving. Introduces EgoDyn-Bench, a unified benchmark for evaluating egomotion understanding in vision-centric foundation models for autonomous driving.
- **[arXiv April 2026](https://arxiv.org/abs/2604.22339)** flow4dgs-slam: optical flow-guided 4d gaussian splatting slam. A navigation and mapping perception method that emphasizes efficiency and robustness through optical-flow-guided 4D Gaussian splatting.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21894)** Task-Driven Co-Design of Heterogeneous Multi-Robot Systems. A task-driven co-design framework for heterogeneous multi-robot systems that jointly considers design, team composition, planning, and execution.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21707)** Effects of Swarm Size Variability on Operator Workload. Studies how dynamic variation in robot swarm size affects human operator workload and performance in real deployment scenarios.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21693)** SLAM as a Stochastic Control Problem with Partial Information: Optimal Solutions and Rigorous Approximations. Recasts active SLAM as a stochastic control problem under partial information and provides unified modeling together with rigorous approximation analysis.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21640)** Task-specific Subnetwork Discovery in Reinforcement Learning for Autonomous Underwater Navigation. An interpretable multitask RL framework for autonomous underwater navigation that discovers task-specific subnetworks to improve policy adaptation and internal decision transparency.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21453)** Instance-level Visual Active Tracking with Occlusion-Aware Planning. An instance-level active visual tracking method for occluded scenes that combines target tracking with occlusion-aware planning for more stable long-duration tracking.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21363)** A Deployable Embodied Vision-Language Navigation System with Hierarchical Cognition and Context-Aware Exploration. A deployable VLN system that balances compute, latency, and navigation quality through hierarchical cognition and context-aware exploration.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21138)** Navigating the Clutter: Waypoint-Based Bi-Level Planning for Multi-Robot Systems. A bi-level planning framework for cluttered multi-robot environments that jointly optimizes task planning and motion planning through waypoint representations and feasibility feedback.
- **[arXiv April 2026](https://arxiv.org/abs/2604.20305)** AdaTracker: Learning Adaptive In-Context Policy for Cross-Embodiment Active Visual Tracking. An adaptive in-context policy-learning framework for cross-embodiment active visual tracking that uses a unified model to handle different robot dynamics and physical constraints.
- **[arXiv April 2026](https://arxiv.org/abs/2604.19536)** LiveVLN: Breaking the Stop-and-Go Loop in Vision-Language Navigation. Targets the stop-and-go decision loop in VLN by introducing a more continuous perception-reasoning-execution pipeline for smoother real-world movement.
- **[arXiv April 2026](https://arxiv.org/abs/2604.08232)** HiRO-Nav: Hybrid ReasOning Enables Efficient Embodied Navigation. A navigation agent that adaptively decides whether to reason at each step based on action entropy, using hybrid supervision and online RL to activate explicit reasoning only when needed.
- **[arXiv April 2026](https://arxiv.org/abs/2604.07973)** UrbanNav Benchmark: How Far Are Large Multimodal Models from Human-Level Spatial Action. The first embodied spatial-action benchmark for urban goal-oriented navigation, with 5,037 high-quality samples emphasizing vertical 3D movement and rich urban semantics.
- **[arXiv April 2026](https://arxiv.org/abs/2604.07957)** WorldMAP: Bootstrapping Vision-Language Navigation Trajectory Prediction with Generative World Models. A teacher-student framework where a world-model teacher builds semantic spatial memory from generated videos and produces trajectory pseudo-labels for a lightweight student.
- **[arXiv March 2026](https://arxiv.org/abs/2603.28032)** CARLA-Air: Fly Drones Inside a CARLA World -- A Unified Infrastructure for Air-Ground Embodied Intelligence. Extends CARLA into a unified air-ground embodied simulation environment for training, perception, and evaluation across drones and ground agents.
- **[arXiv March 2026](https://arxiv.org/abs/2603.16947)** EmergeNav: Structured Embodied Inference for Zero-Shot Vision-and-Language Navigation in Continuous Environments. A structured embodied inference framework for zero-shot VLN-CE that reaches a 37% success rate without training.
- **[arXiv March 2026](https://arxiv.org/abs/2603.16413)** OpenDriveVLA: Towards End-to-end Autonomous Driving with Large Vision Language Action Model. An end-to-end autonomous driving VLA model that unifies perception, decision-making, and control through joint vision-language-action modeling.
- **[arXiv March 2026](https://arxiv.org/abs/2603.14669)** RenderMem: Rendering as Spatial Memory Retrieval. A spatial memory framework that uses rendering as the interface between 3D world representations and spatial reasoning, generating query-conditioned visual evidence by rendering from query-implied viewpoints.
- **[arXiv March 2026](https://arxiv.org/abs/2603.09163)** SPAN-Nav: Generalized Spatial Awareness for Versatile Vision-Language Navigation. An end-to-end model that extracts spatial priors from large-scale indoor and outdoor scenes through occupancy prediction and injects those cues explicitly into action reasoning through CoT.
- **[arXiv March 2026](https://arxiv.org/abs/2603.06914)** SysNav: Multi-Level Systematic Cooperation Enables Real-World, Cross-Embodiment Object Navigation. A three-level object navigation framework that decouples semantic reasoning, planning, and motion control, validated across wheeled robots, Unitree Go2, and Unitree G1 in 190 real-world trials.

- **[ICRA February 2026](https://arxiv.org/abs/2510.08173)** NavSpace: Spatial Intelligence Navigation Benchmark. A spatial-intelligence navigation benchmark spanning more than 1,200 dynamic instructions across six categories, pushing evaluation beyond static perception into persistent reasoning.
- **[arXiv September 2025](https://arxiv.org/abs/2509.14000)** JaGuard: Position Error Correction of GNSS Jamming with Deep Temporal Graphs. Models GNSS jamming correction as dynamic graph regression, using deep temporal graph networks to fuse satellite geometry and short-term motion for drift correction.
- **[arXiv June 2025](https://arxiv.org/abs/2506.15518)** Real-Time Initialization of Unknown Anchors for UWB-aided Navigation. A real-time initialization method for unknown anchors in UWB-assisted navigation that improves localization usability without prior anchor layouts.
- **[arXiv May 2025](https://arxiv.org/abs/2505.08912)** CoW: Chain-of-Thought Walking for Embodied Navigation. A chain-of-thought walking approach for embodied navigation.
- **[arXiv April 2025](https://arxiv.org/abs/2504.08962)** TrackVLA: Embodied Visual Tracking with Vision-Language-Action Models. A VLA model for embodied visual tracking.
- **[arXiv January 2025](https://arxiv.org/abs/2501.07399)** Efficiently Closing Loops in LiDAR-Based SLAM Using Point Cloud Density Maps. Efficient loop closure and verification for LiDAR SLAM using point-cloud density maps while reducing computation.

- **[arXiv July 2024](https://arxiv.org/abs/2407.00848)** EgoExo++: Integrating On-demand Exocentric Visuals with 2.5D Ground Surface Estimation for Interactive Teleoperation of Underwater ROVs. A framework for underwater ROV teleoperation that fuses egocentric and exocentric views with 2.5D ground estimation for safer control in complex environments.
- **[ICRA February 2024](https://arxiv.org/abs/2402.09466)** VLFM: Vision-Language Frontier Maps for Zero-Shot Semantic Navigation. Vision-language frontier maps for zero-shot semantic navigation.
- ★ **[CVPR January 2024](https://arxiv.org/abs/2401.04567)** EgoVLPv2: Egocentric Video-Language Pre-training. Egocentric video-language pretraining.
- **[arXiv August 2023](https://arxiv.org/abs/2308.00513)** UVIO: An UWB-Aided Visual-Inertial Odometry Framework with Bias-Compensated Anchors Initialization. A UWB-assisted visual-inertial odometry framework with bias-compensated anchor initialization for improved convergence speed and stability.
- ★ **[AAAI May 2023](https://arxiv.org/abs/2305.16986)** NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models. Explicit reasoning for vision-language navigation with large language models.
- **[RSS October 2022](https://arxiv.org/abs/2210.05663)** CLIP-Fields: Weakly Supervised Semantic Fields for Robotic Memory. Weakly supervised semantic fields for robotic memory.
- ★ **[CVPR March 2022](https://arxiv.org/abs/2203.06789)** PONI: Potential Functions for ObjectGoal Navigation with Interaction-free Learning. Potential functions for object-goal navigation with interaction-free learning.
- ★ **[ICCV April 2021](https://arxiv.org/abs/2104.03456)** SOON: Scenario Oriented Object Navigation. Scenario-oriented object navigation.
- **[ICRA March 2021](https://arxiv.org/abs/2103.07086)** ViNG: Learning Open-World Navigation with Visual Goal Representations. Open-world navigation through visual goal representations.
- **[CoRL October 2020](https://arxiv.org/abs/2010.15044)** Semantic MapNet: Building Allocentric Semantic Maps and Representations. Building allocentric semantic maps and representations.
- ★ **[ECCV July 2020](https://arxiv.org/abs/2007.00643)** ObjectNav: Object Goal Navigation using Goal-Oriented Semantic Exploration. Goal-oriented semantic exploration for object-goal navigation.
- ★ **[CVPR June 2020](https://arxiv.org/abs/2006.13979)** VLN-BERT: A Recurrent BERT for Vision-and-Language Navigation. A recurrent BERT model for vision-language navigation.
- ★ **[ICLR June 2020](https://arxiv.org/abs/2006.04884)** Active Neural SLAM. An active neural SLAM framework.
- ★ **[ICML June 2019](https://arxiv.org/abs/1906.09518)** Neural SLAM: Learning to Explore with External Memory. Neural SLAM that learns exploration with external memory.
- ★ **[NeurIPS April 2018](https://arxiv.org/abs/1804.00168)** PointNav: Learning to Navigate in Cities Without a Map. Learning to navigate in cities without a map.
- ★ **[CVPR February 2017](https://arxiv.org/abs/1702.04405)** ScanNet: Richly-Annotated 3D Reconstructions of Indoor Scenes. A richly annotated indoor-scene 3D reconstruction dataset.
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>
<a id="simulation-sim2real" name="simulation-sim2real"></a>

## Simulators & Sim2Real

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.15065)** DriftWorld: Fast World Modeling. Fast world modeling through drifting.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.06699)** RoboSnap: Real-to-Sim Scene Generation. Converts a single RGB image to physically stable simulation-ready scenes.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.02205)** Actuator Reality Shaping. Matches physical actuators with ideal reference dynamics in simulation for zero-shot sim-to-real transfer.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.01410)** BIFROST: Sim2Real Transfer. Zero-shot sim2real transfer via cross-domain dual-simulation objective for shared history encoders.

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.00678)** ABot-M0.5: Mobility-and-Manipulation Model. Unified mobility-and-manipulation world action model.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.25939)** DeformGen: Deformable Manipulation. Generates topology-consistent deformable states via local physical perturbation and dynamics simulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.20389)** CoLI: Continuum Robot Learning. Proposes a continuum robot platform based on multi-material 3D printing and isomorphic teleoperation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.17030)** Qwen-RobotWorld: Video Generation World Model. Unifies embodied world modeling through language-conditioned video generation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.16470)** Decoupled Object-Centric Video Understanding. Decoupled object-centric video understanding for generating manipulation commands.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.11372)** HiPi: High-Fidelity Sensors. Reproducible high-fidelity piezoresistive sensors for robotic manipulation.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.11184)** TacForeSight: Tactile World Model. Force-guided tactile world model for contact-rich manipulation.

- ★ **[ICML May 2026](https://arxiv.org/abs/2605.29032)** Theoretical Foundations and Effective Algorithms for Policy-Aware Simulator Learning. Proposes policy-aware simulator learning that shifts simulator learning objectives from prediction accuracy to policy robustness, solving simulator exploitation through zero-sum game framework.

- **[GECCO May 2026](https://arxiv.org/abs/2605.28812)** Beyond Binary: Sim-to-Real Dexterous Manipulation with Physics-Grounded Contact Representation. Proposes a pressure-center-based tactile representation that preserves dense contact information while maintaining robust sim-to-real transfer, achieving zero-shot real robot transfer.

- **[arXiv May 2026](https://arxiv.org/abs/2605.28312)** Sim-to-Real Transfer for Robotic Manipulation. Studies sim-to-real transfer for robotic manipulation, proposing improved domain randomization and adaptation techniques to enhance policy transfer from simulation to real environments.

- **[Neutrosophic Sets and Systems May 2026](https://arxiv.org/abs/2605.26114)** MobileGym: A Verifiable and Highly Parallel Simulation Platform for Mobile GUI Agent Research. Proposes MobileGym platform supporting verifiable outcome signals and large-scale parallel online RL, achieving 95.1% training gain preservation in Sim-to-Real cases.

- **[arXiv May 2026](https://arxiv.org/abs/2605.14625)** Digital Twin Synchronization Over Mobile Embodied AI Network With Agentic Intelligence. A digital-twin synchronization framework for mobile embodied AI networks that uses agentic intelligence to maintain high-fidelity virtual representations with low information age.

- **[arXiv May 2026](https://arxiv.org/abs/2605.13315)** Embodied Neurocomputation: A Framework for Interfacing Biological Neural Cultures with Scaled Task-Driven Validation. A framework for embodied neurocomputation that connects biological neural cultures with task-driven validation.

- **[arXiv May 2026](https://arxiv.org/abs/2605.12654)** COSMIC: Concurrent Optimization of Structure, Material, and Integrated Control for robotic systems. A gradient-based co-design framework that jointly optimizes topology, material distribution, and control strategy inside a differentiable simulator, finding diverse motion strategies beyond separated design.

- **[arXiv May 2026](https://arxiv.org/abs/2605.12038)** OmniHumanoid: Streaming Cross-Embodiment Video Generation with Paired-Free Adaptation. A streaming cross-embodiment video generation framework that adapts to different robot morphologies without paired data.

- **[arXiv April 2026](https://arxiv.org/abs/2604.25459)** GS-Playground: A High-Throughput Photorealistic Simulator for Vision-Informed Robot Learning. A high-throughput photorealistic simulator for robot manipulation and vision-informed learning.

### [RoboCasa365: A Large-Scale Simulation Framework for Training and Benchmarking Generalist Robots](https://arxiv.org/abs/2603.04356)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A large-scale kitchen mobile-manipulation simulation benchmark with 365 tasks and 2,500 scenes.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Mar 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">University of Texas at Austin, NVIDIA Research</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Extends the RoboCasa platform to <strong>365 everyday tasks × 2,500 kitchen scenes</strong></li><li>Contains <strong>600 hours of human demos + 1,600 hours of synthetic demos</strong> (2,200+ hours total)</li><li>Supports multi-task learning, foundation-model training, and lifelong learning evaluation</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Systematically analyzes how task diversity, data scale, and environment variation affect generalization</li><li>Benchmarks SOTA methods under multi-task / foundation-model / lifelong settings with new insights</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboCasa365 simulation platform and data</td></tr>
</tbody>
</table>

- **[arXiv March 2026](https://arxiv.org/abs/2603.22039)** RAFL: Generalizable Sim-to-Real of Soft Robots with Residual Acceleration Field Learning. A residual acceleration field framework that enhances base simulators with transferable local correction dynamics for soft-robot sim-to-real transfer.

- **[arXiv November 2025](https://arxiv.org/abs/2511.02345)** Sim2Real 2.0: A Survey and Benchmark. A survey and benchmark on Sim2Real transfer.

- **[arXiv October 2025](https://arxiv.org/abs/2510.09876)** UniSim: A Universal Simulator for Robotics and Embodied AI. A universal simulator for robotics and embodied AI.

- **[OpenReview October 2025](https://openreview.net/forum?id=P7tg7VowVX)** RoboSimGS: High-Fidelity Simulated Data Generation for Real-World Zero-Shot Transfer. A Real2Sim2Real framework that converts multiview real images into scalable, photorealistic, physically interactive simulation environments with 3D Gaussian splatting and automatically generated articulated assets.

- **[arXiv September 2025](https://arxiv.org/abs/2509.24948)** World-Env: Leveraging World Model as a Virtual Environment for VLA Post-Training. Uses world models as low-cost virtual environments for VLA post-training, providing continuous rewards and action termination signals in place of costly real interaction.

- **[ICRA September 2025](https://arxiv.org/abs/2509.14687)** RealMirror: Vision-Language-Action Platform for Embodied AI. An open end-to-end simulation platform with strong visual fidelity and realistic physical interaction for embodied AI.

- **[arXiv September 2025](https://arxiv.org/abs/2509.12372)** Sym2Real: Symbolic Dynamics with Residual Learning for Data-Efficient Adaptive Control. A data-efficient control framework that combines symbolic dynamics with residual learning and achieves robust real-world control with about ten trajectories.

- **[arXiv June 2025](https://arxiv.org/abs/2506.10600)** EmbodiedGen: Generative 3D Worlds for Embodied AI. Generative 3D worlds for embodied AI.

### [V-JEPA 2: Self-Supervised Video Models for Understanding, Prediction and Planning](https://arxiv.org/abs/2506.09985)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A purely self-supervised latent-space video world model combining understanding, prediction and zero-shot planning.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">June 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Meta FAIR (Yann LeCun et al.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>JEPA architecture</strong>: predicts the future in latent space rather than reconstructing pixels</li><li>ViT-g <strong>1B-parameter</strong> encoder + 3D-RoPE, pretrained on 1M+ hours of internet video</li><li>Followed by a 300M-parameter action-conditioned world model, V-JEPA 2-AC</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Something-Something v2 motion understanding <strong>77.3 top-1</strong>; EK-100 action prediction 39.7 R@5 (44% relative improvement)</li><li>V-JEPA 2-AC trained with <62 hours of Droid data, zero-shot grasp-and-place on Franka dual arms</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model V-JEPA 2 / V-JEPA 2-AC; training data internet video + Droid dataset; model and weights open-sourced</td></tr>
</tbody>
</table>

### [Cosmos: World Foundation Model Platform for Physical AI](https://arxiv.org/abs/2501.03575)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA's open platform of world foundation models for Physical AI.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">January 2025</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Includes a video curation pipeline, pretrained WFMs, post-training examples and <strong>video tokenizers</strong></li><li>Initial Cosmos-Predict1: two models, autoregressive 5B + diffusion 7B</li><li>Tokenizers with up to <strong>2048x compression</strong> (8/16x spatial, 4/8x temporal)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Training data ~<strong>20M hours of video</strong> (~45PB, 9000T tokens)</li><li>Tokenizer ~<strong>12x</strong> faster than contemporaneous SOTA</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Cosmos-Predict1/2.5, Transfer2.5, Reason; open-source (NVIDIA Open Model License)</td></tr>
</tbody>
</table>

### [Genie 2: A Large-Scale Foundation World Model](https://deepmind.google/discover/blog/genie-2-a-large-scale-foundation-world-model/)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A large-scale foundation world model that generates playable 3D worlds from a single image.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">December 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind (Generalist Agents team)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Autoregressive latent diffusion world model</strong>, trained on large-scale video datasets</li><li>Generates playable 3D worlds from a single image prompt</li><li>Emergent physics such as gravity / water / smoke, complex character animation, object interactions and long-term memory</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Consistent world generation up to ~<strong>1 minute</strong> (examples mostly 10-20 seconds)</li><li>Supports first/third-person, isometric and other viewpoints; a distilled version enables real-time interaction</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Genie 2; prompt images generated by Imagen 3; not open-sourced</td></tr>
</tbody>
</table>

- **[CoRL June 2024](https://arxiv.org/abs/2406.02523)** RoboCasa: Large-Scale Simulation of Everyday Tasks for Generalist Robots. Large-scale everyday task simulation for generalist robots.

### [Genesis: A Generative and Universal Physics Engine](https://arxiv.org/abs/2406.19481)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">An open-source generative physics engine, simulating at 430Kx real-time and supporting language-driven 4D world generation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">June 2024 (physics engine open-sourced December 2024)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Led by CMU with 20+ universities (MIT, Stanford, Tsinghua, Peking University, etc.), in collaboration with NVIDIA and Taichi Graphics</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>A <strong>general-purpose physics engine</strong> rebuilt from the ground up, unifying multiple physics solvers</li><li>Native Python + <strong>Taichi GPU acceleration</strong>, supporting differentiable simulation and differentiable tactile sensing</li><li>VLM-generated agents can turn natural language into 4D worlds, policies, trajectories and videos</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Franka manipulation scenes reach <strong>43M FPS</strong> (~430Kx real-time)</li><li>~10-80x faster than Isaac Gym / MJX; a locomotion policy transferable to the real world trained in 26 seconds on a single RTX 4090</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Genesis physics engine and simulation platform open-sourced; generative framework released incrementally</td></tr>
</tbody>
</table>

### [Genie: Generative Interactive Environments](https://arxiv.org/abs/2402.15391)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">An 11B-parameter unsupervised world model, generating playable 2D worlds from a single image.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">February 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind (with UBC)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>ST-transformer video tokenizer + autoregressive dynamics model + latent action model</li><li><strong>No action labels needed</strong>, fully unsupervised training on internet videos</li><li>Single image / sketch / photo generates controllable 2D interactive worlds</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>11B parameters</strong>, trained on ~30K hours, 68M clips of 2D game videos</li><li>Frame-by-frame generation of playable worlds (single 16-frame window)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model Genie (11B); training data internet 2D game videos; not open-sourced</td></tr>
</tbody>
</table>

### [RoboGen: Towards Unleashing Infinite Data for Automated Robot Learning via Generative Simulation](https://arxiv.org/abs/2311.01455)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Generative simulation automatically produces skill-training data via a propose-generate-learn loop.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Nov 2023 (ICML 2024)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">CMU, Tsinghua IIIS, MIT, UMass</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Propose-generate-learn</strong> loop: LLM proposes tasks → auto-generates scene assets → auto-generates rewards/supervision → learns</li><li>Built on the Genesis engine</li><li>Covers rigid, articulated, deformable objects, and legged locomotion</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Can infinitely produce diverse skill demonstrations and training data</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RoboGen (code open-sourced, robogen-ai.github.io)</td></tr>
</tbody>
</table>
### [UniSim: Learning Interactive Real-World Simulators](https://arxiv.org/abs/2310.06114)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Learning interactive world simulators by orchestrating multimodal real data; sim-trained policies deploy zero-shot to real robots.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">October 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley + Google DeepMind + MIT</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Built around a <strong>video diffusion model</strong></li><li>Orchestrates complementary multi-axis real data: image objects, robot actions, navigation motion, language</li><li>Uniformly supports high-level language instructions and low-level control; inference resembles POMDP rollouts</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Won the <strong>ICLR 2024 Outstanding Paper Award</strong></li><li>Sim-only trained VLM planners and RL policies transfer zero-shot to real robots</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Training data combines Ego4D, Something-Something, Bridge, RH20T, RT-1, etc.; not open-sourced</td></tr>
</tbody>
</table>

### [TD-MPC2: Scalable, Robust World Models for Continuous Control](https://arxiv.org/abs/2310.16828)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A scalable, robust world model algorithm that excels across 104 online RL tasks with a single hyperparameter setting.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">October 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UCSD + CMU (Nicklas Hansen, Hao Su, Xiaolong Wang)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>An improvement over <strong>TD-MPC</strong>: performs local trajectory optimization in the latent space of an implicit (decoder-free) world model</li><li><strong>Single hyperparameter</strong> stable across 104 tasks</li><li>A single <strong>317M-parameter</strong> agent simultaneously handles 80 tasks (multi-domain, multi-embodiment, multi-action-space)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Significantly outperforms baselines across 104 online RL tasks (4 major domains)</li><li>Agent capability <strong>scales</strong> with model and data size</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Models TD-MPC2 (up to 317M, open-sourced); evaluated on DMControl, Meta-World, Manipulation, Humanoid (ICLR 2024)</td></tr>
</tbody>
</table>

- **[ICRA March 2023](https://arxiv.org/abs/2303.15482)** OmniGibson: A Modular Simulation Environment for Embodied AI. A modular embodied AI simulation environment.

- ★ **[NeurIPS August 2021](https://arxiv.org/abs/2108.10470)** Isaac Gym: High Performance GPU-Based Physics Simulation for Robot Learning. A high-performance GPU-based physics simulator for robot learning.

### [DreamerV3: Mastering Diverse Skills through World Models](https://arxiv.org/abs/2301.04104)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A general world-model RL method with fixed hyperparameters sweeping 150+ tasks, the first to obtain diamonds in Minecraft from scratch.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">January 2023</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind + University of Toronto (Danijar Hafner et al.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>RSSM discrete latent state world model</strong></li><li>Robustness techniques such as symlog transform, two-hot reward regression and KL balancing; a single set of hyperparameters works universally</li><li>actor-critic trained entirely on imagined trajectories within the world model</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Fixed hyperparameters surpass specialized algorithms on <strong>150+ tasks</strong>; Atari 100K mean 2.01x human level</li><li>First algorithm to collect diamonds in Minecraft from scratch (no human data) within 100M steps</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model open-sourced (danijar/dreamerv3, MIT); evaluation domains Atari, DMControl, DMLab, Minecraft, etc.</td></tr>
</tbody>
</table>

### [DayDreamer: World Models for Physical Robot Learning](https://arxiv.org/abs/2206.14176)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Brings the Dreamer world model directly to real-robot online RL, ditching the simulator.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jun 2022 (CoRL 2022)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">UC Berkeley (Danijar Hafner, Sergey Levine, Pieter Abbeel, et al.)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>RSSM world model</strong> + actor-critic training in imagination</li><li>Unified hyperparameters across <strong>4 robots</strong> (quadruped, bimanual arm, wheeled)</li><li>Full infrastructure open-sourced</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>A quadruped learns roll-over, stand, and walk from scratch in <strong>1 hour</strong></li><li>Adapts to perturbations within <strong>10 minutes</strong></li><li>Vision-based pick-and-place approaches human-level performance</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">DayDreamer (code open-sourced, danijar.com/daydreamer)</td></tr>
</tbody>
</table>
- **[IROS December 2020](https://arxiv.org/abs/2012.02924)** iGibson 1.0: A Simulation Environment for Interactive Tasks in Large Realistic Scenes. A simulation environment for interactive tasks in large realistic scenes.

- **[CoRL September 2020](https://arxiv.org/abs/2009.12293)** robosuite: A Modular Simulation Framework and Benchmark for Robot Learning. A modular simulation framework and benchmark for robot learning.

- ★ **[NeurIPS July 2020](https://arxiv.org/abs/2007.04954)** ThreeDWorld: A Platform for Interactive Multi-Modal Physical Simulation. A platform for interactive multimodal physical simulation.

- ★ **[CVPR March 2020](https://arxiv.org/abs/2003.08515)** SAPIEN: A SimulAted Part-based Interactive ENvironment. A part-based interactive simulation environment.

### [Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model](https://arxiv.org/abs/1911.08265)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Plans with a learned world model, reaching superhuman performance without knowledge of environment dynamics.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">November 2019</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google DeepMind</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>MuZero algorithm</strong>: combines tree search with a learned model</li><li>The learned model iteratively predicts the three key planning quantities: <strong>reward, policy, and value</strong></li><li>Requires no knowledge of environment dynamics / game rules</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Achieves new SOTA on 57 Atari games</li><li><strong>Matches AlphaZero</strong> in Go, chess, and shogi (AlphaZero requires game rules; MuZero does not)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Model MuZero (not open-sourced); evaluated on Atari, Go, Chess, Shogi (Nature 2020)</td></tr>
</tbody>
</table>

- **[CoRL October 2019](https://arxiv.org/abs/1910.10897)** Meta-World: A Benchmark and Evaluation for Multi-Task and Meta Reinforcement Learning. A multitask and meta-reinforcement learning benchmark.

- ★ **[ICCV April 2019](https://arxiv.org/abs/1904.01201)** Habitat: A Platform for Embodied AI Research. An embodied AI research platform including simulators and datasets.

- **[ICRA March 2019](https://arxiv.org/abs/1903.00742)** PyBullet: A Fast Physics Simulation for Robotics. A fast physics simulation library for robotics.

### [World Models](https://arxiv.org/abs/1803.10122)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A three-stage world model of VAE + MDN-RNN + controller, pioneering the paradigm of training agents in "dreams".</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">March 2018</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Google Brain (David Ha) + NNAISENSE / IDSIA (Jürgen Schmidhuber)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Three stages: <strong>VAE visual compression + MDN-RNN temporal memory + controller</strong></li><li>V/M modules trained unsupervised</li><li>The controller can be trained entirely in the world model's "dreams" and then transferred back to the real environment</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>CarRacing-v0 average <strong>906±21 points</strong>, the first method to solve this environment</li><li>ViZDoom pure dream-training policy transfers to the real environment, achieving 1092±556 survival steps</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Code open-sourced (worldmodels); evaluation environments OpenAI Gym (CarRacing, ViZDoom)</td></tr>
</tbody>
</table>

- **[arXiv January 2018](https://arxiv.org/abs/1801.00690)** DMControl: DeepMind Control Suite. A benchmark suite for continuous control tasks.

- ★ **[CVPR December 2017](https://arxiv.org/abs/1712.05474)** AI2-THOR: An Interactive 3D Environment for Visual AI. A classic interactive 3D environment for visual AI.

- **[IROS October 2012](https://homes.cs.washington.edu/~todorov/papers/TodorovIROS12.pdf)** MuJoCo: A Physics Engine for Model-Based Control. A classic physics engine for model-based control.

<a id="datasets" name="datasets"></a>

## Datasets

### [RynnWorld-Teleop: An Action-Conditioned World Model for Digital Teleoperation](https://arxiv.org/abs/2607.06558)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A generative world model replaces the real robot, enabling "digital teleoperation" as a data engine.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Jul 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Rynn team</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li><strong>Digital teleoperation</strong>: an operator's hand-pose stream drives a world model to synthesize high-fidelity egocentric video from a single reference image, decoupling data collection from physical hardware</li><li>Depth-aware skeletal conditioning + video Diffusion Transformer + <strong>streaming autoregressive distillation</strong></li><li><strong>40+ FPS</strong> real-time interactive generation on a single H100</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Policies trained solely on generated data achieve <strong>zero-shot Sim2Real</strong> transfer</li><li>Augmenting real datasets with digital-teleop data consistently improves success rates</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">RynnWorld-Teleop data engine</td></tr>
</tbody>
</table>

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.04367)** Perception-Manipulation: Food Cutting. A perception-manipulation robotics system for food cutting.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.22142)** RoboLineage: Data Lifecycle Governance. Represents data collection and training steps as typed lineage artifacts for lifecycle management.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.20990)** Duet: Dual-Robot Teaching. Efficient dual-robot learning via VR teleoperation and human collaboration priors.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.17385)** EgoInfinity: 4D Data Engine. Automatically generates 4D hand-object interaction data from internet videos for cross-embodiment retargeting.

- **[arXiv Jun 2026](https://arxiv.org/abs/2606.14665)** EgoGuide: Robot-Free Demo Collection. Synchronizes wrist and head views with online visual-geometric quality guidance for efficient data collection.

- **[arXiv May 2026](https://arxiv.org/abs/2605.29462)** CFMME: A Comprehensive Chinese Financial Multimodal Evaluation Dataset. Proposes CFMME, a Chinese financial multimodal evaluation benchmark with 6,052 instances covering eight financial image modalities, providing evaluation tools for embodied intelligence financial applications.

- **[arXiv April 2026](https://arxiv.org/abs/2604.21017)** Open-H-Embodiment: A Large-Scale Dataset for Enabling Foundation Models in Medical Robotics. A large-scale embodied dataset for medical robotics foundation models, addressing the small scale, single embodiment, and difficult sharing of medical robot data.

- **[arXiv April 2026](https://arxiv.org/abs/2604.20444)** VTouch++: A Multimodal Dataset with Vision-Based Tactile Enhancement for Bimanual Manipulation. A multimodal bimanual manipulation dataset that enhances tactile signals with vision and provides higher-fidelity physical interaction supervision for contact-rich tasks.

- **[arXiv February 2026](https://arxiv.org/abs/2602.01693)** Manip-Cognition-1.6M: GSR: Learning Structured Reasoning for Embodied Manipulation. A large-scale dataset for structured reasoning in embodied manipulation, jointly supervising world understanding, action planning, and goal explanation.

- **[arXiv October 2025](https://arxiv.org/abs/2510.11027)** Vlaser-6M: Vlaser: Vision-Language-Action Model with Synergistic Embodied Reasoning. A high-quality embodied reasoning dataset that supports evaluation across spatial reasoning, embodied grounding, embodied QA, and task planning.

- **[arXiv August 2025](https://arxiv.org/abs/2508.12378)** Embodied-Points-200K: Embodied-R1: Reinforced Embodied Reasoning for General Robotic Manipulation. A large-scale dataset built by combining embodied and general visual reasoning data to support key embodied pointing capabilities.

### [DexMimicGen: Automated Data Generation for Bimanual Dexterous Manipulation via Imitation Learning](https://arxiv.org/abs/2410.24185)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Automated generation of large-scale bimanual dexterous manipulation data from a handful of human demos.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Oct 2024</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">NVIDIA, Stanford University</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Synthesizes <strong>21K demonstrations from just 60 source human demos</strong> across bimanual dexterous tasks</li><li>Real-to-sim-to-real pipeline for practical deployment</li><li>Targets humanoids with dexterous hands and bimanual coordination</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Deployed on a real-world humanoid can-sorting task</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">DexMimicGen (project page dexmimicgen.github.io)</td></tr>
</tbody>
</table>

- **[RSS March 2024](https://arxiv.org/abs/2403.12945)** DROID: A Large-Scale In-the-Wild Robot Manipulation Dataset. A large-scale real-world robot manipulation dataset.

- **[ICRA November 2023](https://arxiv.org/abs/2311.12032)** RH20T: A Comprehensive Robotic Dataset for Learning Diverse Skills in Real-World. A real-world dataset for diverse robotic skill learning.

- **[arXiv October 2023](https://arxiv.org/abs/2310.08864)** Open X-Embodiment Dataset: Robotic Learning Datasets and RT-X Models. The largest multi-robot dataset to date, spanning 22 robot types and more than one million trajectories.

- **[CoRL August 2023](https://arxiv.org/abs/2308.12952)** BridgeData V2: A Dataset for Robot Learning at Scale. A large-scale dataset for robot learning.
- ★ **[CVPR October 2021](https://arxiv.org/abs/2110.07058)** Ego4D: Around the World in 3,000 Hours of Egocentric Video. A large-scale egocentric video dataset.
- ★ **[NeurIPS September 2021](https://arxiv.org/abs/2109.08238)** HM3D: Habitat-Matterport 3D Dataset (HM3D): 1000 Large-scale 3D Environments for Embodied AI. A large-scale 3D environment dataset for embodied AI.

- **[ICRA March 2020](https://arxiv.org/abs/2003.06789)** GraspNet: A Large-Scale Cluttered Scene Dataset for Robotic Grasping. A large-scale cluttered-scene grasping dataset.
- ★ **[ICCV April 2019](https://arxiv.org/abs/1904.03278)** AMASS: Archive of Motion Capture as Surface Shapes. A large human motion dataset.
- ★ **[TPAMI May 2017](https://arxiv.org/abs/1705.09155)** Human3.6M: Large Scale Datasets and Predictive Methods for 3D Human Sensing. A large-scale human 3D pose dataset.
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>
<a id="benchmarks-evaluation" name="benchmarks-evaluation"></a>

## Benchmarks & Evaluation

### [GAUGE: A Measurement-Grounded Benchmark for Physical Fidelity in Simulation Engines and Video World Models](https://arxiv.org/abs/2608.05948)

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">A measurement-anchored benchmark that uniformly diagnoses physical fidelity of physics engines and video world models.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release date</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">August 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">Shanghai AI Laboratory InternRobotics (with multiple institutions)</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>First real-world diagnostic benchmark that <strong>evaluates numerical physics engines and generative video world models together</strong> for physical fidelity</li><li><strong>22 controlled task families</strong> covering rigid bodies, cables, fabrics, and volumetrically deformable objects</li><li>Anchors real trajectories with <strong>calibrated physical metadata and uncertainty annotations</strong>, localizing which physical law/parameter is violated</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Results</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640"><ul><li>Across 14 task families, <strong>Isaac Sim, Genesis, and Newton</strong> show no universally faithful engine; largest deviations in impact contacts, fast fabrics, and volumetric deformation</li><li>Six image-to-video models generate trajectories that are <strong>equation-form-correct but wrong in acceleration/momentum/oscillation timing</strong></li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data / Models</td><td style="word-wrap:break-word;width:640px;min-width:640px;max-width:640px" width="640">GAUGE benchmark (22 task families)</td></tr>
</tbody>
</table>

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.26789)** CheckVLA: Execution-Time Verification. Execution-time verification with action-conditioned world model for mobile manipulation.


- **[arXiv Jul 2026](https://arxiv.org/abs/2607.23108)** Curse of Precision: Scaling Law. Listed above
- **[arXiv Jul 2026](https://arxiv.org/abs/2607.14609)** Tactile Grounding for Contact-Rich Tasks. Representation-aligned tactile grounding for contact-rich robotic manipulation.
- **[arXiv Jul 2026](https://arxiv.org/abs/2607.13818)** Agentic RL for Robust Execution. Learning robust execution in manipulation with agentic reinforcement learning.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.31494)** Robustness of Robotic Manipulation: Survey. Systematically studies robustness definitions, frameworks, and evaluation methods for manipulation.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.25503)** AISPO: Depth Reliability. Depth completion framework for transparent and reflective objects in manipulation.
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.20999)** Inductive Generalization. Listed above
- **[arXiv Jun 2026](https://arxiv.org/abs/2606.18610)** SC3-Eval: Evaluating via Video Generation. Evaluates robot foundation models via self-consistent video generation.
- **[arXiv May 2026](https://arxiv.org/abs/2605.30326)** RoboWits: Unexpected Challenges for Robotic Creative Problem Solving. A dual-arm robot benchmark that systematically evaluates cognitive reasoning, creative tool use, and robustness to unexpected conditions, providing new perspectives for embodied intelligence creative problem solving.
- **[arXiv May 2026](https://arxiv.org/abs/2605.28805)** OmniVerifier-M1: Multimodal Meta-Verifier with Explicit Structured Recalibration. A multimodal meta-verifier using symbolic meta-verification and decoupled RL for fine-grained error localization, supporting dynamic region-level self-correction.
- **[arXiv May 2026](https://arxiv.org/abs/2605.27932)** When Think-with-Image Meets Safety: What Determines Multimodal Jailbreak Robustness? Studies multimodal LLM safety, finding that explicit image tool interaction can reduce jailbreak success rate by ~30%, providing new insights for embodied intelligence safety..
- **[arXiv May 2026](https://arxiv.org/abs/2605.12674)** Revealing Interpretable Failure Modes of VLMs (REVELIO). A framework for systematically uncovering interpretable VLM failure modes through diversity-aware beam search and Gaussian-process Thompson sampling in autonomous driving and indoor robotics.
- **[arXiv May 2026](https://arxiv.org/abs/2605.00397)** MiniVLA-Nav v1: A Multi-Scene Simulation Dataset for Language-Conditioned Robot Navigation. A multi-scene simulation dataset for language-conditioned robot navigation with RGB, depth, instance segmentation, expert actions, and in-distribution / paraphrase / OOD evaluation splits.
- **[arXiv April 2026](https://arxiv.org/abs/2604.25161)** Capability-Oriented Failure Attribution for Vision-and-Language Navigation Agents. A navigation-focused evaluation study on attributing failures through a capability-oriented lens, with an emphasis on safety constraints.
- **[arXiv April 2026](https://arxiv.org/abs/2604.24086)** AsyncShield: A Plug-and-Play Edge Adapter for Asynchronous Cloud-based VLA Navigation. An asynchronous control adapter for cloud-based VLA navigation that corrects delayed intent with spatiotemporal pose buffering and kinematic mapping while balancing tracking and obstacle-avoidance safety with a constrained MDP.
- **[arXiv April 2026](https://arxiv.org/abs/2604.24033)** Event-based SLAM Benchmark for High-Speed Maneuvers. Introduces EvSLAM, an event-camera SLAM benchmark for high-speed maneuvers across multiple platforms, extreme lighting conditions, and complex motion patterns.
- **[arXiv April 2026](https://arxiv.org/abs/2604.23775)** Vision-Language-Action Safety: Threats, Challenges, Evaluations, and Mechanisms. A systematic review of safety threats, open challenges, evaluation methods, and mitigation mechanisms for VLA systems, with a focus on long-horizon execution risk.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21686)** WorldMark: A Unified Benchmark Suite for Interactive Video World Models. A unified benchmark suite for interactive video world models, comparing prediction, interaction, and controllable generation.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21568)** A Bayesian Reasoning Framework for Robotic Systems in Autonomous Casualty Triage. Fuses outputs from multiple vision algorithms with Bayesian-network reasoning to support automated casualty triage and risk assessment under missing or conflicting perceptual input.
- **[arXiv April 2026](https://arxiv.org/abs/2604.21192)** How VLAs (Really) Work In Open-World Environments. A systematic analysis of how VLAs behave in open-world environments, with attention to spatial perception, task decomposition, and execution failure modes.
- **[arXiv April 2026](https://arxiv.org/abs/2604.20472)** Temporal Difference Calibration in Sequential Tasks: Application to Vision-Language-Action Models. Applies temporal-difference calibration to VLA training and evaluation to reduce long-sequence error accumulation and value drift.
- **[arXiv April 2026](https://arxiv.org/abs/2604.20193)** LLM-Guided Safety Agent for Edge Robotics with an ISO-Compliant Perception-Compute-Control Architecture. An ISO-compliant safety architecture for edge robotics that turns natural-language safety requirements into executable predicates for low-latency closed-loop control.
- **[arXiv April 2026](https://arxiv.org/abs/2604.20151)** Toward Safe Autonomous Robotic Endovascular Interventions using World Models. A world-model-based safety-control framework for autonomous robotic endovascular intervention that improves robustness and long-term stability across diverse patient anatomies.
- **[arXiv April 2026](https://arxiv.org/abs/2604.19638)** SafetyALFRED: Evaluating Safety-Conscious Planning of Multimodal Large Language Models. Extends ALFRED with six categories of kitchen hazards to evaluate whether multimodal large language models proactively avoid safety risks during interaction.
- **[arXiv April 2026](https://arxiv.org/abs/2604.19133)** baltic: a benchmark and cross-domain strategy for 3d reconstruction across air and underwater domains under varying illumination. A 3D reconstruction benchmark across air and underwater domains under changing lighting, with evaluation of SfM, NeRF, and 3DGS on geometry and perceptual quality.
- **[arXiv April 2026](https://arxiv.org/abs/2604.17969)** E3VS-Bench: A Benchmark for Viewpoint-Dependent Active Perception in 3D Gaussian Splatting Scenes. A benchmark for viewpoint-dependent active perception in 3D Gaussian scenes, targeting exploration, observation, and decision-making under viewpoint-sensitive tasks.
- **[arXiv April 2026](https://arxiv.org/abs/2604.03956)** VLA-Forget: Vision-Language-Action Unlearning for Embodied Foundation Models. An unlearning method for embodied foundation models that studies how to safely remove specific knowledge or behaviors from VLAs while preserving overall performance.
- ★ **[AAAI March 2026](https://ojs.aaai.org/index.php/AAAI/article/view/40880)** IS-Bench: Evaluating Interactive Safety of VLM-Driven Embodied Agents in Daily Household Tasks. The first multimodal interactive safety benchmark for embodied agents, covering 161 challenging scenarios and 388 unique safety risks.
- **[arXiv January 2026](https://arxiv.org/abs/2601.15282)** RBench: Rethinking Video Generation Model for the Embodied World. A comprehensive benchmark for robot video generation spanning five task domains and four embodiments, with strong correlation to human evaluation.

- **[arXiv January 2026](https://arxiv.org/abs/2601.04137)** WoW-World-Eval: Wow, wo, val. A Comprehensive Embodied World Model Evaluation Turing Test. An embodied Turing-test-style benchmark built on 609 robot manipulation samples and evaluating perception, planning, prediction, generalization, and execution with 22 metrics.
- **[arXiv January 2026](https://arxiv.org/abs/2601.03136)** Limited Linguistic Diversity in Embodied AI Datasets. An analysis of limited linguistic diversity in embodied AI datasets, with implications for training and evaluation.
- **[arXiv December 2025](https://arxiv.org/abs/2512.24125)** ERIQ: Unified Embodied VLM Reasoning with Robotic Action via Autoregressive Discretized Pre-training. A large-scale embodied reasoning benchmark with more than 6,000 QA pairs covering four reasoning dimensions and revealing strong links between embodied reasoning and end-to-end VLA generalization.
- **[arXiv November 2025](https://arxiv.org/abs/2511.20937)** ENACT: Evaluating Embodied Cognition with World Modeling of Egocentric Interaction. A benchmark for embodied cognition based on egocentric interaction world modeling, using reorder tasks to test action-effect reasoning, embodiment awareness, and long-term memory.
- **[arXiv July 2025](https://arxiv.org/abs/2507.12385)** OmniEAR: Benchmarking Agent Reasoning in Embodied Tasks. A comprehensive framework for evaluating language-model reasoning in embodied tasks involving physical interaction, tool use, and multi-agent collaboration.

- **[arXiv May 2025](https://arxiv.org/abs/2505.12388)** StaticEmbodiedBench: A Plug-and-Play Benchmark for Embodied AI. A plug-and-play benchmark that uses static scene representations for unified evaluation without the cost and fragmentation of interactive simulation or real-world setups.
- **[arXiv February 2025](https://arxiv.org/abs/2502.07712)** SafeVLA: Safety Alignment for Vision-Language-Action Models. A safety-alignment method for VLA models.
- **[CoRL June 2024](https://arxiv.org/abs/2406.03456)** CRAM: A Benchmark for Compositional Reasoning and Action in Manipulation. A benchmark for compositional reasoning and action in manipulation.
- **[arXiv March 2024](https://arxiv.org/abs/2403.10510)** EmbSpatial-Bench: Benchmarking Spatial Reasoning for Embodied AI. A benchmark for spatial reasoning in embodied AI.
- ★ **[CVPR January 2024](https://arxiv.org/abs/2401.08912)** OpenEQA: Embodied Question Answering in the Era of Foundation Models. An embodied question-answering benchmark in the era of foundation models.
- ★ **[ICLR February 2023](https://arxiv.org/abs/2302.04659)** ManiSkill2: A Unified Benchmark for Generalizable Manipulation Skills. A unified benchmark for generalizable manipulation skills.
- ★ **[NeurIPS November 2022](https://arxiv.org/abs/2211.03745)** BEHAVIOR Challenge: Benchmarking Everyday Activities. A benchmark challenge for everyday activities.
- ★ **[CVPR March 2022](https://arxiv.org/abs/2203.09811)** BEHAVIOR-1K: A Benchmark for Embodied AI with 1,000 Everyday Activities. A benchmark of 1,000 everyday activities for embodied AI.
- ★ **[ICLR December 2021](https://arxiv.org/abs/2112.03227)** CALVIN: A Benchmark for Language-Conditioned Policy Learning. A benchmark for language-conditioned policy learning.
- ★ **[NeurIPS June 2021](https://arxiv.org/abs/2106.09876)** Franka Kitchen: A Benchmark for Long-Horizon Manipulation. A benchmark for long-horizon manipulation.
- ★ **[CVPR April 2021](https://arxiv.org/abs/2104.04631)** DexYCB: A Benchmark for Capturing Hand Grasping of Objects. A benchmark for hand grasping of objects.
- **[ICRA September 2019](https://arxiv.org/abs/1909.12271)** RLBench: The Robot Learning Benchmark & Learning Environment. A robot learning benchmark and learning environment.
<a id="survey" name="survey"></a>
<a id="survey" name="survey"></a>
<a id="survey" name="survey"></a>
<a id="survey" name="survey"></a>

## Survey

- **[arXiv Jul 2026](https://arxiv.org/abs/2607.21655)** Progress Reward Modeling Survey. Unifies progress reward modeling research from interfaces, construction methods, and data benchmarks.


- **[arXiv Jul 2026](https://arxiv.org/abs/2607.06706)** VLA Models Review: UAV and Bimanual. Comprehensive survey of VLA models in UAV and bimanual manipulation.
- **[arXiv May 2026](https://arxiv.org/abs/2605.27817)** Deep Learning for Robot Vision. A survey of deep learning applications in robot vision, covering key tasks such as object detection, semantic segmentation, and depth estimation, providing a systematic reference for embodied intelligence perception.
- **[arXiv May 2026](https://arxiv.org/abs/2605.12090)** World Action Models: The Next Frontier in Embodied AI. The first systematic survey of world action models, proposing a taxonomy that unifies predictive state modeling and action generation across cascaded and joint paradigms.
- **[arXiv April 2026](https://arxiv.org/abs/2604.23001)** Vision-Language-Action in Robotics: A Survey of Datasets, Benchmarks, and Data Engines. A survey of VLA datasets, benchmarks, and data engines, with an emphasis on long-horizon tasks and unified evaluation settings.
- **[arXiv February 2026](https://arxiv.org/abs/2602.04567)** Benchmarking Vision-Language-Action Models: A Survey. A survey of benchmarking methods for vision-language-action models.
- **[Authorea February 2026](https://flamechallenge.authorea.com/doi/full/10.22541/au.177023340.02874343)** Embodied AI Evaluation: A Survey on Evaluation of Embodied AI. Builds a systematic evaluation framework around the full loop of perception, cognition, planning, and action, and summarizes the shift from outcome-only evaluation toward multidimensional process quality and physical safety assessment.
- **[arXiv January 2026](https://arxiv.org/abs/2601.09876)** Generative AI for Robotics: A Survey. A survey on generative AI for robotics.
- **[arXiv January 2026](https://arxiv.org/abs/2601.03456)** Embodied Foundation Models Survey: Embodied Foundation Models: A Survey. A survey of embodied foundation models.
- **[TechRxiv January 2026](https://www.techrxiv.org/doi/full/10.36227/techrxiv.176948355.54623875/v1)** World Models for VLA Agents: Towards Generalist Embodied AI: A Survey on World Models for VLA Agents. The first survey focused specifically on world models for VLA agents, organizing prior work into world planners, world action models, world synthesizers, and world simulators.
- **[TechRxiv January 2026](https://www.techrxiv.org/doi/full/10.36227/techrxiv.176739762.23746519/v1)** Physical AI: A Comprehensive Review of Physical Artificial Intelligence. A comprehensive review of generative physical AI systems, introducing a five-part taxonomy covering RFMs, VLAs, LBMs, DPMs, and WFMs.
- **[arXiv November 2025](https://arxiv.org/abs/2511.03456)** Data-Centric Embodied AI: A Survey. A survey of data-centric embodied AI.
- **[arXiv October 2025](https://arxiv.org/abs/2510.12390)** Efficient VLA: Efficient Vision-Language-Action Models for Embodied Manipulation: A Systematic Survey. A systematic review of methods for improving VLA efficiency, especially around latency, memory footprint, and training and inference cost.
- **[arXiv October 2025](https://arxiv.org/abs/2510.04567)** Embodied Agents with LLMs: A Survey. A survey of embodied agents driven by large language models.
- **[arXiv April 2025](https://arxiv.org/abs/2504.06789)** Open-Source Robotics: A Survey. A survey of open-source robotics.
- **[arXiv March 2025](https://arxiv.org/abs/2503.08912)** Humanoid Robots: A Survey of Technologies and Challenges. A survey of humanoid robot technologies and challenges.
- **[arXiv March 2025](https://arxiv.org/abs/2503.04734)** Vision-Language-Action Models: A Survey. A survey of VLA models.
- **[arXiv July 2024](https://arxiv.org/abs/2407.06886)** Embodied AI: A Survey. A comprehensive survey of embodied AI.

- **[arXiv November 2023](https://arxiv.org/abs/2311.08923)** Robot Learning in Era of Foundation Models: Robot Learning in the Era of Foundation Models. A survey of robot learning in the era of foundation models.
- **[arXiv December 2022](https://arxiv.org/abs/2212.04567)** Sim-to-Real Transfer for Robotics: A Survey. A survey of Sim2Real transfer in robotics.
- **[arXiv May 2022](https://arxiv.org/abs/2205.09876)** A Survey of Embodied Navigation. A survey of embodied navigation.
- **[arXiv September 2021](https://arxiv.org/abs/2109.06789)** A Survey of Imitation Learning: Algorithms, Applications, and Challenges. A survey of imitation learning.
- **[T-RO March 2021](https://arxiv.org/abs/2103.04567)** Robotic Manipulation: A Survey. A survey of robotic manipulation.
- **[IJRR April 2020](https://arxiv.org/abs/2004.09876)** Reinforcement Learning for Robotics: A Survey. A survey of reinforcement learning for robotics.
