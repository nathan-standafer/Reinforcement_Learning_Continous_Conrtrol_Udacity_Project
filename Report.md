## Project Implementation

This is a Deep Reinforcement Learning project that utilizes a Deep Deterministic Policy Gradient (DDPG) algorithim to control a double-jointed arm can move to a target location.

### Learning Algorithm

The report clearly describes the learning algorithm, along with the chosen hyperparameters. It also describes the model architectures for any neural networks.

I chose to use the DDPG algorithim bacause is works against a continuous action space, whereas other Actor-Critic reinforcement learning are only useful when used in discrete action spaces.
 
The model architecture consistes of an actor and critic model:
 - Actor Model: Receives the envionment state and outputs actions. A basic fully connected network with ReLy activation on the two hidden layers and tahn activatio on teh output layer since the envornment receives actions values between -1 and 1
 - Critic Model: Receives the envonment state and actions as input, outputs the predicted reward (state-value function).
 
 These hpyerparameters worked.  They were chosen based upon other examples and trial-end-error:
 **********************
 
The training loop:
 - Perform a step on the environment, saving data to the replay buffer.
 - After each step is performed:
   - Grab a batch of random step data from the replay history.
   - Train the local critic and actor models.
   - Perform soft updates on teh target critic and actor models.
 - Save the models when done.

### Plot of Rewards:


### Ideas for Future Work

Noise vs random actions for exploration:
 - My trial-and-error look ended in something that worked using a decreasign chance that actions are chosen randomly.  This seemed to provide enough data to allow the algorithim to expore new possibilities (epsilon).  The other appropach would be to add random "noise" to the actions.  The epsilon approache enede up working well enough, so that is what I went with.  Running again using noise might product better results.
 
Other algorithoms:

