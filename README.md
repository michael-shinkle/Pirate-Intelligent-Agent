## Pirate Intelligent Agent

<details> 
  <summary>Table of Contents</summary> 
  <ol> 
    <li><a href="#code-summary">Code Summary</a></li> 
    <li><a href="#what-do-computer-scientists-do">What Do Computer Scientists Do?</a></li> 
    <li><a href="#my-approach">My Approach</a></li> 
    <li><a href="#ethical-responsibilities">Ethical Responsibilities</a></li> 
  </ol> 
</details> 

### Code Summary
The goal of this project was to develop an intelligent agent that is capable of solving a pathfinding problem. In this project I was given the majority of the code for the treasure hunt game, including the sample environment, the moveset, and the agent as a player in the game. I created a deep-Q learning algorithm that allowed the intelligent agent to navigate the maze and to find the most efficient path through it. The agent was able to achieve 100% win rate after 176 epochs with a training time of 309.8 seconds.

Exploitation is derived from the rewards that the agent is given as it progresses through the maze. The AI in this program is using an epsilon greedy algorithm where its goal is to maximize the reward. However, the potential reward that it calculates may not be the optimal reward. That is where exploration comes in. Exploration allows the AI to try different paths in the maze to potentially get a better reward (Khan, n.d.). The original value for the exploration factor in my program was 0.1, so 10% of all moves would be an exploration move. In my testing, increasing the exploration factor to 0.2 shortened the number of iterations to solve the maze from 514 in 12 minutes, to 212 in 4 minutes. Further increasing the exploration factor to 0.3 caused the agent to not be able to solve the maze, as the additional exploration moves caused the agent to get lost too many times and inhibited the learning process. Setting the exploration factor to 0.15 gave me the quickest results, with the AI solving the maze in 132 moves in under 3 minutes. However, it did not discover the optimal path compared to the 0.1 and 0.2 versions

![10_exp](/screenshots/map20.PNG?raw=true "10% and 20% exploration") ![15_exp](/screenshots/map15.PNG?raw=true "15% exploration")

On the left is the path the AI produced at 10% and 20% exploration factor. On the right is the path the AI generated at 15% where an extra move is clearly seen. 

Setting the exploration factor to 0.175 took longer than both the 15% and 20% trials, but it gave the same results as the 10% and 20% maps. Based on this data, the proportion of exploration would either be 15% or 20% depending on your goal. If you want a model that is solved quickly but might not be the most efficient, go with 15%. 20% gives you a more efficient final model but did take more processing power to generate. As a final experiment, I trained the model again at 15% exploration rate and it took 176 iterations in 6 minutes to solve the map. The solution was similar to the 20% map, a slight alteration in the path, but the same number of moves as shown in figure 4. The discrepancy in training time and result is due to the random nature of where the agent is placed during each iteration.

![15_exp](/screenshots/map15_2.PNG?raw=true "15% exploration trained again")

15% exploration trained again.

Looking at the epochs in the training data, the second round at 15% had many more instances where the agent was placed farther away from the goal. This explains why this round had a better path but did take longer. One thing to note is that when the win ratio of the agent surpasses 0.9, the exploration value is lowered to 5%. Because the bounds and move set of this map is very constrained and rigid, this makes sense. As the agent gets closer to solving the map, we want it to move away from exploration and start relying on exploitation (Lutalo, 2022). Due to the rigidity of the map, the agent can predict the outcome of the move easily and accurately. 

### What Do Computer Scientists Do?
Computer scientists use technology to solve problems in innovative ways. Sometimes this is as simple as developing a web application, other times it is creating revolutionary artificial intelligence systems. The algorithm I created isn't a ground breaking new way to develop a pathfinding system in games, but it is important as a first step into the world of artificial intelligence. 

### My Approach
My approach to solving this problem was to get algorithm working so that the agent could successfully be trained. After that was complete, I went back and tweaked the hyper-parameters of the model and retrained the agent to find a more efficient set of parameters that would still train the agent succesfully, but take less time and computing power.

### Ethical Responsibilities
For this particular application, there are not a lot of ethical dilemmas for a model that is trained entirely through gameplay and no outside sources of information, and its only goal is to get from point A to point B. However, AI as a whole can lead to some ethical issues. With the advent of AI targeted ads, self-driving cars, and stable diffusion, ethics comes into play when you analyze where the training data was acquired, how it is used, and the decisions the AI makes. As a computer scientist, my responsibility to the end user and the organization is be as transparent as possible, only use data that I require and have permission to use, and to make sure that I don't let any of my inherent biases find their way into the code.
