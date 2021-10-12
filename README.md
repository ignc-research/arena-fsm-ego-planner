# Arena-FSM-EGO-Planner

This repository contains the code for the paper [Obstacle-aware Waypoint Generation for Long-range Guidance of
Deep-Reinforcement-Learning-based Navigation Approaches](https://arxiv.org/pdf/2109.11639.pdf). It implements a waypoint generator, which considers dynamic obstacles for mid-range guidance of a DRL-based local planner. Therefore, Delaunay Triangles are utilized to encode dynamic obstacles and to extend a hybrid A* planner with a time domain. Subsequently the computed trajectory is optimized using the [EGO Optimizer](https://github.com/ZJU-FAST-Lab/ego-planner-swarm) from Zhou et al. The approach is called Arena-FSM-EGO-Planner.

Arena-FSM-EGO-Planner is developed on top of the navigation framework [arena-rosnav](https://github.com/ignc-research/arena-rosnav/), which is a modular high-level library for end-to-end experiments in embodied AI -- defining embodied AI tasks (e.g. navigation, obstacle avoidance, behavior cloning), training agents (via imitation or reinforcement learning, or no learning at all using conventional approaches like DWA, TEB or MPC), and benchmarking their performance on the defined tasks using standard metrics. It uses [Flatland](https://github.com/avidbots/flatland) as the core simulator.


| <img width="400" height="400" src="/img/fsm-demo1.gif"> | <img width="400" height="400" src="/img/fsm-demo5.gif"> |
|:--:| :--:| 
| *performance an a map with static obstacles* | *performance on an empty map* |



### Documentation & References
* How to use flatland: http://flatland-simulator.readthedocs.io
* ros navigation stack: http://wiki.ros.org/navigation

## 1. Installation
Please refer to [Installation.md](docs/Installation.md) for detailed explanations about the installation process.

## 2. Usage

### Test the FSM-EGO-Planner

Please refer to [DRL-Training.md](docs/DRL-Training.md) for detailed explanations about agent, policy and training setups.

### 2.1 Test the simulation environment and task generator

* In one terminal, start simulation.
```
roslaunch arena_bringup start_arena_flatland.launch map_file:="map1"  disable_scenario:="false" scenario_file:="eval/obstacle_map1_obs20.json"
```
Now click on the `2D Nav Goal` Button and click on the goal towards which the triangulation points. The agent will automatically navigate to the goal.

Alternatively you we provide other maps and scenarios for you to test:
- `map_empty` with the scenarios `empty_map_obs05.json` `empty_map_obs10.json` `empty_map_obs20.json`
- `map1` with the scenarios `obstacle_map1_obs05.json` `obstacle_map1_obs10.json` `obstacle_map1_obs20.json`
