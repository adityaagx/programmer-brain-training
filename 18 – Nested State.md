# 🧠 18 – Nested State (Layered Truth)

So far your state structures looked like this:

* Value
* List
* Object
* List of objects

Now we introduce **layers inside layers**.

---

## The Core Truth

Nested state is:

> State where a value contains another structured value inside it.

That’s it.

Structure inside structure.

---

## Simple Example

```
user = {
  name: "Aditya",
  address: {
    city: "Mumbai",
    zip: 400001
  }
}
```

The address is not just a value.
It is an object inside an object.

That is nesting.

---

## More Complex Example

```
school = {
  name: "ABC",
  students: [
    {
      name: "Riya",
      marks: {
        math: 90,
        english: 85
      }
    }
  ]
}
```

Now we have:

* Object

  * List

    * Object

      * Object

That is 4 layers deep.

---

# Why Nested State Is Dangerous

Because immutability must be respected at **every layer**.

When something deep changes,
all layers above it must also be replaced.

If you skip even one,
you break the chain.

---

# The Replacement Ladder

When updating a deep value:

1. Create new deepest object.
2. Create new parent object containing it.
3. Create new higher-level object containing that.
4. Replace state.

Each parent must get a new reference.

This is not optional.

---

## Visualize It

Original:

school
→ students (list)
→ student object
→ marks object
→ math

If math changes:

New marks object
New student object
New students list
New school object

That’s the ladder.

---

# Why This Is Necessary

Because each level contains the next.

If marks changes but student object is reused,
the student still points to old marks reference.

System sees no change at student level.

That’s silent inconsistency.

---

# The Core Law of Nested Updates

> When a nested value changes, every ancestor must be recreated.

That’s the law.

---

# Why Deep Nesting Feels Painful

Because:

* Update code becomes longer
* Mental load increases
* Mutation mistakes increase
* Performance mistakes increase

This is why architecture matters.

---

# Important Realization

Nested state is not wrong.

Deeply nested state without structure discipline is wrong.

---

# Practice Tasks (Answer in logic words only)

### Task 1

Explain what nested state is.

--- Nested state is a state which contanis list and objects which again contains other objects and lists.

### Task 2

Why must parent objects be recreated when a child changes?

--- Old parent points to the same reference, system will not detect the change, causing sync errors.

### Task 3

If updating `address.city`, which references must change?

--- City - Address - User

### Task 4

What happens if you mutate `marks.math` directly?

--- System will not detect the change, because reference is still the same, causing sync bugs.

### Task 5

In the school example, if math changes, list every layer that must become new.

--- Maths - Marks - Student - Students - School

### Task 6

Why does nesting increase mutation risk?

--- Harder debugging, More chances to forget replacement, Higher chances of partial mutation.

### Task 7

How does nesting affect performance?

--- Updating deep state requires recreating multiple layers, More memory allocation, Harder to optimize.

### Task 8

Why do large systems try to avoid deep nesting?

--- It costs perofrmace, mental load, update becomes harder, harder to identify bugs.

### Task 9

How does nested state interact badly with derived state?

--- Depper the nested state, harder to sync derived state.

### Task 10

What mindset is required to safely manage nested state?

--- Think in reference, think in layers, think systematically.

Take your time.

This chapter separates small app thinking from scalable architecture thinking.
