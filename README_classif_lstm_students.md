# Data Description

The data consists of trajectories of a 7 dof robotic arm performing a task of peg insertion into a hole.

## Organisation des données:
For classification tasks, you have several data files available:

- `class1_trajectories.npy`
- `class2_trajectories.npy`
- `class3_trajectories.npy`

Each file contains trajectories from one of the classes. The different classes correspond to trajectories generated either with different robots or with different reinforcement learning (RL) models.

The data is provided as tensors with dimensions (`n_samples`, `n_timesteps`, `n_features`):

- `n_samples` represents the number of trajectories in your database; each trajectory corresponds to a different initial configuration of your robot.
- `n_timesteps` is the number of iterations per trajectory (here, 150 steps per trajectory).
- `n_features` is the size of the feature vector available at each time step.

By default, you have 20 observation features available at each time step, detailed below.

## Observations

At each timestep, the agent receives the following 20 observations:


| Observation | Description                                                   | Shape  |
| ----------- | ------------------------------------------------------------- | ------ |
| `peg_pose`  | Position and orientation of the peg  (𝑥, 𝑦, 𝑧, 𝑞𝑤, 𝑞𝑥, 𝑞𝑦, 𝑞𝑧)  | `(7,)` |
| `peg_vel`   | Linear and angular velocity of the peg ( 𝑣𝑥, 𝑣𝑦, 𝑣𝑧, 𝜔𝑥, 𝜔𝑦, 𝜔𝑧)| `(6,)` |
| `hole_pos`  | Position and orientation of the hole (𝑥, 𝑦, 𝑧, 𝑞𝑤, 𝑞𝑥, 𝑞𝑦, 𝑞𝑧)  | `(7,)` |

Orientation is a quaternion

# Your task
For this homework your task will be to train a LSTM model to classify a trajectory.
A code template is available in your directory as well as the data files in .npy format.
You will fill in/modify this code to train and evaluate your model.
In particular in this code you will load the numpy tensor available and prepare your data to build your dataset. You will build a model that takes a sequence as input and predict its class. Your goal will be first to have good classification performances on the test set with your model, and second to evaluate the influence of the number of features given to the model on the performance.

You will also prepare in your code the function to evaluate your model on a new test set that your teacher kept for evaluation, and that will be in the same format as the data you have.


