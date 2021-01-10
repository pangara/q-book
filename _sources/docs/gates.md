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

You use gates to get from one state to another in the quantum universe. You can think of gates as small microwave pulses that transform the qubit and allow it to go from one state (say $ |0\rangle $) to another state (say (say $ |1\rangle $). 


```{figure} /_static/gate.jpg
:scale: 50%
:name: gate 

A quantum gate

```


We will go over a few important single qubit gates for quantum teleportation. These are the Pauli X gate and the the Hadamard Gate. 
Unlike states which are vectors, gates are matrices, specifically these are unitary matrices. All this means is that a matrix multiplied by its conjugate transpose gives us the identity matrix.
The reason why we choose unitary matrices are because they preserve the length of our state vector. 

$$

    UU^* = U^*U = I

$$

```{note}
You will see that may quantum textbooks use the dagger symbol for a conjugate transpose. This is a phycist/mathematician terminology ambiguity and is essentially interchangeable. 
```

## Pauli-X Gate
```{figure} /_static/x-gate.PNG
:scale: 30%
:name: x-gate 

The X gate
```

Pauli gates are single qubit gates, i.e, they act on a single qubit. These represent rotations around the X, Y and Z axes. We will discuss only the Pauli-X gate here. 
As the name suggests, the Pauli-X gate performs a rotation about the X-axis and is equivalent to the NOT gate in classical computing. In matrix representation, it is given by:

$$

 X = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}

$$



Let's see how the X gate acts on a qubit which is in the $|0\rangle$ state. It is simply a matrix (X) multiplied by a vector ($|0\rangle$).

$$

X |0\rangle = \begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}\begin{pmatrix}
1\\ 0 \end{pmatrix} = \begin{pmatrix}
0 \\ 1 
\end{pmatrix} = |1\rangle

$$

### Exercise 

You are given a state $ |\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle $. What happens to the state when the Pauli-X gate is applied to it? 

## Hadamard Gate

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

### Exercise 

You are given a state $ |\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle $. What happens to the state when the Hadamard gate is applied to it? 



