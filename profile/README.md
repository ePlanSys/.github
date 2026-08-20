# ePlanSys — Epistemic Planning System for ROS 2

<p align="center">
  <img src="eplansys_docs/eplansys.png" alt="ePlanSys Logo" width="280"/>
</p>

<p align="center">
  <a href="https://github.com/eplansys/eplansys/actions/workflows/epistemic-humble.yaml"><img src="https://github.com/eplansys/eplansys/actions/workflows/epistemic-humble.yaml/badge.svg?branch=rolling" alt="epistemic-planner (humble)"/></a>
  <a href="https://github.com/eplansys/eplansys/actions/workflows/rolling.yaml"><img src="https://github.com/eplansys/eplansys/actions/workflows/rolling.yaml/badge.svg?branch=rolling" alt="rolling"/></a>
  <img src="https://img.shields.io/badge/License-Apache_2.0-blue.svg" alt="License"/>
  <img src="https://img.shields.io/badge/ROS2-Humble%20%7C%20Jazzy-blue" alt="ROS 2"/>
  <a href="https://sites.google.com/view/epistemic-competition/"><img src="https://img.shields.io/badge/IεPC_2026-Intermediate-purple" alt="IεPC 2026"/></a>
</p>

**ePlanSys** (Epistemic Planning System) is a ROS 2 framework that brings **Dynamic Epistemic Logic (DEL)** reasoning into practical robotic planning.

It extends [PlanSys2](https://github.com/PlanSys2/ros2_planning_system) with native support for epistemic planning, enabling robots to reason about knowledge, beliefs, and partial observability in multi-robot scenarios.

### Key Features

- **EPDDL** domain support
- **S5** and **KD45** epistemic models
- Heuristic search over epistemic states
- Multi-robot coordination under partial observability
- Full integration with the PlanSys2 architecture (Domain Expert, Problem Expert, Planner, Executor, Behavior Trees)
- Designed for real robotic deployment, not just offline solvers

---

### Motivation

Classical PDDL planning assumes full observability and perfect knowledge. In multi-robot systems this assumption rarely holds. Agents often need to reason about *what other agents know* (or don’t know) in order to coordinate effectively.

ePlanSys aims to close the gap between formal Dynamic Epistemic Logic research and deployable ROS 2 systems by providing a practical, modular, and extensible epistemic planning stack built on top of PlanSys2.

---

### Architecture

ePlanSys follows the modular design of PlanSys2 and adds specialized epistemic components:

| Component                        | Role                                              |
|----------------------------------|---------------------------------------------------|
| `plansys2_epistemic_planner`     | Epistemic planner with DEL reasoning              |
| `plansys2_epistemic_executor`    | Execution of epistemic plans                      |
| `plansys2_epistemic_bt_builder`  | Behavior Tree generation from epistemic plans     |
| `plansys2_epistemic_msgs`        | Messages and services for epistemic state         |

All classic PlanSys2 nodes (Domain Expert, Problem Expert, Executor, Terminal, etc.) remain available and interoperable.

---

### Getting Started

> Detailed installation and usage instructions will be expanded soon.  
> For now, the system follows the same workspace structure as PlanSys2.

```bash
# Clone into your ROS 2 workspace
cd ~/ros2_ws/src
git clone https://github.com/eplansys/eplansys.git

# Install dependencies
cd ~/ros2_ws
rosdep install --from-paths src --ignore-src -r -y

# Build
colcon build --symlink-install
source install/setup.bash
```

---

### Documentation & Background

- [PlanSys2 Documentation](https://plansys2.github.io) — highly recommended as foundation
- Dynamic Epistemic Logic literature and EPDDL specifications

---

### Contributing

We welcome contributions! Whether you are interested in:

- New epistemic models
- Heuristic improvements
- Multi-robot experimental scenarios
- Integration with perception / world modeling
- Documentation and examples

…feel free to open issues and pull requests.

---

### License

Apache License 2.0

---

### Citation

If you use ePlanSys in academic work, please cite both this project and PlanSys2:

```bibtex
@inproceedings{PlanSys2,
  author    = {Martín, Francisco and Ginés, Jonatan and Rodríguez, Francisco J. and Matellán, Vicente},
  title     = {PlanSys2: A Planning System Framework for ROS2},
  booktitle = {2021 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  year      = {2021},
  publisher = {IEEE}
}
```

---

**Made for the robotics community.**  
Let’s make formal epistemic reasoning practical.
``` 

Want me to adjust the tone (more academic / more engineering-focused), add installation details, or include a specific section?
