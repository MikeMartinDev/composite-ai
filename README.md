# composite-ai
Theoretical model for composite AI capable of problem-solving beyond simple unsupervised learning

## Background
* Many models for machine learning within an unsupervised environment are based on simulated annealing algorithms
  * The physical model is usually a neural network
  * Training such models requires an enormous number of training samples or cycles in order to achieve optimal results
  * These models could not be called true "problem solving", but rather unsupervised discover of an optimal function that can transform inputs to outputs

## Goals
* The goal of the model described here is to produce a machine intelligence that can:
  * infer rules for how the environment functions (learning)
  * follow a directed path for environment exploration and self-training, based on inferring potential solution paths based on previous learning (innovation)
    * this can allow for faster future learning attempts through rule chaining and environment-validated inferencing
  * create procedures for itself to follow to directly achieve specific desired states in the environment, which have not be specifically encountered before within the training set (executive control)

## Model Overview
This model is based on how the human brain works, where the prefrontal lobe performs executive function in conjunction with other parts of the brain that perform fast, automatic processing

The model consists of these components:
* A - executive function
* B - fast associative processing
* C - memory

## A - Executive Function
* follow procedures
* follow rules explicitly defined

### Modes
#### Exploration


#### Procedure Execution and Validation


## B - Associative Processing


## C - Memory
* Stores definitions for rules and procedures
* Stores memory of what happened in the environment under various conditions, so that rules can be constructed from this
* repetition of actions/procedures can train B

## Rote Programming
The real system would contain some rote programming - that is, the system is pre-trained or explicitly programmed, rather than learning these aspects.
* Goal definition and progress scoring - for a giving environment, a function that defined whether the AI has achieved the end goal (true/false) or a value function that scores the current state of the environment based on how close the AI is to achieving the goal

Copyright 2022 Mike Martin 
