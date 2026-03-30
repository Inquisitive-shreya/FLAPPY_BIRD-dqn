# Flappy Bird Deep Q-Network Agent

This project implements a Deep Q-Network (DQN) Reinforcement Learning agent to play Flappy Bird using PyTorch, Gymnasium, and Pygame.

## Key Features

- Deep Q-Network (DQN) implementation using PyTorch
- Experience Replay for stable learning
- Epsilon-Greedy exploration strategy
- Reward shaping (survival + pipe reward)
- Target network synchronization

## Demo

Coming soon: AI playing Flappy Bird

## How it Works

The agent interacts with the Flappy Bird environment and learns optimal actions using Deep Q-Learning.  
It uses a neural network to approximate Q-values and improves over time through experience replay and reward shaping.


## Installation

First, clone the repository to your local machine:

```bash
git clone https://github.com/AdarshBhoutekar/flappy-bird-dqn.git
cd flappy-bird-dqn
```

### Setup Environment

Because `flappy-bird-gymnasium` requires an older version of Python, it is highly recommended to create a dedicated environment using a tool like Conda.

1. Create a Conda environment with Python 3.10:
```bash
conda create -n flappy_env python=3.10.0
```

2. Activate the virtual environment:
```bash
conda activate flappy_env
```

3. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## How to Run

The agent relies on hyperparameters defined in `parameters.yaml`. You need to specify a parameter set name when running the script. Assuming `flappybirdv0` is one of the parameter sets defined in `parameters.yaml`:

### Training the Agent

To train a new agent, run:

```bash
python agent.py flappybirdv0 --train
```

During training, the model weights and training logs will be saved in the `runs/` directory as `<parameter_set>.pt` and `<parameter_set>.log`.

### Testing the Agent

To watch the trained agent play, run the script without the `--train` flag. It will load the previously saved weights and render the environment:

```bash
python agent.py flappybirdv0
```

### Basic Game Environment

You can also run a simple test script to view the environment (press `SPACE` to flap):

```bash
python game_flappy_bird.py
```

## Project Structure

- `agent.py`: Main Deep Q-Learning agent implementing training and evaluation logic.
- `dqn.py`: Deep Q-Network model architecture built with PyTorch.
- `experience_replay.py`: The Replay Memory buffer used for storing past experiences to train the agent.
- `game_flappy_bird.py`: Basic script using `flappy_bird_gymnasium` and `pygame` for testing the environment.
- `parameters.yaml`: Stores training hyperparameters.
- `requirements.txt`: Python package dependencies.