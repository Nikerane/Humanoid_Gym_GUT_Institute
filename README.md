# 🤖 Humanoid-Gym Setup Guide (Using Isaac Gym)

This repository provides step-by-step instructions to install and use [Humanoid-Gym](https://github.com/zlw21gxy/humanoid-gym) with NVIDIA's **Isaac Gym**, enabling reinforcement learning for humanoid robots.

---

##  **System Requirements**
- **OS**: Linux (Ubuntu recommended)
- **GPU**: NVIDIA GPU with driver **≥ 515** (recommended: **525**)
- **Python**: 3.8 (via Conda)
- **CUDA**: 11.7

---

## **1. Create a Conda Environment**
First, create and activate a new Conda environment:

```bash
conda create -n humanoid-gym-env python=3.8 -y
conda activate humanoid-gym-env
```

Install PyTorch 1.13.1 with CUDA 11.7:

```
pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117 \
    torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu117

```
Download Issac gyma and unzip the file , then install dependencies in the conda env

```
pip install -e .
```

Run an example script to confirm it works (navigate to the issacgym folder):
```
cd examples
python 1080_balls_of_solitude.py
```

Now, the humanoid repo can be insalled
```
git clone https://github.com/zlw21gxy/humanoid-gym.git
cd humanoid-gym
pip install -e .
```

Trainning the robot
```
cd humanoid
python scripts/train.py --task=humanoid_ppo --run_name experiment1 --headless --num_envs 4096

```

Evaluation
```
python scripts/play.py --task=humanoid_ppo --run_name experiment1
```

other things can also be foung on https://github.com/zlw21gxy/humanoid-gym

