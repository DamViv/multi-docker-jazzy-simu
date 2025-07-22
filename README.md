
# Multi-Docker ROS 2 Jazzy Simulation Environment

This project sets up a multi-container development environment using Docker and ROS 2 Jazzy for robotics simulation and navigation. It uses Docker Compose to orchestrate two separate containers:

- `ros-jazzy-gz-simulator`: Handles simulation with Gazebo and RViz2
- `ros-jazzy-nav`: Handles ROS other packages for navigation purpose to mimic a real robot

Each container launches a Terminator terminal with predefined layouts for ease of use during development.

---

## Prerequisites

- Docker and Docker Compose installed
- NVIDIA drivers and `nvidia-docker` if you use GPU acceleration
- X server running and accessible (`xhost +local:root`)

---

## Directory Structure

```text
multi-docker-jazzy-simu/
├── ros_jazzy_nav/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   ├── launch.sh
│   ├── build.sh
│   ├── terminatorLayout.txt
│   └── ws/
├── ros_jazzy_gz_simulator/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   ├── launch.sh
│   ├── build.sh
│   ├── terminatorLayout.txt
│   └── ws/
├── docker-compose.yml
├── terminatorLayout.txt
├── launch.sh
└── build.sh
```


---

## Quick Start

### 1. Clone the repository **with submodules**

```bash
git clone --recurse-submodules https://github.com/DamViv/multi-docker-jazzy-simu.git
cd multi-docker-jazzy-simu
```

### 2. Build and launch both dockers**

```bash
./build.sh
./launch.sh
```

This will :
- Stop any existing containers
- Start Gazebo simulator and ROS2 navigation containers
- Open Terminator windows with preset layouts for each container


### 3. Build and launch only one of the docker**
```bash
./ros_jazzy_gz_simulator/build.sh
./ros_jazzy_gz_simulator/launch.sh
```
OR
```bash
./gz_simulator/build.sh
./gz_simulator/launch.sh
```


