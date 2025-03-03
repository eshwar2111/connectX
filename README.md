# ConnectX Using Q-Learning

## Overview
This project implements the **ConnectX** game using **Q-Learning**, a reinforcement learning technique. The agent is trained to play ConnectX by learning from past experiences, adjusting its actions to maximize long-term rewards. The environment is designed as a 6x7 board with a win condition of 4 connected pieces (default Connect Four settings).

## Features
- **Custom ConnectX Game Environment**
- **Q-Learning Agent** with state-action mapping
- **Training and Evaluation** scripts
- **Exploration vs. Exploitation** handling using **epsilon-greedy strategy**

## Installation
Ensure you have Python installed along with NumPy:

```bash
pip install numpy
```

## How It Works
### ConnectX Environment
The game is implemented as a class `connectX` with functionalities to:
- **Drop a disc** in a column if valid
- **Check for a win condition** (horizontal, vertical, diagonal)
- **Detect draw conditions**
- **Switch players**
- **Render the board**

### Q-Learning Agent
The agent is implemented using **Q-Learning**, which follows these steps:
1. **Initialize Q-Table** (stores state-action values)
2. **Choose an action** using an **epsilon-greedy policy**
3. **Perform the action** and observe the new state and reward
4. **Update Q-values** using the Bellman equation:
   
   \[
   Q(s, a) \leftarrow Q(s, a) + \alpha [r + \gamma \max Q(s', a') - Q(s, a)]
   \]
   
5. **Repeat until convergence**

## Usage
### Training the Agent
Run the following script to train the agent:

```python
train_agent(episodes=10000)
```

This trains the agent over **10,000 episodes**, printing progress every **1,000 episodes**.

### Evaluating the Agent
After training, evaluate the agent by running:

```python
evaluate_agent(episodes=1000)
```

This evaluates the trained agent against a random opponent. The output displays the number of wins, draws, and losses.

## Results
Example training output:
```
Episode 1000/10000
Episode 2000/10000
...
Episode 10000/10000
```
Example evaluation output:
```
Wins: 1000, Draws: 0, Losses: 0
```

## Future Improvements
- Implement **Deep Q-Learning (DQN)** for better generalization
- Train against different opponent strategies
- Optimize state representation to reduce memory usage

## License
This project is open-source under the **MIT License**.

---



