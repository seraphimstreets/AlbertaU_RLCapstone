# AlbertaU_RLCapstone

The capstone project for the Reinforcement Learning specialization by Alberta University on Coursera. Here, we simulate the landing of a lunar module on the moon and train the agent using deep reinforcement learning.

Concretely, we define a Markov Decision Process (MDP) with the lunar module as the agent, firing of left/right thrusters as actions, and its coordinates, angle, and velocity as its state. We reward the agent for its ability to land in a designated zone, but penalize it for landing too quickly or outside the zone. This will be an  episodic task, with each episode terminating when the agent makes contact with the ground or flies outside the environment boundaries. The agent should also be allowed to learn at every time step (Temporal-Difference learning) to allow more efficient learning and continuous learning in the case that input is lost. (eg. damaged sensors) 

In view of this formulation, we utilize the Expected SARSA algorithm for training our agent. This is due to its ability to handle episodic control problems with continous state variables through TD-Learning. We choose Expected SARSA over Q-Learning as we feel a soft-epsilon policy will be more effective than a deterministic policy at function approximation and avoiding state aliasing. 

The estimates (Q-values) in the action-value network will be updated with a 2-layer NN trained with the Adam optimizer. This is to allow the agent to estimate non-linear functions and thus provide greater robustness in its predictions. 

We also utilize experience replay buffers (data store of previous episodes) to increase the efficiency of training. 

After about 300 episodes, the module had learnt to safely land on the moon. 

After 1000 episodes, reward maximisation goal had reached a plateau. 

# Visualization

Simulation


![Simulation](https://i.imgur.com/WDuUkno.gif)



Learning Curve


![Learning Curve](https://i.imgur.com/855DgGA.png)


