# Meta-Learning-aspiration-RL-agent

Senior Thesis Project at Princeton. I am currently working on developing a reinforcement learning agent with an adjusted reward function such that $r_t = w_1 \cdot r_t + (r_t - \rho)$ where $\rho$ is the "aspiration" of the agent – the reward the agent expects to achieve in order to be minimally satisfied. The agent will learn to set the optimal value of $\rho$ via meta-learning which will be implemented with a PyTorch optimizer. This work extends a paper produced by the Computational Cognitive Science lab at Princeton which showed that the maximum average cumulative reward achieved over multiple episodes in a grid world environment was achieved with a value of $\rho > 0$, providing inspiration for this work. 


**DeepGridWorld** class: contains the grid-world environment with methods for taking a step in the environment, getting available actions and rewards, checking if a state is terminal and printing the agent on the map.    

**DeepQ_Agent** class: contains the Q-learning agent with methods for choosing an action, updating the Q-table (learning), and getting the aspiration.

**play** function: Runs iterations of the agent on the environment and updates the Q-table if required.
