## Pirate Intelligent Agent
These are the system and business requirement documents to implement the DriverPass system.

Briefly explain the work that you did on this project: What code were you given? What code did you create yourself?
Connect your learning from throughout this course to the larger field of computer science:
What do computer scientists do and why does it matter?
How do I approach a problem as a computer scientist?
What are my ethical responsibilities to the end user and the organization?

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

### >What Do Computer Scientists Do?
Computer scientists use technology to solve problems in innovative ways. Sometimes this is as simple as developing a web application, other times it is creating revolutionary artificial intelligence systems. The algorithm I created isn't a ground breaking new way to develop a pathfinding system in games, but it is important as a first step into the world of artificial intelligence. 

### My Approach
My approach to solving this problem was to get algorithm working so that the agent could successfully be trained. After that was complete, I went back and tweaked the hyper-parameters of the model and retrained the agent to find a more efficient set of parameters that would still train the agent succesfully, but take less time and computing power.

### Ethical Responsibilities
For this particular application, there are not a lot of ethical dilemmas for a model that is trained entirely through gameplay and no outside sources of information, and its only goal is to get from point A to point B. However, AI as a whole can lead to some ethical issues. With the advent of AI targeted ads, self-driving cars, and stable diffusion, ethics comes into play when you analyze where the training data was acquired, how it is used, and the decisions the AI makes. As a computer scientist, my responsibility to the end user and the organization is be as transparent as possible, only use data that I require and have permission to use, and to make sure that I don't let any of my inherent biases find their way into the code.
