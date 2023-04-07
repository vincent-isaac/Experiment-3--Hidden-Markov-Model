# Experiment-3--Hidden-Markov-Model

## Aim:
 Construct a Python code to find the sequence of hidden states by the known sequence of obsevances using Hidden Markov Model. Consider two hidden states Sunny and Rainy with observable states,happy and sad. 
## Algorithm:
Step 1:Define the transition matrix, which specifies the probability of transitioning from one hidden state to another.</br>
Step 2:Define the emission matrix, which specifies the probability of observing each possible observation given each hidden state.</br>
Step 3:Define the initial probabilities, which specify the probability of starting in each possible hidden state.</br>
Step 4:Define the observed sequence, which is the sequence of observations that we want to analyze.</br>
Step 5:Initialize the alpha matrix with zeros, where each row represents a time step and each column represents a possible hidden state.</br>
Step 6:Calculate the first row of the alpha matrix by multiplying the initial probabilities by the emission probabilities for the first observation.</br>
Step 7:Loop through the rest of the observed sequence and calculate the rest of the alpha matrix by multiplying the emission probabilities by the sum of the product of the previous row of the alpha matrix and the corresponding row of the transition matrix.</br>
Step 8:Calculate the probability of the observed sequence by summing the last row of the alpha matrix.</br>
Step 9:Find the most likely sequence of hidden states by selecting the hidden state with the highest probability at each time step based on the alpha matrix.</br>

##  Program:
```python

import numpy as np
transition_matrix = np.array([[0.7,0.3],
                              [0.4,0.6]])
emission_matrix = np.array([[0.1,0.9],
                            [0.8,0.2]])
initial_probablities = np.array([0.5,0.5])
observed_sequence = np.array([1,1,1,0,0,1])
alpha = np.zeros((len(observed_sequence),len(initial_probablities)))
alpha[0,:] = initial_probablities * emission_matrix[:,observed_sequence[0]]
for t in range(1,len(observed_sequence)):
  for j in range(len(initial_probablities)):
    alpha[t,j] = emission_matrix[j,observed_sequence[t]] *np.sum(alpha[t-1,:] * transition_matrix[:,j])
probablity = np.sum(alpha[-1,:])
print("The probablity of the observed sequence is:",probablity)
most_likely_sequence = []
for t in range(len(observed_sequence)):
  if alpha[t,0]>alpha[t,1]:
    most_likely_sequence.append("Sunny")
  else:
    most_likely_sequence.append("Rainy")
print("The most likely sequence of weather states is:",most_likely_sequence)

```

## Output:

![image](https://user-images.githubusercontent.com/74660507/230551844-f590235c-afeb-4fac-8ca0-b1d9fb623dd5.png)

![image](https://user-images.githubusercontent.com/74660507/230551888-d64be5bf-d808-4551-ad2d-635d503388f2.png)

## Result:

Thus, the Hidden Markov Model to identify the sequence of Hidden states  is executed successfully 
