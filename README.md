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
''' Type your code here'''

## Output:



## Result:

Thus, the Hidden Markov Model to identify the sequence of Hidden states  is executed successfully 
