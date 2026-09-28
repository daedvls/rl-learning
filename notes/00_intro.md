### Formal Definition
Reinforcement learning is a framework for solving control tasks (aka 'Decision Problems') by building agents that learn from the environment by interacting with it through trial and error and receiving rewards.


## Definitions

For a system, every time step has State, Action, Reward, Next State associated with it.

- Agent:
Takes state (S_t) and reward (R_t) as inputs, and outputs an action A_t

- Environment:
Takes this A_t, and then outputs the next State and next Reward

- **Expected Return**:
The cumulative reward for the agent. The goal of the agent is to maximise this 'cumulative reward'

* Why? - Because RL is based on the concept of **reward hypothesis** : "All goals can be described as the maximisation of the expected return."


