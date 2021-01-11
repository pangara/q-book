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

(measurement)=

# Measurement

We now move from the quantum realm to the classical realm. A measurement is essentially an operation on a qubit to get some classical information. This is because one cannot look at quantum information, it is hidden. Whatever state the qubits are in, they resolve to 0 or 1 on measurement. To understand more about measurement, one needs to know the postulates of quantum mechanics. These provide a mathematical framework for describing everything from quantum states to our universe. Postulates are beyond the scope of this introductory tutorial, however, a great resource is [Quantum Country](https://quantum.country/qm).

For now, we will think of measurement as a probability and stick to the computational basis. 

```{figure} /_static/measurement-highlight.png
:scale: 40%
:name: measurement-highlight 

Part of the quantum teleportation diagram with the qubits, gates, and measurements highlighted.
```

## A guessing game

```{figure} /_static/box.png
:scale: 50%
:name: box 

A black box: Can you guess how many are pink and how many are grey?
```


* The box has 50 balls colored pink and grey.

* How many of these are pink, and how many are grey? 

* Can you make a guess?  

We can look a ball out one at a time and see what color it is. If we pick pink the first time, it doesn't give us an idea about the rest of the balls. However, if we keep picking up more and more balls, we start to get an idea - it could be 25% pink, 75% grey, or 50% pink and 50% grey or 100% pink. 

## Qubit Measurement
Quantum states are very similar. The possibility of measuring a qubit to be in the state $|0\rangle$ or $|1 \rangle$ is based on the values of $\alpha$ and $\beta$ called the probability amplitudes. 
Given a state $ |\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle $, the probability of finding the qubit in state  $|0\rangle$ is $|\alpha|^2$ and the probability of finding the qubit in state  $|1\rangle$ is $|\beta|^2$.
Measuring a qubit destroys the state that it was in resulting in a classical 0 or 1. 


```{admonition} Exercise: Measurement
:class: tip

1. Given a state $ |\psi\rangle~= \frac{1}{\sqrt 2}~|0\rangle-~\frac{1}{\sqrt 2}~|1\rangle $, what is the probability of finding the qubit in state $|0\rangle$ ? Hint: probabilities are always positive and have a value between 0 and 1.

2. Given a state $ |\psi\rangle~= \frac{12}{13}~|0\rangle+~\frac{5}{13}~|1\rangle $, what is the probability of finding the qubit in state $|1\rangle$ ? 

3. Given a state $|\psi\rangle~= -|1\rangle$, what is the probability of finding the qubit in the state $|0\rangle~$ ? 
```
