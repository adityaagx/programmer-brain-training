## 12 – Multiple States Working Together (First Principles)

Up till now, you’ve mostly thought in **one state at a time**.

That’s good for learning.
But real systems **never work with just one state**.

This chapter teaches you how **many states coexist** and **interact** without chaos.

---

### The Core Truth

A system is not one value.
A system is **many values existing at the same time**.

Each value answers a different question.

Example (logic only):

* How many items?
* Is the system active or inactive?
* What message should be shown?

Each of these is **separate state**.

---

### What Is a State, Again? (Regrounding)

From first principles:

A state is:

* A stored piece of information
* That represents “what is true right now”
* And can change over time

Important:

> One state should represent **one idea only**.

---

### Why One State Is Not Enough

Imagine a counter app.

You might need:

* The number (count)
* Whether the counter is enabled
* A message to show to the user

If you force all this into one value:

* Meaning becomes unclear
* Logic becomes fragile
* Changes break unrelated behavior

So we **separate concerns**.

---

### Multiple States = Multiple Truths

Each state:

* Has its own meaning
* Has its own rules
* Changes for its own reasons

Example:

* `count` → quantity
* `status` → condition
* `message` → communication

They can exist together without conflict.

---

### States Can Influence Each Other (Carefully)

Important rule:

States do **not automatically change each other**.

Instead:

* An action happens
* Logic runs
* One or more states may update

Example logic:

* If count reaches limit → status changes
* If status changes → message updates

But:

> Each update is **intentional**, not automatic.

---

### Why This Is Powerful

This allows:

* One action → many effects
* One state → many consequences
* Clean reasoning about complex behavior

This is how real apps behave without breaking.

---

### Bad Thinking vs Good Thinking

Bad thinking:

* “Everything is connected, so everything updates everything”

Good thinking:

* “Actions trigger logic, logic decides which states change”

States are passive.
Logic is active.

---

### Example (Pure Logic)

State:

* count
* isLimitReached

Action:

* user clicks increase

Logic:

* count increases
* if count reaches max → isLimitReached becomes true

Notice:

* Two states
* One action
* Controlled updates

---

### Why This Prevents Bugs

When states are separate:

* Changing one doesn’t accidentally break another
* You can reason about each independently
* Debugging becomes possible

This is not about code quality.
This is about **thinking quality**.

---

### Mental Model (Memorize This)

1. States store facts
2. Actions attempt change
3. Logic decides updates
4. Multiple states update only when needed

If you understand this, frameworks become trivial.

---

## Practice Tasks (Do NOT Skip)

Task 1
Name three different states a simple music player might have.

- State of number of songs in a playlist
- State of number of downloaded songs.
- State of Songs already played.
  
Task 2
Explain why volume level and play/pause status should be separate states.

- Volume level State shouldn't affect play/pause state.
  and also play/pause action has nothing to do with volume level.

Task 3
Describe how one action can update two different states.

- Action of logging out the music player affetc multiple states
- Wishlist comes back to initial state.
- Playlist comes back to initial state.
- Account infirmation gets back to initial state.

Task 4
Explain why states should not update each other automatically.

- If states will update each other, confusion will happen, because of which
  logic breaks and system crashes.
- And also states are always updated by action and logic.

Task 5
Describe a system where one state depends on another, logically.

- On social media platform, follow state depends on login state.
- Only if the user is logged in, he/she can follow someone.

Task 6
Explain what happens if multiple states are mixed into one.

- Confusion happens, logic breaks, bugs appear, system breaks.

Task 7
Describe how separating states makes systems easier to control.

- Separating states overall improve the readabality and usability of code.
  It makes debugging easier and overall improve the logic flow of code.

Task 8
Explain how multiple states still remain independent.

- Multiple states can still remain independent because each action updates different states, not every state.
- So at the same time multiple states can update via single action and vice - versa.

Task 9
Describe a real-world system that uses many states at once.

- Starting a laptop updates many states at once.

Task 10
Explain why this chapter is necessary before learning lists and objects.

- This chapter explains how states are updated, which defines how lists and objects are updated.

---

Take your time.
Answer honestly, not perfectly.
