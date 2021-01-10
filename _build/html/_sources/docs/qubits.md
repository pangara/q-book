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

(qubits)=

# Basics
In this section, we will go over what qubits are, how qubits are represented, and the dirac notation
## Qubits

A qubit or a quantum bit is a unit of quantum information. Unlike a classical bit which can be 0 or 1, quantum mechanics allows qubits to be in a superposition of both states 0 and 1. We will learn more about superposition soon, but it can be thought of as a combination of 0 and 1. 
A bloch sphere shows us one representation of a qubit and is shown in the figure below.

```{figure} /_static/bloch.png
:scale: 50%
:name: bloch 

Bloch Sphere
```

You can see that the 0 and 1 are wrapped in a pipe/angle bracket notation - this is the dirac notation. 

## Dirac Notation

The Dirac Notation, also called the Braket notation is a simple way of representing vectors.

A column vector is called a ket and is represented in the following way: 
$|a\rangle = \begin{bmatrix}
           a_{1} \\
           a_{2} \\
           \vdots \\
           a_{n}
         \end{bmatrix}$

A row vector is called a bra and is represented in the following way: 
$\langle a| = \begin{bmatrix}
           a_{1}* &
           a_{2}* & 
           \dots &
           a_{n}*
         \end{bmatrix}$

A ket can be converted into a bra by performing a complex conjugate on each of the elements and then performing a transpose. 
## Refresher
### Complex conjugates

Given a complex number $x = 3 + 2i$, 

Its complex conjugate will be $x{*} = 3 - 2i$
Perform a complex conjugate again,
$x^{**} = 3 + 2i$

### Transpose
Given a row vector $ c = \begin{bmatrix}
           3 &
           2 
         \end{bmatrix}$

Here is its transpose: $ c = \begin{bmatrix}
           3 \\
           2 
         \end{bmatrix}$
### Dot product
A description of dot products will go here if required.

## Converting between Bras and Kets
Now that we understand how complex conjugates and transposes work, lets do some exercises converting between bras and kets. 

### Exercise 1
Convert the following bras into kets.

$$ 
\langle x| = \begin{bmatrix}
           3 &
           2 & 
           1
         \end{bmatrix} 
$$

$$ 
\langle y| = \begin{bmatrix}
           3 + 2i &
           2 - i & 
           1
         \end{bmatrix} 
$$

### Exercise 2
Convert the following kets into bras.

$$ 
|u\rangle = \begin{bmatrix}
           1 \\
           0 
         \end{bmatrix} 
$$

$$ 
|u\rangle = \frac{1}{\sqrt 2}\begin{bmatrix}
           1 \\
           i 
         \end{bmatrix} 
         
$$

## Qubits in the Dirac notation


Let's take a look at the Bloch spehere again.

The north and south poles are given by $|0\rangle$ and $|1\rangle$. We now know what the symbols mean - $|0\rangle$ and $|1\rangle$ are vectors! 
It's important to remember here that 0 is very much different from $|0\rangle$ and 1 is very much different from $|1\rangle$.
$|0\rangle$ is given by 

$$

|0\rangle = \begin{bmatrix}
           1 \\
           0
         \end{bmatrix} 
$$ 

and $|1\rangle$ is given by 

$$

|u1\rangle = \begin{bmatrix}
           0 \\
           1
         \end{bmatrix} 
$$
 
## A quantum state

The bloch sphere does not only represent the states $|0\rangle$ and $|1\rangle$, but can also represent a variety of states on the sphere. Think of the bloch sphere as a balloon. Every point on the balloon is a valid quantum state and is a combination of $|0\rangle$ and $|1\rangle$. We can write down an arbitrary state $|\psi\rangle$ as follows:

$$

|\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle

$$

where 

$$

\sqrt{|\alpha|^2 + |\beta|^2 } = 1 

$$

In vector notation we can write this as:

$$

|\psi\rangle~= \alpha~\begin{bmatrix}
           1 \\
           0
         \end{bmatrix} +~\beta~\begin{bmatrix}
           0 \\
           1
         \end{bmatrix} 
$$

In short, 

$$

|\psi\rangle~= \begin{bmatrix}
           \alpha \\
           \beta
         \end{bmatrix} 
$$

Given the following state: 

$$ 

|\psi>~= \frac{1}{\sqrt 2}|0\rangle+~\frac{1}{\sqrt 2}|1\rangle

$$

We calculate $ \sqrt{|\alpha|^2 + |\beta|^2} $ to check whether it sums up to 1. 

$$

\sqrt{(\frac{1}{\sqrt 2})^2 + (\frac{1}{\sqrt 2})^2} = \sqrt{\frac{1}{2} + \frac{1}{2}} = 1

$$

```{note}
You must also wonder about the angles on the bloch sphere $ \phi $ and $ \theta $. You can use these angles to represent the state $ |\psi\rangle $ as $ |\psi\rangle = cos \frac{\theta}{2}|0\rangle +  e^{i\phi}sin \frac{\theta}{2}|1\rangle $. This is important, but we will not discuss this in the scope of this tutorial

```
### Exercise 3
Verify whether the following are valid quantum states or not. 

2. $ |\psi>~= \frac{1}{4}|0>+~\frac{3}{4}|1> $

3. $|\psi>~= \frac{12}{13}|0>+~\frac{5}{13}|1>$

4. $|\psi>~= \frac{4}{5}|0>+~\frac{2}{5}|1> $



## Superposition

Superposition is defined as a combination of the states of $|0\rangle$ and $|1\rangle$, therefore $|\psi\rangle~= \alpha~|0\rangle+~\beta~|1\rangle$ is a superposition state. 
The state we look at before $ |\psi>~= \frac{1}{\sqrt 2}|0>+~\frac{1}{\sqrt 2}|1>  $ is also a superpostion state. Moreover, since the value of $\alpha$ and $\beta$ are the same, we can say that the state is in an equal superposition of $|0\rangle$ and $|1\rangle$. In classical computing we are always manipulating zeros and ones to get what we want. You must wonder how we get from one state to another quantumly because at the end of the day, we want to perform a computation quantumly! This is where gates come in, and are the topic of discussion in the next section.
