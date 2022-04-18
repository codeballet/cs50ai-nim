# Nim

## Introduction

Nim is an Artificial Intelligence that teaches itself to play Nim through reinforcement learning.

In the game Nim, we begin with some number of piles, each with some number of objects. Players take turns: on a player’s turn, the player removes any non-negative number of objects from any one non-empty pile. Whoever removes the last object loses.

There is some simple strategy for this game: if there is only one pile and three objects left in it, and it is your turn, your best bet is to remove two of those objects, leaving your opponent with the third and final object to remove. But if there are more piles, the strategy gets considerably more complicated. In this problem, the AI learns the strategy for this game through reinforcement learning. By playing against itself repeatedly and learning from experience, eventually the AI will learn which actions to take and which actions to avoid.

## Algorithm

In particular, I use an algorithm called Q-learning for this project. In Q-learning, the AI tries to learn a reward value (a number) for every (state, action) pair. An action that loses the game will have a reward of -1, an action that results in the other player losing the game will have a reward of 1, and an action that results in the game continuing has an immediate reward of 0, but will also have some future reward.

The implemented Q-learning formula is:

```
Q(s, a) <- Q(s, a) + alpha * (new value estimate - old value estimate)
```

In the above formula, `alpha` is the learning rate (how much we value new information compared to information we already have). The `new value estimate` represents the sum of the reward received for the current action and the estimate of all the future rewards that the player will receive. The `old value estimate` is just the existing value for Q(s, a). By applying this formula every time the AI takes a new action, over time the AI will start to learn which actions are better in any state.

## How to play

In order to play, enter the following command:

```
python play.py
```

Before the game starts, the AI will play against itself 10,000 times, learning the game. Then, the first player is randomly chosen between you and the AI.

Once it is your turn to play, you will be offered the options to choose a pile, and then the number to remove from that pile.

At the end of the game, the winner will be announced.

Enjoy playing!

# Intellectual Property Rights

MIT
