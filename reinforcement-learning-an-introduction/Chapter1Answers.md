1.1. The agent in this case will reach optimal play, i.e. every game against itself will result in a draw, any mistake by an opponent will result in a win.
The actual policy will probably be different, because first agent will be "playing for 3 results", i.e. making suboptimal plays to have a change to win OR lose, rather than guarantee itself a draw.
It will be so because first agent is assigned 0 reward for the draw. So, against a suboptimal player, first agent can reach higher winrate than second, optimal agent, maybe sacrisficing some
point/overall score.

1.2. We can assign same value for all rotations and mirrorings of the boards, because this position are the same. This can drastically improve the speed of learning.
It is generally true that rotations should have the same value. But if we're optimizing against specific opponent which makes a weak move in specific position/rotation of it, we should try
to reach this position and assign higher value to it.

1.3. Counterintuitevely, this algorithm can be better against specific opponent, in which key it will have 100% winrate, but it will fail to generalize.

1.4. If we do not learn from exploration, I believe we will converge to the same set of probabilities. 

1.5. Tabula-rasa learning is a way to go.) Actually, simple brutforce solution works here, and it is probably even less computationally expensive.
