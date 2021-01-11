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

(pennylane2)=
# PennyLane II: Entanglement
In this section, we will create a quantum circuit that entangles two qubits. 

## Setup
Let's start with our usual setup by importing the necessary libraries

```{code-cell} ipython3
import pennylane as qml
from pennylane import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```
## Create a device with two qubits

```{code-cell} ipython3

dev = qml.device("default.qubit", wires=2)

```
## Create the entanglement circuit

The entanglement circuit involving applying the Hadamard gate to the first qubit followed by the CNOT gate with the second qubit as the target qubit.

```{code-cell} ipython3

@qml.qnode(dev)
def entanglement():
    # Prepare q1
    qml.Hadamard(wires=0)
    qml.CNOT(wires=[0, 1])
    
    return qml.probs(wires=[0, 1])

```
## Run the circuit

```{code-cell} ipython3

entanglement()
```
`array([0.5, 0. , 0. , 0.5])`  



## Visualize Results
Since we have two qubits it can be in one of four states. 


```{code-cell} ipython3
states = ['00', '01', '10', '11']
probs = entanglement()

plt.figure()

plt.bar(states, probs)
plt.xlabel('State', fontsize=18)
plt.ylabel('Probability', fontsize=16)

```

```{figure} /_static/probs-2.PNG
:scale: 100%
:name: probs-2 
Results of `entanglement()` visualized using matplotlib

```
The results show that the qubits cannot be in the state $|01\rangle$, $|10\rangle$ and the probability of finding both qubits in state 00 is 0.5 and the probability of finding the qubits in 11 is 0.5 showing that we have indeed achieved an entangled state. 

## More Code
```{admonition} Exercise: Test with other initial states
Try to create entanglement states with other starter states such as $|01\rangle$, $|10\rangle$, $|11\rangle$. Tip: You can flip the qubit by using the `qml.PauliX()` gate.

```

## Further reading

[PennyLane documentation](https://pennylane.readthedocs.io/en/stable/introduction/circuits.html) provides more information about creating quantum nodes and circuits.