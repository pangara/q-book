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

# Teleportation

The concepts of superposition and entanglement are what give quantum computing its power over classical computers. We have heard about teleportation, a miraculous form of transportation from one place to another. Quantum Teleportation has a slightly different meaning, it enables quantum states to be transported across long distances without a need to send it directly. {cite}`bennett1993teleporting`

## Problem Statement

* Alice has to send a qubit to Bob. 
* Alice and Bob have a pre-shared Bell State
* Alice can send only classical information to Bob
* lice doesn’t know the state of the qubit, even if she does, describing it would take infinite amount of classical information since qubits take value in a continuous space. 

## Solution
* Alice interacts $\psi$ with her half of the EPR pair, and then makes a measurement (Bell basis measurement)
* She obtains one of four classical results 00, 01, 10 or 11 and sends this information to Bob
* Depending on Alice’s classical message, Bob performs one of four operations on his half of the EPR pair
* This recovers the state $\psi$!



