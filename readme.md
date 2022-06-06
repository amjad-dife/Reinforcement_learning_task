# Introduction 
- Reinforcement learning is the process of learning by interacting with an environment 
- Gym is released by Open AI in 2016. It is a toolkit for developing and comparing reinforcement learning algorithms
- taxi game : 
    - Actions: There are 6 discrete deterministic actions: 
         *  0: move south 
         *  1: move north 
         *  2: move east 
         *  3: move west 
         *  4: pickup passenger 
         *  5: dropoff passenger 
    - Rewards: There is a reward of : 
        * -1 for each action and an additional reward of 
        * +20 for delievering the passenger. 
        * There is a reward of * -10 for executing actions "pickup" and "dropoff" illegally. 
    - Rendering: 
        * blue: passenger 
        *  magenta: destination 
        *  yellow: empty taxi 
        *  green: full taxi 
        *  other letters: locations
- --------------------------------------------------------------------
# Libraries and modules 
- pandas 
- numpy 
- Gym 
- --------------------------------------------------------------------
# Functions 
- showEnvInfo() 
    - input : the environment 
    - output : print the Action Space and the State  Space of an environment 
- brute_force() 
    - input : the environment
    - output : print the Timesteps taken and the Penalties incurred
- print_frames() 
    - input : frames 
    - output : it print the frames in term of actions and states 
- trainTheAgent() 
    - input : the environment, alpha, gamma, epsilon
    - output : it return the q-table after the training phase.
- evaluateTheAgent() 
    - input : q_table,episodes 
    - output :print the Average timesteps per episode and Average penalties per episode
- optimizedTraining() 
    - input : the environment, alpha, gamma, epsilon
    - processing : the differece between this function and the traditional training [ trainTheAgent() ] is that , inside this function i decay the epsilon depending on a specific condition. 
    - output : it return the q-table after the training phase. 
- --------------------------------------------------------------------
# Sloution approaches 
1. Brute-force approach (Solving the environment without Reinforcement Learning)
    - about this approach : it is Not good, Our agent takes thousands of timesteps and makes lots of wrong drop offs to deliver just one passengerto the right destination
2. Q-learning approach 
    * The core of the idea is the Q-matrix Q(s, a) 
    * Q-learning lets the agent use the environment's rewards to learn, over time, the best action to take in a given state
    * we have the reward table, P, that the agent will learn from. It does thing by looking receiving a reward for taking an action in the current state, then updating a Q-value to remember if that action was beneficial . 
    * The values store in the Q-table are called a Q-values, and they map to a (state, action) combination
- --------------------------------------------------------------------
# How the code work 
1. install the neccessary libraries and modules. 
2. import gym and set up the environment.
3. use [ showEnvInfo() ]  to see the actions and states in the environment.
4. run the first solution ( Brute-force approach ) by using [ brute_force() ].
5. use the [ print_frames() ] to keep track of the game while it is running.
6. run the second solution ( Q-learning approach using Reinforcement learning ) 
    1. use [ trainTheAgent() ] to train the agent  
    2. use [ evaluateTheAgent() ] to evalute the agent
7. I have built three nested loop to implment the Grid search technique , just to find the  best parameter values to train the model with .
8. by using [ optimizedTraining() ] you can try training the model with the mechanism of decay the epsilon depending on specific condition.
    - the condition is : if the number of iteration is one of the following [10000,25000,40000,55000,70000,85000,90000] , then multiply epsilon by 0.1 .  
    - Note that : may be it is not the best way to decay the epsilon but i'm still learning. 
        - "say what you do , and do what you say" Dr/Arya Rahgozar 
- --------------------------------------------------------------------
# References 
1. https://www.kaggle.com/code/charel/learn-by-example-reinforcement-learning-with-gym
2. https://www.learndatasci.com/tutorials/reinforcement-q-learning-scratch-python-openai-gym/
3. https://youtu.be/-WbN61qtTGQ




