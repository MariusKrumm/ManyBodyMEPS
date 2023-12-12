# ManyBodyMEPS

## Overview
This repository provides python code and results for the paper <em>Multi-Excitation Projective Simulation, And A Many-Body Physics Inspired Inductive Bias</em> by Philip A. LeMaitre, Marius Krumm, and Hans J. Briegel.

The code in this package has been developed by Philip A. LeMaitre and Marius Krumm.

## Projective Simulation and its many-body extension

<em>Projective Simulation</em> (PS) is a framework in eXplainable Artificial Intelligence (XAI). It models <em>chains-of-thought</em> as a random walk of one particle/excitation on a graph in which vertices represent concepts or memories. While this framework has been successfully applied to many domains, it does not directly capture concepts of thoughts that have a compositional nature. This includes thoughts that combine several memories to arrive at a new conclusion. 

As a solution to this issue, we developed <em>Multi-Excitation Projective Simulation</em>, an extension of PS that uses several particles/excitations instead of just one.

## Many-body physics inspired inductive bias
A direct implementation of MEPS without any restrictions on the graph and random walk steps would suffer from an exponential complexity. To reduce the complexity to a low-degree polynomial, we also developed an inductive bias inspired by quantum many-body physics. Our inductive bias classically mimics the time evolution of many-body quantum systems, and puts a cutoff on how many excitations can interact in a time step. 

The cutoff is motivated by the observation that most of modern physics can be understood as arising from fundamental interactions of just a handful of particles. We believe that this inductive bias will also perform well in reinforcement learning problems. This belief is supported by the observation that also humans can only combine few concepts at a time, and are nonetheless very successful in many domains.

## Environments
To demonstrate the application of MEPS for explainable reinforcement learning, and provide numerical evidence for the resource savings provided by our inductive bias, we test MEPS in three synthetic environments:

* The <em>Invasion Game With Distraction</em>. The Invasion Game is a standard toy environment in the PS literature. Here, we extend it in two ways that allow to showcase the numerical properties of our inductive bias in a simple environment. The agent observes the values of three observables, each of them represented as an excitation. The agent has to pick one of two doors. The right choice depends non-trivially on the values of the first two observables. To map the combined information of the first two observables to the action, we need a MEPS agent who can consider at least two excitations simultaneously. Furthermore, the third observable is a useless distraction. MEPS agents that consider three excitations simultaneously are less efficient, because their random walk distinguishes between different values of the useless observable.
* The <em>Deceptive Invasion Game</em>. An extension of the above environment to include the possibility of the attacker lying about the door it will go through. 
* <em>Computer Maintenance</em>. The second environment models scenarios in which an agent observes symptoms of a malfunctioning computer, and has to take actions to repair the computer. We train a multi-layered MEPS agent to solve the environment. The hidden layer of the agent represents guesses of the agent about the cause of the symptoms. Therefore, this setting provides an example for a simple MEPS agent that uses chains-of-thought consisting of two thoughts to solve a problem.

## Used packages
* Pytorch v2.0.1
* Numpy v1.25.2
* Matplotlib v3.8.0
* Seaborn v0.12.2
