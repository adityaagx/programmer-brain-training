# 🧠 Chapter 21 – React State Mapping

This is where everything you learned becomes real React behavior.

You already understand:

* Immutability
* Reference identity
* Replacement ladder
* Normalization
* Selectors
* Update patterns

Now we map that into how **React actually behaves**.

---

# 1️⃣ React’s Core Contract

React assumes:

> If you give me a new reference, I will re-render.
> If you give me the same reference, I will not.

That’s the contract.

React does not track internal mutations.
React does not deep inspect objects.
React trusts reference identity.

If you break immutability,
you break the contract.

React is not broken.
You violated the rule.

---

# 2️⃣ How React Detects Changes

For state updates:

React compares:

```
oldState === newState ?
```

If true → no render
If false → render

That’s it.

No deep comparison.
No nested inspection.

Shallow reference comparison only.

This is why:

```
state.push(item)
setState(state)
```

Fails.

Same reference.

---

# 3️⃣ Why React Is Designed This Way

Because deep comparison is expensive.

Imagine:

* 5,000 items
* Nested objects
* Complex UI tree

If React deep-compared everything,
performance would collapse.

So React keeps it simple:

Reference change = signal.

Immutability makes that signal reliable.

---

# 4️⃣ Applying Update Patterns in useState

Now we connect your Chapter 20 patterns to React.

---

## 🔹 Add

```
setItems(prev => [...prev, newItem])
```

New array reference.
React re-renders.

---

## 🔹 Remove

```
setItems(prev => prev.filter(item => item.id !== id))
```

New array.
React re-renders.

---

## 🔹 Update

```
setItems(prev =>
  prev.map(item =>
    item.id === id
      ? { ...item, name: "Updated" }
      : item
  )
)
```

New array.
New object only for updated item.

Efficient.
Correct.

---

## 🔹 Toggle

```
setOpen(prev => !prev)
```

Primitive change.
Clean.

---

## 🔹 Replace

```
setData(newData)
```

Full replacement.

Used when fetching fresh server data.

---

# 5️⃣ Functional Updates – Why They Matter

Always prefer:

```
setState(prev => ...)
```

Why?

Because React batches updates.

Example:

```
setCount(count + 1)
setCount(count + 1)
```

Might result in 1 instead of 2.

Because both use same stale value.

Functional update:

```
setCount(prev => prev + 1)
setCount(prev => prev + 1)
```

Now React applies correctly → 2.

Functional updates prevent race conditions.

---

# 6️⃣ Common React State Bugs

### ❌ Mutating nested object

UI doesn’t update.

### ❌ Forgetting to replace parent object

Partial update fails.

### ❌ Storing derived state

Data drifts out of sync.

### ❌ Recreating objects unnecessarily

Too many re-renders.

Most React “mystery bugs” are reference mistakes.

---

# 7️⃣ Why Sometimes React Re-renders “Too Much”

If you return:

```
[...prev]
```

Even if values are same,
it’s a new reference.

React re-renders.

React cannot know content didn’t change.

Reference changed → re-render.

This is correct behavior.

Optimization requires memoization.

That’s next level.

---

# 8️⃣ Writing Bug-Free React State

Discipline checklist:

* Never mutate
* Replace correct level
* Use functional updates
* Avoid storing derived data
* Keep state minimal
* Normalize relational data
* Memoize expensive selectors

Follow this and your React code becomes predictable.

---

# 🧠 Important Mental Shift

React doesn’t track data.

React tracks references.

If you understand references,
you understand React.

---

Now answer carefully.

### 1

If you mutate state and React doesn’t re-render, is React broken?

--- No, react is not broken.
    React only re-render on the change of reference, 
    Mutating state doesn't change its reference identity.

### 2

Why does returning a new array always cause re-render?

--- Because new array has a new reference identity,
    react always re-renders on catching new referenc identity.

### 3

Why are functional updates safer in concurrent rendering?

--- It prevents state bugs and race conditions.

### 4

If you update deeply nested value but forget to replace top-level object, what will React do?

--- React will not see any change in reference identity, hence will not re-render.

### 5

What is React actually observing — values or references?

--- React always observes references.
