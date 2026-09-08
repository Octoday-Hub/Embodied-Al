# 🛠️ Tools & Open-Source Projects

> 💡 This list is continuously updated. If you find a good tool that is not included, or if existing information needs updating, please submit a [PR](https://github.com/Octoday-Hub/Embodied-AI/pulls) or provide feedback in [Issues](https://github.com/Octoday-Hub/Embodied-AI/issues).

<a name="toc"></a>

## Table of Contents

**Categories:** [🎮 Simulation Platforms](#simulation-platforms) · [🤖 Models](#models) · [🧰 General Tools & Libraries](#general-tools) · [🏗️ Learning Frameworks](#learning-frameworks) · [🤖 Robot Projects](#robot-projects) · [🧠 Reasoning / RL](#reasoning-rl) · [🗺️ SLAM & Perception](#slam-perception) · [🔧 Middleware & ROS Tools](#middleware-ros) · [🛒 Other](#other)

<a name="simulation-platforms"></a>

## 🎮 Simulation Platforms

### ManiSkill3

<div align="center">
  <img src="tools-img/maniskill3.jpg" alt="ManiSkill3" style="width:100%">
</div>

<table style="width:100%;display:table;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:1200px" width="1200">A SAPIEN-based GPU-parallel manipulation simulation, data-generation, and policy-evaluation framework for generalizable manipulation skills.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release & maintenance</td><td style="word-wrap:break-word;width:1200px" width="1200">Released 2024 (RSS 2025); actively maintained through 2026</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:1200px" width="1200">Stanford (Hao Su lab, haosulab) with the open-source community</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li><strong>Fastest contact-rich GPU-parallel simulation</strong>: sim and rendering share one GPU, 30,000+ FPS (RGBD+seg on a 4090), 10-1000x faster than Isaac/MJX with 2-3x lower memory</li><li><strong>Heterogeneous simulation & large task zoo</strong>: every parallel env can load a different scene; 12 task domains, 20+ robots, scenes from ReplicaCAD/AI2-THOR</li><li><strong>Dual data & evaluation pipeline</strong>: Real2Sim enables 100x-accelerated large-scale evaluation of real policies, plus millions of demonstration frames (motion planning / RL / teleop)</li><li><strong>Ready-to-run baseline zoo</strong>: RL (PPO/SAC/TD-MPC2), imitation (BC/Diffusion Policy), and VLA (Octo/RDT-1B/RT-x) configs included</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Use cases</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>GPU-scale synthetic demonstration generation</li><li>Vision/state RL and imitation training</li><li>Simulation-scaled evaluation of real-robot policies (SIMPLER-style)</li><li>Rapid benchmark comparison across embodiments and new tasks</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Case studies</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Used as a unified evaluation platform by many VLA / diffusion-policy studies for large-scale demo synthesis and benchmarking</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data & models</td><td style="word-wrap:break-word;width:1200px" width="1200">ManiSkill3 framework (based on SAPIEN); ManiSkill2/3 benchmark tasks and demonstration datasets</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Official link</td><td style="word-wrap:break-word;width:1200px" width="1200"><a href="https://github.com/haosulab/ManiSkill">GitHub haosulab/ManiSkill</a> · <a href="https://maniskill.ai/">maniskill.ai</a> · <a href="https://maniskill.readthedocs.io/">Docs</a> · <a href="https://arxiv.org/abs/2410.00425">arXiv 2410.00425</a></td></tr>
</tbody>
</table>

### Genesis

<div align="center">
  <img src="tools-img/genesis.jpg" alt="Genesis" style="width:100%">
</div>

<table style="width:100%;display:table;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:1200px" width="1200">A generative simulation platform for physical AI, unifying multiple physics solvers with photorealistic rendering.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release & maintenance</td><td style="word-wrap:break-word;width:1200px" width="1200">Academic release Dec 2024, actively maintained (GitHub ⭐ 29.8k); Apache 2.0.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:1200px" width="1200">Joint project of 20+ universities (Stanford, CMU, MIT, Tsinghua, HKU, et al. — Genesis-Embodied-AI).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li><strong>Unified multi-physics solvers</strong>: rigid, FEM, MPM, SPH, PBD, IPC sharing one scene state</li><li>In-house <strong>Nyx photorealistic renderer</strong> + Luisa ray tracing + Pyrender rasterization</li><li><strong>Quadrants cross-platform compiler</strong>: Python kernels compiled to CUDA/ROCm/Metal/Vulkan</li><li>Built-in sensor simulation: depth, IMU, LiDAR, tactile, contact forces</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Use cases</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Large-scale parallel RL/IL training for manipulation and locomotion</li><li>Embodied tasks with deformables, fluids, and cloth under multi-physics coupling</li><li>Sensor-level synthetic data generation for Sim2Real pipelines</li><li>Scalable training from laptop GPU to data-center clusters</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Case studies</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>RoboGen and other generative-simulation frameworks build on it as the underlying engine</li><li>Widely used for quadruped/arm RL training and multi-physics coupling demos</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data & models</td><td style="word-wrap:break-word;width:1200px" width="1200">Fully open source (Apache 2.0); supports URDF/MJCF/USD assets with a built-in example scene library.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Official link</td><td style="word-wrap:break-word;width:1200px" width="1200"><a href="https://github.com/Genesis-Embodied-AI/Genesis">github.com/Genesis-Embodied-AI/Genesis</a></td></tr>
</tbody>
</table>


### XTDrone

<div align="center">
  <img src="tools-img/xtdrone.jpg" alt="XTDrone" style="width:100%">
</div>

<table style="width:100%;display:table;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:1200px" width="1200">An open-source UAV simulation platform built on ROS / PX4 / Gazebo, supporting multiple vehicle types and swarm simulation — a go-to environment for UAV algorithm development and education.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release & maintenance</td><td style="word-wrap:break-word;width:1200px" width="1200">Open-source project, actively maintained (GitHub ⭐ 6.5k).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:1200px" width="1200">Maintained by robin-shaun and open-source contributors (National University of Defense Technology background).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li><strong>Multiple vehicle types</strong>: multirotor, fixed-wing, compound-wing UAVs, plus UGVs, USVs, and robotic arms</li><li><strong>Full-stack simulation</strong>: dynamics, sensors (camera / LiDAR / IMU), control, state estimation, and 3D scenes</li><li><strong>Deep integration with PX4 and ROS</strong>, supporting Offboard control, SLAM, and path planning</li><li>Comprehensive tutorials and an active community for teaching and research</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Use cases</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Developing and validating UAV control, obstacle avoidance, and path planning algorithms</li><li>Visual SLAM, target tracking, formation and swarm simulation</li><li>PX4 firmware development and SITL / HITL validation</li><li>University UAV courses, graduation projects, and competitions</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Case studies</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Many developers validate algorithms in simulation before deploying to real aircraft</li><li>Used as an entry-level PX4 simulation environment in courses and workshops</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data & models</td><td style="word-wrap:break-word;width:1200px" width="1200">Fully open source; built on the PX4 / Gazebo / ROS ecosystem with built-in example scenes and sensor models.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Official link</td><td style="word-wrap:break-word;width:1200px" width="1200"><a href="https://github.com/robin-shaun/XTDrone">github.com/robin-shaun/XTDrone</a></td></tr>
</tbody>
</table>

- **BEHAVIOR-1K** — [`StanfordVL/BEHAVIOR-1K`](https://github.com/StanfordVL/BEHAVIOR-1K) ⭐ 1.5k
  📄 Stanford benchmark for embodied AI agents on 1,000 everyday household activities.

- **Prometheus** — [`amov-lab/Prometheus`](https://github.com/amov-lab/Prometheus) ⭐ 4.5k
  📄 An open-source system for autonomous UAVs, supporting detection, SLAM, and formation control.

- **Aerial Gym** — [`github.com/ntnu-arl/aerial_gym_simulator`](https://github.com/ntnu-arl/aerial_gym_simulator)
  📄 An aerial robot simulation environment based on Isaac Gym, supporting UAV reinforcement learning training.

- **AllenAct** — [`allenact.org`](https://allenact.org/)
  📄 A training framework for embodied AI research supporting iTHOR, RoboTHOR, Habitat, and common RL/IL algorithms.

- **BEHAVIOR** — [`behavior.stanford.edu`](https://behavior.stanford.edu/)
  📄 A large-scale interactive simulation benchmark built on SAPIEN, with 100 everyday household items and 30 complex tasks — a comprehensive physical interaction testing environment.

- **CARLA** — [`carla.org`](https://carla.org)
  📄 An open-source simulator for autonomous driving and robotics research, providing urban road scenes, traffic participants, sensors, and scenario scripting.

- **CoppeliaSim (V-REP)** — [`www.coppeliarobotics.com`](https://www.coppeliarobotics.com)
  📄 A robotics simulation platform with remote API, embedded scripting, and multiple interfaces, suitable for education, research, and industrial prototyping.

- **DISCOVERSE** — [`air-discoverse.github.io`](https://air-discoverse.github.io/)
  📄 A high-fidelity simulation framework for Real2Sim2Real, combining 3DGS scene representation with MuJoCo physics and control interfaces.

- **Drake** — [`github.com/RobotLocomotion/drake`](https://github.com/RobotLocomotion/drake)
  📄 A toolkit for robot modeling, planning, and control, suitable for system analysis, simulation, and algorithm research.

- **EmbodiedCity** — [`github.com/tsinghua-fib-lab/EmbodiedCity`](https://github.com/tsinghua-fib-lab/EmbodiedCity)
  📄 An embodied intelligence platform for real-world open environments. Built by Tsinghua University on Unreal Engine 5, supporting online/offline deployment for navigation and task planning in urban settings.

- **Gazebo Sim** — [`gazebosim.org`](https://gazebosim.org)
  📄 A high-fidelity open-source robot simulator supporting multiple physics engines (ODE, Bullet, DART) with realistic rendering and sensor models, widely used in the ROS ecosystem.

- **Genesis** — [`genesis-embodied-ai.github.io`](https://genesis-embodied-ai.github.io/)
  📄 A universal robotics simulation engine designed for generative physical AI, integrating rigid body, fluid, and soft body physics solvers.

- **GRUtopia** — [`github.com/OpenRobotLab/GRUtopia`](https://github.com/OpenRobotLab/GRUtopia)
  📄 A general embodied AI simulation platform by Shanghai AI Lab, providing massive interactive scenes and data with simple code-defined tasks.

- **Gymnasium-Robotics** — [`robotics.farama.org`](https://robotics.farama.org/)
  📄 A collection of robot simulation environments based on the Gymnasium API, suitable for RL algorithm development and standardized benchmarking.

- **Habitat-Lab** — [`github.com/facebookresearch/habitat-lab`](https://github.com/facebookresearch/habitat-lab)
  📄 A high-level development library for embodied AI tasks, typically used with Habitat Sim for task definition, agent configuration, training, and evaluation.

- **Habitat Sim** — [`github.com/facebookresearch/habitat-sim`](https://github.com/facebookresearch/habitat-sim)
  📄 Meta's open-source high-performance 3D simulator, often paired with Habitat-Lab for large-scale scene navigation and interaction tasks.

- **Habitat 3.0** — [`aihabitat.org`](https://aihabitat.org/)
  📄 Meta AI's latest social embodied AI simulation platform focusing on human-robot and robot-robot interaction with high-fidelity social behavior simulation.

- **ManiSkill3** — [`github.com/haosulab/ManiSkill`](https://github.com/haosulab/ManiSkill)
  📄 A next-generation manipulation skill simulation framework by Shanghai AI Lab, supporting complex articulated objects and efficient parallel physics simulation.

- **MORSE Simulator** — [`morse-simulator.github.io`](https://morse-simulator.github.io/)
  📄 A Blender-based academic robot simulator supporting mobile robots, human-robot interaction, and multi-middleware integration.

- **MuJoCo** — [`github.com/google-deepmind/mujoco`](https://github.com/google-deepmind/mujoco)
  📄 A high-performance physics engine designed for robotics, biomechanics, and graphics, widely used in RL and motion control research.

- **NVIDIA Isaac Gym** — [`developer.nvidia.com/isaac-gym`](https://developer.nvidia.com/isaac-gym)
  📄 A high-performance RL simulation environment for robot learning with GPU-accelerated massively parallel training.

- **NVIDIA Isaac Lab** — [`developer.nvidia.com/isaac/lab`](https://developer.nvidia.com/isaac/lab)
  📄 An open-source, GPU-accelerated modular robot learning framework for large-scale policy training and sim-to-real transfer.

- **NVIDIA Isaac Sim** — [`developer.nvidia.com/isaac-sim`](https://developer.nvidia.com/isaac-sim)
  📄 A robotics simulation platform built on Omniverse, supporting physical AI training, synthetic data generation, and Sim2Real workflows.

- **NVIDIA RAD-MARS** — [`developer.nvidia.com/omniverse`](https://developer.nvidia.com/omniverse)
  📄 A robot-assisted design and simulation platform built on Omniverse for designing robot hardware and testing kinematic algorithms in physically realistic environments.

- **OmniGibson** — [`behavior.stanford.edu/omnigibson/overview.html`](https://behavior.stanford.edu/omnigibson/overview.html)
  📄 An embodied AI simulation framework based on Isaac Sim supporting interactive scenes, task definition, data collection, and parallel training.

- **PyBullet** — [`github.com/bulletphysics/bullet3`](https://github.com/bulletphysics/bullet3)
  📄 A Python interface to the Bullet physics engine, lightweight and easy to use for rapid prototyping and RL experiments.

- **RLBench** — [`github.com/stepjam/RLBench`](https://github.com/stepjam/RLBench)
  📄 A large-scale vision-guided robot manipulation benchmark and learning environment for RL, imitation learning, multi-task, and few-shot settings.

- **RoboCasa** — [`robocasa.ai`](https://robocasa.ai/)
  📄 A large-scale simulation framework for everyday household manipulation, supporting diverse scenes, objects, demonstration data, and benchmarks.

- **robosuite** — [`github.com/ARISE-Initiative/robosuite`](https://github.com/ARISE-Initiative/robosuite)
  📄 A modular robot learning simulation framework based on MuJoCo with benchmark suites for manipulation research.

- **RobotStudio** — [`www.abb.com/global/en/areas/robotics/products/software/robotstudio-suite`](https://www.abb.com/global/en/areas/robotics/products/software/robotstudio-suite)
  📄 ABB's official robot programming, simulation, and offline programming software for industrial robotic cell development.

- **SAPIEN** — [`github.com/haosulab/SAPIEN`](https://github.com/haosulab/SAPIEN)
  📄 A simulation environment for part-level interaction and manipulation tasks, supporting articulated object modeling and manipulation learning research.

- **SimplerEnv** — [`github.com/simpler-env/SimplerEnv`](https://github.com/simpler-env/SimplerEnv)
  📄 A simulation evaluation environment for real-world robot manipulation policies, supporting reproduction and comparison of real-to-sim manipulation policies under unified settings.

- **Unity ML-Agents** — [`github.com/Unity-Technologies/ml-agents`](https://github.com/Unity-Technologies/ml-agents)
  📄 Unity game engine's ML agent toolkit for training intelligent agents in 3D environments.

- **UnrealCV** — [`unrealcv.org`](https://unrealcv.org/)
  📄 An open-source plugin connecting Unreal Engine with external vision/robotics programs, suitable for building simulation environments and synthetic data pipelines.

- **Webots** — [`cyberbotics.com`](https://cyberbotics.com)
  📄 An open-source cross-platform desktop robot simulation application with a complete environment for modeling, programming, and simulation.

- **KWAISEM DexVerse** — [`dexforce.com`](https://www.dexforce.com/)
  📄 A generative simulation engine (released at WAIC 2026) for large-scale embodied AI training, supporting real-time multi-physics simulation and generative simulation for rapid conversion of real scenes into trainable virtual environments.
[↑ Back to TOC](#toc)

<a name="models"></a>

## 🤖 Models

- **VLA-Adapter** — [`OpenHelix-Team/VLA-Adapter`](https://github.com/OpenHelix-Team/VLA-Adapter) ⭐ 2.2k
 📄 Efficient training paradigm for small-scale VLA models — VLA Adapter

- **LLaVA-OneVision** — [`EvolvingLMMs-Lab/LLaVA-OneVision`](https://github.com/EvolvingLMMs-Lab/LLaVA-OneVision) ⭐ 754
 📄 Fully open-source large multimodal model achieving SOTA at low cost

- **Otter** — [`EvolvingLMMs-Lab/Otter`](https://github.com/EvolvingLMMs-Lab/Otter) ⭐ 3.3k
 📄 OpenFlamingo-based multimodal model trained on MIMIC-IT dataset for improved instruction following

- **XR-1** — [`Open-X-Humanoid/XR-1`](https://github.com/Open-X-Humanoid/XR-1)
 📄 China's first national standard VLA foundation model (Beijing Humanoid Robot Innovation Center), supporting cross-robot platform operation with RoboMIND 2.0 dataset and ArtVIP assets

- **DexVLA** — [`juruobenruo/DexVLA`](https://github.com/juruobenruo/DexVLA)
 📄 Qwen2-VL based vision-language-action model supporting single-arm, dual-arm, and dexterous hand control

- **ManiFoundation** — [`NUS-LinS-Lab/ManiFM`](https://github.com/NUS-LinS-Lab/ManiFM)
 📄 General robot manipulation foundation model (NUS/Tsinghua) handling rigid, articulated, and deformable objects via contact synthesis

- **RoboBrain 2.5** — [`FlagOpen/RoboBrain2.5`](https://github.com/FlagOpen/RoboBrain2.5)
 📄 Next-gen embodied AI foundation model (BAAI/Peking University) supporting precise 3D spatial reasoning, depth-aware coordinate prediction, and temporal modeling

- **WholebodyVLA** — [`OpenDriveLab/WholebodyVLA`](https://github.com/OpenDriveLab/WholebodyVLA) ⭐
 📄 ICLR 2026, unified latent-space VLA model for humanoid whole-body mobile manipulation (Shanghai AI Lab)

- **X-VLA** — [`2toinf/X-VLA`](https://github.com/2toinf/X-VLA)
 📄 ICLR 2026, soft-prompt Transformer cross-morphology VLA model, AgiBot World Challenge (IROS 2025) champion

- **RoboticsDiffusionTransformer (RDT-1B)** — [`thu-ml/RoboticsDiffusionTransformer`](https://github.com/thu-ml/RoboticsDiffusionTransformer)
 📄 Bimanual robot manipulation foundation model (Tsinghua University) using diffusion Transformer architecture, SOTA across multiple bimanual tasks

- **AgiBot-World** — [`OpenDriveLab/AgiBot-World`](https://github.com/OpenDriveLab/AgiBot-World)
 📄 IROS 2025 Best Paper candidate, large-scale manipulation platform for scalable embodied intelligence (Shanghai AI Lab)

- **Dexterity-BEV** — See [Dexterity-BEV](https://arxiv.org/abs/2606.02274)
  📄 Aligning 3D world and actions for generalizable robot policy learning

- **cuRobo** — [`github.com/NVlabs/curobo`](https://github.com/NVlabs/curobo)
  📄 NVIDIA's CUDA-accelerated robot motion generation library supporting inverse kinematics, collision detection, trajectory optimization, and high-DOF planning.

- **VIMA** — [`vimalabs.github.io`](https://vimalabs.github.io/)
  📄 A multimodal embodied task benchmark from UIUC, providing complex "block-building" style tasks for evaluating VLAs on visual, linguistic, and spatial reasoning.

- **MiniCPM-RobotManip** — [`github.com/OpenBMB/MiniCPM-Robot`](https://github.com/OpenBMB/MiniCPM-Robot)
  📄 A 1.5B general-purpose VLA model (released at WAIC 2026) with 1-minute context memory, 120ms per decision step, top-tier comprehensive VLA benchmark performance.

- **MiniCPM-RobotTrack** — [`github.com/OpenBMB/MiniCPM-Robot`](https://github.com/OpenBMB/MiniCPM-Robot)
  📄 A 0.9B end-to-end visual instruction tracking model (released at WAIC 2026) supporting single-target, dynamic multi-target, and ambiguous target tracking at 5+ Hz with offline local deployment.
[↑ Back to TOC](#toc)

<a name="general-tools"></a>

## 🧰 General Tools & Libraries

### Diffusion Policy

<div align="center">
  <img src="tools-img/diffusion-policy.jpg" alt="Diffusion Policy" style="width:100%">
</div>

<table style="width:100%;display:table;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:1200px" width="1200">A visuomotor policy that generates action sequences directly with diffusion models — a representative imitation-learning method for robot manipulation.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release & maintenance</td><td style="word-wrap:break-word;width:1200px" width="1200">Released 2023 (RSS 2023, Best Paper Award); actively maintained (GitHub ⭐ 4.1k).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:1200px" width="1200">Stanford (Cheng Chi, Chelsea Finn, et al.).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>End-to-end <strong>conditional diffusion (DDPM)</strong> action generation, non-autoregressive</li><li>Naturally represents <strong>multimodal action distributions</strong>, stable training, scales to high-DOF action spaces</li><li>Flexible vision encoders (ResNet / spatial-temporal transformers), multi-camera support</li><li>Official open-source implementation with data and training code</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Use cases</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Single-arm / bimanual manipulation policy training (imitation learning)</li><li>Dexterous manipulation, tabletop tasks, and long-horizon manipulation</li><li>As the action expert of VLA stacks (e.g., π0, Hi Robot)</li><li>Common baseline for visuomotor and VLA research</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Case studies</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Complex dexterous tasks on the ALOHA bimanual platform (hanging clothes, tying shoelaces)</li><li>Widely referenced and compared by flow-matching VLA methods such as π0</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data & models</td><td style="word-wrap:break-word;width:1200px" width="1200">Open source (MIT); includes self-collected and simulated demonstration data, supports custom task training.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Official link</td><td style="word-wrap:break-word;width:1200px" width="1200"><a href="https://github.com/real-stanford/diffusion_policy">github.com/real-stanford/diffusion_policy</a></td></tr>
</tbody>
</table>

> Covering simulation tools, development frameworks, middleware, benchmarks, and general-purpose libraries

- **AI2-THOR** — [`ai2thor.allenai.org`](https://ai2thor.allenai.org/)
 📄 Semantic interactive simulator from the Allen Institute, with 200+ rooms and 2600+ interactive objects.

- **DORA** — [`github.com/dora-rs/dora`](https://github.com/dora-rs/dora)
 📄 Dataflow middleware for AI robotics with low-latency, composable, distributed pipelines.

- **Intern-Robotics** — [`internrobotics.shlab.org.cn`](https://internrobotics.shlab.org.cn/)
 📄 Open-source full-stack embodied robotics framework from Shanghai AI Lab, covering navigation and manipulation.

- **LeRobot** — [`huggingface.co/docs/lerobot/main/en/index`](https://huggingface.co/docs/lerobot/main/en/index)
 📄 Hugging Face real-world robot ML toolkit with models, datasets, and training utilities.

- **MimicGen** — [`github.com/NVlabs/mimicgen`](https://github.com/NVlabs/mimicgen)
 📄 Data generation system that scales few demos into large robot datasets for manipulation.

- **Octo** — [`github.com/octo-models/octo`](https://github.com/octo-models/octo)
 📄 Open-source general robot policy pretrained on multi-robot trajectories.

- **OK-Robot** — [`ok-robot.github.io`](https://ok-robot.github.io/)
 📄 Modular framework from NYU for zero-shot pick-and-place in real homes using VLMs.

- **OpenVLA** — [`github.com/openvla/openvla`](https://github.com/openvla/openvla)
 📄 Open-source VLA model for general robot manipulation, supporting fine-tuning and evaluation.

- **OpenXLab** — [`openxlab.org.cn`](https://openxlab.org.cn/)
 📄 Open embodied AI platform from Shanghai AI Lab with full toolchain from data to deployment.

- **RobotecAI RAI** — [`github.com/RobotecAI/rai`](https://github.com/RobotecAI/rai)
 📄 Open-source agentic robotics framework on ROS 2, supporting natural language and multimodal execution.

- **RoboGen** — [`robogen-ai.github.io`](https://robogen-ai.github.io/)
 📄 Code-generative robotics framework from MIT that uses LLMs to auto-generate Python robot policies.

- **robomimic** — [`github.com/ARISE-Initiative/robomimic`](https://github.com/ARISE-Initiative/robomimic)
 📄 General framework for robot learning from demonstration with datasets and baselines.

- **ROS / ROS2** — [`www.ros.org`](https://www.ros.org)
 📄 Robot Operating System providing tools for modular, distributed robot software development.

- **RQT Frame Editor** — [`github.com/ipa320/rqt_frame_editor_plugin`](https://github.com/ipa320/rqt_frame_editor_plugin)
 📄 Rqt plugin for creating and adjusting TF frames for multi-sensor coordination.

- **Theseus** — [`github.com/facebookresearch/theseus`](https://github.com/facebookresearch/theseus)
  📄 Differentiable nonlinear optimization library for robotics and vision state estimation.

- **Universal Manipulation Interface (UMI)** — [`github.com/real-stanford/universal_manipulation_interface`](https://github.com/real-stanford/universal_manipulation_interface)
 📄 Stanford general manipulation interface for robot learning and manipulation tasks.

- **VEX Robotics Software** — [`www.vexrobotics.com/?srsltid=AfmBOoqB_9zu0-eFHO4wzVB_33rsABV6DRRJ_drQfuk67n-MLcUmVy9M`](https://www.vexrobotics.com/?srsltid=AfmBOoqB_9zu0-eFHO4wzVB_33rsABV6DRRJ_drQfuk67n-MLcUmVy9M)
 📄 Software tools for VEX robotics platform with drag-and-drop programming for education.

- **insightOS Semantic** — [`insightos.cn`](https://www.insightos.cn/)
  📄 An embodied semantic agent system (released at WAIC 2026) that uses semantics as a central hub to connect "understanding-planning-execution-evolution", enabling natural language command of multi-heterogeneous robots.

- **RoboPocket** — [`noematrix.ai`](https://www.noematrix.ai/)
  📄 A hardware-agnostic data collection system (released at WAIC 2026) that dramatically lowers the barrier to real-world data acquisition, managing nearly 10,000 data entries per day without teleoperation dependency.

- **Meta-World** — [`metaworld.farama.org`](https://metaworld.farama.org/)
  📄 A classic robot manipulation benchmark with 50 tasks, commonly used for multi-task learning and meta-RL evaluation.

- **RoboTwin 2.0** — [`github.com/RoboTwin-Platform/RoboTwin`](https://github.com/RoboTwin-Platform/RoboTwin)
  📄 A data generation and benchmark platform for bimanual manipulation, emphasizing strong domain randomization, scalable generation, and standardized evaluation.

- **TairosAgent** — [`tairos.tencent.com`](https://tairos.tencent.com/)
  📄 An embodied-native agent framework (released at WAIC 2026) with three-layer architecture (perception-reaction, cognitive-decision, exploration-sedimentation) natively designed for embodied tasks.

- **Apexio** — [`tairos.tencent.com`](https://tairos.tencent.com/)
  📄 A persistent online embodied agent (released at WAIC 2026) with three concurrently running layers at different frequencies: on-demand cognition, 15Hz perception-action loop, and high-frequency reflex execution.

- **PhyAI** — [`github.com/OpenBMB/MiniCPM-Robot`](https://github.com/OpenBMB/MiniCPM-Robot)
  📄 An open-source inference framework for Physical AI (released at WAIC 2026), designed for on-device inference and cloud RL rollout, delivering 1.8-2.8x acceleration for π0/π0.5/GR00T models.
[↑ Back to TOC](#toc)

<a name="learning-frameworks"></a>

## 🏗️ Learning Frameworks

### LeRobot

<div align="center">
  <img src="tools-img/lerobot.jpg" alt="LeRobot" style="width:100%">
</div>

<table style="width:100%;display:table;table-layout:fixed" width="100%">
<tbody>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">One-line summary</td><td style="word-wrap:break-word;width:1200px" width="1200">Hugging Face's PyTorch real-world robotics suite: models, datasets, and tools in one place.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Release & maintenance</td><td style="word-wrap:break-word;width:1200px" width="1200">Released 2024, actively maintained; ICLR 2026 paper; Apache 2.0.</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Organization</td><td style="word-wrap:break-word;width:1200px" width="1200">Hugging Face (Remi Cadene, Thomas Wolf team).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Highlights</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li><strong>Hardware-agnostic Python interface</strong>: unified control from low-cost SO-100 arms to Unitree G1 humanoids</li><li><strong>LeRobotDataset</strong> standard format (Parquet + MP4), hosting thousands of datasets on the HF Hub</li><li><strong>SOTA policy suite</strong>: ACT, Diffusion, VQ-BeT, HIL-SERL, π0/π0.5, GR00T, SmolVLA in pure PyTorch</li><li>LIBERO / MetaWorld evaluation support and a third-party hardware plugin ecosystem</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Use cases</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>End-to-end pipeline from data capture (lerobot-record) to training (lerobot-train) and deployment/eval</li><li>Low-cost arm (SO-ARM101) embodied-AI education and hackathons</li><li>Standard infrastructure for VLA training and real-robot deployment</li><li>Hosting, visualization, and sharing of community datasets</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Case studies</td><td style="word-wrap:break-word;width:1200px" width="1200"><ul><li>Widely used in global hackathons and university courses (Tongji SO-ARM101 Chinese tutorial, et al.)</li><li>T-shirt folding end-to-end experiment (HF Spaces demo)</li></ul></td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Data & models</td><td style="word-wrap:break-word;width:1200px" width="1200">Fully open source (Apache 2.0); installs directly from PyPI (pip install lerobot).</td></tr>
<tr><td style="width:110px;min-width:110px;max-width:110px" width="110">Official link</td><td style="word-wrap:break-word;width:1200px" width="1200"><a href="https://github.com/huggingface/lerobot">github.com/huggingface/lerobot</a></td></tr>
</tbody>
</table>


(Items merged from repos and tools)

- **RLinf** — [`RLinf/RLinf`](https://github.com/RLinf/RLinf) ⭐ 3.7k
 📄 Reinforcement learning infrastructure for embodied and agentic AI.

- **OpenLoong (Brain)** — [`loongOpen`](https://github.com/loongOpen)
 📄 Qinglong humanoid full-stack skill scheduling framework with MPC+WBC control, Gymloong/MiniGym training platforms.

- **AimRT** — [`AimRT/AimRT`](https://github.com/AimRT/AimRT)
 📄 Modern C++ runtime framework for robotics, lightweight and compatible with ROS2/HTTP/gRPC.

- **Open-TeleVision** — [`OpenTeleVision/TeleVision`](https://github.com/OpenTeleVision/TeleVision)
 📄 Immersive VR-based robot teleoperation system for real-time bimanual manipulation.

- **AgileX Cobot Magic** — [`agilexrobotics`](https://github.com/agilexrobotics)
 📄 open-source bimanual mobile manipulation platform based on Mobile ALOHA (AgileX Robotics).

[↑ Back to TOC](#toc)

- **every-embodied** — [`datawhalechina/every-embodied`](https://github.com/datawhalechina/every-embodied) ⭐ 2.2k
  📄 Build VLA/OpenVLA/SmolVLA/Pi0 from scratch with only Python basics.

[↑ Back to TOC](#toc)

<a name="robot-projects"></a>

## 🤖 Robot Projects

### Humanoid

- **AgiBot X1** — [`infer`](https://github.com/AgibotTech/agibot_x1_infer) · [`train`](https://github.com/AgibotTech/agibot_x1_train) · [`hardware`](https://github.com/AgibotTech/agibot_x1_hardware)
 📄 Agibot X1 fully open-sourcehumanoid project with inference, RL training code, and hardware design.

- **OpenLoong Qinglong** — [`loongOpen`](https://github.com/loongOpen)
 📄 Full-stack open-sourcehumanoid project (Shanghaihumanoid Innovation Center/OpenAtom Foundation) with MPC+WBC control and training platform

- **Fourier N1** — [`FFTAI`](https://github.com/FFTAI)
 📄 World first fully open-sourcehumanoid (Fourier Intelligence) with full hardware design, BOM, assembly guide, and SDK (1.3m/38kg/3.5m/s).m/s

- **EngineAI Humanoid** — [`engineai-robotics/engineai_humanoid`](https://github.com/engineai-robotics/engineai_humanoid)
 📄 EngineAI SA01/PM01 bipedal robot open-source motion control with end-to-end neural gait.

- **Booster Gym** — [`BoosterRobotics`](https://github.com/BoosterRobotics)
 📄 Booster T1/K1 humanoid end-to-end RL motion control framework (Booster Robotics) with RoboCup kicking demo.

- **Humanoid-Gym** — [`roboterax/humanoid-gym`](https://github.com/roboterax/humanoid-gym)
 📄 Isaac Gym-basedhumanoid RL training framework supporting zero-shot sim-to-real transfer.

- **Unitree Qmini** — [`unitreerobotics/Qmini`](https://github.com/unitreerobotics/Qmini)
 📄 Unitree open-source bipedal platform with BOM, assembly guide, and URDF models.

### Quadruped

- **OpenCat** — [`PetoiCamp/OpenCat`](https://github.com/PetoiCamp/OpenCat) ⭐ 15k
 📄 open-sourcequadruped platform

- **Xiaomi CyberDog** — [`MiRoboticsLab/cyberdog_ros2`](https://github.com/MiRoboticsLab/cyberdog_ros2)
 📄 Xiaomi CyberDog open-source quadruped software and hardware.

- **Unitreequadruped ROS** — [`unitreerobotics/unitree_ros`](https://github.com/unitreerobotics/unitree_ros)
 📄 Unitreequadruped Go1/Go2 ROS driver packages.

### Arms & Desktop Robots

- **vlm_arm** — [`TommyZihao/vlm_arm`](https://github.com/TommyZihao/vlm_arm)
 📄 Robot arm + LLM + multimodal integration (Tongji Zihao).

- **Dummy-Robot (Mini Robot Arm)** — [`peng-zhihui/Dummy-Robot`](https://github.com/peng-zhihui/Dummy-Robot)
 📄 DIY mini robot arm (ZhiHuijun).

- **ElectronBot Mini Desktop Robot** — [`peng-zhihui/ElectronBot`](https://github.com/peng-zhihui/ElectronBot)
 📄 Compact desktop robot (ZhiHuijun).

- **Rubik Cube Robot** — [`diy-robots.com`](http://www.diy-robots.com/?page_id=46)
 📄 LEGO-based Rubik cube-solving robot.

### Mobile Robots

- **MiniRover Mars Rover** — [`peng-zhihui/MiniRover-Hardware`](https://github.com/peng-zhihui/MiniRover-Hardware)
 📄 DIY Mars rover open-source project (ZhiHuijun).

- **ONE-Robot Unicycle Robot** — [`peng-zhihui/ONE-Robot`](https://github.com/peng-zhihui/ONE-Robot)
 📄 IMU and STM32-based one-wheel self-balancing robot (ZhiHuijun).

### SLAM & Perception

- **Visual SLAM 14 Lectures** — [`gaoxiang12/slambook2`](https://github.com/gaoxiang12/slambook2) ⭐ 12k
 📄 Classic SLAM Chinese tutorial with companion code (Gao Xiang).

- **VINS-Mono** — [`HKUST-Aerial-Robotics/VINS-Mono`](https://github.com/HKUST-Aerial-Robotics/VINS-Mono) ⭐ 5k
 📄 Robust monocular visual-inertial state estimator (HKUST).

- **VINS-Fusion** — [`HKUST-Aerial-Robotics/VINS-Fusion`](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion)
 📄 Optimization-based multi-sensor estimator supporting mono/stereo + IMU fusion.

- **LIO-SAM** — [`TixiaoShan/LIO-SAM`](https://github.com/TixiaoShan/LIO-SAM) ⭐ 3.5k
 📄 Tightly-coupled LiDAR-inertial odometry, widely cited LiDAR SLAM solution.

- **FAST_LIO** — [`hku-mars/FAST_LIO`](https://github.com/hku-mars/FAST_LIO) ⭐ 2.5k
 📄 Efficient and robust LiDAR-inertial odometry (HKU MARS Lab).

- **FAST-LIVO2** — [`hku-mars/FAST-LIVO2`](https://github.com/hku-mars/FAST-LIVO2)
 📄 Fast direct LiDAR-inertial-visual odometry with tight coupling.

- **R3LIVE** — [`hku-mars/r3live`](https://github.com/hku-mars/r3live) ⭐ 2.0k
 📄 Robust real-time RGB-colored LiDAR-inertial-visual SLAM.

- **Unitree 4D LiDAR SLAM** — [`unitreerobotics/point_lio_unilidar`](https://github.com/unitreerobotics/point_lio_unilidar)
 📄 Point-LIO based SLAM for Unitree L1 4D LiDAR.

### Grasping & Manipulation

- **AnyGrasp** — [`graspnet/anygrasp_sdk`](https://github.com/graspnet/anygrasp_sdk)
 📄 Efficient 6-DoF grasp pose estimation (Shanghai AI Lab) for general object grasping.

- **MYNT EYE Stereo Camera** — [`slightech/MYNT-EYE-S-SDK`](https://github.com/slightech/MYNT-EYE-S-SDK)
 📄 MYNT EYE stereo camera series with complete SLAM and vision solutions.

### Others

- **ALOHA 2** — [`aloha-2.github.io`](https://aloha-2.github.io/)
 📄 Low-cost open-source hardware platform, with tutorials and MuJoCo simulation models.

- **Beijing Humanoid Innovation Center·Huisi Kaiwu** — [`login.x-humanoid-cloud.com/?responseType=code&clientId=fd6c22fb&redirectUri=https%3A%2F%2Fopen.x-humanoid-cloud.com%2Fhome&stamp=1778429122172&env=cloud`](https://login.x-humanoid-cloud.com/?responseType=code&clientId=fd6c22fb&redirectUri=https%3A%2F%2Fopen.x-humanoid-cloud.com%2Fhome&stamp=1778429122172&env=cloud)
 📄 toolchain platform covering skill invocation, agent configuration, and deployment.

- **DexCap** — [`dex-cap.github.io`](https://dex-cap.github.io/)
 📄 Stanford dexterous hand data collection system, using motion capture cameras to collect human dexterous manipulation data at scale for Sim-to-Real transfer.

- **Dobb-E** — [`dobb-e.com`](https://dobb-e.com/)
 📄 NYU full-stack pipeline from hardware to data, with low-cost handheld Stick hardware, dataset, and imitation learning framework for robots to learn tasks from 15 min demos.

- **GR-1 (ByteDance Model)** — [`github.com/bytedance/GR-1`](https://github.com/bytedance/GR-1)
 📄 ByteDance open-source GPT-style vision robot model for language-conditioned multitask learning.

- **JD JoyInside** — [`joyinside.com`](https://joyinside.com/)
 📄 conversational agent platform

- **kscale·K-Bot** — [`github.com/kscalelabs/kbot`](https://github.com/kscalelabs/kbot)
  📄 open-source full-stack humanoid platform

- **Agibot LinkCraft Platform** — [`www.agibot.com.cn/filepage/295.html`](https://www.agibot.com.cn/filepage/295.html)
 📄 Agibotzero-code robot content creation platform, supporting motion imitation and speech-driven task generation.

- **Tencent Tairos** — [`tairos.tencent.com`](https://tairos.tencent.com/)
 📄 open embodied AI platform, providing models, tools, and data services.

- **Viam** — [`www.viam.com`](https://www.viam.com)
 📄 software platform, with unified API, module registry, remote operations, and fleet management.

- **NetEase Lingdong Lingjue** — [`lingdong.fuxi.163.com/productSummary/wj`](https://lingdong.fuxi.163.com/productSummary/wj)
  📄 Embodied AI model and training framework for mining excavator loading.

- **Unitree XR Teleoperation** — [`unitreerobotics/xr_teleoperate`](https://github.com/unitreerobotics/xr_teleoperate)
  📄 XR-based (Apple Vision Pro/Quest) H1/G1 humanoid teleoperation system

- **RoboWiki** — [`yfrobotics/robowiki`](https://github.com/yfrobotics/robowiki)
  📄 Robotics wiki (Yunfei Robotics Lab).

- **Unitree Robot Control Guide** — [`unitreerobotics/unitree_guide`](https://github.com/unitreerobotics/unitree_guide)
  📄 Open-source tutorial for Unitree quadruped robot control, suitable for beginners.

[↑ Back to TOC](#toc)

<a name="reasoning-rl"></a>

## 🧠 Reasoning / Reinforcement Learning

- **OpenR1-Multimodal** — [`EvolvingLMMs-Lab/open-r1-multimodal`](https://github.com/EvolvingLMMs-Lab/open-r1-multimodal) ⭐ 1.5k
 📄 R1 reasoning paradigm on multimodal models with 8K open-source multimodal RL samples.

- **unitree_rl_gym** — [`unitreerobotics/unitree_rl_gym`](https://github.com/unitreerobotics/unitree_rl_gym)
 📄 Unitree quadruped/humanoid RL training framework based on Isaac Gym.

- **unitree_rl_lab** — [`IsaacLab`](https://github.com/unitreerobotics/unitree_rl_lab) · [`MuJoCo`](https://github.com/unitreerobotics/unitree_rl_mjlab)
 📄 Unitree robot RL implementations based on Isaac Lab and MuJoCo.

- **unitree_IL_lerobot** — [`unitreerobotics/unitree_IL_lerobot`](https://github.com/unitreerobotics/unitree_IL_lerobot)
 📄 LeRobot-based imitation learning tool for G1 bimanual dexterous hand data.

[↑ Back to TOC](#toc)

<a name="slam-perception"></a>

## 🗺️ SLAM & Perception

- **AprilTag** — [`github.com/AprilRobotics/apriltag`](https://github.com/AprilRobotics/apriltag)
 📄 A widely used visual fiducial system for robotics, supporting tag detection, pose estimation, and camera / robot calibration.

- **Cartographer** — [`google-cartographer-ros.readthedocs.io`](https://google-cartographer-ros.readthedocs.io/)
 📄 Google's classic real-time 2D / 3D SLAM system, supporting multi-sensor mapping, localization, and loop-closure optimization.

- **Kalibr** — [`github.com/ethz-asl/kalibr`](https://github.com/ethz-asl/kalibr)
 📄 A multi-sensor calibration toolbox supporting camera intrinsics, multi-camera setups, and camera-IMU joint calibration.

- **Nav2 (Navigation2)** — [`github.com/ros-navigation/navigation2`](https://github.com/ros-navigation/navigation2)
 📄 A ROS 2 navigation framework that provides a full mobile-robot navigation stack, including localization, planning, control, and recovery behaviors.

- **Open3D** — [`www.open3d.org`](https://www.open3d.org)
 📄 A modern 3D data processing library for point clouds, reconstruction, registration, visualization, and 3D machine learning.

- **OpenCV** — [`opencv.org`](https://opencv.org/)
 📄 A classic computer vision library providing image processing, feature extraction, detection, tracking, and geometric vision fundamentals.

- **ORB-SLAM3** — [`github.com/UZ-SLAMLab/ORB_SLAM3`](https://github.com/UZ-SLAMLab/ORB_SLAM3)
 📄 An open-source visual / visual-inertial / multi-map SLAM system supporting monocular, stereo, and RGB-D cameras.

- **PCL (Point Cloud Library)** — [`pointclouds.org`](https://pointclouds.org/)
 📄 A classic point cloud processing library covering filtering, segmentation, registration, reconstruction, visualization, and other core 3D perception functions.

- **RTAB-Map** — [`introlab.github.io/rtabmap`](https://introlab.github.io/rtabmap/)
 📄 A visual / RGB-D / LiDAR SLAM framework based on graph optimization and appearance-based loop closure, suitable for large-scale mapping and localization.

- **RViz / RViz2** — [`docs.ros.org/en/rolling/p/rviz2`](https://docs.ros.org/en/rolling/p/rviz2/)
 📄 The core 3D visualization tool in ROS / ROS 2 for real-time inspection of robot models, TF, point clouds, paths, and maps.

[↑ Back to TOC](#toc)

<a name="middleware-ros"></a>

## 🔧 Middleware & ROS Tools

- **Cyclone DDS** — [`projects.eclipse.org/projects/iot.cyclonedds`](https://projects.eclipse.org/projects/iot.cyclonedds)
 📄 An Eclipse Foundation DDS implementation known for robustness and network adaptability, widely used in ROS 2 deployment.

- **DDS (Data Distribution Service)** — [`www.omg.org/omg-dds-portal/index.htm`](https://www.omg.org/omg-dds-portal/index.htm)
 📄 The publish-subscribe communication standard for real-time distributed systems and the middleware foundation behind ROS 2.

- **Fast DDS (formerly Fast RTPS)** — [`fast-dds.docs.eprosima.com/en/latest/index.html`](https://fast-dds.docs.eprosima.com/en/latest/index.html)
 📄 eProsima's DDS implementation, providing high-performance and configurable communication middleware for ROS 2.

- **MQTT** — [`mqtt.org`](https://mqtt.org/)
 📄 A lightweight publish-subscribe messaging protocol commonly used for robot edge devices, gateways, and cloud data transport.

- **Open-RMF** — [`www.open-rmf.org`](https://www.open-rmf.org)
 📄 An open-source framework for coordinating multi-robot fleets and building infrastructure, supporting task scheduling, resource coordination, and interoperability.

- **Zenoh** — [`zenoh.io`](https://zenoh.io/)
 📄 A lightweight data communication protocol and middleware for robots and edge systems, well suited for efficient pub/sub and query workflows in distributed settings.

- **Foxglove** — [`foxglove.dev`](https://foxglove.dev)
 📄 A data-visualization and observability platform for robotics and Physical AI, supporting ROS, MCAP, 3D scenes, and multimodal log debugging.

- **PlotJuggler** — [`github.com/facontidavide/PlotJuggler`](https://github.com/facontidavide/PlotJuggler)
 📄 A visualization and analysis tool for robot time-series data, ideal for topic debugging, log replay, and metric comparison.

- **ros2_latency_analysis** — [`github.com/TUM-AVS/ros2_latency_analysis`](https://github.com/TUM-AVS/ros2_latency_analysis)
 📄 A latency analysis tool for ROS 2 that helps break down end-to-end, communication, and computation bottlenecks.

- **ROSboard** — [`github.com/dheera/rosboard`](https://github.com/dheera/rosboard)
 📄 A lightweight tool that turns ROS / ROS 2 topics into web dashboards for remote monitoring and mobile viewing.

- **rqt_plot** — [`docs.ros.org/en/rolling/p/rqt_plot`](https://docs.ros.org/en/rolling/p/rqt_plot/)
 📄 A common ROS / ROS 2 plotting plugin for viewing topic values in real time during tuning and debugging.

- **system_fingerprint** — [`github.com/MetroRobots/ros_system_fingerprint`](https://github.com/MetroRobots/ros_system_fingerprint)
  📄 A system snapshot tool for ROS / ROS 2 runtime environments, nodes, topics, and TF state, useful for debugging and delivery validation.

- **Webviz** — [`webviz.io`](https://webviz.io/)
 📄 A browser-based visualization platform for ROS bag files and live robot data, useful for layout-based analysis, replay, and remote debugging.

- **Arduino IDE** — [`www.arduino.cc`](https://www.arduino.cc)
 📄 An open-source electronics prototyping environment suited for quick sensor, actuator, and control-board integration, with support for C / C++ programming.

- **Clearpath·Husky** — [`clearpathrobotics.com`](https://clearpathrobotics.com)
 📄 A common ROS research mobile robot platform with standardized interfaces, well suited to outdoor navigation and algorithm validation.

- **Clearpath·TurtleBot 4** — [`www.turtlebot.com`](https://www.turtlebot.com/)
 📄 A plug-and-play ROS 2 starter platform for teaching and research, ideal for navigation and multi-sensor experiments.

- **MoveIt** — [`moveit.ai`](https://moveit.ai)
 📄 A motion planning, manipulation, and kinematics framework for ROS, widely used for arm planning, grasping, and task orchestration.

- **OMPL** — [`ompl.kavrakilab.org`](https://ompl.kavrakilab.org)
 📄 An open-source motion planning library that includes many classic sampling-based planners for path planning and arm planning.

[↑ Back to TOC](#toc)

<a name="other"></a>

## 🛒 Other

> Tools, platforms, and projects not covered by the above categories

[↑ Back to TOC](#toc)

*Data updated: June 22, 2026*
