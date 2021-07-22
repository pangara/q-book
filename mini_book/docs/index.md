# From Qubits to Quantum Teleportation

In this tutorial, we
1. focus on the basics of quantum computing that are necessary to understand quantum teleportation and 
2. explain the quantum teleportation algorithm.

We chose quantum teleportation because it is one of the core primitives of quantum computing and keeps popping up in popular science articles. 
This tutorial has been built in the form of an interactive textbook using [Jupyter Books](https://jupyterbook.org/intro.html). 

## Learning Outcomes
By the end of this tutorial, you will:

* learn about single qubit systems and multi-qubit systems, their mathematical representation 
* learn about the mathematical explanations of superposition and entanglement
* be able to manipulate quantum states using gates
* learn to write short quantum programs using Pennylane
* understand quantum teleportation mathematically
* learn how to build the quantum teleportation circuit
* implement the quantum teleportation circuit on Pennylane

## Medium
Since the content was to be designed for an online educational environment, after a lot of contemplation, we thought something in the style of Jupyter notebooks would be appropriate because one could share code, text, equations, and visualizations. Jupyter Textbooks seemed appropriate for this because of the following reasons:
1. They have all the advantages of Jupyter notebooks
2. They allow the addition of LaTeX-style math using MathJax and BibTeX files for references
3. They are open source (as a part of the [Executable Book Project](https://executablebooks.org/en/latest/))
4. They have a command-line interface to quickly build textbooks
5. They are easy to deploy with Github Pages/Actions

### PennyLane
While Pennylane is certainly suitable mostly for Quantum Machine Learning, I have chosen it as the library of choice for implementing the quantum teleportation algorithm, because 
1. it is possible to do so,
2. there are not many resources online on the basic algorithms of quantum computing using Pennylane, and 
3. it allows the reader to get a Hello World into PennyLane. 
  
## Audience

This tutorial is suitable for someone who is in high-school or first-year university and is curious to get started with quantum computing. Knowledge of quantum mechanics/physics or computer science is not required to understand this tutorial. Some basic linear algebra (matrices, vectors), complex numbers, and probability is useful to understand the concepts. There are some important concepts that we have skipped over, such as the postulates of quantum computing, eigenvalues and eigenvectors, beginner programming, etc. in the interest of keeping it a bit concise.  

```{note}
This repository is based on Scientific Python Quickstart: a short sequence of lectures on Python programming for scientific work, written by [Thomas J.  Sargent](http://www.tomsargent.com/) and [John Stachurski](https://johnstachurski.net/). This uses the new Sphinx-based [Jupyter Book 2.0](https://beta.jupyterbook.org/intro.html) toolset, as part of the [ExecutableBookProject](https://ebp.jupyterbook.org/en/latest/).  
Instructions for how to build them from source can be found in the Jupyter Book documentation.
```



