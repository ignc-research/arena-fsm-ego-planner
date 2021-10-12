# Arena-FSM-EGO-Planner

This repository contains the code for the paper [Obstacle-aware Waypoint Generation for Long-range Guidance of
Deep-Reinforcement-Learning-based Navigation Approaches](https://arxiv.org/pdf/2109.11639.pdf). It implements a waypoint generator, which considers dynamic obstacles for mid-range guidance of a DRL-based local planner. Therefore, Delaunay Triangles are utilized to encode dynamic obstacles and to extend a hybrid A* planner with a time domain. Subsequently the computed trajectory is optimized using the [EGO Optimizer](https://github.com/ZJU-FAST-Lab/ego-planner-swarm) from Zhou et al. The approach is called Arena-FSM-EGO-Planner.

Arena-FSM-EGO-Planner is developed on top of the navigation framework [arena-rosnav](https://github.com/ignc-research/arena-rosnav/), which is a modular high-level library for end-to-end experiments in embodied AI -- defining embodied AI tasks (e.g. navigation, obstacle avoidance, behavior cloning), training agents (via imitation or reinforcement learning, or no learning at all using conventional approaches like DWA, TEB or MPC), and benchmarking their performance on the defined tasks using standard metrics. It uses [Flatland](https://github.com/avidbots/flatland) as the core simulator.


| <img width="400" height="400" src="/img/fsm-demo1.gif"> | <img width="400" height="400" src="/img/fsm-demo5.gif"> |
|:--:| :--:| 
| *performance an a map with static obstacles* | *performance on an empty map* |


## 1. Installation
Please refer to [Installation.md](docs/Installation.md) for detailed explanations about the installation process.

## 2. Usage

### Test the FSM-EGO-Planner

Please refer to [FSM-EGO-Planner](docs/time_space_planner.md) for detailed explanations about the waypoint generators.

