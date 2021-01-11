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

(motivation)=

# Motivation

```{figure} /_static/xkcd.png
:scale: 70%
:name: xkcd 

A relevant xkcd comic on quantum teleportation. 
```

Teleportation of humans and objects has been the subject of fascination for all of us since a very long time. One of the first examples of teleportation in literature were in an 1897 novel called [To Venus in Five Seconds by Fred T. Jane](https://en.wikipedia.org/wiki/To_Venus_in_Five_Seconds).  

In this tutorial, we won't discuss this kind of teleportation but we will discuss Quantum Teleportation, which is a scheme for the transfer of quantum information, which is _almost_ as cool as the teleportation of matter.

In 1993, Bennett et al.,{cite}`bennett1993teleporting` showed that quantum teleportation was actually possible using the rules of quantum mechanics, and has since been followed by [experiments that demonstrate quantum teleportation](https://news.fnal.gov/2020/12/fermilab-and-partners-achieve-sustained-high-fidelity-quantum-teleportation/).

Quantum Teleportation is not only cool, but also has important implications to quantum computing, quantum communication, and also interestingly to quantum hardware too~{cite}`Pirandola_2015`. 

## Quantum Teleportation
```{figure} /_static/teleport.png
:scale: 40%
:name: teleport 

The quantum teleportation circuit in full. 
```

Quantum Teleportation is a technique for transferring quantum information from a source to a destination far away. The quantum teleportation circuit shown in the figure above has many components which we will discuss in detail in the next few sections. I introduce it here is so that you know what to expect from this tutorial. By the end of this tutorial, you will learn all the symbols used here and what they mean in the context of quantum computing.

**Let's begin our journey!**