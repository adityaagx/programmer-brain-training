03 - State (Memory of a Program)

Goal of this lesson
To understand what “state” is, from first principles, so things like counters, likes, scores, and values that change over time finally make sense.

First principle: computers have no memory by default

A computer does not remember anything on its own.
It does not remember what happened one second ago.
It does not remember previous values.
It only knows what exists right now.

If you want a computer to remember something, you must explicitly store it.

That stored value is called state.

What state really is?

State is simply a value that exists right now and can change later.

In simple words:
State is the memory of a program.

If something can change, it must be remembered somewhere.
If it is remembered, it is state.

Real-life examples of state

Fan speed
Phone volume
Bank balance
Game score
Number of likes
Unread messages

All of these have three things in common:
They have a current value.
That value can change.
The value must be remembered.

That remembered value is state.

Example: fan speed

Current state: speed is 2
Action: press the button
New state: speed becomes 3

If the fan did not remember its speed, it would reset every time.

First principle: counting is impossible without state

Imagine counting steps, but after every step the count goes back to zero.

You can never reach 2, 3, or 4.
Counting completely breaks.

This is exactly what happens in programs when state is not stored.

Example: counter thinking (no code)

Start value is 0
Add one → value becomes 1
Add one → value becomes 2
Add one → value becomes 3

This only works because the value is remembered after each step.

First principle: state always has a current value

At every moment, state has one current value.

Programmers constantly think in this way:
“What is the value right now?”

Not what it was.
Not what it will be.
Only what it is right now.

Example: likes on a post

Current likes: 10
User clicks like
New likes: 11

The old value is replaced by the new one.

First principle: state changes only after an action

State does not change randomly.

Something must happen:
A click
A button press
User input
A timer finishing

No action means no change in state.

Example: game score

Initial score is 0
Player defeats an enemy
Score becomes 10

Action causes state change.

First principle: every state must start somewhere

Every state needs an initial value.

If you do not define it:
Logic breaks
Bugs appear
Results feel random

Examples:
A counter starts at 0
A score starts at 0
Volume starts at a specific level

Initial state is not optional.

Common beginner mistakes

Forgetting to store the value
Resetting the value accidentally
Confusing old value with new value
Not realizing that changing values must be remembered

Most beginner confusion comes from not understanding state.

One golden rule

If a value changes over time, it must be stored.

That storage is called state.

Practice Tasks (Do NOT Skip)

Task 1
Identify the state involved in turning a fan on and off.

- Button is the action which chnages the state, on or off is the state
  whihc gets changed.

Task 2
What value must be remembered to count how many times a button is clicked?

- Number that stores the value of how mnay times a button is clicked must be remembered, starting from zero.
  
Task 3
Explain the state change when phone volume goes from 6 to 5.

- State decreases by one.
  
Task 4
What is the state in a shopping cart that has 4 items?

- State is number of items in a cart, which is 4.
  
Task 5
Explain why counting fails if the number resets after every step.

- Ater each count, number again comes back to zero, so count doesnt move further.
  
Task 6
Identify the state in a game scoring system.

- Score is state, each time you win, state increases by fixed value.

Task 7
What happens to state when a webpage is refreshed?

- When a webpage is refreshed, most-in memory state is lost and state resets to its initial.
  
Task 8
What state is required to track unread messages?

- State of number of chats not opened after a message has arrived.
  
Task 9
Explain the difference between initial state and current state.

- Initial state is the state at which is starts or initializes.
- Current state is the current present state of the thing.
  
Task 10
Give one real-life example where state changes only after an action.

- Counting how many times you did a pushup.
- After each pushup, state increases by one.

  
Lesson 03 takeaway

State is memory.
Programs forget everything without it.
Counters, likes, scores, and totals exist only because state exists.
