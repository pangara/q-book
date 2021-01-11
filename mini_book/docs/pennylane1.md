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

(pennylane1)=
# PennyLane I: Introduction

Now that we understand some of the basics of quantum computing we are ready to code!

```{admonition} Installation
:class: note

1. If you plan to run the code on your own machine, you need Python 3.6 or above. Recommended install: [Anaconda Python](https://www.anaconda.com/products/individual#download-section). 

2. [Install PennyLane](https://pennylane.readthedocs.io/en/stable/development/guide/installation.html)


```

## Setup 

Import the necessary libraries for our code to run PennyLane

```{code-cell} ipython3
import pennylane as qml
from pennylane import numpy as np
import matplotlib.pyplot as plt
%matplotlib inline
```

## Create a device
Create a device. `default.qubit` is a statevector simulator which allows us to simulate qubits. More about [qml.device here](https://pennylane.readthedocs.io/en/stable/code/api/pennylane.device.html). With the wires argument we can specify the number of qubits we are working with. 

```{code-cell} ipython3

dev = qml.device("default.qubit", wires=1)

```
## Create a circuit
Let's create our circuit. In PennyLane, quantum circuits are created as quantum functions. These quantum computations are represented as quantum node (QNode) objects. We create the QNodes with something called a qnode decorator. All you need to know about this for now is that you need to precede your function with `@qml.qnode(dev)`



```{code-cell} ipython3

@qml.qnode(dev) # the decorator
def quantum_circuit():
    # your circuit here

```
We need to populate this quantum circuit. Let's try out some gates.


```{code-cell} ipython3

@qml.qnode(dev) # the decorator
def quantum_circuit():
    # your circuit here
    qml.Hadamard(wires=0)
    qml.PauliX(wires = 0)
```

## Perform a measurement
There are different ways in PennyLane in which we can obtain our measurement outcome.  We will be using the `qml.probs()` function for this tutorial since we do need to know the probability of measuring all the different outcomes. PennyLane qnodes adhere to the rule that all measurements must be done at the end of the circuit and returned in the order of measurement. Since we have only one qubit, we measure it and return the value.

```{code-cell} ipython3

@qml.qnode(dev) # the decorator
def quantum_circuit():
    # Gates
    qml.Hadamard(wires=0)
    qml.PauliX(wires = 0)

    # Measurement
    m = qml.probs(wires=[0])
    return m
```

## Run the circuit
Let's see what we get when we run the circuit that we just created.

```{code-cell} ipython3
quantum_circuit()

```
`array([0.5, 0.5])`  
Since we have one qubit it can be in one of two states. The array has two values representing the probabilities of measuring 0 and 1 respectively. Since we applied the Hadamard gate, there is an equal probability of measuring (0.5) 0 or 1. 

## Visualize Results
We can visualize these results by using matplotlib which is a helpful library that helps us plot graphs.

```{code-cell} ipython3
states = ['0', '1']
probs = quantum_circuit()

plt.figure()

plt.bar(states, probs)
plt.xlabel('State', fontsize=18)
plt.ylabel('Probability', fontsize=16)

```

```{figure} /_static/probs-1.PNG
:scale: 100%
:name: probs-1 
Results of `quantum_circuit()` visualized using matplotlib

```

## More Code
```{admonition} Exercise: Create a system of two qubits
:class: tip

Create a circuit with two wires. To the first qubit apply the Hadamard gate. To the second qubit apply the X gate. Return the measurement probabilities for both qubits. If you cannot figure it out, don't worry! The next coding section has you covered.

```

## Further reading

[PennyLane documentation](https://pennylane.readthedocs.io/en/stable/introduction/circuits.html) provides more information about creating quantum nodes and circuits.