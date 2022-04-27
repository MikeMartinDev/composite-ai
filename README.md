# composite-ai
Theoretical model for composite AI capable of problem-solving beyond simple unsupervised learning

## Background
* Most AI models to date for machine learning within an unsupervised environment are based on neural networks
* Training such models requires an enormous number of training cycles through random guessing and checking
* The goal of this model is to improve the training such that the AI can:
** infer rules for how the environment functions (learning)
** allowing faster and more refined future learning attempts (through rule chaining and environment-validated inferencing)
** create procedures for itself to follow to directly achieve specific desired states in the environment (executive control)
* This model is based on how the human brain works, where the prefrontal lobe performs executive function in conjunction with other parts of the brain that perform fast, automatic processing

## Model Overview
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
