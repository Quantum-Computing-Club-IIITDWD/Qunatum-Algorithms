# Qunatum-Algorithms
######** Deutsch-Jozsa Algorithm**

------------

**Table of Contents**
-Result of the Motivation
-Problem
-Problem Solution
-Classical Solution
-Quantum Solution






This algorithm was one of the first example of a quantum algorithm that performs way faster and efficient than the best classical algorithm. It showed that there can be advantages to using a quantum computer as a computational tool.

------------



##### Result of the Motivation

A problem which for all inputs quantum computer can solve with certainity in polynomial time but classical computers take exponential time to solve with certainity.


------------

##### Problem

There is a blackbox quantum computer or oracle that implements a function
Input has n bits , Output is a single bit either 0 or 1 , with a guarantee that f(x) is either constant( either 0 or 1 )or balanced( half 0's half 1's)

##### Problem solution

Determine whether f is constant or balanced.

------------


##### Classical Solution

N is number of bits, 2^n-1 + 1 evaluations of f will be required in the worst case. In order to prove f is constant we could just evaluvate just over half the sets of inputs and their outputs would be identitcal .The best case is when the function is balanced and the first two output values that are selected are diff. A constant k evaluations of the function suffices to produce the correct answer with a high probability. But k= 2^n-1 + 1 evaluvations are still required to get a surely correct answer.

------------

##### Quantum Solution

Solves this in much less time, polynomial time.If f is implemented as a quantum oracle which maps the state |x⟩|y⟩ to |x⟩|y ⊕ f(x), ⊕ is addition modulo 2. 
 

Given below is a generic circuit of the algorithm.


------------

STEP 0: The n qubit part of the input is all 0's, the last qubit will take in a qubit 1

Step 1: Apply Hadamard Gate

we have all 0 input, on applying hadamard get we get equal superposition of all possible states

Step 2: Uses phase kickback 

CNOT |x-⟩ = (-1)^x |x-⟩

if we pass multiqubit x and minus gate is passed through our oracle the phase kick back property ensure we get that output with f(x) in place of x.

Step 3: Hadamard Gate again 

If measurement outputs are all zeroes  , f is constant . For any other output, f is balanced.

Step 4 : Measure first n qubits 

if f is constant the summation = 1
if f is balanced the summation =0 
where y= |0000..00⟩

Hence after simplification it'll be +/- 2^n if f(x) is constant and 0 if f(x) is balanced


[========]











