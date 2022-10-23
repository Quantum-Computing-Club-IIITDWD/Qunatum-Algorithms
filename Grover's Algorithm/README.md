# Grover's Algorithm #

## Introduction ##
The Grover's algorithm demonstrates the superfast database searching capability of a Quantum Computer over a Classical Computer.

## Unstructured Search ##
Suppose you are given a large list of N items. Among these items there is one item with a unique property that we wish to locate; we will call this one the winner w.
Think of each item in the list as a box of a particular color. Say all items in the list are gray except the winner w, which is purple.

![image](https://user-images.githubusercontent.com/98587244/197378206-97cec8ab-ffe6-434b-8035-7c6d423011fd.png)

To find the purple box -- the marked item -- using classical computation, one would have to check on average N/2 of these boxes, and in the worst case, all N of them. On a quantum computer, however, we can find the marked item in roughly √N steps with Grover's amplitude amplification trick. A quadratic speedup is indeed a substantial time-saver for finding marked items in long lists. Additionally, the algorithm does not use the list's internal structure, which makes it generic; this is why it immediately provides a quadratic quantum speed-up for many classical problems.

## Creating an Oracle ##
For the examples in this textbook, our 'database' is comprised of all the possible computational basis states our qubits can be in. For example, if we have 3 qubits, our list is the states |000⟩, |001⟩,… |111⟩ (i.e the states|0⟩→|1).
Grover’s algorithm solves oracles that add a negative phase to the solution states. I.e. for any state |x⟩ in the computational basis:

![image](https://user-images.githubusercontent.com/98587244/197378391-3d8ebb0c-fff7-42f2-812e-c46d0935cb3f.png)

This oracle will be a diagonal matrix, where the entry that correspond to the marked item will have a negative phase. For example, if we have three qubits and ω = 101, our oracle will have the matrix:

![image](https://user-images.githubusercontent.com/98587244/197378428-da7a0957-374d-4c75-88c1-e37973689376.png)

What makes Grover’s algorithm so powerful is how easy it is to convert a problem to an oracle of this form. There are many computational problems in which it’s difficult to find a solution, but relatively easy to verify a solution.
