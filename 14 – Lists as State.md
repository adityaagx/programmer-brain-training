## 14 – Lists as State (Arrays from First Principles)

Up till now:

* One state = one value

Real applications don’t work like that.

Real applications deal with:

* Many items
* Changing collections
* Growing and shrinking data

This chapter explains how **a list is just state — repeated**.

---

### The Core Truth

A list is:

> One state that holds **many related values**

Nothing more.

There is no new magic here.

---

### Why Lists Exist

From first principles:

Sometimes:

* One value is not enough
* You need to remember multiple similar things
* Each thing has the same meaning

Example:

* Items in cart
* Songs in playlist
* Messages in chat
* Tasks in a todo list

These are not separate states.
They are **one grouped state**.

---

### List as a Container of State

Think like this:

* Single state → one fact
* List state → many facts of the same type

The list itself is the state.
The items are its contents.

You do **not** treat each item as separate global state.

---

### Actions on Lists (Logic Only)

There are only **three fundamental actions**:

1. Add an item
2. Remove an item
3. Change an existing item

Every list operation is a variation of these three.

No exceptions.

---

### Adding to a List (First Principles)

Logic:

* Take the existing list
* Create a new version of the list
* Include the new item
* Replace the old list

Key idea:

> You don’t “push into” state — you **replace state**.

This keeps systems predictable.

---

### Removing from a List

Logic:

* Look at the current list
* Decide which item should not exist
* Create a new list without it
* Replace the old list

Again:

* No mutation
* No partial change
* Full replacement

---

### Updating One Item in a List

Logic:

* Find the item
* Replace only that item
* Keep all others the same
* Replace the list

This is controlled, not chaotic.

---

### Lists + Derived State (Important)

You almost never store:

* List length
* Totals
* Status messages

These are **derived** from the list.

Example:

* Number of items = derived from list
* Total price = derived from list

This prevents contradiction.

---

### Why Lists Feel Hard to Beginners

Because:

* Many items change often
* Beginners store extra state
* Sync logic breaks

But:

> Lists are easy if you treat them as one state.

---

### One List, Many Meanings

A single list can give:

* Count
* Total
* Status
* UI display

But only **the list** is stored.

Everything else is derived.

---

### Mental Model (Lock This In)

* The list is the truth
* Items are facts
* Actions replace the list
* Logic derives everything else

If you remember this, arrays never confuse you.

---

## Practice Tasks (Do NOT Skip)

Task 1
Explain what a list is, using logic words only.

- A list is a state which has many value of similar type.

Task 2
Give three real-world examples where list state is needed.

- Names, Ages, Roll No. of children in class

Task 3
Explain why a list should be treated as one state.

- Because all the values are of related type.

Task 4
Describe the logic of adding an item to a list.

- Take the list.
- Add item to list.
- Replace old list with a new list.

Task 5
Describe the logic of removing an item from a list.

- Take the list.
- Remove the item from the list.
- Replace old list with a new list.

Task 6
Explain why list length should not usually be stored as state.

- List length should always be derived, so that it never contradicts.

Task 7
Describe how derived state works with lists.

- Lists can be used to derive list length, total of list.

Task 8
Explain why replacing a list is safer than modifying it.

- Because modifying may create contradictions.

Task 9
Describe a situation where list state changes frequently.

- List state of unread messages on whatsapp.

Task 10
Explain why this chapter is harder than single-value state.

- It is eaiser to manipulate single-value list, harder to manipulate multi-value items list.

---
