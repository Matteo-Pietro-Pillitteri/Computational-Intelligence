# LAB 02 NIM-ES
## Matteo Pietro Pillitteri s314404 polytechnic of turin

### Brief introduction
The code in the repository "Lab2" implements an Adaptive (1+λ)-ES that has the goal to tune a set of weights. The tuining is usefull in order to develop a game strategy that uses a fixed set of rules each used with probability proportional to these weights. See below for more details.
***Note:*** I worked alone for this lab, I did my best and I am grateful to receive advice to improve the solution and learn more

### The steps that led me to a solution:
- Understand the problem: i saw a lot of materials about the NIM GAME and its verions. I became familiar with the nim-sum in order to understand the "optimal strategy". In particular, the goal of the game is to leave the opponent to take the last "object" and to win, nim sum shall always be != 0. The last one to take loses the game. Some references:
   - https://en.wikipedia.org/wiki/Nim
   - https://www.youtube.com/watch?v=UdmkJeI8xIk
- Understand ESs: After having theoretically learned the theory on evolution strategies, I understood the implementation logic of algorithms based on the plus strategy.
  - The code of Squillero: https://github.com/squillero/computational-intelligence/blob/master/2023-24/rastrigin.ipynb helped me a lot!
  - Usefull read:  Essentials of Metaheuristics, A Set of Undergraduate Lecture Notes by Sean Luke (Second Edition), chapter 3.1
- Start to code: first of all i designed a set of rules and a set of actions. Each rule returns True or False depends on whether the condition is satisfied or not. I assigned one action to one rule and then i try if the algorithm was able to play against other strategies:
  - a set of games is composed by 100 games. Player 1 plays always with the my strategy (called adaptive) while Player0 plays with different strategy. In particular, Player0 changes the strategy for each 20 games. At the half ot the set of games, the opponent will play always with the optimal strategy (based on nim sum). This variety will help the tuning in the next steps.
  - each game keeps track about the winner with a simple counter
  - At the end, the fitness will be: $/number of games in which player1 is the winner/total number of games 
