# Answers to Chapter 1

    Exercise 1.1: Self-Play
    Suppose, instead of playing against a random opponent, the
    reinforcement learning algorithm described above played against itself, with both sides
    learning. What do you think would happen in this case? Would it learn a diferent policy for selecting moves?

The agent will reach optimal play, i.e. every game against itself will result in a draw, any mistake by an opponent will result in a win.

The actual policy will probably be different, because the first agent will be "playing for 3 results", i.e. making sub-optimal plays to have a chance to win OR lose, rather than guarantee itself a draw. It will be so because the first agent is assigned zero reward for the draw. So, against a sub-optimal player, the first agent can reach a higher win rate than a second, optimal agent, maybe sacrificing some points/overall score.

    Exercise 1.2: Symmetries
    Many tic-tac-toe positions appear diferent but are really
    the same because of symmetries. How might we amend the learning process described
    above to take advantage of this? In what ways would this change improve the learning
    process? Now think again. Suppose the opponent did not take advantage of symmetries.
    In that case, should we? Is it true, then, that symmetrically equivalent positions should
    necessarily have the same value?

We can assign the same value for all rotations and mirrorings of the boards because this position is the same. This can drastically improve the speed of learning.

It is generally true that rotations should have the same value. But if we're optimizing against a specific opponent which makes a weak move in specific position/rotation of it, we should try to reach this position and assign a higher value to it.

    Exercise 1.3: Greedy Play
    Suppose the reinforcement learning player was greedy, that is, it always played the move that brought it to the position that it rated the best. Might it learn to play better, or worse, than a nongreedy player? What problems might occur?

Counterintuitively, this algorithm can be better against a specific opponent for some time, in which key it will have 100% win rate, but it

- can fail to generalize
- can fail to learn the optimal policy

A non-greedy player will always converge to the optimal policy and have the best possible win rate.

    Exercise 1.4: Learning from Exploration
    Suppose learning updates occurred after all moves, including exploratory moves. If the step-size parameter is appropriately reduced over time (but not the tendency to explore), then the state values would converge to a different set of probabilities. What (conceptually) are the two sets of probabilities computed when we do, and when we do not, learn from exploratory moves? Assuming that we do continue to make exploratory moves, which set of probabilities might be better to learn? Which would result in more wins?

If we do not learn from exploration, I believe we will converge to the same set of probabilities as if we were learning after each move. If we do learn from the exploratory moves, we will converge to a different set of probabilities, which assume some stochasticity in our actions. I think that policy will try to enter positions where an agent has a better chance to win from any move, rather higher probability of winning making the single best move. I.e. from 2 positions with 3 possible moves agent might prefer(depending on the epsilon value):

- 50%, 65%, 45% win rate

to:

- 100%. 0%, 0% winrate

, even though in the second position it would always win with the optimal policy. Which set of probabilities is better highly depends on the epsilon value, if it is large enough - policy learn from exploratory moves too might get a better result.

    Exercise 1.5: Other Improvements
    Can you think of other ways to improve the reinforcement learning player? Can you think of any better way to solve the tic-tac-toe problem as posed?

Tabula-rasa learning is a way to go. Actually, the simple brute-force solution works here, and it is probably even less computationally expensive. If we want to maximize our win rate, we can train agent until it reaches optimal policy in the normal conditions(0.5 points for a draw), and have a room for some online learning so it can maximize its win rate again specific opponent he is playing against.
