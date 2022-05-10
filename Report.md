# Report: Description of the implementation.

The Deep Deterministic Policy Gradients (DDPG) algorithm below successfully solves the task of this project. It learns from the provided environment without any prior knowledge of it or data labels and maximizes reward by interacting with the environment.

## Learning Algorithm
The algorithm trains two agents with exactly the same Neural network architectures:
- Actor
  - Input layer (size 8)
  - FC layer (size 256)
  - Relu
  - FC layer (size 128)
  - Relu
  - Output layer (size 2)
  - Tanh
- Critic
  - Input layer (size 8)
  - FC layer (size 258)
  - Relu
  - FC layer (size 128)
  - Relu
  - Output layer (size 1)

The DDPG agent contains the following components and configs:
- A replay buffer to store memories with the size of 1e5
- Minibatch sizes of 256
- A discount factor of 0.99 for value function approximation
- A soft update to blend the regular into the target network of 1e-3
- Learning rates of the actor and critic each set to 1e-4
- Noise according to the Ornstein-Uhlenbeck process with theta=0.15, sigma=0.2
- Repetitions of learning per agent-step of 3

## Plot of Rewards


The plot shows that the agent was able to receive an average reward of +0.5 over 100 episodes after xxxx episodes. 

## Ideas for Future Work

Future ideas for improving the agent's performance:
- Read the literature and test implementations of other modern multi-agent approaches, e.g.
  - MAA2C
  - IQL
  - IDDPG
  - IPPO
- Tune hyperparameters to accelerate training and better understand how the agent can start working more quickly (not only after 1.xxx episodes) 
