# GHZ State
- It is a certain type of entangled state that involves more than 2 qubits.
- The state (for 3 qubits) can be represented as :

  ![state](https://wikimedia.org/api/rest_v1/media/math/render/svg/806963b685467e9f5252c8199a6946394a43f460 "state")](https://wikimedia.org/api/rest_v1/media/math/render/svg/806963b685467e9f5252c8199a6946394a43f460 "state")

--------
[TOCM]

[TOC]

----------
### _Prerequisites_
To understand the circuit and the furthermore discussion about the GHZ state first 
we should know about three things :
- CNOT Gate
- Hadamard Gate
- Entanglement

##### _CNOT Gate_ 
- This is a two qubit operation gate. It uses the first qubit as a control qubit and
the second qubit is taken as a target qubit.
- It applies Pauli-X gate on the target qubit leaving the control qubit unchanged when
the control qubit is in state |1> but leaves target unchanged when control qubit is in
|0> state.
  [![Cnot gate](data:image/png;base64,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 "Cnot gate")](data:image/png;base64,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 "Cnot gate")

##### _Hadamard Gate_ 
- This is a single qubit gate which creates a superposition of |0> and |1>.
- Its matrix representation is :
  <img src=https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTdo7LVuZG6j0tQIRI7p5F4ml7WaTcNvzjW-xMAV-omksF4WnqJpnbeKrSIDtSIuVwAjj8&usqp=CAU "Hadamard Gate")](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTdo7LVuZG6j0tQIRI7p5F4ml7WaTcNvzjW-xMAV-omksF4WnqJpnbeKrSIDtSIuVwAjj8&usqp=CAU "Hadamard Gate" width="160" height=".">

##### _Entanglement_ 
- It is physical phenomenon in which group of particles are generated, interact or share
spatial proximity in a way such that they cannot be described independently even when the particles are seperated by long distance.
------
### _Creating the GHZ state_ 
1. First create a 3-qubit system. Add a hadamard gate to the first qubit.
2. Apply CNOT gate on the first and second qubit by making first qubit as control qubit and second as target qubit.
3. Again apply CNOT on the second and the third qubit making second qubit as the control qubit and third as the target qubit.

***_Note: _***
Losing one qubit causes the entanglement to collapse and ends up being in separable states unlike W state or EPR state (which are different ways to entangle qubits robustly).