# Answers to Chapter 1

    Exercise 1.1: Self-Play Suppose, instead of playing against a random opponent, the
    reinforcement learning algorithm described above played against itself, with both sides
    learning. What do you think would happen in this case? Would it learn a diferent policy for selecting moves?

The agent in this case will reach optimal play, i.e. every game against itself will result in a draw, any mistake by an opponent will result in a win.
The actual policy will probably be different, because first agent will be "playing for 3 results", i.e. making suboptimal plays to have a change to win OR lose, rather than guarantee itself a draw.
It will be so because first agent is assigned 0 reward for the draw. So, against a suboptimal player, first agent can reach higher winrate than second, optimal agent, maybe sacrisficing some
point/overall score.

    Exercise 1.2: Symmetries Many tic-tac-toe positions appear diferent but are really
    the same because of symmetries. How might we amend the learning process described
    above to take advantage of this? In what ways would this change improve the learning
    process? Now think again. Suppose the opponent did not take advantage of symmetries.
    In that case, should we? Is it true, then, that symmetrically equivalent positions should
    necessarily have the same value?

We can assign same value for all rotations and mirrorings of the boards, because this position are the same. This can drastically improve the speed of learning.
It is generally true that rotations should have the same value. But if we're optimizing against specific opponent which makes a weak move in specific position/rotation of it, we should try
to reach this position and assign higher value to it.

    Exercise 1.3: Greedy Play Suppose the reinforcement learning player was greedy, that is,
    it always played the move that brought it to the position that it rated the best. Might it
    learn to play better, or worse, than a nongreedy player? What problems might occur?

Counterintuitevely, this algorithm can be better against specific opponent, in which key it will have 100% winrate, but it will fail to generalize.

    Exercise 1.4: Learning from Exploration Suppose learning updates occurred after all
    moves, including exploratory moves. If the step-size parameter is appropriately reduced over time (but not the tendency to explore), then the state values would converge to a different set of probabilities. What (conceptually) are the two sets of probabilities computed when we do, and when we do not, learn from exploratory moves? Assuming that we do continue to make exploratory moves, which set of probabilities might be better to learn? Which would result in more wins?

If we do not learn from exploration, I believe we will converge to the same set of probabilities.

    Exercise 1.5: Other Improvements Can you think of other ways to improve the reinforce-
    ment learning player? Can you think of any better way to solve the tic-tac-toe problem
    as posed?

Tabula-rasa learning is a way to go.) Actually, simple brutforce solution works here, and it is probably even less computationally expensive.
