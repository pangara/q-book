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

(pennylane3)=
# PennyLane III: Teleportation 
We are finally ready to create and run the teleportation circuit using PennyLane. We have to do the following after setup:
1. Create a device with three wires
2. Prepare the first qubit in some desired state
2. Eve: Prepare a bell pair between the second and third qubit.
2. Alice: Perform CNOT between the first and second qubit, followed by a Hadamard
3. **Measure the first and second qubit**
4. **Apply the controlled-Z and controlled-NOT gates to the first and second measured qubits.** 

```{admonition} But wait!
:class: warning
A measurement has to be the last part in a quantum circuit in PennyLane, i.e., we cannot perform partial measurements. Fortunately, the [Principle of Deferred Measurement](https://en.wikipedia.org/wiki/Deferred_Measurement_Principle) comes to our rescue. This is a result in quantum computing which states that delaying measurements until the end if a quantum computation does not affect the probability distribution of the outcomes. Therefore, we can swap the last two steps without affecting our results. 
```


## Setup
Let's start with our usual setup by importing the necessary libraries

```{code-cell} ipython3
import pennylane as qml
from pennylane import numpy as np
```
## Create a device with three qubits

```{code-cell} ipython3

dev = qml.device('default.qubit', wires=3)

```
## Create the teleportation circuit


```{code-cell} ipython3

@qml.qnode(dev)
def teleportation():

    # Alice: Prepare q1
    # We do nothing here to send the |0> qubit

    # Eve: Prepare q2 & q3 in the bell state
    qml.Hadamard(wires=1)
    qml.CNOT(wires=[1, 2])
    
    # Alice
    qml.CNOT(wires=[0, 1])
    qml.Hadamard(wires=0)
    
    qml.CZ(wires=[0, 2])
    qml.CNOT(wires=[1, 2])

    return qml.probs(wires=[0, 1, 2])

```

## Run the circuit

```{code-cell} ipython3

teleportation()
```
`array([0.25, 0.  , 0.25, 0.  , 0.25, 0.  , 0.25, 0.  ])`  



## Visualize Results
Since we have three qubits it can be in one of eight ($2^3$) states. Here we focus on the third qubit. 


```{code-cell} ipython3
states = ['00', '01', '10', '11']
probs = entanglement()

plt.figure()

plt.bar(states, probs)
plt.xlabel('State', fontsize=18)
plt.ylabel('Probability', fontsize=16)

```

```{figure} /_static/probs-3.PNG
:scale: 100%
:name: probs-3
Results of `teleportation()` visualized using matplotlib

```
If you look closely at the results, the probability bars only show up when the third qubit is 0. The probability of getting a 1 for the third qubit is 0. 

## More Code
```{admonition} Exercise: Send other states
Interpret the results when Alice sends the following states:
1. $|1\rangle$
2. $\frac{|0\rangle + |1\rangle}{\sqrt 2}$

```

## Further reading

[PennyLane documentation](https://pennylane.readthedocs.io/en/stable/introduction/circuits.html) provides more information about creating quantum nodes and circuits.