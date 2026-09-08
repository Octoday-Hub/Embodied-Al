# 具身智能数据集

> 51 个有代表性的具身智能数据集，覆盖真实采集、跨机器人汇总、RGB-D / 力 / 触觉、桌面操作、仿真基准与数据生成。统计以官方主页、仓库与论文为准。

---

### 索引

| 数据集 | 定位 | 类型 | 体量规模 | 关键模态 | 官方主页 |
|---|---|---|---|---|---|
| [DROID](#droid-sample) | 13 家北美实验室的大规模真实世界遥操作数据集 | 真实采集 | ~76k 轨迹 / 564 场景 | RGB + 本体感觉 + 语言 | [官方主页](https://droid-dataset.github.io/) |
| [Open X-Embodiment / RT-X](#open-x-sample) | 21 家机构汇总的真实机器人数据集集合 | 真实采集 + 汇总 | 1M+ 轨迹 / 22 embodiment | RGB + 语言 | [官方主页](https://robotics-transformer-x.github.io/) |
| [RH20T](#rh20t-sample) | 含力 / 触觉 / 音频多模态的接触丰富操作 | 真实采集 | 110k+ 序列 / 147 任务 | RGB-D + 力 + 触觉 + 音频 | [官方主页](https://rh20t.github.io/) |
| [BridgeData V2](#bridgedata-sample) | 桌面操作的 VR 遥操作数据集 | 真实采集 | 60k 轨迹 / 24 环境 | RGB-D + 语言 | [官方主页](https://rail-berkeley.github.io/bridgedata/) |
| [LIBERO](#libero-sample) | 终身机器人学习 / 知识迁移的仿真 benchmark | 仿真 + 演示 | 130 任务 / 4 套件 | 仿真 RGB + 语言 | [官方主页](https://libero-project.github.io/) |
| [MimicGen](#mimicgen-sample) | 从少量人类示范自动生成大规模仿真数据 | 仿真 + 生成 | 50k+ 轨迹 / 18 任务 | 仿真 RGB + 机器人状态 | [官方主页](https://mimicgen.github.io/) |
| [AgiBot World](#ds-agibot-world) | 智元百万级真机操作轨迹 | 真实采集 | 100万+ 轨迹 / 217 任务 | RGB-D + 力 + 触觉 + 语言 | [官方主页](https://agibot-world.com/) |
| [RoboMIND](#ds-robomind) | 多构型真机遥操作数据集与评测基准 | 真实采集 | 31万+ 轨迹 / 739 任务 | RGB(-D) + 触觉 + 语言 | [官方主页](https://x-humanoid-robomind.github.io/) |
| [Xiaomi-Robotics-1 Dataset](#ds-xiaomi-robotics-1-dataset) | 10万小时 UMI 轨迹 VLA 预训练语料 | 真实采集 | 10万小时 / 1700+ 场景 | 第一视角 RGB + 语言 | [官方主页](https://robotics.xiaomi.com/xiaomi-robotics-1.html) |
| [Hy-UMI-10K](#ds-hy-umi-10k) | 亚毫米精度指套 UMI 人示教数据 | 真实采集 | 1万+ 小时 / 70 类任务 | 第一视角 RGB + 力/力矩 | [官方主页](https://tairos.tencent.com/openSourceModels/hy-embodied-0.5-vla) |
| [ALOHA / Mobile ALOHA](#ds-aloha-mobile-aloha) | 低成本双臂/移动双臂遥操作数据集 | 真实采集 | 6 真机任务 + 7 类移动操作 | 多视角 RGB + 关节位姿 | [官方主页](https://tonyzhaozh.github.io/aloha/) |
| [UMI](#ds-umi) | 手持夹爪野外采集人示教 | 真实采集 | 1447 条野外演示 | 腕部鱼眼 RGB + IMU/SLAM | [官方主页](https://umi-gripper.github.io/) |
| [Dobb·E](#ds-dobb-e) | 家用 iPhone 改造采集棒家庭示教 | 真实采集 | 13 小时 / 5620 轨迹 | RGB-D + 夹爪位姿 | [官方主页](https://www.dobb-e.com/) |
| [Adroit](#ds-adroit) | 24-DoF 灵巧手仿真任务套件 | 仿真 | 4 任务 / 25 演示每任务 | 状态/力矩 | [官方主页](http://sites.google.com/view/deeprl-dexterous-manipulation) |
| [RoboCasa](#ds-robocasa) | 生成式 AI 厨房仿真框架 | 仿真 | 2200+ 小时 / 365 任务 | RGB-D + 本体状态 | [官方主页](https://robocasa.ai/) |
| [BEHAVIOR-1K](#ds-behavior-1k) | 千项日常活动仿真基准 | 仿真 | 1000 活动 / 50 场景 | RGB-D + 物理状态 | [官方主页](https://behavior.stanford.edu/) |
| [CALVIN](#ds-calvin) | 长时程语言条件操作基准 | 仿真 | 34 子任务 / 约 2.4 万轨迹 | RGB-D + 语言 | [官方主页](https://github.com/mees/calvin) |
| [RLBench](#ds-rlbench) | 视觉引导多任务仿真基准 | 仿真 | 100+ 任务 | RGB-D + 分割 | [官方主页](https://sites.google.com/view/rlbench) |
| [Meta-World](#ds-meta-world) | 元强化学习 50 任务基准 | 仿真 | 50 任务 | 状态/关节 | [官方主页](https://meta-world.github.io/) |
| [Franka Kitchen](#ds-franka-kitchen) | 多阶段厨房操作模仿学习基准 | 真实采集 | 566 演示 | 关节 + 物体状态 | [官方主页](https://relay-policy-learning.github.io/) |
| [RoboTwin](#ds-robotwin) | 双臂操作仿真基准与数据生成 | 仿真 + 真实 | 50 双臂任务 / 10万+ 轨迹 | RGB-D + 语言 | [官方主页](https://robotwin-platform.github.io/) |
| [Ego4D](#ds-ego4d) | 大规模第一人称日常视频 | 视频 | 3670 小时 / 923 佩戴者 | 第一人称 RGB | [官方主页](https://ego4d-data.org/) |
| [EPIC-KITCHENS](#ds-epic-kitchens) | 第一人称厨房操作视频 | 视频 | 100 小时 / 45 厨房 | 第一人称 RGB + 音频 | [官方主页](https://epic-kitchens.github.io/) |
| [Physion](#ds-physion) | 物理直觉预测基准 | 仿真 | 约 2.5 万段视频 | RGB-D + 光流 + 分割 | [官方主页](https://physion-benchmark.github.io/) |
| [RoboGen](#ds-robogen) | 基础模型自动生成仿真任务 | 生成 | 100+ 任务 | 仿真生成 | [官方主页](https://generativesimulation.github.io/) |
| [Isaac GR00T](#ds-isaac-gr00t) | 人形数据生成与仿真训练管线 | 生成 + 仿真 | 78万 合成轨迹 / 11h | 多模态 | [官方主页](https://developer.nvidia.com/isaac/gr00t) |
| [RT-1 Robotic Dataset](#ds-rt-1-robotic-dataset) | 700+ 任务大规模真实遥操作数据集 | 真实采集 | 130k+ 轨迹 / 700+ 任务 | RGB + 语言 | [官方主页](https://robotics-transformer1.github.io/) |
| [FurnitureBench](#ds-furniturebench) | 真实家具组装长时程操作基准 | 真实采集 + 仿真 | 5100 轨迹 / 219.6 小时 / 8 任务 | RGB + 关节状态 | [官方主页](https://clvrai.github.io/furniture-bench/) |
| [RoboAgent (RoboSet)](#ds-roboagent) | 低数据量多技能操作数据集 | 真实采集 | 100k+ 轨迹 / 12 技能 / 38 任务 | RGB + 语言 | [官方主页](https://robopen.github.io/) |
| [TriFinger](#ds-trifinger) | 三指灵巧操作远程真实基准 | 真实采集 + 仿真 | 9 DoF 平台 / 10k+ episodes | RGB + 指尖力 | [官方主页](https://is.mpg.de/ei/projects/robot-benchmark) |
| [Ravens](#ds-ravens) | 桌面操作仿真基准 | 仿真 | 10 任务 + 5 变体 | RGB-D | [官方主页](https://transporternets.github.io/) |
| [SoftVTBench](#ds-softvtbench) | 视触觉可变形物体操作数据集与基准 | 真实采集 + 仿真 | 4000 演示 / 50+ 资产 / 20Hz 多模态 | RGB + 触觉 + FEM 状态 | [官方主页](https://arxiv.org/abs/2608.18701) |
| [Open-AoE](#ds-open-aoe) | 开放自我中心操作数据集与工具链 | 真实采集 | 约 2000 小时 / 500+ 贡献者 | 第一人称 RGB + MANO 手部姿态 | [官方主页](https://arxiv.org/abs/2607.14183) |
| [QuadFM](#ds-quadfm) | 文本驱动四足运动生成数据集 | 动作捕捉 | 11784 条运动片段 / 35352 条描述 | 运动 + 语言 | [官方主页](https://github.com/GaoLii/QuadFM) |
| [ManiGuard](#ds-maniguard) | 操作安全评估基准与数据套件 | 真实 + 仿真 | 200 任务 / 1000 场景 / 8000 安全标注演示 | RGB + 规范约束 | [官方主页](https://arxiv.org/abs/2608.17386) |
| [EmbodimentSemantic](#ds-embodimentsemantic) | 具身操作空间场景图数据集与基准 | 真实 + 仿真 | 60K+ 操作帧 / 120K+ 场景图 | RGB-D + 场景图 | [官方主页](https://arxiv.org/abs/2607.00020) |
| [DexYCB](#ds-dexycb) | NVIDIA 手物捕捉基准数据集 | 真实采集 | 58.2 万帧 / 1,000 序列 / 20 物体 | RGB-D + 6D 位姿 + 3D 手部 | [官方主页](https://dex-ycb.github.io/) |
| [OakInk](#ds-oakink) | 手部操作意图与可供性数据集 | 真实采集 + 虚拟迁移 | 5 万次交互 / 1,800 物体 affordance 库 | RGB-D + 手部姿态 + 意图标注 | [官方主页](https://oakink.net/) |
| [GraspNet-1Billion](#ds-graspnet) | 大规模密集抓取位姿数据集 | 真实采集 | 97,280 张 RGB-D / 190 场景 / 超 11 亿抓取位姿 | RGB-D + 6D 位姿 + 抓取标注 | [官方主页](https://graspnet.net/) |
| [HOI4D](#ds-hoi4d) | 类别级动态手物交互 4D 数据集 | 真实采集 | 240 万帧 / 4,000+ 序列 / 800 物体实例 | RGB-D 4D 点云 + 3D 手姿态 | [官方主页](https://hoi4d.github.io/) |
| [ARCTIC](#ds-arctic) | 铰接物体手物交互数据集 | 真实采集 | 210 万帧 / 339 序列 / 11 个铰接物体 | RGB 双视角 + 3D 手/物网格 + 接触标注 | [官方主页](https://arctic.is.tue.mpg.de/) |
| [GigaHands](#ds-gigahands) | 大规模多视角手部操作数据集 | 真实采集 | 34 小时 / 14k 片段 / 183M 帧 | 多视角 RGB + 3D 手/物姿态 + 文本 | [官方主页](https://ivl.cs.brown.edu/research/gigahands.html) |
| [EgoDex](#ds-egodex) | Apple 自我中心桌面操作数据集 | 真实采集 | 829 小时 / 338k 演示 / 194 类任务 | 1080p RGB + 3D 手部骨骼 + 语言 | [官方主页](https://github.com/apple/ml-egodex) |
| [DexCap](#ds-dexcap) | 便携手部捕捉灵巧操作数据 | 真实采集 | 6 个灵巧操作任务评测 | 3D 点云 + 手部 mocap | [官方主页](https://dex-cap.github.io/) |
| [HumanPlus](#ds-humanplus-data) | 人形影子跟随全身数据 | 真实采集 | 40 小时人体运动 / 每任务最多 40 演示 | RGB 自我中心 + 全身关节 | [官方主页](https://humanoid-ai.github.io/) |
| [LeRobot Community Datasets](#ds-lerobot-data) | Hugging Face 社区机器人数据集合 | 真实采集 | 约 189 个数据集（持续增长） | 多相机 RGB + 状态/动作 + 语言 | [官方主页](https://huggingface.co/lerobot) |
| [ABC-130K](#ds-abc-130k) | 迄今最大开源双臂遥操作数据集 | 真实采集 | 134,806 条轨迹 / 3,553 小时 | 3 路 RGB + 本体状态/动作 | [官方主页](https://abc.bot/) |
| [TableVerse-100K](#ds-tableverse-100k) | Real2Sim 物理一致桌面场景生成 | 仿真生成 | 10 万场景 / 100 万物体实例 | 合成多视图 RGB + 网格 | [官方主页](https://bytedance.github.io/TableVerse/) |
| [DexCanvas](#ds-dexcanvas) | 人手灵巧操作 + 逐帧接触力 | 真实采集 + 仿真扩增 | 70 小时种子 / 计划 7,000 小时 | 多视角 RGB-D + MANO + 力觉 | [官方主页](https://dexcanvas.github.io/) |
| [Humanoid Everyday](#ds-humanoideveryday) | 开放世界人形整机操作 | 真实采集 | 10.3k 轨迹 / 260 任务 | RGB + 深度 + 触觉 + 语言 | [官方主页](https://humanoideveryday.github.io/) |
| [VTDexManip](#ds-vtdexmanip) | 人类触觉数据 + 灵巧操作基准 | 真实采集 + 仿真 | 565k 帧 / 2,032 序列 | RGB + 指尖压阻触觉 | [官方主页](https://lqts.github.io/VTDexManip/) |

---

### DROID

[官方主页](https://droid-dataset.github.io/) · [数据下载](https://droid-dataset.github.io/droid/the-droid-dataset) · [论文](https://arxiv.org/abs/2403.12945)

<a id="droid-sample"></a>

<div align="center">
  <img src="datasets-img/droid-sample-01.jpg" alt="DROID 官方 Dataset Visualizer" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方交互式 Viewer](https://droid-dataset.github.io/visualizer/) — 从 1000 条轨迹中按 Scene / Object / Task 三组维度实时筛选与随机浏览。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Stanford / UC Berkeley / Google 等 13 家北美实验室，统一在 Franka Panda 机器人硬件上采集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">跨场景、跨机构、跨任务的真实世界机器人操作；覆盖工业办公、厨房、办公室、客厅、卧室、浴室、走廊、洗衣房等 8 大类室内场景；面向行为克隆与 RLHF 的常用基准；DROID 的设计目标是让研究社区能够"在实验室外"采集大规模真实交互数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：完整 RLDS 版约 1.7 TB，通过 Google Cloud Storage 的 <code>gsutil</code> 命令访问（<code>gs://gresearch/robotics/</code>），文档页提供逐文件命令；另有原始立体高清视频（约 8.7 TB）与 <code>droid_100</code> 调试子集（约 2 GB，约 100 条 episode）；</li><li><strong>示例代码</strong>：官方 <a href="https://colab.research.google.com/drive/1b4PPH4XGht4Jve2xPKMCh-AXXAQziNQa?usp=sharing">Dataset Colab</a> 加载并可视化少量 episode；</li><li><strong>schema 文档</strong>：<a href="https://droid-dataset.github.io/droid/the-droid-dataset">The DROID Dataset</a>。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人在回路的机器人遥操作（human-in-the-loop robot teleoperation），跨多种建筑和场景采集；数据发布前完成人脸模糊处理。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">约 76,000 条轨迹 / 350 小时交互 / 564 个场景 / 52 栋建筑 / 86 个任务 / 18 台机器人 / 13 个机构 / 50 名采集者。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：3 路 ZED 立体 RGB 相机，包括 1 路腕部相机和 2 路外部相机；原始数据包含单目视频、拼接立体视频和 SVO 文件。RLDS 中公开左目 RGB 图像字段，示例尺寸为 180×320×3；原始版本为高清</li><li><strong>本体感觉</strong>：关节位置（7 维）、笛卡尔位置（6 维）、夹爪位置；原始 <code>trajectory.h5</code> 包含动作和本体感觉轨迹</li><li><strong>动作与控制</strong>：夹爪位置 / 速度、笛卡尔位置 / 速度、关节位置 / 速度；RLDS <code>action</code> 示例为 7 维，由关节速度和夹爪位置组成</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：自然语言任务指令及替代指令字段</li></ul></td></tr>
</tbody>
</table>

---

### Open X-Embodiment / RT-X

[官方主页](https://robotics-transformer-x.github.io/) · [数据下载](https://github.com/google-deepmind/open_x_embodiment) · [论文](https://arxiv.org/abs/2310.08864)

<a id="open-x-sample"></a>

<div align="center">
  <img src="datasets-img/open-x-embodiment-sample-01.jpg" alt="Open X-Embodiment 数据集合总览" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方主页](https://robotics-transformer-x.github.io/) — 跨 60 个数据集与 22 种 embodiment 的代表性视频与 RT-1 / RT-2 任务演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Google DeepMind 等 21 家机构合作汇总的真实机器人数据集集合。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">跨 22 种 embodiment（单臂、双臂、四足等）的统一训练集；RT-1 / RT-2 等 VLA 模型的预训练基石；为"一个模型，多种机器人形态"提供数据基础。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载与加载</strong>：官方以 TensorFlow Datasets（TFDS）提供统一接口，代码仓库 <a href="https://github.com/google-deepmind/open_x_embodiment">google-deepmind/open_x_embodiment</a> 的 Dataset Access 章节列出各子数据集的 <code>tfds.load</code> 名称与命令；按子数据集逐个下载；</li><li><strong>元数据</strong>：官方 dataset spreadsheet 记录每个贡献数据集的来源、许可、引用与字段说明（仓库 README 中提供链接）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">汇总 21 家机构公开的真实机器人数据，统一转换为 RLDS episode 格式。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">超过 1,000,000 条真实机器人轨迹 / 22 种 embodiment / 527 项技能 / 160,266 个任务 / 60 个子数据集 / 1,798 个属性 / 5,228 个物体 / 23,486 个空间关系。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：单臂 / 双臂 / 四足机器人的工作区 RGB 图像，统一输入之一；原始贡献数据集含视频演示片段</li><li><strong>本体感觉</strong>：无</li><li><strong>动作与控制</strong>：RLDS episode 序列；动作空间与控制频率由贡献数据集决定</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：自然语言任务字符串 / 任务标签（统一输入之一）；元数据含机器人状态与场景描述</li></ul></td></tr>
</tbody>
</table>

---

### RH20T

[官方主页](https://rh20t.github.io/) · [数据下载](https://rh20t.github.io/#download) · [论文](https://arxiv.org/abs/2307.00595)

<a id="rh20t-sample"></a>

<div align="center">
  <img src="datasets-img/rh20t-sample-01.jpg" alt="RH20T 遥操作数据采集平台" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方主页](https://rh20t.github.io/) — 展示 110k+ 接触丰富操作序列、多机器人配置与人类示范视频的代表性演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">上海交通大学（卢策吾团队 / MVIG 实验室）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">强调"接触丰富"（contact-rich）与多模态感知的真实世界操作数据集；每条机器人序列都配有对应的人类示范视频与语言描述，面向"单次人类示范、一键模仿"（one-shot imitation）研究；覆盖切、插、倒、折、旋等需要视觉与力 / 触觉协同的复杂技能。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：原始数据约 40 TB，官方另提供 640×360 缩放版（RGB 约 5 TB、RGBD 约 10 TB）；按 Cfg1–Cfg7 七种硬件配置分块，从官网的 Google Drive / 百度网盘链接获取；</li><li><strong>解析工具</strong>：官方 <a href="https://github.com/rh20t/rh20t_api">rh20t_api</a> 包提供数据解析（各配置的机器人信息见 <code>configs/configs.json</code>）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">为机器人配备力 / 力矩传感器并采用带力反馈渲染的力触觉设备（haptic device）进行遥操作，以实现精确高效、适应接触丰富交互的采集；同步录制对应的人类示范视频。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">110,000+ 接触丰富操作序列 / 147 个任务（48 个取自 RLBench、29 个取自 MetaWorld、70 个自行设计）/ 7 种硬件配置 / 4 款机械臂（Flexiv、UR5、Franka、Kuka）/ 50M+ 帧图像 / 110k+ 对应人类示范视频。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：每套配置 8–10 路全局 RGB-D 相机 + 1–2 路手内相机；含 RGB、深度、双目红外图像</li><li><strong>本体感觉</strong>：关节角度 / 关节力矩、夹爪状态、末端执行器（EE）位姿</li><li><strong>动作与控制</strong>：6–7 DoF 关节 + 夹爪；同时提供末端 / 夹爪的笛卡尔位姿</li><li><strong>力觉</strong>：6-DoF 力 / 力矩（force-torque）</li><li><strong>触觉</strong>：指尖触觉（仅 Cfg7 配置）</li><li><strong>其他</strong>：音频；每条序列配语言描述与对应人类示范视频</li></ul></td></tr>
</tbody>
</table>

---

### BridgeData V2

[官方主页](https://rail-berkeley.github.io/bridgedata/) · [数据下载](https://rail.eecs.berkeley.edu/datasets/bridge_release/data/) · [论文](https://arxiv.org/abs/2308.12952)

<a id="bridgedata-sample"></a>

<div align="center">
  <img src="datasets-img/bridgedata-v2-sample-01.jpg" alt="BridgeData V2 任务拼图总览" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方主页](https://rail-berkeley.github.io/bridgedata/) — 提供"Sample"按钮随机抽取一条轨迹，展示起始 / 结束状态与对应自然语言标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">加州大学伯克利分校 RAIL 实验室（Sergey Levine 团队）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">在低成本、易采购的 WidowX 250 平台上采集（整套硬件约 4000 美元），便于不同机构复现；每条轨迹配众包事后标注的自然语言指令，可支持目标条件、语言条件、模仿学习与离线强化学习等多种方法；是 OpenVLA、Octo 等 VLA 的常用真实世界微调基准，也是 Open X-Embodiment 汇总集的重要来源之一。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：原始数据以 NumPy 分块提供（约 400 GB），遥操作示范与脚本策略数据分为独立 zip；也可从 Open X-Embodiment 的 GCS 桶（<code>gs://gresearch/robotics</code>）以 RLDS 格式流式加载；</li><li><strong>训练代码</strong>：官方 <a href="https://github.com/rail-berkeley/bridge_data_v2">rail-berkeley/bridge_data_v2</a> 提供训练与评测代码及预训练权重。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">用 VR 控制器遥操作 WidowX 250 六自由度机械臂采集，控制频率 5 Hz，平均每条轨迹约 38 个时步；约每 50 条轨迹随机化相机位姿、更换物体与工作区位置以提升泛化；另含一部分由脚本策略自主采集的抓取-放置数据；任务标签为众包事后自然语言标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">60,096 条轨迹（其中 50,365 条遥操作示范 + 9,731 条脚本策略）/ 13 种技能 / 24 个环境 / 100+ 种物体；图像分辨率 640×480。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：1 路固定肩视 RGB-D 相机 + 2 路随机位姿 RGB 相机 + 1 路腕部 RGB 相机；分辨率 640×480</li><li><strong>本体感觉</strong>：机器人状态 / 夹爪状态</li><li><strong>动作与控制</strong>：WidowX 250 六自由度动作，控制频率 5 Hz；每条轨迹提供起始观测、目标状态（图像或文字）与动作序列</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：每条轨迹配众包事后标注的自然语言指令</li></ul></td></tr>
</tbody>
</table>

---

### LIBERO

[官方主页](https://libero-project.github.io/) · [数据下载](https://libero-project.github.io/datasets) · [论文](https://arxiv.org/abs/2306.03310)

<a id="libero-sample"></a>

<div align="center">
  <img src="datasets-img/libero-sample-01.jpg" alt="LIBERO 四套件任务总览" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方主页](https://libero-project.github.io/) — 展示四个任务套件的代表性任务与终身学习 benchmark 说明。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">德州大学奥斯汀分校（UT Austin）等，作者含 Yuke Zhu、Peter Stone 等。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">面向"终身机器人学习 / 知识迁移"（lifelong robot learning）的仿真 benchmark；提供可程序化生成、原则上可无限扩展任务的流水线；四个套件分别考察物体、空间布局、任务目标的分布迁移以及三者混合，适合系统性研究声明性知识与程序性知识的迁移。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：官方脚本 <code>benchmark_scripts/download_libero_datasets.py</code> 下载四个套件的人类遥操作示范；支持 <code>--datasets</code> 选择特定套件，或 <code>--use-huggingface</code> 从 HuggingFace 镜像下载；</li><li><strong>环境</strong>：基于 MuJoCo 仿真，需 Linux；仿真资产自动从 HuggingFace Hub（<code>lerobot/libero-assets</code>）加载并缓存到本地。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">由程序化生成流水线创建任务，并为全部 130 个任务提供高质量的人类遥操作示范数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">130 个语言条件的操作任务，分为四个套件：LIBERO-Spatial（10）、LIBERO-Object（10）、LIBERO-Goal（10）、LIBERO-100（100，进一步拆为 LIBERO-90 预训练 + LIBERO-10 长时序测试）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：仿真渲染 RGB 图像（示例相机分辨率 128×128）</li><li><strong>本体感觉</strong>：机器人状态 / 夹爪状态</li><li><strong>动作与控制</strong>：7 维动作（关节 + 夹爪）；基于 MuJoCo 的 OffScreenRenderEnv 环境步进</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：每个任务配语言指令（language-conditioned）；BDDL 任务定义文件</li></ul></td></tr>
</tbody>
</table>

---

### MimicGen

[官方主页](https://mimicgen.github.io/) · [数据下载](https://github.com/NVlabs/mimicgen) · [论文](https://arxiv.org/abs/2310.17596)

<a id="mimicgen-sample"></a>

<div align="center">
  <img src="datasets-img/mimicgen-sample-01.jpg" alt="MimicGen 数据生成系统总览" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方主页](https://mimicgen.github.io/) — 逐任务可视化生成轨迹、任务重置分布（reset distribution）与源人类示范到生成数据的对照演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">NVIDIA 与德州大学奥斯汀分校（作者含 Ajay Mandlekar、Yuke Zhu、Dieter Fox 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">本质是一套"数据生成系统"而非单纯数据集：将人类示范拆分为以物体为中心的子任务段，重新锚定到新场景 / 物体位姿后在仿真中回放，从少量示范自动扩增大规模数据；面向长时序与高精度（毫米级）接触任务，且模拟器无关（robosuite/MuJoCo、Isaac Gym 均可）；LIBERO、RoboCasa 等后续工作均采用其思路扩增基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：预生成数据集为标准 robomimic 格式的 HDF5 文件（约 60 GB），官方脚本 <code>download_datasets.py</code> 获取；</li><li><strong>自行生成</strong>：<code>generate_dataset.py</code> 从少量源示范出发，执行子任务分解、物体位姿重采样、仿真回放与成功过滤，生成新的 HDF5；代码见 <a href="https://github.com/NVlabs/mimicgen">NVlabs/mimicgen</a>（依赖 robomimic + robosuite）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">自动数据生成：从约 200 条人类遥操作示范出发，按以物体为中心的子任务段做空间变换并在仿真中回放拼接，过滤成功轨迹，约 250 倍扩增。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">50,000+ 条生成轨迹 / 18 个任务 / 多种机器人（Franka Panda、Sawyer、UR5e、双臂 Panda）/ 多个模拟器；源人类示范约 200 条。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：仿真渲染 RGB（智能体视角 + 腕部视角）</li><li><strong>本体感觉</strong>：低维机器人状态、物体位姿</li><li><strong>动作与控制</strong>：robomimic 标准动作格式；含子任务分段（subtask segmentation）信息</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：任务重置分布（reset distribution）；生成轨迹按源示范扩增而来</li></ul></td></tr>
</tbody>
</table>

---

### AgiBot World

<a id="ds-agibot-world"></a>

[官方主页](https://agibot-world.com/) · [数据下载](https://huggingface.co/datasets/agibot-world) · [论文](https://arxiv.org/abs/2503.06669)


<a id="agibot-world-sample"></a>

<div align="center">
  <img src="datasets-img/agibot-world-sample-01.png" alt="AgiBot World" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方项目页](https://agibot-world.com/) — 提供数据统计、场景浏览与下载入口。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">智元机器人 + 上海 AI Lab + 国家地方共建人形机器人创新中心。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">百万级真机操作轨迹，覆盖家庭/餐饮/工业/商超/办公五大场景；首个大规模含失败恢复数据的数据集，支持 VLA 预训练与失败模式研究。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：Beta 完整集约 43.8 TB，Alpha 精选子集 9.2 万条；HuggingFace 发布，CC BY-NC-SA 4.0；</li><li><strong>配套</strong>：与 AgiBot GO-1 模型及 AgiBot Digital World 仿真数据一同开源。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">双臂人形遥操作 + 人机协同质量校验（human-in-the-loop）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">1,003,672 条轨迹 / 217 任务 / 3000+ 物体 / 100+ 机器人。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB-D 多视角</li><li><strong>本体感觉</strong>：关节状态、六维力</li><li><strong>动作与控制</strong>：双臂动作序列</li><li><strong>力觉</strong>：六维力</li><li><strong>触觉</strong>：视触觉传感器、灵巧手</li><li><strong>其他</strong>：语言指令</li></ul></td></tr>
</tbody>
</table>

---

### RoboMIND

<a id="ds-robomind"></a>

[官方主页](https://x-humanoid-robomind.github.io/) · [论文](https://arxiv.org/abs/2412.13877)


<a id="robomind-sample"></a>

<div align="center">
  <img src="datasets-img/robomind-sample-01.png" alt="RoboMIND" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方项目页](https://x-humanoid-robomind.github.io/) — 提供数据下载、本体说明与评测基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">北京人形机器人创新中心 + 北京大学计算机学院。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">多构型真机遥操作数据集与评测基准，覆盖五大生活场景；含失败演示与 Isaac Sim 数字孪生，支持 VLA 训练与评测。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：HuggingFace 发布，全球下载量超千万；</li><li><strong>版本</strong>：V1.0（10.7 万条/479 任务）与 V2.0。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">遥操作 + 统一采集平台，含失败演示与 Isaac Sim 数字孪生。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">V2.0 超 31 万条轨迹 / 739 任务 / 6 种本体 / 129 技能 / 1.2 万+ 触觉序列。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：多视角 RGB(-D)</li><li><strong>本体感觉</strong>：本体状态、末端执行器信息</li><li><strong>动作与控制</strong>：动作序列</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：触觉序列（部分）</li><li><strong>其他</strong>：语言任务描述</li></ul></td></tr>
</tbody>
</table>

---

### Xiaomi-Robotics-1 Dataset

<a id="ds-xiaomi-robotics-1-dataset"></a>

[官方主页](https://robotics.xiaomi.com/xiaomi-robotics-1.html) · [论文](https://arxiv.org/abs/2607.15330)


<a id="xiaomi-robotics-1-dataset-sample"></a>

<div align="center">
  <img src="datasets-img/xiaomi-robotics-1-dataset-sample-01.png" alt="Xiaomi-Robotics-1 Dataset" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[官方项目页](https://robotics.xiaomi.com/xiaomi-robotics-1.html) — 提供模型与数据说明。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">小米机器人（Xiaomi Robotics）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">10 万小时 UMI 手持轨迹预训练语料，配 VLM 自动标注管线生成状态转移语言；VLA 基座预训练的代表性真实数据源。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：模型权重与完整代码开源（2026-08）；10 万小时训练集本身未公开发布。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">UMI 手持夹爪野外采集（无本体预训练）+ 真机数据后训练。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">预训练 10 万小时 UMI 轨迹 / 1700+ 场景 / 240 万片段 / 260+ 任务；后训练 1 万+ 小时跨本体数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：第一视角 RGB</li><li><strong>本体感觉</strong>：夹爪状态</li><li><strong>动作与控制</strong>：夹爪动作序列</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：VLM 自动生成语言标注（场景状态转移）</li></ul></td></tr>
</tbody>
</table>

---

### Hy-UMI-10K

<a id="ds-hy-umi-10k"></a>

[官方主页](https://tairos.tencent.com/openSourceModels/hy-embodied-0.5-vla) · [论文](https://arxiv.org/abs/2606.14409)


<a id="hy-umi-10k-sample"></a>

<div align="center">
  <img src="datasets-img/hy-umi-10k-sample-01.png" alt="Hy-UMI-10K" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[腾讯 Tairos 平台](https://tairos.tencent.com/openSourceModels/hy-embodied-0.5-vla) — 提供模型与数据说明。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">腾讯 Robotics X + 混元团队。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">亚毫米精度指套 UMI 采集的万小时人示教数据，覆盖厨房/洗衣/收纳/清洁等任务族；支持 VLA 预训练与跨本体迁移。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：部分开源，计划开放 2000 小时自采子集。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">高精度指套式 UMI 手持采集 + 光学运动捕捉（替代 SLAM）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">1 万+ 小时 / 100 万+ 条 episode / 70 类任务。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：第一视角 RGB</li><li><strong>本体感觉</strong>：光学动捕亚毫米 6-DoF 轨迹</li><li><strong>动作与控制</strong>：末端动作序列</li><li><strong>力觉</strong>：末端力/力矩</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：无</li></ul></td></tr>
</tbody>
</table>

---

### ALOHA / Mobile ALOHA

<a id="ds-aloha-mobile-aloha"></a>

[官方主页](https://tonyzhaozh.github.io/aloha/) · [Mobile ALOHA](https://mobile-aloha.github.io/) · [论文](https://arxiv.org/abs/2401.02117)


<a id="aloha-mobile-aloha-sample"></a>

<div align="center">
  <img src="datasets-img/aloha-mobile-aloha-sample-01.png" alt="ALOHA / Mobile ALOHA" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://tonyzhaozh.github.io/aloha/) 与 [Mobile ALOHA](https://mobile-aloha.github.io/) — 提供演示视频、数据与硬件图纸。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Stanford（Tony Zhao / Zipeng Fu / Chelsea Finn）+ UC Berkeley + Meta。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">低成本双臂/移动双臂遥操作数据集，配套 ACT 动作分块算法，双臂模仿学习经典基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源，MIT；代码与硬件图纸一并发布。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">主从遥操作（leader-follower 关节空间映射，全自由度同时控制）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">静态 ALOHA 6 项真机任务 + 2 项仿真任务，每任务 50 条演示；Mobile ALOHA 7 类移动操作每任务 50 条。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：多视角 RGB（顶部 + 双手腕，共 4 相机）</li><li><strong>本体感觉</strong>：关节位姿/力矩</li><li><strong>动作与控制</strong>：关节空间动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：无</li></ul></td></tr>
</tbody>
</table>

---

### UMI

<a id="ds-umi"></a>

[官方主页](https://umi-gripper.github.io/) · [论文](https://arxiv.org/abs/2402.10329)


<a id="umi-sample"></a>

<div align="center">
  <img src="datasets-img/umi-sample-01.png" alt="UMI" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://umi-gripper.github.io/) — 提供数据、硬件设计与采集说明。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Stanford + Columbia + Toyota Research Institute。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">手持夹爪野外采集人示教，跨本体部署无需目标机器人遥操作；100% 免标定，为 Xiaomi-Robotics-1、Hy-UMI-10K 等大规模采集方案的源头工具。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源，MIT；数据与硬件设计一并发布。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">UMI 手持夹爪采集 + SLAM 后处理，100% 免标定。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">官方杯具整理数据：野外 1447 条演示（30 环境）+ 实验室 305 条；采集速率约 30 秒/条。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：腕部 GoPro 鱼眼 RGB（155° + 侧镜隐式双目）</li><li><strong>本体感觉</strong>：IMU/SLAM 6-DoF 轨迹</li><li><strong>动作与控制</strong>：夹爪开度与末端轨迹</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：无</li></ul></td></tr>
</tbody>
</table>

---

### Dobb·E

<a id="ds-dobb-e"></a>

[官方主页](https://www.dobb-e.com/) · [论文](https://arxiv.org/abs/2311.16098)


<a id="dobb-e-sample"></a>

<div align="center">
  <img src="datasets-img/dobb-e-sample-01.png" alt="Dobb·E" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://www.dobb-e.com/) — 提供数据、代码与硬件设计。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">NYU（Lerrel Pinto 组）+ Meta AI。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">家用通用机器人学习系统，iPhone 改造采集棒录制家庭示教，低成本真实家庭数据的代表性来源。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（数据/代码/硬件设计）；RGB 版 814 MB、含深度版 77 GB。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">手持采集棒 The Stick（25 美元取物杆 + 3D 打印件 + iPhone）家庭示教。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">HoNY 数据集 13 小时 / 5620 条轨迹 / 150 万帧 RGB-D / 22 户纽约家庭 216 个环境。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB + 深度（iPhone）</li><li><strong>本体感觉</strong>：夹爪 6-DoF 位姿与开度</li><li><strong>动作与控制</strong>：末端轨迹</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：无</li></ul></td></tr>
</tbody>
</table>

---

### Adroit

<a id="ds-adroit"></a>

[官方主页](http://sites.google.com/view/deeprl-dexterous-manipulation) · [论文](https://arxiv.org/abs/1709.10087)

<a id="adroit-sample"></a>

<div align="center">
  <img src="datasets-img/adroit-sample-01.png" alt="Adroit" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](http://sites.google.com/view/deeprl-dexterous-manipulation) — 提供任务说明与演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">University of Washington + UC Berkeley（Rajeswaran et al.）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">24-DoF Shadow 灵巧手仿真任务套件，D4RL 离线 RL 经典基准，灵巧手操作研究的常用评测集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（数据集 CC BY 4.0，代码 Apache 2.0）；经 D4RL 分发。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">VR 遥操作人类演示 + DAPG 强化学习专家数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">4 项任务（门/锤/笔/物体搬运），每任务 25 条 VR 人类演示；D4RL 提供 human/expert/cloned 变体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：含图像观测变体</li><li><strong>本体感觉</strong>：关节/物体低维状态</li><li><strong>动作与控制</strong>：关节力矩动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MuJoCo 仿真</li></ul></td></tr>
</tbody>
</table>

---

### RoboCasa

<a id="ds-robocasa"></a>

[官方主页](https://robocasa.ai/) · [论文](https://arxiv.org/abs/2406.02538)


<a id="robocasa-sample"></a>

<div align="center">
  <img src="datasets-img/robocasa-sample-01.png" alt="RoboCasa" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://robocasa.ai/) — 提供交互式场景浏览与演示视频。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">UT Austin + NVIDIA Research。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">生成式 AI 构建场景资产的大型厨房仿真框架与数据，VLA 仿真预训练常用基准；RoboCasa365 扩展为 365 任务。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（代码 MIT，资产与数据 CC BY 4.0）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">遥操作（SpaceMouse/键盘）+ MimicGen 自动轨迹合成。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">2200+ 小时演示：预训练 300 任务（人工遥操作 482h + MimicGen 合成 1615h）；RoboCasa365 扩至 365 任务、2500+ 厨房场景、3200+ 物体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB、深度</li><li><strong>本体感觉</strong>：本体状态</li><li><strong>动作与控制</strong>：动作序列</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MuJoCo / Omnivive 渲染仿真</li></ul></td></tr>
</tbody>
</table>

---

### BEHAVIOR-1K

<a id="ds-behavior-1k"></a>

[官方主页](https://behavior.stanford.edu/) · [论文](https://arxiv.org/abs/2403.09227)


<a id="behavior-1k-sample"></a>

<div align="center">
  <img src="datasets-img/behavior-1k-sample-01.png" alt="BEHAVIOR-1K" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://behavior.stanford.edu/) — 提供任务列表、场景浏览与下载。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Stanford（李飞飞、Jiajun Wu、C. Karen Liu 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">千人调查驱动的千项日常活动具身仿真基准，OmniGibson 仿真；覆盖刚体/可变形体/液体交互，适合长时程任务评测。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（GitHub 发布）；NeurIPS 2025 Challenge 另提供 1 万条示范。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">仿真生成（BDDL 语言定义初始/目标状态）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">1000 项日常活动 / 50 个可交互场景 / 9000+ 物体模型。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB、深度、分割</li><li><strong>本体感觉</strong>：物理状态（刚体/可变形体/液体）</li><li><strong>动作与控制</strong>：全臂动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：OmniGibson 仿真</li></ul></td></tr>
</tbody>
</table>

---

### CALVIN

<a id="ds-calvin"></a>

[官方主页](https://github.com/mees/calvin) · [论文](https://arxiv.org/abs/2112.03227)


<a id="calvin-sample"></a>

<div align="center">
  <img src="datasets-img/calvin-sample-01.png" alt="CALVIN" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[GitHub 仓库](https://github.com/mees/calvin) 与[项目页](https://calvin.cs.uni-freiburg.de/) — 提供任务定义、数据与评测代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">弗莱堡大学（Mees、Burgard 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">长时程语言条件操作仿真基准，A–D 四环境 34 子任务；RLBench 派生环境，VLA 长时程评测主流基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源，MIT。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">仿真中遥操作"自由玩耍"录制，事后反向分割并众包标注语言。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">4 个环境（A–D）/ 34 个子任务 / 约 2.4 万条演示轨迹 / 约 24 小时交互数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB-D（静态 + 夹爪相机）</li><li><strong>本体感觉</strong>：本体状态</li><li><strong>动作与控制</strong>：全臂动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：触觉（部分）</li><li><strong>其他</strong>：语言指令</li></ul></td></tr>
</tbody>
</table>

---

### RLBench

<a id="ds-rlbench"></a>

[官方主页](https://sites.google.com/view/rlbench) · [论文](https://arxiv.org/abs/2109.09513)


<a id="rlbench-sample"></a>

<div align="center">
  <img src="datasets-img/rlbench-sample-01.png" alt="RLBench" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://sites.google.com/view/rlbench) — 提供任务列表、演示与评测代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">帝国理工学院（Stephen James、Andrew Davison 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">视觉引导多任务操作仿真基准与学习环境，100+ 任务可无限生成演示；CALVIN、LIBERO 等后续基准的底层环境。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源，MIT。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">仿真 + 基于路径点的运动规划自动生成演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">100 个手写任务（现 100+），每任务可通过运动规划无限生成演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB、深度、分割掩码（肩部立体相机 + 手眼相机）</li><li><strong>本体感觉</strong>：关节/位姿状态</li><li><strong>动作与控制</strong>：关节空间动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：CoppeliaSim 仿真</li></ul></td></tr>
</tbody>
</table>

---

### Meta-World

<a id="ds-meta-world"></a>

[官方主页](https://meta-world.github.io/) · [论文](https://arxiv.org/abs/1910.10897)


<a id="meta-world-sample"></a>

<div align="center">
  <img src="datasets-img/meta-world-sample-01.png" alt="Meta-World" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://meta-world.github.io/) — 提供任务演示、数据与代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">斯坦福、UC Berkeley、哥伦比亚大学、USC、Google。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">元强化学习/多任务学习的 50 任务仿真操作基准，ML/MT 系列评估设置，多任务与 meta-RL 研究经典。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源，MIT。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">程序化生成仿真环境。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">50 个操作任务，提供 ML1/ML10/ML45、MT10/MT50 评估设置。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：可选图像观测</li><li><strong>本体感觉</strong>：关节状态</li><li><strong>动作与控制</strong>：关节空间动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MuJoCo 仿真</li></ul></td></tr>
</tbody>
</table>

---

### Franka Kitchen

<a id="ds-franka-kitchen"></a>

[官方主页](https://relay-policy-learning.github.io/) · [论文](https://arxiv.org/abs/1910.11956)


<a id="franka-kitchen-sample"></a>

<div align="center">
  <img src="datasets-img/franka-kitchen-sample-01.png" alt="Franka Kitchen" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://relay-policy-learning.github.io/) — 提供任务演示与代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">UC Berkeley（Gupta、Levine 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">多阶段长时程厨房操作模仿学习/离线 RL 基准，9-DoF Franka 7 个可交互对象；Relay Policy Learning 与 IBC 的配套数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源；数据随 D4RL 发布。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">VR 遥操作。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">566 条演示，每条完成 4 个子任务；9-DoF Franka、7 个可交互对象。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：含图像版本</li><li><strong>本体感觉</strong>：关节状态、物体状态</li><li><strong>动作与控制</strong>：关节空间动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MuJoCo 仿真</li></ul></td></tr>
</tbody>
</table>

---

### RoboTwin

<a id="ds-robotwin"></a>

[官方主页](https://robotwin-platform.github.io/) · [论文](https://arxiv.org/abs/2506.18088)


<a id="robotwin-sample"></a>

<div align="center">
  <img src="datasets-img/robotwin-sample-01.png" alt="RoboTwin" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://robotwin-platform.github.io/) — 提供任务演示、数据与评测代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">上海交大、香港大学、上海 AI Lab 等（RoboTwin 2.0）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">双臂协作操作仿真基准与规模化数据生成框架，数字孪生 + MLLM 任务代码生成 + 五维域随机化；双臂 VLA 评测常用。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（数据集 Apache 2.0）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">仿真生成（数字孪生 + MLLM 任务代码生成 + 五维域随机化），另有真实遥操作数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">50 个双臂任务 / 5 种机器人本体 / >10 万条预生成专家轨迹 / 731 个物体（147 类）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB、深度（头部 + 双腕相机）</li><li><strong>本体感觉</strong>：关节状态</li><li><strong>动作与控制</strong>：双臂动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：语言指令</li></ul></td></tr>
</tbody>
</table>

---

### Ego4D

<a id="ds-ego4d"></a>

[官方主页](https://ego4d-data.org/) · [论文](https://arxiv.org/abs/2110.07058)


<a id="ego4d-sample"></a>

<div align="center">
  <img src="datasets-img/ego4d-sample-01.png" alt="Ego4D" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://ego4d-data.org/) — 提供数据浏览、下载与基准套件。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Meta AI + 全球 50+ 机构联盟（UC Berkeley、CMU 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">大规模第一人称日常活动视频数据集与基准套件；VLA/世界模型的互联网规模人类行为预训练数据源。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（Ego4D 研究许可，非商用）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">头戴相机非脚本自然记录。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">3670 小时视频 / 923 名佩戴者 / 74 个地点 / 9 个国家。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：第一人称 RGB 视频</li><li><strong>本体感觉</strong>：无</li><li><strong>动作与控制</strong>：无</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：部分含音频、3D 扫描、眼动、立体、同步多相机与文本叙述</li></ul></td></tr>
</tbody>
</table>

---

### EPIC-KITCHENS

<a id="ds-epic-kitchens"></a>

[官方主页](https://epic-kitchens.github.io/) · [论文](https://arxiv.org/abs/2008.00498)


<a id="epic-kitchens-sample"></a>

<div align="center">
  <img src="datasets-img/epic-kitchens-sample-01.png" alt="EPIC-KITCHENS" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://epic-kitchens.github.io/) — 提供视频浏览、标注与基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">布里斯托大学、阿姆斯特丹大学等（Damen 等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">第一人称厨房操作视频数据集与动作理解基准；动作识别与 VLA 预训练的人类操作视频代表数据。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（研究用途）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">头戴 GoPro 在家厨房非脚本录制，Pause-and-Talk 叙述标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">EPIC-KITCHENS-100：100 小时 / 700 个未剪辑视频 / 45 个厨房 / 约 9 万动作段 / 2000 万帧。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：第一人称 RGB 视频</li><li><strong>本体感觉</strong>：无</li><li><strong>动作与控制</strong>：无</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：音频、光流、动词-名词动作标注</li></ul></td></tr>
</tbody>
</table>

---

### Physion

<a id="ds-physion"></a>

[官方主页](https://physion-benchmark.github.io/) · [论文](https://arxiv.org/abs/2104.07661)


<a id="physion-sample"></a>

<div align="center">
  <img src="datasets-img/physion-sample-01.png" alt="Physion" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://physion-benchmark.github.io/) — 提供场景可视化、数据与评测代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">斯坦福、MIT、UCSD。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">物理直觉预测基准（物体接触预测，OCP），8 类物理场景；世界模型物理推理能力评测常用。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源，MIT（GitHub cogtoolslab/physics-benchmarking-neurips2021）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">TDW 仿真程序化生成。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">8 类场景（collide/support/dominoes/contain/drop/link/roll/drape），合计约 2.5 万段视频（1.6 万训练 + 8 千 readout + 1.2 千测试）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB、深度、法向、光流、分割掩码</li><li><strong>本体感觉</strong>：物理状态</li><li><strong>动作与控制</strong>：无</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：TDW 仿真</li></ul></td></tr>
</tbody>
</table>

---

### RoboGen

<a id="ds-robogen"></a>

[官方主页](https://generativesimulation.github.io/) · [论文](https://arxiv.org/abs/2405.15995)


<a id="robogen-sample"></a>

<div align="center">
  <img src="datasets-img/robogen-sample-01.png" alt="RoboGen" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://generativesimulation.github.io/) — 提供生成任务与数据说明。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">CMU、清华、MIT CSAIL、UMass Amherst、MIT-IBM AI Lab。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">用基础模型自动生成仿真任务与数据的机器人技能学习管线，提出-生成-学习循环，可无限产出技能演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：已开源（ICML 2024，代码公开）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">LLM/VLM + 物理仿真器程序化生成（任务、场景、奖励、技能）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">首批自动生成 100+ 任务（论文报告 106 个），管线可无限产出。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：仿真渲染</li><li><strong>本体感觉</strong>：状态信息</li><li><strong>动作与控制</strong>：技能动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：任务/场景/奖励程序化生成</li></ul></td></tr>
</tbody>
</table>

---

### Isaac GR00T

<a id="ds-isaac-gr00t"></a>

[官方主页](https://developer.nvidia.com/isaac/gr00t) · [论文](https://arxiv.org/abs/2503.14734)


<a id="isaac-gr00t-sample"></a>

<div align="center">
  <img src="datasets-img/isaac-gr00t-sample-01.jpg" alt="Isaac GR00T" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[NVIDIA 开发者页](https://developer.nvidia.com/isaac/gr00t) — 提供工作流说明与下载。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">NVIDIA。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人形机器人数据生成与仿真训练管线（GR00T-Teleop/Mimic/Gen/Dreams 工作流），从少量示范合成大规模轨迹；GR00T 系列模型的配套数据体系。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据生成组件开源（代码 Apache 2.0）；模型权重 NVIDIA Open Model License。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">遥操作（Apple Vision Pro 等捕捉人体动作）+ Omniverse 仿真 + Cosmos 世界模型域随机化扩增。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">可从少量人类示范在约 11 小时内生成约 78 万条合成运动轨迹（约 6500 小时等效人类演示）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：图像/视频</li><li><strong>本体感觉</strong>：状态信息</li><li><strong>动作与控制</strong>：动作轨迹/状态</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：语言指令、合成数据生成</li></ul></td></tr>
</tbody>
</table>

---

### RT-1 Robotic Dataset

<a id="ds-rt-1-robotic-dataset"></a>

[官方主页](https://robotics-transformer1.github.io/) · [论文](https://arxiv.org/abs/2212.06817)

<a id="rt-1-robotic-dataset-sample"></a>

<div align="center">
  <img src="datasets-img/rt-1-robotic-dataset-sample-01.jpg" alt="RT-1 Robotic Dataset" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://robotics-transformer1.github.io/) — 展示数据集概览、机器人平台与任务示例。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Google Robotics（Google Research / Everyday Robots）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">RT-1 论文配套的 700+ 真实任务多机器人数据集，是验证 VLA 可扩展性的经典真实世界语料。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：代码开源（Apache 2.0）；原始数据集未直接公开下载。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">13 台机器人历时 17 个月人类远程遥操作采集，逐集标注自然语言指令。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">130k+ 条 episode / 700+ 任务指令。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB 图像</li><li><strong>本体感觉</strong>：机器人状态</li><li><strong>动作与控制</strong>：11 维离散动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：自然语言任务指令</li></ul></td></tr>
</tbody>
</table>

---

### FurnitureBench

<a id="ds-furniturebench"></a>

[官方主页](https://clvrai.github.io/furniture-bench/) · [论文](https://arxiv.org/abs/2305.12821)

<a id="furniturebench-sample"></a>

<div align="center">
  <img src="datasets-img/furniturebench-sample-01.jpg" alt="FurnitureBench" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://clvrai.github.io/furniture-bench/) — 提供数据集、仿真器与基线代码。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">KAIST CLVR Lab + UC Berkeley</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">真实世界家具组装长时程操作基准，配套 FurnitureSim 仿真器，是评估长时程操作与 sim-to-real 的重要平台。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：代码与数据集完全开源。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人类遥操作（Oculus Quest 2 控制器 + 键盘）；配套 IsaacGym 仿真器 FurnitureSim。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">5,100 条遥操作轨迹 / 219.6 小时 / 8 个组装任务（9 种配置）/ 低中高三级初始随机性。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：前视 + 腕部 RGB 相机</li><li><strong>本体感觉</strong>：关节状态</li><li><strong>动作与控制</strong>：关节位置 / 力矩</li><li><strong>力觉</strong>：关节力矩</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：家具部件装配结构信息</li></ul></td></tr>
</tbody>
</table>

---

### RoboAgent (RoboSet)

<a id="ds-roboagent"></a>

[官方主页](https://robopen.github.io/) · [论文](https://arxiv.org/abs/2309.01918)

<a id="roboagent-sample"></a>

<div align="center">
  <img src="datasets-img/roboagent-sample-01.png" alt="RoboAgent (RoboSet)" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://robopen.github.io/) — 展示 RoboSet 数据集与跨任务元学习框架。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Carnegie Mellon University + Meta AI (FAIR)</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">样本高效的多技能操作学习框架与开放数据集，12 种技能 / 38 个任务，是低数据量操作泛化的代表工作。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集与代码开源（MIT License）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">遥操作 + 动觉示教（Franka Panda + Robotiq 夹具），配合 SAM 等语义增强离线扩增。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">RoboSet 共 100,050 条轨迹（全量）；训练子集 RoboSet(MT-ACT) 7,500 条 / 12 种技能 / 38 个任务。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：4 视角 RGB</li><li><strong>本体感觉</strong>：关节状态</li><li><strong>动作与控制</strong>：关节位置动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：自然语言任务描述</li></ul></td></tr>
</tbody>
</table>

---

### TriFinger

<a id="ds-trifinger"></a>

[官方主页](https://is.mpg.de/ei/projects/robot-benchmark) · [论文](https://arxiv.org/abs/2105.02087)

<a id="trifinger-sample"></a>

<div align="center">
  <img src="datasets-img/trifinger-sample-01.png" alt="TriFinger" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://is.mpg.de/ei/projects/robot-benchmark) — 远程真实机器人共享基准平台，配套 PyBullet 仿真。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Max Planck Institute for Intelligent Systems（MPI-IS）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">三指灵巧操作的远程真实机器人共享基准，支持全球团队远程提交策略在真实平台自动评测，灵巧手研究的经典平台。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：平台与仿真开源；数据集 CC BY 4.0，加载工具 BSD-3-Clause。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">全球团队远程提交策略在真实 TriFinger 平台自动执行采集（RRC 竞赛）；另提供 PyBullet 仿真与离线 RL 数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">8 台 TriFinger 平台（3 指 × 3 关节 = 9 DoF）；RRC 2020 数据集 2,856 + 7,422 条 episode。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：三相机 RGB</li><li><strong>本体感觉</strong>：关节位姿 / 速度 / 力矩</li><li><strong>动作与控制</strong>：关节力矩</li><li><strong>力觉</strong>：指尖力传感器</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：物体位姿估计</li></ul></td></tr>
</tbody>
</table>

---

### Ravens

<a id="ds-ravens"></a>

[官方主页](https://transporternets.github.io/) · [论文](https://arxiv.org/abs/2010.14406)

<a id="ravens-sample"></a>

<div align="center">
  <img src="datasets-img/ravens-sample-01.jpg" alt="Ravens" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目页](https://transporternets.github.io/) — 提供任务可视化、代码与数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Google（Robotics at Google / Google Research）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">基于 PyBullet 的视觉桌面操作仿真基准，10 个基础任务 + 5 个难度变体，传输网络（TransporterNets）的评测平台。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：代码与数据开源（Apache 2.0）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">仿真生成（脚本化 oracle 演示 / 部分任务含 RL 奖励），真实硬件验证。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">10 个基础任务 + 5 个难度变体；每任务含 scripted oracle 自动生成专家演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB-D（深度为核心）</li><li><strong>本体感觉</strong>：物体位姿</li><li><strong>动作与控制</strong>：6-DoF 抓取 + 放置</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：状态与奖励信号</li></ul></td></tr>
</tbody>
</table>

---

### SoftVTBench

<a id="ds-softvtbench"></a>

[官方主页](https://arxiv.org/abs/2608.18701) · [论文](https://arxiv.org/abs/2608.18701)

<a id="softvtbench-sample"></a>

<div align="center">
  <img src="datasets-img/softvtbench-sample-01.png" alt="SoftVTBench" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2608.18701) — 视触觉可变形物体数据集与闭环基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">清华大学、北京大学、香港大学等（多机构合作）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">首个面向可变形物体物理交互质量的视触觉数据集：同时提供策略可见接触观测与独立物理真值（FEM 有限元状态），支持评估"任务成功但物理交互差"的隐蔽失败。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集与代码开源。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">专家遥操作演示；多视角 RGB + 双指触觉 RGB + 标记点运动同步采集，含评估者专用 FEM 状态。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">4,000 条专家演示 / 50+ 资产（体积可变形物体 + 视觉匹配刚性孪生）/ 20Hz 多模态同步。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：多视角 RGB</li><li><strong>本体感觉</strong>：本体状态</li><li><strong>动作与控制</strong>：二指夹爪动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：双指触觉 RGB + 标记点运动</li><li><strong>其他</strong>：语言指令、FEM 有限元状态（评估专用）</li></ul></td></tr>
</tbody>
</table>

---

### Open-AoE

<a id="ds-open-aoe"></a>

[官方主页](https://arxiv.org/abs/2607.14183) · [论文](https://arxiv.org/abs/2607.14183)

<a id="open-aoe-sample"></a>

<div align="center">
  <img src="datasets-img/open-aoe-sample-01.png" alt="Open-AoE" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2607.14183) — 开放自我中心操作数据集与完整工具链。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">开放社区协作（500+ 贡献者）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">大规模社区驱动自我中心操作数据集，从手机采集到模型训练全覆盖，支持 VLA、WAM 与世界模型训练及人-机器人迁移。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源，配套处理与训练工具链。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">500+ 贡献者用 400+ 智能手机在自然环境中连续采集；时间动作分割、语义标注、手部重建、相机轨迹重建流水线处理。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">首批约 2,000 小时操作视频 / 500+ 贡献者 / 400+ 手机；MANO 手部姿态 + 相机轨迹 + 时间定位原子动作标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：第一人称 RGB</li><li><strong>本体感觉</strong>：无（人类数据）</li><li><strong>动作与控制</strong>：无（跨本体重定向生成）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MANO 手部姿态、相机轨迹、原子动作标注</li></ul></td></tr>
</tbody>
</table>

---

### QuadFM

<a id="ds-quadfm"></a>

[官方主页](https://github.com/GaoLii/QuadFM) · [论文](https://arxiv.org/abs/2603.24021)

<a id="quadfm-sample"></a>

<div align="center">
  <img src="datasets-img/quadfm-sample-01.png" alt="QuadFM" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[GitHub](https://github.com/GaoLii/QuadFM) — 首个文本驱动的四足基础运动数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">上海人工智能实验室等（Gao Li 团队）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">首个大规模超高保真四足运动数据集：整合运动、交互与情感表达行为，三层语言标注，面向文本到运动生成与运动控制。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集在 GitHub 开源。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">动作捕捉（mocap）采集四足运动，三层标注（细粒度动作标签 / 交互场景 / 自然语言指令）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">11,784 条精选运动片段（走跑、交互、情感表达如跳舞/拉伸）/ 35,352 条语言描述。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：无</li><li><strong>本体感觉</strong>：运动学状态</li><li><strong>动作与控制</strong>：运动轨迹/状态</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：细粒度动作标签、交互场景、自然语言指令</li></ul></td></tr>
</tbody>
</table>

---

### ManiGuard

<a id="ds-maniguard"></a>

[官方主页](https://arxiv.org/abs/2608.17386) · [论文](https://arxiv.org/abs/2608.17386)

<a id="maniguard-sample"></a>

<div align="center">
  <img src="datasets-img/maniguard-sample-01.png" alt="ManiGuard" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2608.17386) — 操作基础模型安全的规范驱动评估基准与数据套件。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Northwestern University 等（Qi Zhu 团队）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">首个把"操作是否安全"与"任务是否成功"独立评估的框架：LTLf 形式化规范监控 + 物理接地谓词，覆盖 200 个锁定基础任务 × 5 类扰动。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：基准与安全标注数据开源。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">自动运动规划生成器 + 人类遥操作，按逐步监控器标注；仿真 + 物理 Franka 平台。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">6 个任务族 / 200 个锁定基础任务 / 1,000 个锁定场景 / 8,000 条安全标注演示（每任务 40 条）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB</li><li><strong>本体感觉</strong>：本体状态</li><li><strong>动作与控制</strong>：动作轨迹</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：LTLf 规范、逐步安全监控标注</li></ul></td></tr>
</tbody>
</table>

---

### EmbodimentSemantic

<a id="ds-embodimentsemantic"></a>

[官方主页](https://arxiv.org/abs/2607.00020) · [论文](https://arxiv.org/abs/2607.00020)

<a id="embodimentsemantic-sample"></a>

<div align="center">
  <img src="datasets-img/embodimentsemantic-sample-01.png" alt="EmbodimentSemantic" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2607.00020) — 具身操作空间场景图数据集与基准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">KAUST（King Abdullah University of Science and Technology）等</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">以有向对象-关系-对象三元组显式建模空间关系（支撑/包含/排序/遮挡/深度敏感关系），诊断 VLA 的空间接地能力并评测场景图对下游策略的增益。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集与基准开源。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">低成本 SO101 机械臂真实操作观测 + 生成场景图；LIBERO 仿真基准 60K+ 操作帧，场景图由 MuJoCo 几何/相机投影/可见性约束自动推导。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">LIBERO 基准 60K+ 操作帧 / 120K+ 相机特定场景图（第三视角 + 腕部视角）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB-D</li><li><strong>本体感觉</strong>：物体位姿</li><li><strong>动作与控制</strong>：操作轨迹</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：有向空间场景图（对象-关系-对象三元组）</li></ul></td></tr>
</tbody>
</table>
---

### DexYCB

<a id="ds-dexycb"></a>

[官方主页](https://dex-ycb.github.io/) · [论文](https://arxiv.org/abs/2104.04631)

<a id="dexycb-sample"></a>

<div align="center">
  <img src="datasets-img/dexycb-sample-01.png" alt="DexYCB" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2104.04631) — NVIDIA 出品的手物捕捉基准数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">NVIDIA、华盛顿大学等</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">全标定多视角工业级手物捕捉基准：8 台同步相机 + 精确物体 6D 位姿与 3D 手部关节真值，是手物姿态估计与灵巧抓取研究的标准评测集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（官方 GitHub 提供下载脚本）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">8 台同步 RGB-D 相机围拍；Vicon 外参标定；物体为 YCB 集合中的 20 个已知物体，6D 位姿由人工标注 + 模型对齐获得。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>58.2 万帧</strong> / 1,000 段序列 / 20 个物体 / 10 名受试者 / 8 相机视角。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：多视角 RGB-D</li><li><strong>本体感觉</strong>：物体 6D 位姿</li><li><strong>动作与控制</strong>：无（感知数据集）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：3D 手部关节（MANO 模型参数）、物体语义掩码</li></ul></td></tr>
</tbody>
</table>

---

### OakInk

<a id="ds-oakink"></a>

[官方主页](https://oakink.net/) · [论文](https://arxiv.org/abs/2203.15709)

<a id="oakink-sample"></a>

<div align="center">
  <img src="datasets-img/oakink-sample-01.png" alt="OakInk" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2203.15709) — 手部操作意图与可供性理解数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">南京大学、香港中文大学（CUHK）等</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"> unique 之处在于<strong>操作意图（intent）标注</strong>与物体可供性（affordance）建模：从 Oak 墨镜库构建 1,800 个物体 affordance，并用虚拟迁移（Tink）合成跨物体交互，是意图驱动手物交互研究的核心数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（官方 GitHub 提供下载脚本）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">实拍（4 视角 RGB-D）+ 虚拟迁移：实拍手物交互标注 MANO 姿态与意图短语，虚拟迁移把抓取姿态重定向到同 affordance 的 1,800 个 Oak 物体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>5 万次</strong>手物交互 / 1,800 个物体 affordance 库 / 100 个实拍物体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：4 视角 RGB-D</li><li><strong>本体感觉</strong>：物体 6D 位姿</li><li><strong>动作与控制</strong>：无（感知数据集）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MANO 手部姿态、操作意图文本、affordance 标注、虚拟迁移交互（Tink）</li></ul></td></tr>
</tbody>
</table>

---

### GraspNet-1Billion

<a id="ds-graspnet"></a>

[官方主页](https://graspnet.net/) · [论文](https://arxiv.org/abs/1912.13470)

<a id="graspnet-sample"></a>

<div align="center">
  <img src="datasets-img/graspnet-sample-01.png" alt="GraspNet-1Billion" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/1912.13470) — 大规模密集抓取位姿基准数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">上海交通大学 MVIG 等</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">抓取检测领域的标准基准：190 个杂乱场景、<strong>超 11 亿</strong>个标注抓取位姿（正/负样本分级标注），配套统一评测脚本与排名榜。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集与评测工具开源（graspnetAPI）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">双相机（Kinect Azure + RealSense D435）采集 190 个杂乱场景；抓取位姿由力仿真（FleX）穷举生成并按力闭合评估分级标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>97,280 张</strong> RGB-D 图像 / 190 个场景 / 88 个物体 / <strong>超 11 亿</strong>抓取位姿标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：双相机 RGB-D</li><li><strong>本体感觉</strong>：物体 6D 位姿</li><li><strong>动作与控制</strong>：抓取位姿（6-DoF 平移+旋转+宽度）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：正/负抓取分级标签、场景分割掩码</li></ul></td></tr>
</tbody>
</table>

---

### HOI4D

<a id="ds-hoi4d"></a>

[官方主页](https://hoi4d.github.io/) · [论文](https://arxiv.org/abs/2203.01577)

<a id="hoi4d-sample"></a>

<div align="center">
  <img src="datasets-img/hoi4d-sample-01.png" alt="HOI4D" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2203.01577) — 类别级动态手物交互 4D 数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">清华大学、北京航空航天大学等</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">类别级（category-level）动态手物 4D 交互的标杆：4D 全景点云 + 运动分割 + 类别级物体位姿 + 动作分割多任务标注，支撑动态场景下的手物联合感知研究。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（官方 GitHub 提供下载脚本）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">单目 RGB-D 相机自由移动采集室内真实场景；逐帧 4D 全景分割与类别级物体位姿人工标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>240 万帧</strong> RGB-D / 4,000+ 序列 / 800 个物体实例 / 16 个类别 / 610 个房间 / 9 名参与者。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB-D 4D 点云</li><li><strong>本体感觉</strong>：类别级物体 6D 位姿</li><li><strong>动作与控制</strong>：无（感知数据集）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：3D 手部姿态、全景/运动分割、动作分割标注</li></ul></td></tr>
</tbody>
</table>

---

### ARCTIC

<a id="ds-arctic"></a>

[官方主页](https://arctic.is.tue.mpg.de/) · [论文](https://arxiv.org/abs/2204.13662)

<a id="arctic-sample"></a>

<div align="center">
  <img src="datasets-img/arctic-sample-01.png" alt="ARCTIC" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2204.13662) — 铰接物体手物交互数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">ETH Zürich、Max Planck 智能系统研究所、阿姆斯特丹大学</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">聚焦<strong>铰接物体</strong>（剪刀、刀、笔、笔记本电脑等 11 类）的手物交互：同时提供第三人称与第一人称（头戴）双视角 RGB 与 3D 手/物网格，含动态接触标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（官方提供下载脚本）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">10 名受试者操作 11 个日常铰接物体（开/关/使用/手递手等交互）；磁追+多目重建 3D 手部与物体网格。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>210 万帧</strong> / 339 段序列 / 10 名受试者 / 11 个铰接物体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：第三人称 + 第一人称双视角 RGB</li><li><strong>本体感觉</strong>：物体铰接状态</li><li><strong>动作与控制</strong>：无（感知数据集）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MANO 手部 / SMPL-X 身体网格、物体网格、动态接触标注</li></ul></td></tr>
</tbody>
</table>
---

### GigaHands

<a id="ds-gigahands"></a>

[官方主页](https://ivl.cs.brown.edu/research/gigahands.html) · [论文](https://arxiv.org/abs/2412.04244)

<a id="gigahands-sample"></a>

<div align="center">
  <img src="datasets-img/gigahands-sample-01.png" alt="GigaHands" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2412.04244) — 大规模多视角手部操作数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Brown University、ETH Zürich（CVPR 2025 Highlight）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">迄今规模领先的手部操作数据集之一：51 个机位、183M 帧的多视角记录 + 3.7M 双手 3D 姿态 + 84k 文本标注，支撑大规模手部操作理解与生成研究。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（官方项目页提供入口）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">51 个相机机位同步采集日常手部操作；自动 3D 手部/物体姿态重建与文本标注流水线。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>34 小时</strong> / 56 名受试者 / 417 个物体 / 14k 动作片段 / <strong>183M 帧</strong> / <strong>3.7M</strong> 双手 3D 姿态 / 84k 文本标注。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：51 机位多视角 RGB</li><li><strong>本体感觉</strong>：3D 物体姿态</li><li><strong>动作与控制</strong>：无（感知数据集）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：MANO 双手 3D 姿态、文本标注、分割掩码</li></ul></td></tr>
</tbody>
</table>

---

### EgoDex

<a id="ds-egodex"></a>

[官方主页](https://github.com/apple/ml-egodex) · [论文](https://arxiv.org/abs/2505.11709)

<a id="egodex-sample"></a>

<div align="center">
  <img src="datasets-img/egodex-sample-01.png" alt="EgoDex" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2505.11709) — Apple 出品的大规模自我中心桌面操作数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Apple（ICLR 2026）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">迄今最大的自我中心桌面操作数据集：<strong>829 小时 / 338k 演示 / 194 类任务</strong>，配 72 关节全身-手部骨骼真值，是自我中心操作策略学习的理想训练场。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（Apple ML 官方 GitHub）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Vision Pro 自我中心 1080p RGB 采集桌面操作；Apple 真实感知管线输出 3D 手部/手指/上半身 72 关节骨骼。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>829 小时</strong>自我中心视频 / <strong>90M 帧</strong> / <strong>338k 条</strong>演示 / 194 类桌面任务 / 约 500 个物体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：30FPS 1080p 自我中心 RGB</li><li><strong>本体感觉</strong>：相机位姿</li><li><strong>动作与控制</strong>：手部/手指轨迹（操作动作）</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：72 关节 3D 骨骼、语言标注</li></ul></td></tr>
</tbody>
</table>

---

### DexCap

<a id="ds-dexcap"></a>

[官方主页](https://dex-cap.github.io/) · [论文](https://arxiv.org/abs/2403.07788)

<a id="dexcap-sample"></a>

<div align="center">
  <img src="datasets-img/dexcap-sample-01.png" alt="DexCap" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2403.07788) — 便携手部捕捉生成的灵巧操作数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Stanford University（Chen Wang、李飞飞、C. Karen Liu）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">便携手部捕捉（SLAM + 电磁场手腕/手指追踪）直出灵巧手操作数据：免大型动捕设备，人手数据可直接重定向到机器灵巧手，是灵巧手模仿学习的轻量数据管线代表。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集开源（官方项目页）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">背包式 SLAM 相机 + 电磁场手腕/手指追踪；前向运动学计算 3D 点云观测；人手 mocap 重定向。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">6 个灵巧操作任务评测（整理物品、抓取放置等）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：3D 点云观测</li><li><strong>本体感觉</strong>：物体位姿</li><li><strong>动作与控制</strong>：灵巧手关节轨迹</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：人手 mocap、SLAM 轨迹</li></ul></td></tr>
</tbody>
</table>

---

### HumanPlus

<a id="ds-humanplus-data"></a>

[官方主页](https://humanoid-ai.github.io/) · [论文](https://arxiv.org/abs/2406.10454)

<a id="humanplus-data-sample"></a>

<div align="center">
  <img src="datasets-img/humanplus-data-sample-01.png" alt="HumanPlus" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[论文页](https://arxiv.org/abs/2406.10454) — 人形影子跟随全身操作数据集。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Stanford University（Zipeng Fu、Chelsea Finn 等）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">通过影子跟随（shadowing）用纯 RGB 相机采集的人形全身数据：穿鞋、仓储卸货、叠衣、打字等真实任务，配合 60-100% 成功率的策略结果。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集、代码与硬件 BOM 全开源（humanoid-ai.github.io）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">低层策略先以 40 小时人体运动数据（AMASS）RL 训练，再影子跟随采集全身数据；自我中心视觉行为克隆训练技能策略。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><strong>40 小时</strong>人体运动数据（AMASS）+ 各任务最多 <strong>40 条</strong>全身演示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：自我中心 RGB</li><li><strong>本体感觉</strong>：全身关节（33-DoF）</li><li><strong>动作与控制</strong>：全身关节动作</li><li><strong>力觉</strong>：无</li><li><strong>触觉</strong>：无</li><li><strong>其他</strong>：180cm 定制人形平台</li></ul></td></tr>
</tbody>
</table>

---

### LeRobot Community Datasets

<a id="ds-lerobot-data"></a>

[官方主页](https://huggingface.co/lerobot) · [论文](https://arxiv.org/abs/2602.22818)

<a id="lerobot-data-sample"></a>

<div align="center">
  <img src="datasets-img/lerobot-data-sample-01.png" alt="LeRobot Community Datasets" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[HF Hub](https://huggingface.co/lerobot) — Hugging Face 社区机器人数据集集合（LeRobot ICLR 2026 论文）。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">Hugging Face 社区（全球开发者众包）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">依托 LeRobotDataset 标准格式（Parquet + MP4）在 HF Hub 上组织的社区数据集生态（约 189 个、持续增长）：从低成本 SO-100 机械臂到 Unitree G1 人形，覆盖广泛本体与任务，是众包具身数据的事实标准。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：HF Hub 直接流式加载（LeRobotDataset API）。</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">社区用 LeRobot 标准采集工具（lerobot-record）遥操作录制；统一格式与可视化工具链。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">组织下约 <strong>189 个</strong>数据集（随社区持续增长），覆盖 SO-100/SO-101、LeKiwi、Koch、Unitree G1 等多本体。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：多相机 RGB（MP4/图像）</li><li><strong>本体感觉</strong>：机器人状态（Parquet）</li><li><strong>动作与控制</strong>：动作序列（Parquet）</li><li><strong>力觉</strong>：部分提供</li><li><strong>触觉</strong>：部分提供</li><li><strong>其他</strong>：语言指令、深度（部分）</li></ul></td></tr>
</tbody>
</table>

---

### ABC-130K

<a id="ds-abc-130k"></a>

[官方主页](https://abc.bot/) · [论文](https://arxiv.org/abs/2606.27375)

<a id="abc-130k-sample"></a>

<div align="center">
  <img src="datasets-img/abc-130k-sample-01.jpg" alt="ABC-130K" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目主页](https://abc.bot/) — 提供任务视频、数据统计、硬件与训练/评测开源方案。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">UC Berkeley / MIT / Amazon FAR / XDOF / CMU</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">迄今最大开源双臂遥操作数据集，134K 条轨迹覆盖 195 个任务，配套 GELLO 式硬件、训练代码与评测 rubric，适合双臂行为克隆规模化研究。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：HuggingFace XDOF/ABC-130k（gated）</li><li><strong>代码</strong>：github.com/amazon-far/abc（开源）</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">GELLO 式无源主臂遥操作双 6-DoF YAM 平台；另有 400 小时仿真遥操作数据</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">134,806 条 episode / 195 个任务 / 3,553 小时真实数据；20 个仿真任务 400 小时</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：3 路 RGB（顶部 + 双腕，224×224 堆叠 MP4）</li><li><strong>本体感觉</strong>：14 维状态/动作</li><li><strong>标注</strong>：任务 / 子任务标签</li></ul></td></tr>
</tbody>
</table>

---

### TableVerse-100K

<a id="ds-tableverse-100k"></a>

[官方主页](https://bytedance.github.io/TableVerse/) · [论文](https://arxiv.org/abs/2607.21017)

<a id="tableverse-100k-sample"></a>

<div align="center">
  <img src="datasets-img/tableverse-100k-sample-01.png" alt="TableVerse-100K" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目主页](https://bytedance.github.io/TableVerse/) — 提供管线图、类别分布与任务生成展示。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">字节跳动（ByteDance）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">以真实网络图片经确定性 Real2Sim 重建生成 10 万物理一致桌面场景，与"文本幻觉布局"路线形成对照，适合桌面操作仿真预训练。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：数据集入口见项目页</li><li><strong>代码</strong>：github.com/bytedance/TableVerse（Apache-2.0）</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">真实网络图片 → 确定性 Real2Sim 物理重建与稳定化 → 自动生成无碰撞 pick-and-place 轨迹</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">100,000 个物理一致桌面场景；约 100 万物体实例、35K+ 语义类别；7 类场景主题</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：合成多视图 RGB（前端 / 俯视）</li><li><strong>几何</strong>：物理稳定网格资产</li><li><strong>动作与控制</strong>：无碰撞专家轨迹</li></ul></td></tr>
</tbody>
</table>

---

### DexCanvas

<a id="ds-dexcanvas"></a>

[官方主页](https://dexcanvas.github.io/) · [论文](https://arxiv.org/abs/2510.15786)

<a id="dexcanvas-sample"></a>

<div align="center">
  <img src="datasets-img/dexcanvas-sample-01.png" alt="DexCanvas" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目主页](https://dexcanvas.github.io/) — 展示动捕与 RL 重建数据样例。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">DexRobot 灵巧智能（与密歇根大学、上海交大等合著）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人手灵巧操作数据，首次在规模上配备物理一致的逐帧接触力；按 Cutkosky 分类法覆盖 21 类操作，适合人手灵巧技能与接触模型研究。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：HuggingFace DEXROBOT/DexCanvas（v0.1，ODbL）</li><li><strong>代码</strong>：github.com/dexrobot/dexcanvas</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">真实光学动捕 + RL real-to-sim 物理仿真扩增（×100）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">v0.1 test 版约 70 小时 / 3000 万帧；完整版计划 7,000 小时（70h 种子 ×100），30 个物体</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：多视角 RGB-D</li><li><strong>姿态</strong>：MANO 手参数 + 6-DoF 物体位姿</li><li><strong>力觉</strong>：逐帧接触点与力 / 力矩</li></ul></td></tr>
</tbody>
</table>

---

### Humanoid Everyday

<a id="ds-humanoideveryday"></a>

[官方主页](https://humanoideveryday.github.io/) · [论文](https://arxiv.org/abs/2510.08807)

<a id="humanoideveryday-sample"></a>

<div align="center">
  <img src="datasets-img/humanoideveryday-sample-01.jpg" alt="Humanoid Everyday" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目主页](https://humanoideveryday.github.io/) — 提供任务概览与演示动图。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">南加州大学（USC）+ 丰田研究院（TRI）</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">面向开放世界的人形整机操作数据集，覆盖移动操作、变形物体、工具使用与人机交互等 7 大类任务，聚焦整机全身操作。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：官网暂未开放下载（2026-09 状态，数据入口待跟进）</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人工监督遥操作的真实世界采集</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">10.3k 条轨迹 / 260 个任务 / 7 大类 / 300 万+ 帧 @30Hz</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB + 深度 + LiDAR</li><li><strong>力觉</strong>：触觉</li><li><strong>标注</strong>：自然语言任务描述</li></ul></td></tr>
</tbody>
</table>

---

### VTDexManip

<a id="ds-vtdexmanip"></a>

[官方主页](https://lqts.github.io/VTDexManip/) · [论文](https://openreview.net/forum?id=jf7C7EGw21)

<a id="vtdexmanip-sample"></a>

<div align="center">
  <img src="datasets-img/vtdexmanip-sample-01.jpg" alt="VTDexManip" height="520">
</div>

<table style="width:100%;table-layout:fixed" width="100%">
<tbody>
<tr><td rowspan="4" style="width:130px;min-width:130px;max-width:130px" width="130">基本介绍</td><td style="width:130px;min-width:130px;max-width:130px" width="130">Dataset Visualizer</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">[项目主页](https://lqts.github.io/VTDexManip/) — 提供数据集与基准概览。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">来源机构</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">浙江大学</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">关注建议</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人类触觉数据（20 路压阻触觉手套采集）+ 配套 Shadow Hand 灵巧操作 RL 基准（6 任务、18 种方法），支持视觉-触觉联合预训练与 sim-to-real 验证。</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据使用</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>下载</strong>：OneDrive（密码 vtdexmanip）</li><li><strong>代码</strong>：github.com/LQTS/VTDexManip（开源）</li></ul></td></tr>
<tr><td rowspan="3" style="width:130px;min-width:130px;max-width:130px" width="130">数据设计</td><td style="width:130px;min-width:130px;max-width:130px" width="130">收集方式</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">人手演示（压阻触觉手套）+ Isaac Gym 中 Shadow Hand 仿真基准</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">体量分布</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620">565k 帧 / 2,032 条序列 / 5 名受试 / 10 个日常任务 / 182 个物体</td></tr>
<tr><td style="width:130px;min-width:130px;max-width:130px" width="130">数据维度</td><td style="word-wrap:break-word;width:620px;min-width:620px;max-width:620px" width="620"><ul><li><strong>视觉</strong>：RGB</li><li><strong>触觉</strong>：指尖压阻（二值化后对仿真噪声鲁棒）</li><li><strong>姿态</strong>：抓取姿态</li></ul></td></tr>
</tbody>
</table>
