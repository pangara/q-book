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

# Entanglement

```{figure} /_static/einstein.PNG
:scale: 30%
:name: einsten 

Following Einstein, Podolski and Rosen's paper, famously called the EPR paper reported something "spooky", which later came to be lnown as entanglement between two particles.

```

Entanglement is a physical phenomenon that occurs between particles or in our case qubits, such that the quantum state of one of the qubits cannot be desceibed independently of the other. In other words, the state cannot be tensor facotrized. Bell states, named after John Bell, are two qubit entangled states. 

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

The state $\frac{|00> + |11>}{\sqrt2}$ is called a Bell state. It cannot be tensor factorized. What this means is that we cannot split this state into a form line $|u\rangle \otimes |v\rangle$. 