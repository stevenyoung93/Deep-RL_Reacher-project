# Deep-RL_Reacher-project

## General 
The goal of this project is to train an agent, which is a double-jointed-arm, to maintain its position at moving target locations for many time steps as possible. The environment is considered solved whenn an average score of 30 over 100 episodes has been reached.

## Project environment
The environment used is UnityML's Reacher environment, provided by Udacity (see below).

<img width="640" alt="Bildschirmfoto 2022-05-04 um 11 48 59" src="https://user-images.githubusercontent.com/23191357/166659675-494d76ad-5d03-470d-bdbb-0efb5cfef996.png">


### Environment details
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

## Method

The approach of my implementation considers the following elements in the model:
- Implementation of the DDPG algorithm (source here https://arxiv.org/abs/1509.02971)
  - Model contains an actor (deterministic approximator of optimal policy mu given the states s, i.e. returning four action values) and the critic (approximates the optimal action-value-function for the actor's action)
  - Both, actor and critic, are neural networks with two fully connected layers after the input (with 400 and 300 units) activated by a relu-function, and an output layer, whereas the size of the second layer for the critic is extended by 4 to additionally consider the actions from mu
  - The output layer of the actor is activated with a tanh to provide action values between -1 and 1
  - The output layer of the critic is activated with a relu to provide a positive action value

The DDPG agent contains the following components and configs:
- A replay buffer to store memories with the size of 1e5
- Minibatch sizes of 128
- A discount factor of 0.99 for value function approximation
- A soft update to blend the regular into the target network of 1e-3
- Learning rates of the actor and critic each set to 1e-4
- Noise according to the Ornstein-Uhlenbeck process with theta=0.15, sigma=0.2

## 	Instructions for installing dependencies or downloading needed files.
- Make sure to use Python v3.6 (I set up a separate environment in my Anaconda to run this)
- Install packages:
  - numpy
  - torch (include torchvision)
- Clone and extract this git repository
- Download the appropriate environment from unity according to your operating system (https://unity.com/de/products/machine-learning-agents)

## 	How to run the code in the repository, to train the agent
- Follow instructions above to install dependencies and do required download
- Open the notebook "Continuous_Control.ipynb"
- Run all cells in shown order
- Notebook include options to (re-)train the model, or to load the trained model and replay without further learning
- Hyperparameters can be adjusted when calling the ddpg function

## Results
Results are reported and documented in Report.md
