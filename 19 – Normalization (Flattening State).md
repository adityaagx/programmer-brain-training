# 🧠 19 – Normalization (Flattening State)

This is where architecture begins.

Nested state increases:

* Replacement complexity
* Mutation risk
* Cognitive load
* Bug probability

Normalization fixes that.

---

## What Is Normalization?

Normalization means:

> Instead of storing data nested inside other data, store entities separately and link them by IDs.

That’s it.

We remove deep nesting.

We store things in flat maps.

---

## Before (Nested)

```
app = {
  users: [
    {
      id: 1,
      profile: {
        stats: {
          achievements: [
            { id: 1, title: "Top Writer" }
          ]
        }
      }
    }
  ]
}
```

Updating achievement title requires 7 replacements.

Painful.

---

## After (Normalized)

```
app = {
  users: {
    1: { id: 1, profileId: 10 }
  },

  profiles: {
    10: { id: 10, statsId: 20 }
  },

  stats: {
    20: { id: 20, achievementIds: [100] }
  },

  achievements: {
    100: { id: 100, title: "Top Writer" }
  }
}
```

Now everything is flat.

Entities are stored separately.

They reference each other using IDs.

---

## What Changes Now?

If title changes:

You only replace:

* achievement 100 object
* achievements map
* app

That’s it.

3 layers instead of 7.

Huge difference.

---

## Why This Is Powerful

1. Shallow updates
2. Easy replacement
3. Lower mutation risk
4. Predictable structure
5. Scalable architecture

This is how Redux stores large data.

This is how databases think.

This is how serious frontend apps are structured.

---

## The Mental Shift

Stop thinking:

> This object contains that object

Start thinking:

> This object references that object

Containment creates depth.
Reference creates structure.

---

## Trade-Off

Normalization increases:

* Indirection
* Lookup steps
* Slight conceptual complexity

But massively reduces mutation chaos.

---

# Practice Tasks (Logic Only)

### Task 1

What is normalization in one sentence?

--- It is flatening the state, giving ids to each entity instead of nesting into one another.

### Task 2

Why does normalization reduce replacement ladder depth?

--- Normalization reduces ladder depth because entities are no longer deeply contained inside each other
--— they exist at the top level, so updating one does not require recreating multiple ancestor containers.

### Task 3

In normalized state, what connects related entities?

--- Ids connect related entities.

### Task 4

Why is normalization similar to database design?

--- because both connect related entities with ids.

### Task 5

What is the main trade-off of flattening state?

--- Slightly harder to read data directly, more indirection.

### Task 6

Why is normalization especially useful in large apps?

--- Normalization reduces update complexity, lowers mutation risk, and makes state predictable
--— which becomes critical when many features interact in large applications.

### Task 7

If you update achievement 100’s title, which layers must change?

--- achievement 100 object, achievement map, app state object

### Task 8

Why does normalization reduce mutation risk?

--- Because each entity lives independently, less risk of accidentally mutating shared nested references.

### Task 9

Why does normalized state improve scalability?

--- Because it is easy to maintain and update and debug.

### Task 10

What mindset shift is required to design normalized state?

--- Stop thinking in nested objects.
--- Start thinking in independent entities and relationships.
