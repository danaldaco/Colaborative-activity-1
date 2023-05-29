![](Aspose.Words.8ea5096f-1a37-4285-b669-9f4b9aab6754.001.png)

Collaborative Activity 

Mini case I 

Linear Programming 





Daniela Gil Quiroz                                 A01734451 

Gabriela Olvera Hernández                   A01737643

Jennifer Vanessa Gutiérrez Vidaurri      A01733822

Bruno Chávez Meza                              A01737301

Walkiria Isabella Valencia Zapata         A01733835

Daniel Ruíz Aldaco                               A01658231 



<a name="_s67xdjl65l8s"></a>Professor Hesus García Cobos

28/05/2023





<a name="_m3u5vuvq0c4q"></a>Decision Support Analysis  Gpo 303

Instituto Tecnológico de Estudios Superiores de Monterrey

**Code Link:**

<https://colab.research.google.com/drive/1hp7yqjwLK9S6dqWOmnAcdz51dS7Yhh3j?usp=sharing>

**Question Set:** Consider the WhiskasModel1.py

1. **What are the two parameters that the LpProblem function implements?**

“TheWhiskasProblem” and “LpMinimize”. The first parameter provides a descriptive name to identify the problem and the second parameter defines the type of optimization to be performed, in this case, minimizing the objective function.

![](Aspose.Words.8ea5096f-1a37-4285-b669-9f4b9aab6754.002.png)

1. **Is it mandatory to name the prob variable as prob?**

No, this name can be changed to any other valid name according to Python naming variable  rules.

1. **What are LpContinous and LpInteger used for?**

Firstly, **LpContinuous** is used to define variables that can take any real value in a specific range (Continuous data type).  **LpInteger** is used to define variables that can **only** take integer values (Discrete data type). 

The choice of variable type depends on the nature of the problem and the specific constraints to be modeled. In the case of this problem, we are using **LpInteger** to define the Chicken percent. ![](Aspose.Words.8ea5096f-1a37-4285-b669-9f4b9aab6754.003.png)

1. **Explain and copy the section of code that defines the objective function.**

The function prob is defined as a variable that contains the problem’s data. Variable “x1” corresponds to the percentage of chicken that the can of whiskas contains. Variable “x2” corresponds to the percentage of beef that the can of whiskas contains.

Once we understand the variables, we want to calculate the total cost of ingredients per can. Each can contains a specific amount of beef and chicken given by the variables “x1” and “x2”. We know that each percent of chicken has a price of 0.013 and for beef, each percent has a price of 0.008. So what the objective function is doing by using “+=” operators is to assign to variable “prob” the sum of the result of the chicken price times the percent of chicken used plus the result of the beef price times the percent of beef used.

\# The objective function is added to 'prob' first

prob += 0.013 \* x1 + 0.008 \* x2, "Total Cost of Ingredients per can"



1. **Explain and copy the section of code that defines the constraints**

In linear programming. constraints are conditions that must be satisfied when optimizing the objective function. They limit the values that the decision variables can take, thereby shaping the feasible solutions. In linear programming constraints are represented as linear inequalities or equalities. 

In this specific problem we define the constraints with the help of the “+-” operators since we are adding more to the “prob” variable, once the constraints are logically entered we add a comma to the end of the constraint as well as a simple description of what each constraint refers to. In the first constraint we define the percentage sum, which has to be a sum of 100 in order to cover the full nutritional value. In the second one, we define the protein requirement, in the third one, we define the fat requirements, in the fourth one, the fiber requirement, and in the last one the salt requirement.



\# The five constraints are entered

prob += x1 + x2 == 100, "PercentagesSum"

prob += 0.100 \* x1 + 0.200 \* x2 >= 8.0, "ProteinRequirement"

prob += 0.080 \* x1 + 0.100 \* x2 >= 6.0, "FatRequirement"

prob += 0.001 \* x1 + 0.005 \* x2 <= 2.0, "FibreRequirement"

prob += 0.002 \* x1 + 0.005 \* x2 <= 0.4, "SaltRequirement"


1. **Is this a minimization or maximization problem?**

This is a minimization problem given the fact that Uncle Ben’s is looking to produce their cat food products as cheaply as possible while ensuring they meet the stated nutritional analysis requirements shown on the cans.

1. **Run the WhiskasModel1.py code. (no need to make changes, just run it as is) What is the value of the following variables? Status: BeefPercent = ChickenPercent = Total Cost of Ingredients per can =**

The execution of this file shows that chicken represents 33.33%, beef 66.67% and the total cost of ingredients per can is 97 cents.![](Aspose.Words.8ea5096f-1a37-4285-b669-9f4b9aab6754.004.png)




