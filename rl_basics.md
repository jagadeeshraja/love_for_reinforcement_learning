
[RL code plus example](https://medium.com/emergent-future/simple-reinforcement-learning-with-tensorflow-part-0-q-learning-with-tables-and-neural-networks-d195264329d0)

[intro to q learning](http://mnemstudio.org/path-finding-q-learning.htm)

The Q-Learning algorithm was proposed as a way to optimize solutions in Markov decision process problems.
The distinctive feature of Q-Learning is in its capacity to choose between immediate rewards and delayed rewards.  
At each step of time, an agent observes the vector of state $ x_t $ , then chooses and applies an action ut. As the process moves to state xt+1, the agent receives a reinforcement r(xt, ut).  The goal of the training is to find the sequential order of actions which maximizes the sum of the future reinforcements, thus leading to the shortest path from start to finish.

The transition rule of Q learning is a very simple formula:

```math
Q(state, action) = R(state, action) + gamma * Max[Q(next state, all actions)]

```

The gamma parameter has a range of 0 to 1 (0 <= gamma > 1), and ensures the convergence of the sum.  If gamma is closer to zero, the agent will tend to consider only immediate rewards.  If gamma is closer to one, the agent will consider future rewards with greater weight, willing to delay the reward.

The Q-Learning algorithm goes as follows:

1. Set the gamma parameter, and environment rewards in matrix R.

2. Initialize matrix Q to zero.

3. For each episode:

Select a random initial state.

Do While the goal state hasn't been reached.

Select one among all possible actions for the current state.
Using this possible action, consider going to the next state.
Get maximum Q value for this next state based on all possible actions.
Compute: Q(state, action) = R(state, action) + gamma * Max[Q(next state, all actions)]
Set the next state as the current state.
End Do

End For


[distributional rl](https://mtomassoli.github.io/2017/12/08/distributional_rl/)
