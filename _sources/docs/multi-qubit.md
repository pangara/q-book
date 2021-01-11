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

(multi-qubit)=

# Multiple Qubit Systems and Gates
A qubit as we know is a single unit of quantum computation, and is represented by a vector with  $ |0\rangle = \begin{pmatrix} 1\\ 0 \end{pmatrix}$ and $|1\rangle = \begin{pmatrix} 0\\ 1 \end{pmatrix}$. As the number of qubits increases, we have to take into account a combined system of qubits. Qubits combine via tensor products. 

```{figure} /_static/multi-qubit-highlight.png
:scale: 40%
:name: multi-qubit-highlight 

Part of the quantum teleportation diagram with the qubits, single qubit gates, two-qubit gates, and measurement highlighted.
```

## Tensor Products
Tensor products are different from regular  matrix multiplication, such that the resulting matrix has a higher dimension than the matrices we started out with. Tensor products work by multiplying every element of one matrix with every other element of the other matrix.







## Combining qubits

Let's create a two qubit system. 

$$

|0\rangle \otimes |0\rangle = \begin{bmatrix}1 \\0\end{bmatrix} \otimes \begin{bmatrix}1 \\0\end{bmatrix} = \begin{bmatrix}1\begin{bmatrix}1 \\0\end{bmatrix} \\0\begin{bmatrix}1 \\0\end{bmatrix}\end{bmatrix} = \begin{bmatrix}1 \\0 \\ 0 \\ 0 \end{bmatrix}
$$

```{admonition} Exercise 1
:class: tip

Given that we have two single qubit quantum systems with the following states, lets combine them via a tensor product. 

$$

|\psi> = \alpha_1|0> + \beta_1|1> \\
|\phi> = \alpha_2|0> + \beta_2|1>

$$

```

```{admonition} Solution to Exercise 1
:class: tip

$$
|\psi> \otimes |\phi> = (\alpha_1|0> + \beta_1|1>) \otimes (\alpha_2|0> + \beta_2|1>) 
$$

$$
|\psi> \otimes |\phi> = 
(\alpha_1\begin{bmatrix}1 \\0\end{bmatrix}
 + \beta_1\begin{bmatrix}0 \\1\end{bmatrix})
 \otimes 
(\alpha_2\begin{bmatrix}1 \\0\end{bmatrix} 
+ \beta_2\begin{bmatrix}0 \\1\end{bmatrix}) 
$$

$$

|\psi> \otimes |\phi> = 
\alpha_1\alpha_2\begin{bmatrix}1 \\0\end{bmatrix}\otimes\begin{bmatrix}1 \\0\end{bmatrix}
+
\alpha_1\beta_2\begin{bmatrix}1 \\0\end{bmatrix}\otimes\begin{bmatrix}0 \\1\end{bmatrix}
+
\beta_1\alpha_2\begin{bmatrix}0 \\1\end{bmatrix}\otimes\begin{bmatrix}1 \\0\end{bmatrix}
+
\beta_1\beta_2\begin{bmatrix}0 \\1\end{bmatrix}\otimes\begin{bmatrix}0 \\1\end{bmatrix} 
$$

$$
|\psi> \otimes |\phi> = 
\alpha_1\alpha_2\begin{bmatrix}1 \begin{bmatrix}1 \\0\end{bmatrix}\\0\begin{bmatrix}1 \\0\end{bmatrix}\end{bmatrix}+
\alpha_1\beta_2\begin{bmatrix}1 \begin{bmatrix}0 \\1\end{bmatrix}
 \\0 \begin{bmatrix}0 \\1\end{bmatrix}
\end{bmatrix}+
\beta_1\alpha_2\begin{bmatrix}0 \begin{bmatrix}1 \\0\end{bmatrix} \\1\begin{bmatrix}1 \\0\end{bmatrix}\end{bmatrix}
+
\beta_1\beta_2\begin{bmatrix}0 \begin{bmatrix}0 \\1\end{bmatrix}
 \\1\begin{bmatrix}0 \\1\end{bmatrix}
\end{bmatrix} 

$$

$$

|\psi> \otimes |\phi> = 
\alpha_1\alpha_2\begin{bmatrix}1 \\ 0 \\0 \\0\end{bmatrix}+
\alpha_1\beta_2\begin{bmatrix}0 \\1\\ 0 \\ 0\end{bmatrix}+
\beta_1\alpha_2\begin{bmatrix}0 \\ 0 \\ 1 \\ 0\end{bmatrix}
+
\beta_1\beta_2\begin{bmatrix}0 \\0 \\0 \\1\end{bmatrix}


$$


$$
|\psi \phi> = \alpha |00> + \beta|01> + \gamma |10> + \delta |11>
$$


```

## States in a two qubit system
When we have two quantum states in the same systems, the qubit can be in one to all of the following states $|00\rangle$, $|01\rangle$, $|10\rangle$, $|11\rangle$.



$$

|\psi\rangle~= \alpha~|00\rangle+~\beta~|01\rangle+~\gamma~|10\rangle+~\delta~|11\rangle\\
|\alpha|^2 + |\beta|^2 + |\gamma|^2 + |\delta|^2  =1

$$


 As the number of qubits increases, the number of states it can be in also increases. In general with an $n$-qubit system, you can have $2^n$ states. 


## CNOT Gate


```{figure} /_static/cnot.png
:scale: 30%
:name: x-gate 

The CNOT gate
```


Now that we know how to create a two-qubit system, we can work woth a two qubit gate. For this tutorial, we will go over the CNOT gate. 
The CNOT gate is given by the matrix:

$$
U = \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
\end{pmatrix}
$$

The CNOT gate flips the second qubit if the first qubit is 1, and leaves the second qubit as it id if the first qubit is 0. THe first qubit remains unchanged. 
Suppose we are given a state $|11\rangle$, applying the CNOT gate changes this state to $|10\rangle$. If we were given a superposition state:

$$
|\psi\rangle~= \alpha~|00\rangle+~\beta~|01\rangle+~\gamma~|10\rangle+~\delta~|11\rangle
$$

Applying the CNOT gate would give us:

$$
CNOT|\psi\rangle~=  \alpha~|00\rangle+~\beta~|01\rangle+~\gamma~|11\rangle+~\delta~|10\rangle
$$




```{admonition} Exercise 2
:class: tip

Given the matrix representation of the CNOT gate, verify that:

$$
CNOT|\psi\rangle~=  \alpha~|00\rangle+~\beta~|01\rangle+~\gamma~|11\rangle+~\delta~|10\rangle
$$

```
