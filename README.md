# Deep-RL_Reacher-project

## General 
The goal of this project is to train an agent, which is a double-jointed-arm, to maintain its position at moving target locations for many time steps as possible. The environment is considered solved whenn an average score of 30 over 100 episodes has been reached.

## Project environment
The environment used is similar to UnityML's Reacher environment, provided by Udacity (see below).

TBD add screenshot

### Environment details
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

The environment is a finite 3D world. Within this world, there are fixed positions with each one double-jointed arm agent and one moving target location:
- States: The state space has 33 dimensions per agent
  - Position
  - Rotation
  - Velocity
  - Angular velocity
- Actions: tbd
- Rewards: tbd
- Solved: tbd

## Method

The approach of my implementation considers the following elements:
- tbd

## 	Instructions for installing dependencies or downloading needed files.
all tbd below
- Make sure to use Python v3.6 (I set up a separate environment in my Anaconda to run this)
- Install packages:
  - numpy
  - torch
- Clone and extract this git repository
- Download the appropriate Banana-environment, depending on your operating system, and put the file in the same directory as Navigation.ipynb, from here: 
 - For Linux: https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip
 - For Windows (64-bit): https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip
 - For Windows (32-bit): https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip
 - For MacOSX: (uploaded in this repo, but please unpack the zip and dont forget to grant rights to execute the .app file)

## 	How to run the code in the repository, to train the agent
- Follow instructions above to install dependencies and do required download
- Open the notebook "Navigation.ipynb"
- If you are not using MacOS: Update the file path in the env variable (second code block)
- Run all cells in shown order
- Notebook include options to (re-)train the model, or to load the trained model and replay without further learning
- Hyperparameters can be adjusted when calling the dqn function

## Results
Results are reported and documented in Report.md
