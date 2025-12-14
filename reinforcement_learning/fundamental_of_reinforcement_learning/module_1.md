# K armed bandit

It is used to formulate the problem statement for the reinforcement learning. 


Example - A doctor (agent) gives 3 different treatment (action), and the result is an unknown reward (until the real result is obtained). One of the treatement makes the patient better (higher reward), and the other 2 will not help the patient (treatment can be discarded). This is the real result or real reward.

Definition - Agent choses K different action and received an award for each action. The agent should take action based on expectation of the unknown reward (i.e. action value).

# Action values:

<img src="images/image-1.png" width="400">

q*(A) - The action value 

Definition - The action value is defined as the expected reward for a given action The goal is to maximize q*.

It is not known beforehand.

## Estimating the action value

### Method 1 - Sample average method 

<img src="images/image.png" width="400">

It is the ratio of the sum of rewards when action is taken and the number of actions taken. (average)

The rewards can be any numerical representation, but often negative is penalty and positive is victory.

Example - A docor creates a table with rewards whenever a patient feels better with a treatment. 

<img src="images/image-2.png" width="400">

The greedy action is the action with the highest value of the action value estimate. The agent cannot explore (investigate non greedy actions) and exploit (investigate only the greedy action) at the same time, which is a typical problem in reinforcement learning. 

<img src="images/image-3.png" width="400">

### Method 2 - Incremental update (page 53)

<img src="images/image-5.png" width="400">

Q - Estimate of the action value  
R - Rewards

The incremental update is just a exponential average of the rewards taken over time.

(Target - OldEstimate) is an error in the estimate. The target is the nth reward. The step size changes from time step to teme step and is normally set to $\frac{1}{n}$. 

It is possible to decay the old rewards based on the distribution of the rewards (ex - when a treatment works better in winter). When step size is constant and closer to 1, then the recent reward have higher weight. 

Pseudocode:  
<img src="images/image-6.png" width="400">

# Exploration vs exploitation

Exploration - Investigates all the actions irrespective of the rewards. Useful when the conditions are changing.

Exploitation - Investigate the action with the best rewards. Ignores other actions. 

Both cannot be done simultaneously.

When to choose exploration and exploitation? How to balance them ?

## 10 armed testbed

It is a method to find the effectiveness of a method to balance the explore vs exploit. 

The general steps to perform the test are:
1. Select 10 actions (arm). 
2. For every action, reward the agent randomly from a sample of normal distribution.
3. For every run of the experiment, repeat the above steps for 1000 time steps (or iterations). 
4. Run the experiment for N times.
5. Take the average of the values, so we get one value per time step. (it will be smoother)

The KPIs are average reward and optimal action.

## Method 1 - Epsilon greedy

<img src="images/image-7.png" width="400">

A simple method to balance exploit and explore. 

The effectiveness of this method can be determined by using 10 armed test bed for different values of epsilon:

<img src="images/image-8.png" width="400">

## Method 2 - Optimistic initial values









