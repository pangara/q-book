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

(entanglement)=


<img style="float: right; max-width:300px; max-height:300px;" src="../_static/einstein.png">

# Entanglement


Following Einstein, Podolski and Rosen's paper, famously called the EPR paper reported something "spooky", which later came to be known as entanglement between two particles.

Entanglement is a physical phenomenon that occurs between particles or in our case qubits, such that the quantum state of one of the qubits cannot be described independently of the other. In other words, the state cannot be tensor factorized. Bell states, named after John Bell, are two-qubit entangled states. Entanglement is one of the components that gives quantum computing its power over classical computers.

```{figure} /_static/Entaglement.jpg
:scale: 40%
:name: entangle-pic 

```

```{figure} /_static/entangle-highlight.png
:scale: 40%
:name: entangle-highlight 

We will focus on this particular part of the circuit that makes a bell pair.

```
## How to create a Bell State/Pair

By combining the Hadamard gate and the CNOT gate, one can create an entangled state. The process is as follows:
1. Initialize two qubits in the state $|00\rangle$. Here the first qubit is in the state $|0\rangle$ and the second qubit is in the state $|0\rangle$
2. Apply the Hadamard gate on the first qubit
3. Apply the CNOT gate with the second qubit as the target qubit.

```{figure} /_static/entangle.PNG
:scale: 40%
:name: entangle 

Creation of a Bell Pair

```

Let's understand how the math works out.

$$
CNOT(H(|00>)) \rightarrow CNOT(\frac{|00> + |10>}{\sqrt2}) \rightarrow \frac{|00> + |11>}{\sqrt2} 
$$

The state $\frac{|00> + |11>}{\sqrt2}$ is called a Bell state. It cannot be tensor factorized. What this means is that we cannot split this state into a form like $|u\rangle \otimes |v\rangle$. 

```{admonition} Exercise: Creating Bell States
:class: tip

The Bell state created above, $\frac{|00> + |11>}{\sqrt2}$, is creating by starting out with both qubits in the state $|00\rangle$. What are the states that get created when you start with the following states
- $|01\rangle$
- $|10\rangle$
- $|11\rangle$

```
