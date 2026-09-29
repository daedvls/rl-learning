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

### NOTE:
* Agent receives state S_o from Env.
* Based on this state, agent takes action A_o
* Env goes to a new state S_1.
* Env gives some reward R_1 to the Agent.

** Thus, R_t is the reward given to the agent as a result of the action A_(t-1). **

## Markov Decision Process (MDP):
- "The RL Process is called a MDP"

Essentially, this means that: 
** Our agent needs _only the current state_ to decide what action to take, and _NOT the history of all states and actions_. **

### Observations and State Space:
This is the information our agent gets from the environment.

**Difference between Observations (o) and States (s):**
State (s) is a complete description of the state of the world. (No hidden information)
Observation (o) is only a partial description of the state. (Ex: One frame of a video game - The agent doesn't know what is beyond this frame)

### Action Space:
Set of all possible actions in an environment.
Actions can be _discrete_ or _continuous space_.


### Reward:
R(tau)  : CHECK: what is tau exactly? ('trajectory: sequence of states and actions.')
Doubt: Didn't we just learn that agent doesn't make decisions based on the history of states and actions? Does this mean reward CAN be a function of those? CHECK!!

#### Gamma (discounting factor):
* between 0 and 1 (Mostly 0.95 to 0.99)
* Larger the gamma, smaller the discount, larger the contribution of that particular time-step reward to the cumulative return.
* Larger gamma -> Agent _cares more about long-term reward_

**NOTE: WORK TO DO. GAMMA and Reward better intuition**


## Tasks:
A task is an instance of an RL problem. Two types: 
Episodic and Continuing Tasks

**Episodic Task**: There is a start and terminal state. Thus an **episode**: _"List of S, A, R, S'"_
Ex: Game level start and level end could constitute the length of the episode.

**Continuing Task:** No terminal state. The agent must learn how to choose the best actions and simultaneously interact with the env.
Ex: Stock market trading bot

## Exploration-Exploitation Trade-off:
**TODO**


## (Major) ways to solve an RL Problem:
Policy-based and value-based.

### Policy $\pi$:
It is the 'brain' of the agent; function that maps state to action.
Policy is the function that we want to learn. Goal: Find the best possible 'optimal policy' $\pi$*

Methods to find this $\pi$*:
* **Directly**: by teaching agent to learn which action to take, given the current state; **Policy-based Methods**
* **Indirectly**: teach the agent which state is more valuable and then take action that leads to more valuable states; **Value-based Methods**


### Policy-Based Methods: 
We learn $\pi$ directly.

Two types of policies:
* _Deterministic:_ a = $\pi$(s) ( a policy for a given state will always return the same action.)

* _Stochastic:_ outputs a probability distribution over actions. 
$\pi$(a|s) = P\[A|s\]

where P is probability distribution over the set of actions, given the state.
(Note: 'A' is the set of actions)

### Value-Based Methods:
Instead of learning a policy fn, we learn a _value function_: maps state to the **expected value of being at that state**

** Value of a state**: the expected discounted return the agent can get if it **starts in that state, and then acts according to our policy**

_"acts according to our policy"_ means that our agent will go to the state with the highest value.

**NOTE: CHECK THE PROPER mathematical expressions for these terms (value fn, policy fn)**

**NOTE: Q-Learning comes under Value-Based Method**



