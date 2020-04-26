# DRLND-Project2-continuous-control
This repository contains my implementation of continuous control project for Deep Reinforcement Learning Nano Degree program. For this project, I will train an agent to with a double-jointed arm that can track a moving target location. Deep Deterministic Policy Gradient (DDPG) is used to solve the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

## Goal of the Project
In this project one of two enviroment (distributed or single training) should be solved to succeed. the task is episodic and an agent is considered successful if it gets (must get) an **average score of +30 over 100 consecutive episodes**. 

## Environment
[Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment can be downloaded from the following links for different operatin systems for both one agent and twenty agents:

    - **_Version 1: One (1) Agent_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)

    - **_Version 2: Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux_NoVis.zip) (version 1) or [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux_NoVis.zip) (version 2) to obtain the "headless" version of the environment.  You will **not** be able to watch the agent without enabling a virtual screen, but you will be able to train the agent.  (_To watch the agent, you should follow the instructions to [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the **Linux** operating system above._)

## State/Action Space and Reward
The **state/observation space** has 33 dimensions which contains the agent's position, rotation, velocity, and angular velocities of the arm.

The **action space** is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The **reward** desing for this environment is in a way that it gives reward of +0.1 when the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

## Distributed Training
The code in this project is developed in way to be applicable to both single agent training as well as the distributed training with different number of agents. Two versions of the environement can be used as follows:

- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment. 
The second version is useful for algorithms like [PPO](https://arxiv.org/pdf/1707.06347.pdf), [A3C](https://arxiv.org/pdf/1602.01783.pdf), and [D4PG](https://openreview.net/pdf?id=SyZipzbCb) that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience. 

## Instructions
1. Activate the conda environment `drlnd` as established in [Udacity deep reinforcement learning repository](https://github.com/udacity/deep-reinforcement-learning)
2. Open `Continuous_Control.ipynb` and follow the instructions in it.
3. Change kernel to `drlnd` in `Continuous_Control.ipynb`
4. Unzip the downloaded Reacher environment and give its path to `file_name="..."` in `Continuous_Control.ipynb`.
5. Execute the code cell in `Continuous_Control.ipynb` from beginning to the end. The trained agent will be saved in `checkpoint_actor.pth` and `checkpoint_critic.pt` if the average score > +30.0.

