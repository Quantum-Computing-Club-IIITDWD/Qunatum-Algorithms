### Quantum teleportation

##### Why teleportation is needed?
Imagine you want to send some information in your laptop to your friend's laptop then, in 
classical way you can do it using say pen drive or sd card but in quantum quibits we use teleportation algorithm but according to no cloning theoroem we cannot simply make an exact copy of an unknown quantum state.

### Let us understand the code :-
we need 3 quibits to perform this operation between two quibits where one quibit acts as the mediator between the other two quibits. 

initial we take 3 quibits name q_0,q_1 and  q_2. where we are transferring the state of q_0 to q_2 and here q_1 acts as the mediator.

we will be creating the bell state between q_1 and q_2. These qubits are in their basis state |0⟩. And make q_0 to |1> state to show clearly the teleportation. For this we apply X gate on q_0.

>|00⟩=|0⟩q_1⊗|0⟩q_2

>X|0> = |1>

Now we apply a Hadamard Gate (H) to q_1

>|+0⟩=(|00⟩+|10⟩)/√2

and CNOT Gate (CX) with q_1 as control and q_2 as target bit, this creates an entangled state.

>(|00⟩+|11⟩)/√2

##### final entangled state is

>1/√2( |111> +|100>)

##### now after applying cnot gate we are getting the following transformation
>1/√2( |101> +|110>)

##### after applying Hadamard gate we get the following state

>1/√2( |001> +|010>- |101> -|110>)

##### after applying Cnot gate again we get the following state

>1/√2( |001> +|011>- |101> -|111>)

##### now after applying CZ gate we get the following state

>1/√2( |001> +|011>+|101>+|111>)

###### finally we can observe that the final state of q_2 is '1' in all the possible states hence the state  is teleported. And we can also see that q_0 state is destroyed.







