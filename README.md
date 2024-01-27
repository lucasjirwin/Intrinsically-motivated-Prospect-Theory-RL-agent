# Intrinsically motivated Prospect Theory RL-agent

The problem of sparsity in reinforcement learning has serious implications for the behavior of AI as researchers em- bark on the road towards developing artificial general intelli- gence. In situations where rewards are sparse, an agent en- counters a dearth of essential feedback, hindering the acqui- sition of human-aligned optimal policies and resulting in sub- optimal behavior. This dilemma prompts an fascinating ques- tion from a cognitive science perspective: what guiding prin- ciples should designers employ when formulating an agent’s intrinsic motivations? Here, we explore the benefits of us- ing an intrinsic reward function inspired by Kahneman’s and Tversky’s Prospect Theory which is risk-averse and treats pos- itive and negative rewards differently. Our results reveal that the Prospect Theory reward function is a good form of intrin- sic motivation to use in dense, sparse and risky environments, suggesting that future reward architectures would benefit from incorporating the cognitive insights of Prospect Theory into their models. \\


Senior Thesis Project at Princeton. This thesis builds on the work of Dubey et al. by exploring the effect of reward shaping in  RL to investigate what forms of intrinsic motivation are most beneficial to an agent's performance in different environments. By testing two reward functions based on Dubey et al.’s aspiration model and a new reward function based on Kahneman and Tversky’s Prospect Theory, this work illustrates that a Prospect Theory value function is a good form of intrinsic motivation to use, especially in sparse environments.  The training process consists of three main steps. First, the parameters of the reward functions are tuned with Bayesian optimization applied to a Q-learning agent which learns a policy in simulated, grid-world environments similar to the ones used in Dubey et al. Next, the optimized values are used to test the aspiration and Prospect Theory reward functions on Q-learning agents in the same environments. Finally, the performance of each model is evaluated by comparing the average cumulative reward obtained over 50 runs of 1000 episodes to the reward obtained by a regular $\epsilon$-greedy RL model with the same learning rate and discount factor.

\
**Prospect Theory** reward function: 

$$V(x) = \begin{cases} x^\alpha & \text{if } x \geq 0  & \\
-\lambda(-x)^\beta & \text{if } x < 0 \end{cases}$$

**Aspiration** reward function:
 $$V(x) = w_1 \cdot r_t + w_2 \cdot (r_t - \rho)$$


**GridWorld** class: contains the grid-world environment with methods for taking a step in the environment, getting available actions and rewards, checking if a state is terminal and printing the agent on the map.    

**Q_Agent** class: contains the Q-learning agent with methods for choosing an action, updating the Q-table (learning), and getting the aspiration.

**play** function: Runs iterations of the agent on the environment and updates the Q-table if required.
