06 - Loops (Repetition With Control)

Goal of this lesson
To understand how programs repeat actions without writing them again and again.
This is what makes programs powerful, fast, and scalable.

First principle: computers are dumb but tireless

A computer cannot think creatively.
But it can repeat instructions perfectly.

If you tell it to do something once, it does it once.
If you tell it to do something 1,000 times, it does it 1,000 times.

Loops exist to tell the computer:
“Do this again and again, but only under certain conditions.”

---

What a loop really is

A loop is a rule that says:
Repeat this action
while a condition is true.

That’s it.

No magic.
No complexity.

---

The three essential parts of every loop

Every loop, no matter the language, has three things:

1. Initial state
2. Condition
3. Repeated action

If even one is missing, the loop breaks.

---

Example: counting pushups

Initial state: count is 0

Condition:
Is count less than 10?

Repeated action:
Do one pushup
Increase count by 1

This continues until the condition becomes false.

---

First principle: loops depend on state

A loop always checks state.

If state never changes, the loop never ends.
If state changes incorrectly, the loop breaks early.

This is why state understanding is critical.

---

Infinite loop (important warning)

If the condition never becomes false, the loop runs forever.

Example:
Count starts at 0
Condition: is count less than 10?
But count is never increased

Result: infinite loop.

This is one of the most common beginner mistakes.

---

First principle: condition controls repetition

The loop does NOT decide when to stop.
The condition does.

The computer checks the condition every time before repeating.

True → repeat
False → stop

---

Real-life example: eating chips

Initial state: chips left = 5

Condition:
Are there chips left?

Repeated action:
Eat one chip
Reduce chips by 1

When chips reach 0, the loop stops.

---

Why loops are everywhere

Loops are used for:

Counting
Processing lists
Rendering UI items
Checking messages
Running animations
Handling data

Without loops, programs would be tiny and useless.

---

Example: checking unread messages

Initial state: index = 0

Condition:
Is index less than number of messages?

Repeated action:
Check message at index
Increase index by 1

This is how apps scan data.

---

Common beginner mistakes

Forgetting to update state inside the loop
Using the wrong condition
Creating infinite loops
Changing the wrong variable
Not understanding when the loop stops

All loop bugs come from state or condition mistakes.

---

Golden loop thinking pattern

Set starting value
Check condition
Perform action
Update state
Repeat

This cycle is everything.

---

Practice Tasks (Do NOT Skip)

Task 1
Describe a loop for counting from 1 to 5 in plain words.

- Keep counting and increasing by one, as long as the number is not greater than 5.

Task 2
Identify the initial state, condition, and repeated action when scrolling through a list of contacts.

- Initial state - list of contacts shown.
- Condition - Until contacts are left.
- Action - load and show the next set of contacts

Task 3
Explain why a loop becomes infinite if state is not updated.

- If state is not updated, state will not progress, and condition will never become false,
  thereby making the loop infinite.

Task 4
Describe a real-life loop involved in brushing your teeth.

- Keep brushing teeth until teeth becomes clean.

Task 5
What condition stops a loop that is counting unread messages?

- Loop stops when count becomes 0

Task 6
Explain how a loop could be used to count items in a shopping cart.

- Count items in a cart, until all items are counted.

Task 7
Identify the mistake in a loop where count never changes.

- State never changes, so it becomes a infinite loop

Task 8
Give an example where a loop runs zero times.

- Count numbers starting 5
- Condition - count < 5
- This loop never runs.

Task 9
Why are loops impossible without conditions?

- Conditions tell loops when to run and when to stop, thereby making the boundaries of start and end.

Task 10
Give one real-life example of a loop with clear start and stop points.

- Starting from 1, Keep increasing the speed of fan until it becomes 5
- Starting point 1, end point 5.

Lesson 06 takeaway

Loops are controlled repetition.
State decides progress.
Conditions decide stopping.
Actions do the work.

If you understand loops, you can handle scale.
