# Quantum Phase Estimation
--------------------------------------------------------------
- Quantum Phase Estimation is an algorithm used to find the phase of an eigen vector of a unitary operator.

- Generalised circuit for the quantum phase estimation is given as follows :

  <a href="url"><img src="https://github.com/dxxdpool/Qunatum-Algorithms-heth-sriram/blob/main/Quantum%20Phase%20Estimation/QPE.png" align="center" width=300></a>

- To understand the quantum phase estimation let us take an example case; but first, let's understand what a T-gate is...

#### T-gate:
- It is a single qubit operation given by

<a href="url"><img src="https://github.com/dxxdpool/Qunatum-Algorithms-heth-sriram/blob/main/Quantum%20Phase%20Estimation/TGate.png " align="center" width=300></a>

- This gate is related to S gate by the relation S = T²
- T-gate adds a phase e^(i*π∕2) to the state |1>

-----------------
### Steps for implementing the algorithm :

- Before starting here we are going to consider 6 qubits among which 5 act as counting qubits and 6th qubit acts as eigen state of unitary operator.

1.) First to create the qubits on the circuit initialise the 6th qubit i.e., the one that has to act as eigen state of unitary operator with X-gate to get |1>.
2.) Apply Hadamard gate for all the remaining qubits.
3.) After initialising, we perform controlled unitary operations.
4.) We then apply inverse quantum fourier transformation, after which we measure the counting registers i.e., 0,1,2,3 & 4.
5.) The value we get from the counting registers in binary form is to be divided by 2^n, where n is the number of counting registers which then gives us the value for theta.



#####  THE END.
