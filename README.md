[p2_solution]: images/p2_solution.gif "p2_solution"

# Udacity Reinforcement Learning Nanodegree Project Two: Continuous Control

This is my submission for Project Two: Continuous Control.

Code is based on https://github.com/ShangtongZhang/DeepRL
 hash [5d0ad07](https://github.com/ShangtongZhang/DeepRL/commit/5d0ad07c7f2081123fddc4faf8db2aa09730e85b) with the following improvements:

* removed dependency on OpenAI Baselines
* adapted to use Unity ML-Agents
* Twined Delayed DDPG (TD3) has been adapted to use environemts containing multiple agents

See Report.md for more details

## Reacher Environment

This submission solves the Reacher environment.

![Reacher Environment][p2_solution]

The goal of this environment is for a double-jointed arm to move it's hand to a target location which is constantly changing. The environment gives a reward of +0.1 for each step where the agents's hand is in the correct target location.

The observation space contains 33 continuios variables that capture position, rotation, velocity and angular velocities of the arm. The action space is a continious vector with four values which driver the torque for the two joints. The low/high range of the action space is -1.0 to +1.0.

I chose the use the 2nd version of the Reacher environment which contains 20 identical environment.

This version of the Reacher environment is considered solved by when an average score of 30 is achived. The score is taken by averaging the score from the 20 agents at the end of each episode and then averaging that score over 100 episodes. Specifically,

After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 20 (potentially different) scores. We then take the average of these 20 scores.
This yields an average score for each episode (where the average is over all 20 agents).
As an example, consider the plot below, where we have plotted the average score (over all 20 agents) obtained with each episode.

## Getting Started

1. Download this codebase

2. Download the Reacher environment

* Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
* Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
* Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
* Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)

Then, place the file in the same folder as the codebase and unzip the file

3. To install and create the Conda environment

``` bash
conda env create -f environment.yml
conda activate p2
pip install -r requirements.txt
cd unityagents
pip install -e .
cd ..
pip install -e .
```

## Instructions

### To train the agent

``` bash
python train.py
```

To follow training via tensorboard

``` bash
tensorboard --logdir=tf_log
```

### To view the pre-trained agent

``` bash
python play.py
```

## References

* [Modularized Implementation of Deep RL Algorithms in PyTorch](https://github.com/ShangtongZhang/DeepRL)
