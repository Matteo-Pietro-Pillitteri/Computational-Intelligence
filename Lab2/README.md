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
- Start to code 
