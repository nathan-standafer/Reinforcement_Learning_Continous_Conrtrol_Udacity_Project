## Reinforcement_Learning_Continous_Control_Udacity_Project

![](https://github.com/nathan-standafer/Reinforcement_Learning_Continous_Conrtrol_Udacity_Project/raw/master/data/reacher.gif)

### Project Details

This is a Deep Reinforcement Learning project that utilizes a Deep Deterministic Policy Gradient (DDPG) algorithim to control a double-jointed arm can move to a target location.  Actions performed upon the enviroment are continuout (not discrete).  The DDPG algorithim works when used against a continuous action space, whereas other Actor-Critic reinforcement learning are only useful when used in discrete action spaces.

### The Environment
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The enviroment allows for controlling 1 arm or 20 arms.  I chose to train using 1 arm.

Additional information on the environment can be found [here](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher).  Additional setup information can be found [here](https://github.com/udacity/deep-reinforcement-learning#dependencies)

### Getting Started
The project runs as a Python 3.7 jupyter notebook.  Dependencies can be found in the repository's python/requirements.txt file.  

## Instructions
Refer to the README file about how to run the code in this repository.

![](https://github.com/nathan-standafer/Reinforcement_Learning_Continous_Conrtrol_Udacity_Project/raw/master/data/Continuous%20Control%20Training%20(score%20vs.%20epoch).png)
