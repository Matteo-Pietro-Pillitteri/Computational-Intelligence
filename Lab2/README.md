# LAB 02 NIM-ES
## Matteo Pietro Pillitteri s314404 polytechnic of turin

### Brief introduction
The code in the repository "Lab2" implements an Adaptive (1+λ)-ES that has the goal to tune a set of weights. The tuining is useful in order to develop a game strategy that uses a fixed set of rules each used with probability proportional to these weights. See below for more details.
> [!IMPORTANT]
> I worked alone for this lab, I did my best and I am grateful to receive advice to improve the solution and learn more.

### The steps that led me to a solution:
- Understand the problem: i saw a lot of materials about the NIM GAME and its verions. I became familiar with the nim-sum in order to understand the "optimal strategy". In particular, the goal of the game is to leave the opponent to take the last "object" and to win, nim sum shall always be != 0. The last one to take loses the game. Some references:
   - https://en.wikipedia.org/wiki/Nim
   - https://www.youtube.com/watch?v=UdmkJeI8xIk
- Understand ESs: After having theoretically learned the theory on evolution strategies, I understood the implementation logic of algorithms based on the plus strategy.
  - The code of Squillero: https://github.com/squillero/computational-intelligence/blob/master/2023-24/rastrigin.ipynb helped me a lot!
  - Useful read:  Essentials of Metaheuristics, A Set of Undergraduate Lecture Notes by Sean Luke (Second Edition), chapter 3.1
- Start to code: first of all i designed a set of rules and a set of actions. Each rule returns True or False depends on whether the condition is satisfied or not. I assigned one action to one rule and then i try if the algorithm was able to play against other strategies:
  - a set of games is composed by 100 games. Player 1 plays always with the my strategy (called adaptive) while Player0 plays with different strategy. In particular, Player0 changes the strategy for each 20 games. At the half ot the set of games, the opponent will play always with the optimal strategy (based on nim sum). This variety will help the tuning in the next steps.
  - each game keeps track about the winner with a simple counter
  - At the end, the fitness will be: number of games in which player1 is the winner/total number of games
- Chose the action: several rules at the same time could be active. It means that different conditions could return True when they are evaluated by the **test_condition** function. So, how i chose the action to apply?
   - the **voting(list_of_actions)** function implements a sort of roulette wheel selection of the action to apply. It receives a list composed by tuples (action, weight). As it is possible to see in the next steps, the weights can have a value over one. I wanted to use the weights as probability but only in the __action selection__. So, the weights are normalized and a random floating point number is generated and the action with the highest score will have a greater chance of being selected.
   - useful read: https://stackoverflow.com/questions/44430194/roulette-wheel-selection-with-positive-and-negative-fitness-values-for-minimizat
- (1+λ)-ES: an individual is a fixed lenght list of weights. The first individual is initialized with elements with the same value. In particular the initial weights are: 1/len(CONDITIONS), so if there are seven rules, the initial individual that represents the initial solution will be an array of 7 elements of value 0,14285714285714285.  With this configuration, it is possible to see in the test at the bottom of the .ipynb that it is possible to obtain a fitness in the range between 0.27 and 0.41.
> [!NOTE]
> the fitness fluctuates for each game with the same set of weights because player 0 plays with different strategies. Some moves are chosen randomly by both the opponent and my player (Player1) without any particular strategy. What matters is that with the sets of rules that describe the strategy called "adaptive" large fitness values are not obtained
