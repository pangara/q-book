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

(teleportation)=

# Quantum Teleportation

We are now ready to understand how the teleportation circuit works. From our section on motivation, we understand that teleportation is a process of sending quantum information. Sounds simple enough, but we have a problem called the **no-cloning theorem**. The no-cloning theorem is a result of quantum mechanics which forbids the creation of identical copies of an arbitrary unknown quantum state.

## Problem Statement

* Alice has to send a qubit to Bob. 
* Alice and Bob have a pre-shared Bell State
* Alice can send only classical information to Bob
* Alice doesn’t know the state of the qubit, even if she does, describing it would take infinite amount of classical information since qubits take value in a continuous space. 

## Solution
* Alice interacts $|\psi\rangle$ with her half of the Bell pair, and then makes a measurement (Bell basis measurement)
* She obtains one of four classical results 00, 01, 10 or 11 and sends this information to Bob
* Depending on Alice’s classical message, Bob performs one of four operations on his half of the EPR pair
* This recovers the state $|\psi\rangle$!

## A step-by-step explanation
```{figure} /_static/teleport.png
:scale: 40%
:name: teleport 

The quantum teleportation circuit
```
Given Alice's qubit $|q_0\rangle$, we wish to transfer this state to Bob's $|q_2\rangle$. 

### Prepare the Bell Pair
First a third party, Eve, creates an entangled pair and gives one of the qubits in this pair to Alice and the other qubit in this entangled pair to Bob. 
Let's refer back to our diagram from the section on entanglement.
```{figure} /_static/entangle-t.png
:scale: 40%
:name: entangle-t 

Creation of a Bell Pair

```

### Teleport
Now, we start with $|q_0\rangle$ in the state $|0\rangle$. $|q_1\rangle$ and $|q_2\rangle$ represent the entangled pair 

$$

|\psi_1\rangle = |0\rangle \frac{|00\rangle + |11\rangle}{\sqrt 2}

$$

Applying the CNOT gate between $|q_0\rangle$ and $|q_1\rangle$, we observe no change since the source qubit is in the state $|0\rangle$

$$

|\psi_1\rangle =  \frac{|000\rangle + |011\rangle}{\sqrt 2} \\
CNOT(|\psi_1\rangle) = \frac{|000\rangle + |011\rangle}{\sqrt 2}

$$

Now we apply the Hadamard gate to this state to get

$$

H(CNOT(|\psi_1\rangle)) = H(\frac{|000\rangle + |011\rangle}{\sqrt 2}) \\
|\psi_2\rangle = \frac{|000\rangle + |100\rangle}{2} +  \frac{|011\rangle + |111\rangle}{2}
$$

At this point, we perform two measurements on $|q_0\rangle$ and $|q_1\rangle$.  
```{figure} /_static/teleport-eq.png
:scale: 30%
:name: teleport-eq

$|\psi_2\rangle$ before measurement

```

We can see from the figure and the equation that there are 4 possibilities for $|q_0\rangle$ and $|q_1\rangle$.  From the circuit diagram we see that there there are two more gates after measurement, the Controlled-NOT and Controlled-Z gate, that are applied onto Bob's $|q_2\rangle$. Note that $|q_0\rangle$ and $|q_1\rangle$ get destroyed upon measurement giving us two classical bits $c_1$ and $c_2$.

The controlled gates at the end are there to apply the corresponding (NOT/X and Z) gates only if either or both of $|q_0\rangle$ and $|q_1\rangle$ are 1 resulting in the following table. Note that X and NOT are used here interchangeably. 

```{figure} /_static/teleport-results.png
:scale: 50%
:name: teleport-results

When to apply the controlled-NOT and controlled-Z gates.
```





```{admonition} Exercise: Practice with different states
:class: tip

1. Start with the state $|q_0\rangle = |1\rangle$ (Alice). What is the resulting $|q_2\rangle (Bob), after the circuit is run?
1. Start with the state $|q_0\rangle = \frac{|0\rangle + |1\rangle}{\sqrt 2}$. What is the resulting $|q_2\rangle (Bob), after the circuit is run?

```

```{admonition} Bonus Exercise
:class: tip

1. Start with the state $|q_0\rangle = \alpha|0\rangle + \beta|1\rangle$. What is the resulting $|q_2\rangle (Bob), after the circuit is run?

```