## Project Implementation
This is a Deep Reinforcement Learning project that utilizes a Deep Deterministic Policy Gradient (DDPG) algorithim to control a double-jointed arm can move to a target location.

### Learning Algorithm
I chose to use the DDPG algorithim bacause is works against a continuous action space, whereas other Actor-Critic reinforcement learning are only useful when used in discrete action spaces.
 
The model architecture consistes of an actor and critic model:
 - Actor Model: Receives the envionment state and outputs actions. A basic fully connected network with ReLy activation on the two hidden layers and tahn activatio on teh output layer since the envornment receives actions values between -1 and 1
 - Critic Model: Receives the envonment state and actions as input, outputs the predicted reward (state-value function).
 
These hyperparameters worked.  They were chosen based upon other examples and trial-end-error:
 - buffer_length: 100000   Seems like big number, but worked.
 - learning rage for actor and critic models:  .0002    larger learning rates proved unstable.
 - discount rate of future rewards (gamma): 0.99   I didn't experiment much here, but 0.99 seems to be the standard value.
 - batch_size:  128  The data involved here is relatively small, so 128 sounded like a nice value.
 - epsilon:  During training, this ranged between 0.9 and 0
 
The training loop:
 - Perform a step on the environment, saving data to the replay buffer.
 - After each step is performed:
   - Grab a batch of random step data from the replay history.
   - Train the local critic and actor models.
   - Perform soft updates on teh target critic and actor models.
 - Save the models when done.

In the end, about 200 episodes were required to meet the goal of a score of 30 

### Plot of Rewards:
![](https://github.com/nathan-standafer/Reinforcement_Learning_Continous_Conrtrol_Udacity_Project/raw/master/data/Continuous%20Control%20Training%20(score%20vs.%20epoch).png)

### Ideas for Future Work
Noise vs random actions for exploration:
 - My trial-and-error ended in something that worked using a decreasing chance that actions are chosen randomly.  This seemed to provide enough data outside of the model's chosen actions to allow the algorithim to explore new possibilities (epsilon).  The other appropach would be to add random "noise" to the actions.  The epsilon approach ended up working well enough, so that is what I went with.  Running again using noise might product better results.
 
Other algorithoms:
 - The Distributed Distributional Deterministic Policy Gradients (D4PG) algorithm is one that I could research and attempt to utilize.
 
