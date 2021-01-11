---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

(gates)=

# Single Qubit Gates
```{figure} /_static/gates-highlight.png
:scale: 40%
:name: gates-highlight 

Part of the quantum teleportation diagram with the qubits and gates highlighted.
```
The boxes in yellow represent gates. We use gates to get from one state to another in the quantum universe. You can think of gates as small microwave pulses that transform the qubit and allow it to go from one state (say $ |0\rangle $) to another state (say (say $ |1\rangle $). 


```{figure} /_static/gate.jpg
:scale: 50%
:name: gate 

A quantum gate

```







We will go over a few important single-qubit gates for quantum teleportation. These are the Pauli-X gate and the Hadamard Gate. 
Unlike states which are vectors, gates are matrices, specifically, these are unitary matrices. All this means is that a matrix multiplied by its conjugate transpose gives us the identity matrix.
The reason why we choose unitary matrices is that they preserve the length of our state vector. 

$$

    UU^* = U^*U = I

$$

```{note}
You will see that many quantum textbooks use the dagger symbol for a conjugate transpose. This is a physicist/mathematician terminology ambiguity and is interchangeable. 
```
## Identity Gate

```{figure} /_static/wire.png
:scale: 30%
:name: wire

The Identity gate
```

The simplest gate is the identity gate, which doesn't change the qubit. It is represented by the Identity matrix. While this might seem trivial, qubits are very fragile and it is not quite easy to keep the qubit in its given state. 

## Pauli-X Gate
```{figure} /_static/x-gate.PNG
:scale: 30%
:name: x-gate 

The X gate
```

Pauli gates are single-qubit gates, i.e, they act on a single qubit. These represent rotations around the X, Y and Z axes. We will discuss only the Pauli-X gate here. 
As the name suggests, the Pauli-X gate performs a rotation about the X-axis and is equivalent to the NOT gate in classical computing. In matrix representation, it is given by:

$$

 X = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}

$$



Let's see how the X gate acts on a qubit that is in the $|0\rangle$ state. It is simply a matrix (X) multiplied by a vector ($|0\rangle$).

$$

X |0\rangle = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}\begin{pmatrix}
1\\ 0 \end{pmatrix} = \begin{pmatrix}
0 \\ 1 
\end{pmatrix} = |1\rangle

$$


```{admonition} Exercise 1
:class: tip

You are given a state $ |\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle $. What happens to the state when the Pauli-X gate is applied to it? 

```


## Hadamard Gate

```{figure} /_static/hadamard.png
:scale: 30%
:name: h-gate 

The Hadamard gate
```

The Hadamard gate is a famous one, it takes a state (say |0\rangle) into a superposition state. This is also a single qubit gate and is given by:

$$

H = \frac{1}{\sqrt2}\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}

$$

Let's see how the gate works.

$$

H |0> = \frac{1}{\sqrt2}\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}\begin{pmatrix}
1\\ 0 \end{pmatrix} = \frac{1}{\sqrt2}\begin{pmatrix}
1 \\ 1 
\end{pmatrix} = \frac{|0>+|1>}{\sqrt2}   

$$

Similarly,

$$

\frac{1}{\sqrt2}\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}\begin{pmatrix}
0\\ 1 \end{pmatrix} = \frac{1}{\sqrt2}\begin{pmatrix}
1 \\ -1 
\end{pmatrix} = \frac{|0>-|1>}{\sqrt2} 
$$


```{admonition} Exercise 2
:class: tip

You are given a state $ |\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle $. What happens to the state when the Hadamard gate is applied to it?  
```

## Pauli-Z Gate
The Pauli-Z gate performs a rotation about the Z-axis. 

$$
Z |0\rangle = |0\rangle \\
Z |1\rangle =- |1\rangle
$$

The Pauli-Z gate leaves the state $|0\rangle$ as it is, however, changes the sign of $|1\rangle$. The change of sign represents a change in the phase of the qubit. 

The Pauli-Z gate represented in the matrix form is given by:

$$

Z = \begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}

$$

```{admonition} Exercise 
:class: tip

Given the matrix representation of the Pauli-Z gate, what happens when you apply a Pauli-Z gate to the states $|0\rangle$ and $|1\rangle$? Hint: Start with the vector representations of $|0\rangle$ and $|1\rangle$.

```


## Quantum Circuits
Quantum circuits represent a sequence of manipulations that a qubit or multiple qubits go through. The salmon lines you see in the figure are called wires. There can be multiple wires (symbolizing different qubits) in a circuit. Gates are applied from left to right and a measurement is performed at the end. We will leave measurements for the next section. In this section, we will learn how to build a circuit with gates. 


```{admonition} Example: Create a  circuit
:class: tip

You are given a state $|0\rangle$. A Hadamard gate followed by a Pauli-X gate is applied to the qubit. Draw the circuit. What is the final state? 

```{figure} /_static/exercise-gate .png
:scale: 30%
:name: exercise-gate 
Solution
```

```



```{admonition} Exercise 3: Create circuits and calculate the final state
:class: tip

1. You are given a state $|1\rangle$. A Pauli-X gate followed by another Pauli-X gate is applied to the qubit. Draw the circuit. What is the final state? 
 

```