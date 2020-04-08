# Train an RL Agent to collect Bananas :banana:

---

Udacity Deep Reinforcement Learning Nanodegree

Project 1 - Navigation

---

## Introduction

The project is based on Unity Environment. The Agent is trained to navigate ( and collect yellow bananas!) in the large, square world!

| Before Training | After Training |
| :---: | :---: |
| ![](https://raw.githubusercontent.com/Ansheel9/P1-Navigation-DeepRL/master/BT.gif) | ![](https://raw.githubusercontent.com/Ansheel9/P1-Navigation-DeepRL/master/AT.gif) |

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. The goal of our agent is to collect as many yellow bananas as possible while avoiding blue bananas. In order to solve the environment, our agent must achieve an average score of +13 over 100 consecutive episodes.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available:
- 0 - move forward
- 1 - move backward
- 2 - move left
- 3 - move right

---

## Getting Started

1. Download the environment from one of the links below. You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - MacOS: [click here](https://s3-us-west-amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

    (For Windows users) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (For AWS) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

2. Place the file in the DRLND GitHub repository, in the 'p1_navigation/' folder, and unzip (or decompress) the file.

3. Install conda environment with  <code> conda env create -f environment.yml </code>

---

## Instruction

To train the agent, start jupyter notebook, open <code> Navigation.ipynb </code> and execute! For more information, please check instructions inside the notebook.

---

## Result

Plot showing the score per episode over all the episodes. The environment was trained over 1000 episodes & tested on 10 episodes.

![](https://raw.githubusercontent.com/Ansheel9/P1-Navigation-DeepRL/master/Plot.PNG)
