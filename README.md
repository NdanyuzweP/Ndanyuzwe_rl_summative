# Patient Monitoring Reinforcement Learning System

This project implements a reinforcement learning system for proactive patient monitoring in healthcare settings. The system trains agents to learn optimal intervention policies based on patient vital signs, helping to determine when medical attention is needed.

## Project Overview

The system uses a custom Gymnasium environment that simulates patient vital sign monitoring. Two reinforcement learning algorithms are implemented and compared:
- Deep Q-Network (DQN)
- Proximal Policy Optimization (PPO)

The agents learn to select appropriate interventions based on patient vital signs, balancing the need for timely intervention against the risk of false alarms.

## Environment

The environment simulates a patient monitoring system with:
- Four vital signs: Heart Rate (HR), Blood Pressure (BP), Oxygen Saturation (SpO2), and Temperature
- Four possible actions: Continue Monitoring, Send Mild Alert, Request Medical Evaluation, Activate Emergency Protocol

![Patient Monitoring System](docs/environment_screenshot.png)

## Features

- Custom Gymnasium environment for patient monitoring
- 3D visualization system using PyOpenGL
- Implementation of DQN and PPO algorithms using Stable-Baselines3
- Performance comparison between value-based and policy-based methods
- Checkpoint saving during training
- Evaluation and visualization tools

## Project Structure

```
project_root/
├── environment/
│   ├── custom_env.py        # Custom Gymnasium environment
│   ├── rendering.py         # PyOpenGL visualization
├── training/
│   ├── dqn_training.py      # DQN training implementation
│   ├── pg_training.py       # PPO training implementation
├── models/
│   ├── dqn/                 # Saved DQN models
│   └── pg/                  # Saved PPO models
├── logs/
│   ├── dqn/                 # DQN training logs
│   └── ppo/                 # PPO training logs
├── main.py                  # Main script for running experiments
├── requirements.txt         # Project dependencies
└── README.md                # This documentation
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/patient_monitoring_rl.git
cd patient_monitoring_rl
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Training

To train both DQN and PPO models:
```bash
python main.py --mode train --algorithm both --timesteps 100000
```

To train just one algorithm:
```bash
python main.py --mode train --algorithm dqn --timesteps 100000
```

### Evaluation

To evaluate the trained models:
```bash
python main.py --mode evaluate --algorithm both --episodes 10 --render
```

### Visualization

To run the 3D visualization:
```bash
python main.py --mode visualize
```

### Compare Algorithms

To compare the performance of DQN and PPO:
```bash
python main.py --mode compare
```

## Results

The implementation demonstrates how reinforcement learning can be applied to healthcare monitoring systems. Both DQN and PPO successfully learn effective intervention policies, with PPO generally showing more stable learning curves and better performance in terms of average rewards.

Detailed performance comparisons and visualizations can be found in the accompanying report.

## Dependencies

- gymnasium==0.28.1
- numpy==1.24.3
- stable-baselines3==2.1.0
- torch==2.0.1
- pygame==2.5.0
- PyOpenGL==3.1.6
- matplotlib==3.7.1
