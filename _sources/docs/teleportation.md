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



