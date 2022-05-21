# Example of Following a Procedure to Achieve a Goal

## Terms
* LVC: Left visual cortex
* S1: System 1 (general)
* WM: Working memory
* S2: System 2

## Notation
System: inputs or query > outputs

## Example

Setup: Solving a long division problem

* See long division problem (10000 divided by 37)
 * LVC: sight > "Long division problem"
 * LVC: sight > Slot1: number, Slot2: number
  * LVC: (Slot1, what?) > "37"
  * LVC: (Slot2, what?) > "10000"
* S1: ("Long division problem", what can I do?) > "Solve it"
  * WM: (Goal: "Solve it") >
* S1: ("Long division problem", "Solve it") > (step 1: find smallest number on right larger than number on left)
  * WM: (Sub-goal: "Find smallest number on right larger than number on left") >
* S1: ("Find smallest number larger than another number", how?) > procedure: step 1: compare same number of digits
  * WM: (sub-goal: compare same number of digits)
* S1: (37, number of digits?) > 2
  * S1: (10000, 2 digits) > 10
    * WM: (tempR: 10) >
* WM: Slot1 > 37
  * S1: (10, 37, greater than?) > no
* S1: ("Find smallest number larger than another number", step 2, no) > choose one more digit
  * S1: (10000, 10, one more digit?) > 100
* S1: (100, 37, greater than?) > yes
  * ??: "Continue/end"
  * WM: (current numerator: 100)
* S1: ("Long division", "Solve it", step: number on right greater than left, next step) > find number of times number on left fits into number on right
* S1: (37, 100, how many times fits into?) > [don't know]
  * S2: "Okay, then I need to figure it out"
* S1: (how many times a number fits into another, how?) > procedure: review times table for smaller number and choose the largest that is smaller than bigger number
* S1: (37, times table?) > 37, ...
* WM: (1: 37) >
* S1: (37, x2) > [don't know]
  * S2: "Okay, then I need to figure it out"
* ... follow subgoal to figure out the times table ...
  * S1: (74, 100, greater than?) > no
  * S1: (101, 100, greater than?) > yes
  * WM: (chosen: 74)


Observations:
* The human brain does not learn whole procedures as a single unit of memory. It learns how to recognize what action to take, given the goal (or procedure identity) and the current conditions
  * It learns to recognize the conditions that represent each step in the procedure and what action needs to be taken next for that step
  * In this sense, it learns steps individually - it is only by stringing all the steps together that an entire procedure effectively emerges
  * As a proof of this, talk out, in order, the steps of long division; then, try to recall step 3 or step 4 - you generally won't be able to recall this without first walking through the steps and conditions that come before that step
* The executive function appears to move toward goals in a stacked or hierarchical fashion
  * For example, it starts with the goal "solve long division" (goal 1)
    * Goals: 1
  * The first step is "find the number on the right that is larger than the one on the left"
  * This becomes a new sub-goal (goal 1a)
    * Goals: 1, 1a
  * Once this is found, that sub-goal (goal 1a) is popped off the stack (considered "finished")
    * Goals: 1
  * The next step (for goal 1) is "find the number of times that the left number fits into the right number"; this becomes a new sub-goal (goal 1b)
    * Goals: 1, 1b
  * To find the answer to this, perhaps one needs to write out the times table for the number on the left; this becomes a new sub-sub-goal (goal 1b1)
    * Goals: 1, 1b, 1b1
  * Once this (goal 1b1) is finished, focus returns to the previous goal (1b)
    * Goals: 1, 1b
  * The answer is chosen from the table and now it (goal 1b) too is finished
    * Goals: 1
  * etc.














.
