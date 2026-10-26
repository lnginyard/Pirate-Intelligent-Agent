# Pirate Intelligent Agent

This project uses deep reinforcement learning to train a pirate agent to navigate an 8x8 maze and reach a treasure located in the bottom-right corner. The agent learns through trial and error rather than following a hard-coded route.

## Project Overview

The starter project provided the maze environment, the game rules, the state representation, the available actions, and portions of the neural-network and training code. The main files provided were:

- `TreasureMaze.py`: Defines the maze, movement rules, rewards, valid actions, and game status.
- `GameExperience.py`: Stores transition experiences and prepares replay batches for training.
- `TreasureHuntGame_starterCode.ipynb`: Provides the notebook structure, model setup, training skeleton, and evaluation workflow.

I completed and extended the intelligent-agent portion of the notebook. In particular, I implemented the training loop in `qtrain()`, including:

- Epsilon-greedy action selection
- Random valid-action exploration
- Model-based action exploitation
- Experience replay
- Bellman target calculation
- Q-value updates
- Target-model synchronization
- Win-rate tracking and completion validation

The final model uses a flattened 8x8 maze state, two fully connected hidden layers with 64 and 32 ReLU neurons, and four linear outputs representing the Q-values for left, up, right, and down. The model is trained with mean squared error and the Adam optimizer.

## Course Learning and Computer Science

This project connected reinforcement learning, neural networks, software development, and algorithmic problem solving. The agent treats maze navigation as a Markov decision process: it observes a state, chooses an action, receives a reward, and updates its strategy based on the expected future value of that action. Experience replay helps reduce the correlation between consecutive experiences, while the target model makes Q-value updates more stable.

The project also demonstrated why testing is important in machine-learning applications. A high recent win rate does not necessarily mean that an agent has learned a reliable policy. The notebook includes `completion_check()` to test the trained model from multiple valid starting positions. In the recorded training run, the agent reached a recent win rate of `1.000`, but the master completion checks reported validation failures and training resumed. This distinction helped me understand the difference between a promising metric and a verified result.

### What Computer Scientists Do and Why It Matters

Computer scientists analyze problems, design algorithms, build software systems, evaluate results, and improve solutions based on evidence. Their work matters because software increasingly influences education, business, transportation, communication, healthcare, and decision-making. In this project, the computer-science contribution was not just writing code; it was translating navigation into states, actions, transitions, rewards, and measurable evaluation criteria.

### How I Approach Problems as a Computer Scientist

I approach a problem by first understanding its requirements and constraints, then breaking it into smaller components. For this project, I separated the environment, experience memory, neural-network model, training process, and evaluation process. I used existing interfaces and data structures, implemented one behavior at a time, and tested the result using training metrics and completion checks. When the win rate appeared successful but the broader validation failed, I treated that as evidence to investigate rather than assuming the system was complete.

This approach emphasizes reproducibility and measurable outcomes. Instead of relying only on a visualization or a single successful game, I compare the implementation with the intended design, inspect intermediate results, and use tests that cover multiple starting configurations.

### Ethical Responsibilities

My ethical responsibility to the end user is to present the system's capabilities and limitations honestly. A successful demonstration from one starting position should not be described as proof that the agent works in every situation. Users should know how the model was trained, what data or environment it depends on, how performance is evaluated, and where errors can occur.

My responsibility to the organization is to produce maintainable, testable, and documented software; protect sensitive information; follow project requirements; and report results accurately. For an autonomous system, I should also consider safety, fairness, transparency, privacy, and accountability. Before deploying a system that makes decisions, I would add broader testing, monitoring, failure handling, and human oversight appropriate to the consequences of incorrect behavior.

## Running the Project

Install the dependencies listed in `requirements.txt`, open `TreasureHuntGame_starterCode.ipynb`, and run the notebook cells in order. The notebook trains the model, runs the completion check, and evaluates a final game from the starting position `(0, 0)`.

## Repository Contents

- `TreasureHuntGame_starterCode.ipynb`: Completed project notebook
- `Ginyard_Lorenzo_TreasureHuntGame.html`: Exported notebook
- `GameExperience.py`: Experience replay implementation
- `TreasureMaze.py`: Maze environment implementation
- `requirements.txt`: Python dependencies
