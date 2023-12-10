# ManyBodyMEPS

## Overview
This repository provides python code and results for the paper <em>Multi-Excitation Projective Simulation, And A Many-Body Physics Inspired Inductive Bias</em> by Philip A. LeMaitre, Marius Krumm, and Hans J. Briegel.

## Projective Simulation and its many-body extension

<em>Projective Simulation</em>(PS) is a framework in eXplainable Artificial Intelligence (XAI). It models <em>chains-of-thought</em> as a random walk of one particle/excitation on a graph in which vertices represent concepts or memories. While this framework has been successfully applied to many domains, it does not directly capture concepts of thoughts that have a compositional nature. This includes thoughts that combine several memories to arrive at a new conclusion. 

As a solution to this issue, we developed <em>Multi-Excitation Projective Simulation</em>, an extension of PS that uses several particles/excitations instead of just one.

## Many-body physics inspired inductive bias
A direct implementation of MEPS without any restrictions on the graph and random walk steps would suffer from an exponential complexity. To reduce the complexity to a low-degree polynomial, we also developed an inductive bias inspired by quantum many-body physics. Our inductive bias classically mimics the time evolution of many-body quantum systems, and puts a cutoff on how many excitations can interact in a time step. 

The cutoff is motivated by the observation that most of modern physics can be understood as arising from fundamental interactions of just a handful of particles. We believe that this inductive bias will also perform in reinforcement learning problems. This belief is supported by the observation that also humans can only combine few concepts at a time, and are nonetheless very successful in many domains.

## Used packages
