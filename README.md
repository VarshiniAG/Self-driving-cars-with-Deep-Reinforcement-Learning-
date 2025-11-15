Project: Self-Driving Taxi Simulation Using Reinforcement Learning (Q-Learning & OpenAI Gym)
1. Introduction

The rapid growth of intelligent transportation systems has created a strong need for autonomous decision-making techniques. Reinforcement Learning (RL) offers a powerful framework for training autonomous agents to learn optimal actions through interaction with an environment. This project focuses on applying RL to the Taxi-v2 environment from OpenAI Gym, which models a simplified self-driving taxi scenario.

The autonomous taxi operates in a grid-like world where it must pick up passengers from specific locations and drop them off at their designated destinations. The aim is to train the taxi to perform these tasks safely and efficiently while minimizing wrong moves and maximizing rewards.

This project illustrates the complete workflow—from environment understanding and Q-table initialization to model training using Q-learning and performance evaluation.

2. Problem Description

The Taxi-v2 environment provides a 5×5 grid world with fixed pick-up and drop-off points. The taxi must:

Navigate through the grid

Pick up the passenger from the correct location

Drop the passenger at the correct destination

Avoid illegal actions such as wrong pick-ups or drops

Minimize time taken and penalties

Each state represents the taxi’s position, passenger location, and drop-off point.
Each action represents movement (north, south, east, west), pick-up, or drop-off.

The environment supports a reward mechanism:

+20 for a successful drop-off

-1 for each time step

-10 for incorrect pick-up or drop-off

The goal is to train the taxi to learn an optimal policy that maximizes long-term reward.

3. Reinforcement Learning Approach
3.1 Q-Learning Algorithm

Q-learning is a value-based RL algorithm that helps the agent learn the expected utility of taking an action in a particular state. It does not require a model of the environment, making it suitable for environments like Taxi-v2.

The Q-learning update formula used:
Q(s,a)=Q(s,a)+α[r+γa′max​Q(s′,a′)−Q(s,a)]
max
	
Where:

s = current state

a = action

r = reward

s’ = next state

α (alpha) = learning rate

γ (gamma) = discount factor

3.2 Exploration Strategy

The agent uses an ε-greedy (epsilon-greedy) strategy to balance exploration and exploitation:

With probability ε → choose a random action

With probability (1−ε) → choose the best known action

Over time, ε decays, reducing randomness and allowing the agent to exploit learned knowledge.

4. Implementation Details
4.1 Libraries Used

OpenAI Gymnasium for environment simulation

NumPy for numerical operations

Matplotlib for plotting training performance (optional)

4.2 Training Procedure

Initialize Q-table with zeros

For each episode:

Reset the environment

Loop until the episode terminates:

Choose action using ε-greedy strategy

Execute action, observe reward and next state

Update Q-value

Reduce epsilon for controlled exploration

Track rewards and convergence patterns

The Q-table converges to a near-optimal policy after sufficient training episodes.

5. Results & Observations

After training:

The taxi successfully learns to pick up and drop off passengers.

Time steps per episode reduce significantly.

Wrong pick-ups and wrong drops are minimized.

Overall cumulative reward improves steadily over episodes.

Visualization graphs show the agent progressively learning the shortest and safest routes.

The final learned policy results in:
✔ More efficient taxi navigation
✔ Fewer penalties
✔ Consistent successful drop-offs

6. Applications & Significance

This simulated problem captures core ideas of real-world autonomous navigation systems, such as:

Learning optimal routes

Avoiding invalid actions

Balancing exploration vs. safety

Decision-making under uncertainty

Though simplified, it reflects principles used in self-driving cars, robotics navigation, and intelligent transport systems.

7. Conclusion

This project demonstrates how Q-learning, combined with OpenAI Gym, can be used to build an intelligent taxi agent capable of solving a complex navigation task. The autonomous taxi learns through trial and error and achieves an efficient and safe strategy for passenger pick-up and drop-off.

The project serves as a strong foundation for understanding Reinforcement Learning concepts and provides the groundwork for future expansion into more realistic autonomous driving environments.
