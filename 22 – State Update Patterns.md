# 🧠 Chapter 22 – State Update Patterns

(Add, Remove, Update, Toggle, Replace — for Objects & Lists)

This chapter is mechanical discipline.
If you master this, 80% of state bugs disappear.

No React yet. Just pure state logic.

---

# Core Rule (Again, But Sharper)

State is immutable.

That means:

* Never mutate existing object
* Never mutate existing array
* Always create new reference at the correct level

Now we formalize update patterns.

---

# 1️⃣ ADD

## Add to Array

State:

```
items = [A, B, C]
```

Add D.

Correct mental model:

New array = old items + new item

```
[A, B, C, D]
```

Old array untouched.
New reference created.

---

## Add Property to Object

State:

```
user = { name: "Aditya" }
```

Add age.

Correct:

```
{ name: "Aditya", age: 20 }
```

You don’t mutate user.
You create a new object.

---

# 2️⃣ REMOVE

## Remove from Array

State:

```
[A, B, C]
```

Remove B.

Correct:

```
[A, C]
```

New array without B.

You filter.
You do not splice.

---

## Remove Property from Object

State:

```
{ name: "Aditya", age: 20 }
```

Remove age.

Correct conceptually:

Create new object without that key.

You never delete directly from original.

---

# 3️⃣ UPDATE

## Update Primitive in Object

State:

```
user = { name: "Aditya", age: 20 }
```

Update age to 21.

Correct:

```
{ name: "Aditya", age: 21 }
```

New object.

---

## Update Object Inside Array

State:

```
[
  { id: 1, name: "A" },
  { id: 2, name: "B" }
]
```

Update id 2 name.

Correct logic:

* Iterate
* Replace only matching item
* Keep others same

Result:

```
[
  { id: 1, name: "A" },
  { id: 2, name: "New B" }
]
```

New array.
New object only for id 2.

---

# 4️⃣ TOGGLE

Toggle is just update of boolean.

State:

```
{ isOpen: false }
```

Toggle:

```
{ isOpen: true }
```

New object.

Simple but important.

---

# 5️⃣ REPLACE

Replace entire state.

State:

```
[A, B, C]
```

Replace with:

```
[X, Y]
```

Valid when you intentionally discard old state.

Common when fetching fresh data.

---

# ⚠ Nested Application

Now the real discipline:

If you update nested data:

You must apply these patterns at every level.

Example:

```
school.students[1].name
```

You must:

* Create new student object
* Create new students array
* Create new school object

Update pattern climbs the ladder.

---

# 🔥 The 5 Core Patterns Cover Everything

Every state change in React is one of these:

* Add
* Remove
* Update
* Toggle
* Replace

Nothing else exists.

If a bug happens, it’s because one of these patterns was applied incorrectly.

---

# Now Practice (Logic Only)

### 1

If you remove an item from array using splice, what goes wrong?

--- It does't create the new array, hence the same reference identity, 
    system will not detect the change, sync bugs will happen.

### 2

When updating one object inside array, should other objects get new references?

--- No, other objects need not get any new references.

### 3

If you toggle a boolean inside nested object, how many levels must be replaced?

--- You must replace every ancenstor container up to the state root.

### 4

When is full replacement safer than partial update?

--- When you want to reset state completely, or you are dealing with fresh data.

### 5

Why is "update" actually just a combination of replace at specific depth?

--- Because update doesn't mean changing everything, it just creates the new state with old objects + new objects.

