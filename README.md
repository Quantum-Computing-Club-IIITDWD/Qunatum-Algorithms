# Qunatum-Algorithms
# Quantum Counting

In quantum counting, we simply use the quantum phase estimation algorithm to find an eigenvalue of a Grover search iteration. You will remember that an iteration of Grover’s algorithm G, rotates by theta the state vector in w and s  basis:
  

The percentage number of solutions in our search space affects the difference between s and s'. 


In w and s' we can write the grover iterator matrix :

G = ( cos theta  -sin theta 
      sin theta   cos theta )

The matrix G has eigen vectors -

(-i , 1)
, (i, 1 )   





## Controlled Grover Iteration

Python function takes no input and returns a QuantumCircuit object with 4qubits.A function like this allows us to turn the QuantumCircuit object into a single gate that we can control . We can use .to_gate() and .control  to create a controlled gate  from.


## Inverse QFT

Another QauntumCircuit object is created to easily invert the gate . We can create the gate with t=4 qubits as this is the number of coutning qubits we have chosen in this guide.


## Finding the Number of solutions

Create a function calculate_M() hat takes as input the decimal integer output of our register, the number of counting qubits ( 
t
 ) and the number of searching qubits ( 
n
 ).

 Theta = 4.31969

 ( ref code )

 From the Grover's algorithm chapter, you will remember that a common way to create a diffusion operator,Us is actually to implement -Us, In a normal Grover search, this phase is global and can be ignored, but now we are controlling our Grover iterations, this phase does have an effect.The result is that we have effectively searched for the states that are not solutions, and our quantum counting algorithm will tell us how many states are not solutions. To fix this, we calculate N-M.
## Authors

- [jaishana25](https://www.github.com/octokatherine)

