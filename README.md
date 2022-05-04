# composite-ai
Theoretical model for composite AI capable of problem-solving beyond simple unsupervised learning

## Background
### Existing Models
One type of machine learning model consists of:
* an environment that provides inputs
* to a neural network capable of producing outputs
* and a fitness function that measures how "good" the outputs are at achieving a certain goal
Through many training cycles, the neural network becomes trained in how to produce a set of outputs that maximizes fitness function over all possible inputs.

Applications of this model include driving race cars around a track, or learning to play a game against another player.

This model of machine learning is fairly easy to implement and well understood, but also has some limitations:
* A large number of training cycles are needed and the network's only means of learning is brute-force trial and error
* A trained neural network is capable of producing the best or correct output, but is is not generally possible to inspect the network to determine how or why it arrived at the answer it did. This means it is not possible to reverse engineer concrete rules that would accurately describe the behavior of the network. The ability to determine such rules means that humans could learn from and expand on what the network had discovered trough trial and error in its training

### Questions
This leads to the following questions:
1. Can we improve upon this model to produce one that *is* capable of giving us a set of concrete rules that define its behavior?
2. Can we create a model that is capable of creating its own algorithms to follow and learn to refine those models over time?
3. Can such a model create its own structured plans for knowledge acquisition and learn that will allow for faster training that the brute-force training involved in the unsupervised training of a neural network?

### Human Brain
We can seek inspiration for a such a model in some of the features of the human brain.

The human brain seems to have the following (non-exhaustive list of) components:
* Executive function
  * prefrontal lobe
  * capable of following explicitly-defined rules, including algorithms
  * most like a virtual machine
* Inferencing and ideation
  * grey matter
  * an automatic associative engine, capable of producing a set of weighted ideas or associations, based on the current set of inputs or recent inputs
  * this network can be trained to quickly produce the correct outputs for a given set of inputs
  * most like a neural network
* Memory
  * Working memory - a small (4-6) number of "chunk" (human brain atoms of thought), used when doing computations or following algorithms
    * Tied most closely to and used by the execution function
  * Short-term memory - a memory of recent inputs, experiences and actions
    * Appears to be cleared during sleep as these memories are transferred into long-term memory
  * Long-term memory - a permanent memory of past experiences
    * Likely a result of permanent connections made in the grey matter

# Model
## Overview
We propose the following model for machine learning:
* EF - executive function and virtual machine
* NA - neural network
  * input 1 - current state of environment
  * input 2 - desired state of the environment
  * output - action to take
* NB - neural network
  * input 1 - current state of environment
  * input 2 - desired state of the environment
  * output - procedure identifier
* RCE - rule chaining engine
  * graph traversal algorithm that chains discovered rules in order to formulate new procedures that could hypothetically achieve a desired new environment state
* EM - Experience Memory
  * record of all single interactions with the environment - tuples of the form [precondition, action, postcondition]
   * i.e. given a current state of the environment [precondition] and an action taken [action], what new environment state resulted [postcondition]?
* PM - Procedure Memory
  * record of all procedures that D has produced and have been validated as correct through execution and interaction with the environment

At a high level, NA and NB act as a recommendation engines, feeding their outputs to EF.

B answers the following question:
* Given the current state of the environment (input 1) and a desired new state of the environment (input 2), what single action should be followed (output 1) in order to achieve a desired next state?
B is trained based on recorded past single interactions with the environment (i.e. ?)

C answers the following question:
* Given the current state of the environment (input 1) and a desired new state of the environment (input 2), what procedure (output 1) should be followed in order to achieve the desired new state?
C is trained based on the set of validated procedures (see below)

EF operates in one of the following modes:
* Exploration - takes the next action recommended by NA
  * The purpose is to:
    * explore the environment in a non-structured way
  * this mode is used early on in the learning process to generate experiences
* Procedure execution for validation
  * Procedure is a non-validated procedure produced by RCE
  * The purpose is to:
    * validate the correctness of a hypothesized procedure not yet tested
    * explore the environment in a structured manner in order to answer specific questions about it
* Procedure execution for goal achievement
  * Procedure is a validated procedure recommended by NB
  * The purpose is to:
    * directly achieve a goal

As the model interacts with its environment, the model explicitly remembers its experiences (EM) and uses those experiences to train the neural networks during a "sleep" phase, or in the background.

## Goals
The goal of the model described here is to produce a machine intelligence that can:
  * infer rules for how the environment functions (learning)
  * follow a directed algorithm for environment exploration and self-training
  * infer potential solution paths based on previous learning (innovation)
    * this can allow for faster future learning attempts through rule chaining and environment-validated inferencing
  * create procedures for itself to follow to directly achieve specific desired states in the environment, which have not been specifically encountered before within the training set (executive control)

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
* When a sufficient amount of exploration has been done, NB will begin producing recommendations for new rules to validate or procedures to execute to achieve the stated goal.
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
