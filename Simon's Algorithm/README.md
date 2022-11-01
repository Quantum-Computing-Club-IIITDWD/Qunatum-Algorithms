# Simon's Algorithm
---
Simon’s Algorithm is one that’s often overlooked in quantum resources, unjustly so. While it lacks the beautifully simple execution of The Deutsch-Jozsa Algorithm, or the incredible versatility and usefulness of Grover’s Algorithm, Simon’s Algorithm acts as the precursor towards a very important concept; the Quantum Fourier Transform,which itself served as the inspiration for arguably the single most influential topic in Quantum Computing: Shor’s Algorithm.
It was also the first algorithm to show exponential speedup compared to the classical algorithm to solve this problem.
***
## Problem
We are given an unknown blackbox function f, which is guaranteed to be either one-to-one ( 1:1 ) or two-to-one ( 2:1 ), where one-to-one and two-to-one functions have the following properties: one-to-one: maps exactly one unique output for every input. An example with a function that takes 4 inputs is:f(1)→1,f(2)→2,f(3)→3,f(4)→4two-to-one: maps exactly two inputs to every unique output. An example with a function that takes 4 inputs is:f(1)→1,f(2)→2,f(3)→1,f(4)→2
This two-to-one mapping is according to a hidden bitstring,  b , where:
given x1,x2 : f(x1)=f(x2)
it is guaranteed : x1⊕x2=b
Given this blackbox  f , how quickly can we determine if  f  is one-to-one or two-to-one? Then, if  f  turns out to be two-to-one, how quickly can we determine  b ? 
As it turns out, both cases boil down to the same problem of finding b, where a bitstring of  b=000... represents the one-to-one  f
 
***
## Classical Solution
Classically, if we want to know what b is with 100% certainty for a given f, we have to check up to  2^(n−1)+1 inputs, where n is the number of bits in the input. This means checking just over half of all the possible inputs until we find two cases of the same output. Thus classical solution has worst case time complexity of O(2^n)
***
## Quantum Solution
Simon’s Algorithm has an extraordinarily good speedup. It runs in polynomial time thus having a exponential sppedup compared to classical solution

**The Oracle**
The Oracle must map a binary bit-string Query onto a binary bit-string Output of the same length. The Query will be preserved.
* For one particular type of Oracle function, each Query has a unique Output, specific to it.
* For the other particular type of Oracle function, each possible Query has another possible Query which produces the same Output bit-string.
* The Oracle must contain a hidden bit string, which we’ll call ‘b’ for ‘bits’. Each original pair of Queries, when a bitwise XOR Gate (or bitwise addition modulo 2) is applied, will give ‘b’ as a result.

**Algorithm**
1. We have two registers at state |0⟩^n.
2. We apply H-gate on the qubits of the first register and get 2^n states of equal superposition.
Here |x⟩ is all 2^n possible bit-strings of equal superposition.
3. After applying the oracle function on both registers, we get |x⟩ on the first register and |y ⊕ f(x)⟩ on the second register. As |y⟩ =|0⟩, we get only |f(x)⟩ on the second register.
4. We measure the qubits of the second register. Here we will get a state |f(z)⟩ on the second register and the first register superposition of two inputs |z ⟩ and |z ⊕ s⟩ that can produce f(z). The s here is our arbitrary bit-string.
From now we will not need the value of the second register, |f(z)⟩.
5. At this stage, we apply H-gate on the first register. And we get an ugly formula like this.
The formula shows y(z ⊕ s) in the second exponent, equal to y·z ⊕ y·s. If y·s = 1, the value of the whole thing will be 0. We will get values only where y·s = 0 mod(2) with equal superposition. (x = y mod(z) means if x is divided by z, y will be the remainder).
6. In our final step, we measure our first register repeatedly to get different values of y from which we can calculate the s.