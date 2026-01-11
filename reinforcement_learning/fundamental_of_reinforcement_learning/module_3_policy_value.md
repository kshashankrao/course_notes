# Policy

Informal definition (as I understood) - For a given state S, Policy is the set of rules and there is a x% of probability that one of the rules will be used to select an action A.

Formal defintion - A policy (π) is the formal definition of an agent’s behaviour, serving as a mapping from perceived states of the environment to the probabilities of selecting each available action. The policy $\pi$ is the probability of occurence of action A given the state S.

$$\pi(a|s) = P(A_t = a | S_t = s)$$

Characterstics of policies:

1. Policy can depend only on current state and not previous state. 
2. The state should contain all the neccessary information to make a decision.

There are 2 types of policy:

1. Deterministic -  It is a direct mapping where each state is associated with exactly one specific action.
2. Stochastic - It provides a probability distribution over the available actions for a given state.

Note:
1. Policy can depend only on current state and not previous state. This is because the markov property states that the future state based on only current state and it is independent of previous states. 

# Value funtion

Value functions estimate the expected return, the total reward the agent can expect to accumulate in the future.


