# LAB 09
## Matteo Pietro Pillitteri s314404 Polytechnic of Turin

### Brief introduction
The code in the repository "lab9" implements an Adaptive Generational GA + Elitism that has the goal solve the *Problem* instances 1, 2, 5, and 10 on a 1000-loci genomes, using a minimum number of fitness calls. 
See below for more details.
> [!IMPORTANT]
> I worked alone for this lab, I did my best and I am grateful to receive advice to improve the solution and learn more.

### The steps that led me to a solution:
- **You must understand that there is nothing to understand**: it very important to understand that the make_problem function is a blackbox that provide you the fitness metric to evaluate your individuals. Everything you need to take the first steps into the problem:
   - the individual's genome is encoded as a bit string
   - choose the strategy
- Explore the possibilities: I choosed to work with Genetic algorithm (GA)  After having theoretically learned the theory on GA, I understood the implementation logic and i tried different kind of GA. There are two main approaches:
  - Recombination + Mutation:
    ![Screenshot](./images/recplusmut.png)
  - Recombination vs Mutation:
    ![Screenshot](./images/recvsmut.png)
    Modern GA algorithms are based on  this second strategy using crossover or mutation according to some probability. Here you can find a basic implementation based on this approach: https://github.com/squillero/computational-intelligence/blob/master/2023-24/set-covering_ea.ipynb
- Start to code: as I said, I tried several strategies such as: Steady state GA, Generational GA, **Generetional GA + Elitism** and some GA variants like the Islands Model
  - I found Generational GA + Elitism the best one in optimizing fitness and minimizing fitness calls:
    - Generational:
    - Elitism:
  - Parameter tuning
  - **Diversity is all you need**

- Exploration vs exploitation: 

### Some results:
> [!NOTE]
> Trying my code you might get different results from the ones below. This depends on several factors:
> - initial population
> - At each generation the number of mutations or recombinations applied
> - probabilities by which different mutation or recombination operators are selected 
> Anyway the results do not vary much with each run of the algorithm with the same values for the parameters of POPULATION SIZE, MUTATION PROBABILITY, TOURNAMENT SIZE
