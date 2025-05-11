# Step 0: Isaac Lab Environment Validation
This repository contains deliverables for the Step 0 challenge, demonstrating a working setup of Isaac Sim 4.5.0 and Isaac Lab 4.5.0 within a Conda environment on Ubuntu 22.04.

## Objectives
- Establish the specified development environment below.
- Confirm core functionality: run and modify an example (quadcopter demo modified to spin in place CCW).
- Validate the code-sharing workflow.
- Share video demonstration of environment setup and execution of validation example.

---

## Development Environment
- OS: Ubuntu 22.04
- Software: Conda, Isaac Sim 4.5.0, Isaac Lab 4.5.0

---

# Step 1: Create and activate Conda environment
```bash
# Step 1: Create and activate Conda environment
conda create -n isaac_lab_env python=3.10 -y
conda activate isaac_lab_env

# Step 2: Upgrade pip
pip install --upgrade pip

# Step 3: Install Isaac Sim 4.5.0
pip install 'isaacsim[all,extscache]==4.5.0' --extra-index-url https://pypi.nvidia.com

# Step 4: Clone Isaac Lab 4.5.0 and install it
git clone https://github.com/isaac-sim/IsaacLab.git
cd IsaacLab
git checkout tags/v4.5.0 -b isaaclab-4.5.0
./isaaclab.sh --install

# Step 6: Clone this validation repository (for modified example)
cd ..
git clone https://github.com/oscardev256/isaac-lab-challenge.git
cd IsaacLab

# Step 7: Run the modified quadcopter example (must be in IsaacLab root)
./isaaclab.sh -p ../isaac-lab-challenge/step0/quadcopter_spin.py

