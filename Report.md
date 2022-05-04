# Report: Description of the implementation.

The Deep Deterministic Policy Gradients (DDPG) algorithm below successfully solves the task of this project. It learns from the provided environment without any prior knowledge of it or data labels and maximizes reward by interacting with the environment.

## Algorithm walkthrough
<img width="837" alt="Bildschirmfoto 2022-05-04 um 12 08 17" src="https://user-images.githubusercontent.com/23191357/166662274-d28e2a22-f419-4606-a660-c3a0f94a57ac.png">

Based on this implementation, adaptations were needed in the model and Noise process to adapt from one to multiple agents. Moreover, the learning rate of the critic was reduced to 1e-3 to 1e-4 which lead to faster and more stable learning.

## Learning Algorithm
Neural network architectures
- Actor
  - Input layer (size 33)
  - FC layer (size 400)
  - Relu
  - FC layer (size 300)
  - Relu
  - Output layer (size 4)
  - Tanh
- Critic
  - Input layer (size 33)
  - FC layer (size 404)
  - Relu
  - FC layer (size 300)
  - Relu
  - Output layer (size 1)

Hyperparameters:
- BUFFER_SIZE = int(1e5)  # replay buffer size
- BATCH_SIZE = 128        # minibatch size
- GAMMA = 0.99            # discount factor
- TAU = 1e-3              # for soft update of target parameters
- LR_ACTOR = 1e-4         # learning rate of the actor 
- LR_CRITIC = 1e-4        # learning rate of the critic

## Plot of Rewards
![image](https://user-images.githubusercontent.com/23191357/166662789-f9c226d9-1d9c-42e9-b02c-1e03fd24d073.png)

The plot shows that the agent was able to receive an average reward over 100 episodes, which is stable between 30 and 40 between episodes 100 to 300. The agent was able to surpass the minimium requirement of +30 after 100 episodes.

## Ideas for Future Work

Future ideas for improving the agent's performance:
- Conduct more hyperparameter tuning
- Implement algorithm for single agent
- Enhance NN architecture 
