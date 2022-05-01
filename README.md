# composite-ai
Theoretical model for composite AI capable of problem-solving beyond simple unsupervised learning

## Background
* Machine learning models are often based on neural networks are often used for implementing unsupervised learning within structured environments
* Unsupervised training for such models requires a large number of training cycles as the the model interacts with the environment, failing over and over until its neural network weights have been optimized to produce the best results within that environment
* While this type of model simulates what happens in the human brain from a learning standpoint, it has some drawbacks:
  * as mentioned above, the training requires a large amount of cycles before the model can achieve acceptable results
  * when fully trained, the model is capable of achieving good results, but moving the model to a different environment may significant decrease its performance, depending on how similar the new environment is to the old one
  * the model is opaque - it is not generally possible to extract the "knowledge" that the model has learned or inspect the reasons for why it produces the results it does
* This type of model cannot be said to be doing any kind of "thinking" or deductive reasoning - it is only a function capable of producing a specific set of outputs based on its inputs

## Goals
* The goal of the model described here is to produce a machine intelligence that can:
  * infer rules for how the environment functions (learning)
  * follow a directed algorithm for environment exploration and self-training
  * infer potential solution paths based on previous learning (innovation)
    * this can allow for faster future learning attempts through rule chaining and environment-validated inferencing
  * create procedures for itself to follow to directly achieve specific desired states in the environment, which have not been specifically encountered before within the training set (executive control)

## Model Overview
This model is based on how the human brain is structured, where the prefrontal lobe performs executive function in conjunction with other parts of the brain that perform fast, automatic, associative processing.

The model consists of these components:
* A - executive function
* B - inferencing and ideation
* C - memory

## Rules
A rule contains the following parts:
* Preconditions - a given state of the environment
* Action - an action taken by the model or an event that happens in the environment
* Postconditions - an expected state of the environment after the action occurs

A rule is said to be valid if expresses a true attribute of the environment, named that "when the environment has state (preconditions) and action is taken, then the environment will have state (postconditions)."

## Procedures


## A - Executive Function
* follow procedures
* follow rules explicitly defined
* validate ideas presented by B

### Modes
#### Exploration
During this mode, the model takes actions to further explore and learn about its environment.

Exploration follows these steps:
1. Snapshot (record) current state of the environment (pre-conditions)
2. Take an action (random or as directed by B)
3. Snapshot state of environment after action (post-condition)
4. Formulate rule and write it to memory
5. Repeat until triggered to move to Procedure Execution and Validation mode

#### Procedure Execution and Validation
During this mode, the model follows a defined procedure, either for the purpose of achieving a goal or for validating whether a proposed procedure achieves the anticipated results.

Procedure execution follows these steps:
1. Check preconditions - verify that current state of environment matches the preconditions defined for the first step of the procedure
2. Take the action defined for the current step of the procedure
3. Check postconditions - verify that the state of the environment matches the postconditions defined for the current step of the procedure
  * If the postconditions to not match, abort the procedure and mark the current step of the procedure as invalid
  * Also add a new rule that links the precondition of the current step action to the actual environment state as a postcondition
4. If postconditions do match, continue to the next step of the procedure and go to step 2 above (it is assumed here that the postconditions of a procedure step always match the preconditions of the next step in a procedure)
5. If an entire procedure completes successfully, mark the procedure and all its steps as valid. The procedure is added to the set of known reliable procedures that can be used to achieve goals.

> Future: When a step or procedure fails, instead of marking it as a boolean valid/invalid, its "truthfulness" or "reliability" score is decreased; when it succeeds, it is increased. This score then acts as a weight for B selecting procedures in the future for exploration or for execution to achieve goals.

#### Choosing Modes
* By default, the model uses the exploration mode, with random selection of action.
* When a sufficient amount of exploration has been done, B will begin producing recommendations for new rules to validate or procedures to execute to achieve the stated goal.
* When no the queue of recommended procedures is empty, the model reverts to exploration mode.

## B - Ideation


## C - Memory
* Stores definitions for rules and procedures
* Stores memory of what happened in the environment under various conditions, so that rules can be constructed from this
* repetition of actions/procedures can train B

## Rote Programming
The real system would contain some rote programming - that is, the system is pre-trained or explicitly programmed, rather than learning these aspects.
* Goal definition and progress scoring - for a giving environment, a function that defined whether the AI has achieved the end goal (true/false) or a value function that scores the current state of the environment based on how close the AI is to achieving the goal


# Testing Environment
In order to validate and test this model, we need an environment in which to test it. We choose the following environment:
* A grid of cells, sized N (width) x M (height)
* Each cell can be one of the following:
  * Empty
  * Player marker - can be moved by taking directional actions
  * Goal position
  * Moveable obstacle
  * Immoveable obstacle
  * Hazard
  * Gate
  * Gate toggle


Copyright 2022 Mike Martin
