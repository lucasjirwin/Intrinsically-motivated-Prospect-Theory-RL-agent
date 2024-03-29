# Intrinsically motivated Prospect Theory RL-agent

Sparse rewards present a significant challenge for agents trained via reinforcement learning. When rewards are sparse, an agent is missing essential feedback, hindering the acquisi- tion of effective policies and resulting in sub-optimal behavior. This problem prompts a fascinating question from a cognitive science perspective: what guiding principles should designers employ when formulating an agent’s intrinsic motivations? We explore the benefits of using an intrinsic reward function in- spired by Kahneman’s and Tversky’s Prospect Theory which is risk-averse and treats positive and negative rewards differently. Our results reveal that the Prospect Theory reward function is a good form of intrinsic motivation to use in dense, sparse, and risky environments, suggesting that future reward architectures could benefit from incorporating insights from human cogni- tion into their models.


Expanding on Senior Thesis Project at Princeton. This thesis builds on the work of Dubey et al. By testing two reward functions based on Dubey et al.’s aspiration model and a new reward function based on Kahneman and Tversky’s Prospect Theory, this work illustrates that a Prospect Theory value function is a good form of intrinsic motivation to use, especially in sparse environments.  The training process consists of three main steps. First, the parameters of the reward functions are tuned with Bayesian optimization applied to a Q-learning agent which learns a policy in simulated, grid-world environments similar to the ones used in Dubey et al. Next, the optimized values are used to test the aspiration and Prospect Theory reward functions on Q-learning agents in the same environments. Finally, the performance of each model is evaluated by comparing the average cumulative reward obtained over 50 runs of 1000 episodes to the reward obtained by a regular $\epsilon$-greedy RL model with the same learning rate and discount factor.

\
**Prospect Theory** reward function: 

$$V(x) = \begin{cases} x^\alpha & \text{if } x \geq 0  & \\
-\lambda(-x)^\beta & \text{if } x < 0 \end{cases}$$

**Aspiration** reward function:
 $$V(x) = w_1 \cdot r_t + w_2 \cdot (r_t - \rho)$$


**GridWorld** class: contains the grid-world environment with methods for taking a step in the environment, getting available actions and rewards, checking if a state is terminal and printing the agent on the map.    

**Q_Agent** class: contains the Q-learning agent with methods for choosing an action, updating the Q-table (learning), and getting the aspiration.

**play** function: Runs iterations of the agent on the environment and updates the Q-table if required.
