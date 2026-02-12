# 🧠 Chapter 22 – Mental Models of State (Expert Level)

If you internalize this chapter, you stop “coding React”
and start **designing systems**.

---

# 1️⃣ State as Truth

State is not UI.
State is not variables.
State is not temporary storage.

State is **the current truth of your application**.

The UI does not decide truth.

The state decides truth.

The UI simply displays it.

Think of it like this:

```
UI = f(state)
```

The UI is just a projection.

If UI looks wrong,
you don’t fix the UI.

You fix the state.

Beginners manipulate UI.

Experts control truth.

---

# 2️⃣ State as Source of UI

Your UI should never contain hidden truth.

If something is visible,
it must come from state.

Bad thinking:

* “Let me manually hide this”
* “Let me tweak the DOM”

Good thinking:

* “What state would make the UI look like this?”

UI should be predictable.

If the same state is given twice,
UI must look identical both times.

That’s deterministic rendering.

---

# 3️⃣ State as Transitions (Not Modifications)

Beginner thinking:

> “How do I change this value?”

Expert thinking:

> “What should the next state look like?”

You never “edit” state.

You transition from one truth to another truth.

Example:

Old truth:

```
isLoggedIn = false
```

New truth:

```
isLoggedIn = true
```

You are not modifying old truth.

You are declaring a new truth.

This mindset eliminates mutation thinking.

---

# 4️⃣ State as History

Immutability gives you history for free.

Every state update creates a new reference.

That means:

* You can compare previous and next
* You can log transitions
* You can debug easier
* You can undo/redo
* You can time-travel

Mutation destroys history.

If you mutate the same object repeatedly,
there is no past version.

History collapses.

Immutable transitions preserve the timeline.

Large systems need history.

---

# 5️⃣ State as Single Source of Truth

There must be only one place where truth lives.

If you store:

* totalPrice
* items
* itemCount

All separately…

You now have multiple truths.

If items change and totalPrice doesn’t update?

System lies.

Derived state duplication creates drift.

Single source of truth means:

Store raw facts.
Compute everything else.

Selectors > duplication.

---

# 6️⃣ Why Immutability Scales Systems

Immutability enables:

### 🔹 Predictable change detection

Reference changed → something changed.

### 🔹 Safe concurrency

Parallel updates don’t mutate shared memory.

### 🔹 Easier debugging

You can inspect previous state.

### 🔹 Memoization

Stable references make caching possible.

### 🔹 Performance optimization

Shallow comparison becomes valid.

Mutation-based systems become chaotic at scale.

Immutability keeps systems mathematically clean.

---

# 7️⃣ State as Data, Not Behavior

State should describe:

What is true.

Not:

What should happen.

State is declarative.

Example:

Good state:

```
isModalOpen: true
```

Bad state:

```
shouldOpenModal: true
```

State describes condition,
not action.

Actions produce transitions.
State stores truth.

---

# 8️⃣ State Minimalism

Expert rule:

Store the minimum amount of truth necessary.

If something can be calculated,
don’t store it.

If something can be derived,
derive it.

Smaller state surface = fewer bugs.

---

# 9️⃣ UI Is a Projection Layer

The UI is not logic.

The UI is a visual function.

State is your data layer.

Mixing them creates:

* Hard-to-debug code
* Fragile systems
* Side-effect chaos

Clean architecture separates:

Truth → Projection → Interaction

---

# 🔟 The Final Mental Shift

State is not something you “update.”

State is something you **replace with a new version of reality**.

That shift alone changes how you write code.

You stop mutating.

You start declaring transitions.

---

# 🧠 If You Understand This Chapter

You now understand:

* Why immutability matters
* Why React behaves the way it does
* Why normalization exists
* Why selectors exist
* Why memoization works
* Why mutation causes chaos
* Why large systems require discipline

This is not beginner React anymore.

This is system-level thinking.

---
