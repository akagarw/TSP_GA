# Solving Travelling Salesman Problem using Genetic Algorithms
  Given Python Code in "TSP_GA.ipynb" Jupyter Notebook aims to solve the following famous,
  Travelling salesman problem(TSP) - Given a set of cities and distance between every pair of cities, the problem is to find the shortest possible route that visits every city exactly once and returns to the starting point.   
  Hence is a Tour/Path Cost Minimization problem and which makes Genetic Algorithm eligible to be used as valid technique to find near optimal or even best solutions to this problem.
  
### TSP Graph considered here:
  Total Cities = 5
  
  ![](/TSP_Graph.png?raw=true)

### Overview:    
  The GA solves the TSP based on the finding the best order of visiting the given cities such that the cost is minimized. GA first of all, generates an initial Population(Gen 0) of possible solutions. Each possible TSP solution(Chromosome Class) is a possible order of visiting the cities, represent using Permutation Encoding in the genotype/Phenotype  representation. As each solution is generated, it is evaluated sequentially to calculate the Tour Cost and set is as the class attribute for future use. Using the initial Population, GA uses various operators - Elitism, Selection, Crossover and Mutation Operators to evolve the Population across next generations/iterations to get better solutions.  The Metrics are plotted in the end across generations and after a fixed no. of iterations the GA is stopped and the obtained near optimal or even best solution is extracted and displayed.
  
### Genetic Algorithm Parameters:
- Population Size = 10
- Max Generations = 30
- Using Permutation Encoding to represent chromosome solution
- Each Chromosome defined as = ( order of cities ) = ( city1, city2, ...., cityi, ...., cityN )
- Total Genes = Total Cities = 5
- Probability Of Crossover = 0.8
- Probability Of Mutation = 0.1
- Objective Function = Tour Cost
- Elitism = 10% of Population
- Selection Operator = Roulette Wheel Selection
- Crossover Operator = David Crossover
- Mutation Operator = Scramble Mutation


## Algorithm Workflow

### Algorithm Setup:
  - Required Libraries are imported, the GA operating variables discussed above are declared and set to the required values in the Jupyter Kernel Environment
  - GA Operator Functions - David Crossover, Scramble Mutation
  - Defining Chromosome Class : Encapsulating all random tour order Initialization and cost evaluation functions
  - Defining Generation Class : Encapsulating all Generation Operations to create Next Gen, Sets initial Gen, and declares metric storing variables, defining functions for Generation Metrics logging, elitism, roulette Wheel selection.
  
### Initial Population Generation:
  A Set of Chromosome Class Objects is generated. Count is "Population Size" parameter.
  
### Creating Next Generation:
  Generation Class Object is declared and initialized with Initial Generation List.
#### Fitness Calculation : 
The Tour Cost of Each chromosome is used by the objective function to calculate its Fitness. The Tour Cost of whole current generation is first grouped together in the Generation Object's Gen Metrics Attributes and then the Fitness is calulated and logged to Gen Fitness attribute. 
#### Elitism:
Now, The Best 10% of the Population are chosen and taken as it is in the next Generation to keep best solution and control diversity and maintain exploration.
#### Selection:
To get the remaining population, from the Current Generation offsprings are generated. So based on the Fitness Metric, Two parents are selected at random 
by the Roulette Wheel Selection Method, from which Two offspring will be created based on their genetic material in genotype representation. 
#### Crossover and Mutation:
Based on a randomly generated number value, it is decided whether crossover and mutation operators will be performed on the Two chosen parents to generate corresponding offsprings.
The Probability of Crossover and Probability of Mutation are kept as such to explore more in the initial iterations of creating new generations to increase diversity 
whereas do more of exploitation in the generations to decrease diversity and converge to the optimal solution found.

### Metrics Plotting
After iterating for max generations, the evalutation metrics(Tour Cost and Solution Fitness) are plotted accross generations.

## End Results:
  The Best Solution obtained after execution of the Algorithm is:
    Min Cost :  15
    Possible Min Cost Tour :  [3, 2, 1, 4, 5]      
  The results may vary for executions at different times due to inculcation of stochastic process like random initialization in GA. 
  
 ## Comparison of Results:
  The Best Solution after Iterating for Max Generation in the end, after Multiple Executions of the Algorithm are compared and was seen to be converging to the same minimum tour cost, which is in fact the correct solution in the graph considered here. The tour order may vary though.  
  
  This validates the correctness of the written Algorithm from Scratch.
  

