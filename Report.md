Project 1 - Navigation
===

Train an RL Agent to collect Bananas :banana:

Udacity Deep Reinforcement Learning Nanodegree

## Table of Contents

1. [ Summary ](#sum)
2. [ Learning Algorithm ](#algo)
3. [ Result ](#res)
4. [ Ideas of Future Work ](#work)

<a name="sum"></a>
## Summary

The project is based on Unity Environment. The Agent is trained to navigate ( and collect yellow bananas!) in the large, square world!

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. The goal of our agent is to collect as many yellow bananas as possible while avoiding blue bananas. In order to solve the environment, our agent must achieve an average score of +13 over 100 consecutive episodes.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available:
- 0 - move forward
- 1 - move backward
- 2 - move left
- 3 - move right

<a name="algo"></a>
## Learning Algorithm
---

As for constructing the Q-Learning algorithm, the general approach is to implement a handful of different components, then run a series of tests to determine which combination of components and which hyperparameters yield the best results.

We have modified our Deep-Q Learning method using two techniques inorder to stabilize training process and reach the optimal action-value function.
- Fixed Q-target: 2 different networks are combined in order to keep the method off-policy. A target network is updated at every iteration while an evalution network at the end of updating phase.
- Experience Replay: In order to decouple sequential states of each episode, Replay buffer <S,a,R,S'> is created. At each iteration a random batch is pulled from buffer.

As an input the vector of state is used instead of an image so convolutional neural nework is replaced with deep neural network. The deep neural network has following layers:
- Fully connected layer - input: 37 (state size), output: fc1_units
- Fully connected layer - input: fc1_units, output fc2_units
- Fully connected layer - input: fc2_units, output: 4(action size)

The agent was trained on different sizes of [fc1_units, fc2_units] to find best performing agent.

Parameters used in DQN algorithm:
- Maximum steps per episode: 1000
- Starting epsilion: 1.0
- Ending epsilion: 0.01
- Epsilion decay rate: 0.995
- Buffer size: 1e5
- Gamma: 0.99
- Update every: 4
- Learning rate: 5e-4
- tau: 1e-3

<a name="res"></a>
## Result
---

The agent's performance within the Banana environment was measured by the average score. The table below shows the complete set of experiments.

| [fc1_units, fc2_units] | Average Score |
| :---: | :---: |
| 64, 64 | 15.4 |
| 64, 32 | 16.7 |
| 128, 64 | 16.3 |
| 64, 16 | 15.0 |
| 128, 32 | 15.5 |

Note that every Deep-Q network was trained on 1000 episodes & tested on 10 episodes.

The top performing agent was with [fc1_units, fc2_units] = [64, 32]. The agent was able to have a average score 17.1 over 10 test episodes.

![](https://raw.githubusercontent.com/Ansheel9/P1-Navigation-DeepRL/master/Plot.PNG)

This is plot of rewards when training. With mean score of 16.7, agent passes met the criteria (mean scores of last 100 episodes is above +13)

<a name="work"></a>
## Ideas of Future Work
---

- Implementing Deep-Q network using methods like Double Deep-Q network, Dueling Deep-Q network & Rainbow.
- Modifying Deep-Q Network by using Pritorized Experience Replay.
- Implementing Deep-Q network learning from pixels.
