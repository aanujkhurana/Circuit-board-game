# Circuit Function

This is my implementation for simulation of a simple game. The final Circuit has 2 subcircuits: one for part A labelled as “logic P=Q” and one for part B labelled as “counter”.

## Part A

Given:
- P = Q+1
- P = Q-1
- P = Q+2
- P = Q-2

P and Q can be 0-7.

Let's consider P = Q:
- When P = 0, Q = P + 1 or P + 2 or P - 1 or P - 2. So, Q can be 1 or 2.
- Similarly, when:
  - P = 1, Q = 0 or 2 or 3
  - P = 2, Q = 0 or 1 or 3 or 4
  - P = 3, Q = 1 or 2 or 4 or 6
  - P = 4, Q = 2 or 3 or 5 or 6
  - And so on...

Following this logic, I have used OR Gates to combine inputs of Q & AND Gates to combine Q inputs with P inputs ranging from 0-7. Each successful combination gives output 1.

## Part B

I utilized a NOT Gate to count successful and unsuccessful combinations using a Counter for part B, where the input is the output of part A. A button can be used to count the items. This was utilized as an input to maintain the button connected to the main circuit. I used a comparator with a constant 3 for the reasoning that 3 unsuccessful combinations reset the counter. I used a comparator with a constant of 6 followed by a Dflipflop to save the value to control the simulation for the logic of 6 successful combinations stopping the simulation.

