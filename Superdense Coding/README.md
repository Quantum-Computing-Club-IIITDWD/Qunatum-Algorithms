
# Superdense Coding

Superdense coding is a procedure that allows someone to send two classical bits to another party using just a single qubit of communication.


Quantum teleportation and superdense coding are closely related, to avoid confusion we need to clarify the difference.


#####Difference between Quantum Teleportation and Superdense Coding

------------


###### Teleportation 
*Transmit one qubit using two classical bits*

###### Superdense coding
Transmit two classical bits using one qubit

### How does Superdense Coding work ?

------------



#######Sending the bits

Initially we take two qubits, q0 and q1. These qubits are in their basis state |0⟩.




>|00⟩=|0⟩<sub>q0</sub>⊗|0⟩<sub>q1</sub>

------------



We create a bell-pair out of them by applying a Hadamard Gate (**H**) to q1




>|+0⟩=(|00⟩+|10⟩)/√2

------------


and CNOT Gate (**CX**) with q1 as control and q0 as target bit, this creates an entangled state.




>(|00⟩+|11⟩)/√2

------------

Now, to send 2 Classical bits of information using q1, we need to use some encoding rules, a protocol that will help us to send the information.
This set of protocol is to apply quantum gates depending on the 2 bits of information that needs to be sent.


###### Encoding Rules

| Information | Gate Applied  | Output State |
| :------------ |:---------------:| :--------:|
| 00| I | l00⟩+l11⟩/√2 |
| 01| X | l10⟩+l01⟩/√2 |
| 10 | Z |l00⟩-l11⟩/√2 |
| 11 | ZX|-l10⟩+l01⟩/√2 |

                

If information is 00, no gates are applied during sending.
If information is 01,** X** gate is applied during sending.
If information is 10,** Z** gate is applied during sending.
If information is 11, both **Z** and **X** gates are applied during sending.


####### Receiving the bits

After the encoding of the information qubits the receiver simply decodes the message by applying the reverse of the entanglement operations, there is no need to knowing the encoding protocols for the receiving end.

Simply apply CNOT Gate with q1 as control and q0 as target bit.

| Received Message | After CNOT Gate |
| :------------ |:---------------:|
| l00⟩+l11⟩/√2 | l00⟩+l10⟩/√2 |
| l10⟩+l01⟩/√2 |l11⟩+l01⟩/√2 |
|l00⟩-l11⟩/√2 |l00⟩-l10⟩/√2 |
|-l10⟩+l01⟩/√2 |-l11⟩+l01⟩/√2 |


Then apply the Hadamard Gate to q1.

| After CNOT Gate | After H Gate |
| :------------ |:---------------:|
 |l00⟩+l10⟩/√2 | l00⟩
| l11⟩+l01⟩/√2 | l01⟩
|l00⟩-l10⟩/√2 | l10⟩
|-l11⟩+l01⟩/√2 | l11⟩

We have successfully received the sent information using the Superdense Coding Protocols 


