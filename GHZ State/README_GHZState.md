# GHZ State

- It is a certain type of entangled state that involves more than 2 qubits.

- The state (for 3 qubits) can be represented as :

  <a href="url"><img src="https://github.com/dxxdpool/Qunatum-Algorithms-heth_sriram/blob/main/GHZ%20State/ghzstate.png" align="center" width=300></a>
--------
### _Prerequisites_

To understand the circuit and the furthermore discussion about the GHZ state, first we should know about three things :

- CNOT Gate

- Hadamard Gate

- Entanglement

#### _CNOT Gate_

- This is a two qubit operation gate. It uses the first qubit as a control qubit and the second qubit is taken as a target qubit.

- It applies Pauli-X gate on the target qubit leaving the control qubit unchanged when the control qubit is in state |1> but leaves target unchanged when control qubit is in |0> state.

  <a href="url"><img src="https://github.com/dxxdpool/Qunatum-Algorithms-heth_sriram/blob/main/GHZ%20State/cnotgate.png" align="center" width=225></a>

#### _Hadamard Gate_

- This is a single qubit gate which creates a superposition of |0> and |1>.

- Its matrix representation is :

  <a href="url"><img src="https://github.com/dxxdpool/Qunatum-Algorithms-heth_sriram/blob/main/GHZ%20State/hadagate.png" align="center" width=180></a>

##### _Entanglement_

- It is physical phenomenon in which group of particles are generated, interact or share spatial proximity in a way such that they cannot be described independently even when the particles are separated by long distance.

------

### _Creating the GHZ state_

1. First create a 3-qubit system. Add a Hadamard gate to the first qubit.

2. Apply CNOT gate on the first and second qubit by making first qubit as control qubit and second as target qubit.

3. Again apply CNOT on the second and the third qubit making second qubit as the control qubit and third as the target qubit.

***Note:***

Losing one qubit causes the entanglement to collapse and ends up being in separable states unlike W state or EPR state (which are different ways to entangle qubits robustly).