# Read 05 - Linked Lists

## Big O - Algorithm Efficiency

### Big Picture

Big O notation helps describe how efficient an algorithm is as the amount of
input data grows.

The two major things we measure are:

- **Time Complexity** - how the amount of work grows
- **Space Complexity** - how memory usage grows

The input size is commonly represented by:

`n`

A useful question is:

**"If the amount of data gets much larger, how does the work required by this
algorithm grow?"**

Big O is not mainly about measuring exact seconds on one particular computer.

Different computers have different speeds.

Instead, we focus on how the number of operations grows relative to the input.

---

### Input Size

If an algorithm processes an array containing 10 items:

`n = 10`

If the array grows to 1,000 items:

`n = 1000`

We then ask whether the algorithm performs:

- about the same amount of work
- proportionally more work
- dramatically more work

---

## Constant Complexity - O(1)

O(1) means the amount of work does not grow as the input grows.

Example:

```javascript
function getFirst(array) {
  return array[0];
}
```

Whether the array contains:

```text
5 items
500 items
5,000,000 items
```

the operation still accesses one location.

Mental model:

```text
Input grows
   |
   v
Work stays roughly the same
```

**O(1) = constant time**

---

## Logarithmic Complexity - O(log n)

O(log n) means the algorithm can eliminate large portions of the remaining
input during each step.

Binary search is an example.

Instead of checking every value, we repeatedly divide the search area in half.

Example:

```text
100 items
   |
   v
50
   |
   v
25
   |
   v
12
   |
   v
6
```

The search space becomes much smaller very quickly.

**O(log n) = logarithmic growth**

---

## Linear Complexity - O(n)

O(n) means the amount of work grows approximately in proportion to the number
of items.

Example:

```javascript
for (let item of array) {
  console.log(item);
}
```

If there are 10 items, we process about 10 items.

If there are 1,000 items, we process about 1,000 items.

Mental model:

```text
More items
   |
   v
More work at about the same rate
```

**O(n) = linear growth**

---

## Why Big O Matters

Two algorithms can produce the same correct answer but behave very differently
when the amount of data becomes large.

Big O gives us a way to discuss that difference.

For this class, an important habit is:

**Do not only ask, "Does my code work?"**

Also ask:

**"How much work does my code do as the input grows?"**

---

## Quick Reference - Big O

```text
O(1)      -> Constant
O(log n)  -> Logarithmic
O(n)      -> Linear
```

For this reading, these are the most important growth patterns to understand.

---

## Things I Want to Remember - Big O

1. Big O describes algorithm efficiency.

2. Time complexity measures growth in the amount of work.

3. Space complexity measures growth in memory requirements.

4. `n` represents input size.

5. O(1) stays approximately constant as input grows.

6. O(log n) reduces the remaining problem substantially at each step.

7. O(n) grows proportionally with the input.

8. Big O helps me think beyond whether code merely works.

---

## Singly Linked Lists

### Big Picture

A linked list is a data structure made from individual objects called
**nodes**.

Unlike an array, the nodes are not organized by numbered indexes.

Instead, each node contains information that tells us where the next node is.

A singly linked list can be pictured like this:

```text
HEAD
 |
 v
{ A | next } -> { B | next } -> { C | null }
```

Each node knows about the node that comes after it.

The final node points to `null`, which tells us that we have reached the end
of the list.

---

## What is a Node?

A Node is an individual element in a linked list.

For our purposes, a Node needs two important properties:

```text
value
next
```

### value

The `value` contains the data stored in the node.

### next

The `next` property points to the next node in the linked list.

Example:

```text
Node
+-------------+
| value = 10  |
| next = ---- |---->
+-------------+
```

The arrow represents the reference to another Node.

---

## What is the Head?

The `head` is the beginning of the linked list.

It points to the first Node.

Example:

```text
head
 |
 v
{ 10 } -> { 20 } -> { 30 } -> NULL
```

The head itself is not another data node.

It is a reference that tells us where the linked list begins.

If the linked list is empty:

```text
head -> null
```

This is important because without the head reference, we would not know where
to begin accessing the list.

---

## What Does Next Mean?

Each Node contains a `next` reference.

The `next` reference connects one Node to another.

Example:

```text
Node A
value = 10
next
 |
 v
Node B
value = 20
next
 |
 v
Node C
value = 30
next
 |
 v
null
```

Because this is a **singly** linked list, the connection moves in one
direction.

A Node knows which Node comes next.

It does not automatically know which Node came before it.

---

## Linked List Vocabulary

### Node

An individual object in the linked list containing a value and a reference to
the next Node.

### Head

A reference to the first Node in the linked list.

### Next

A property containing a reference to the next Node.

### Null

Represents the end of the linked list.

### Singly Linked List

A linked list where each Node contains a reference to the next Node.

### Current

A temporary reference commonly used while moving through a linked list.

### Traversal

The process of moving through the Nodes of a linked list one at a time.

---

## Traversal

Because linked lists do not use array indexes, we cannot normally jump directly
to an arbitrary position using something like:

```javascript
array[5]
```

Instead, we begin at the head and follow each `next` reference.

Mental model:

```text
current = head
      |
      v
    Node A
      |
     next
      v
    Node B
      |
     next
      v
    Node C
      |
     next
      v
     null
```

Conceptually, traversal looks like:

```javascript
let current = this.head;

while (current !== null) {
  // do something with current.value

  current = current.next;
}
```

The important line is:

```javascript
current = current.next;
```

That moves our temporary `current` reference forward to the next Node.

We continue until:

```javascript
current === null
```

which means we have reached the end.

---

## Searching a Linked List

Suppose we want to determine whether the value `20` exists:

```text
head
 |
 v
{ 10 } -> { 20 } -> { 30 } -> NULL
```

We start at the head.

```text
10 == 20 ? NO
```

Follow `next`.

```text
20 == 20 ? YES
```

The value has been found.

If the value does not exist, we continue following `next` until we reach
`null`.

Because we may need to inspect every Node, searching a singly linked list can
require:

```text
O(n)
```

time.

---

## Inserting at the Head

One advantage of a linked list is that inserting a new Node at the beginning
can be very efficient.

Suppose our list is:

```text
head
 |
 v
{ B } -> { C } -> NULL
```

We want to insert `A`.

First create the new Node:

```text
{ A }
```

Make the new Node point to the current head:

```text
{ A } ------> { B } -> { C } -> NULL
```

Then move `head` to the new Node:

```text
head
 |
 v
{ A } -> { B } -> { C } -> NULL
```

Conceptually:

```javascript
newNode.next = this.head;
this.head = newNode;
```

Notice what we did **not** have to do.

We did not traverse:

```text
B -> C
```

The size of the existing list does not determine how many steps are required
to insert at the head.

Therefore, inserting at the head is:

```text
O(1)
```

constant time.

---

## Why Linked Lists Are Different From Arrays

An array can be pictured as indexed positions:

```text
Index:   0     1     2
       +-----+-----+-----+
Value: |  A  |  B  |  C  |
       +-----+-----+-----+
```

An array gives us numbered positions.

A linked list instead uses connections:

```text
head
 |
 v
{ A } -> { B } -> { C } -> NULL
```

The key difference to remember is:

```text
Array       -> position/index based

Linked List -> reference/connection based
```

This difference affects how we access and manipulate the data.

---

## A Simple Node Mental Model

Think of each Node as a person holding two things:

```text
+-----------------------+
| My value is "A"       |
|                       |
| The next person is -> |
+-----------------------+
```

That person does not need to know where everybody in the line is.

They only need to know who comes next.

The Linked List only needs to know who is first:

```text
Linked List:
"The first person is A."

A:
"The next person is B."

B:
"The next person is C."

C:
"There is nobody after me."
```

Which becomes:

```text
HEAD -> A -> B -> C -> NULL
```

---

## Things I Want to Remember - Linked Lists

1. **A linked list is made of Nodes.**

2. **Each Node stores a value.**

3. **Each Node in a singly linked list also stores a reference called `next`.**

4. **The head points to the first Node.**

5. **An empty linked list has a head of `null`.**

6. **The final Node's `next` is `null`.**

7. **Traversal means following the `next` references through the list.**

8. **Singly linked lists move in one direction.**

9. **Searching may require visiting every Node, making it O(n).**

10. **Inserting at the head can be O(1) because we do not need to traverse the
    existing list.**

11. **Arrays organize data by indexes; linked lists organize data through
    references between Nodes.**

### One Sentence to Remember

**A singly linked list is a chain of Nodes where the head tells me where to
start and each Node tells me where to go next.**

---

# Teaching Linked Lists

## Topic: Understanding a Singly Linked List

### WHY would we use a linked list?

Sometimes we need to organize a collection of data where the pieces are
connected to one another rather than stored according to numbered positions.

A linked list gives us a way to build that chain dynamically.

One useful feature is that adding a new Node to the beginning of a singly
linked list can be done without walking through the entire list.

That operation can be O(1), or constant time.

---

## WHAT is a singly linked list?

A singly linked list is a chain of Nodes.

Each Node contains:

1. a value
2. a reference to the next Node

The Linked List has a `head`, which tells us where the chain begins.

Example:

```text
HEAD
 |
 v
{ A } -> { B } -> { C } -> NULL
```

Here:

- `HEAD` points to Node A
- A points to B
- B points to C
- C points to `NULL`

`NULL` tells us that we have reached the end of the list.

---

## An Analogy: Following Directions From Person to Person

I think of a singly linked list as a line of people where each person only
knows who comes next.

Imagine asking:

"Who is first?"

The Linked List answers:

"A is first."

Then I ask A:

"Who comes after you?"

A says:

"B."

I ask B:

"Who comes after you?"

B says:

"C."

I ask C:

"Who comes after you?"

C says:

"Nobody."

That becomes:

```text
Linked List -> A -> B -> C -> NULL
```

The Linked List does not need an index telling me that B is at position 1.

Instead, I discover B by starting at the head and following the connections.

---

## HOW do we move through the list?

We begin with the head.

```text
current = head
```

Then we examine the current Node and follow its `next` reference.

```text
HEAD
 |
 v
 A -> B -> C -> NULL
 ^
current
```

Move once:

```text
HEAD
 |
 v
 A -> B -> C -> NULL
      ^
    current
```

Move again:

```text
HEAD
 |
 v
 A -> B -> C -> NULL
           ^
         current
```

Eventually:

```text
current -> NULL
```

At that point we know we have reached the end.

This process is called **traversal**.

---

## How does inserting at the head work?

Suppose the list is:

```text
HEAD -> B -> C -> NULL
```

We want to insert A.

Create A:

```text
A
```

Point A at the old head:

```text
A -> B -> C -> NULL
```

Then change the head:

```text
HEAD -> A -> B -> C -> NULL
```

We only needed to change references near the beginning of the list.

We did not need to walk through B and C.

That is why inserting at the head can be:

```text
O(1)
```

---

## How does searching work?

Suppose we want to know whether C exists:

```text
HEAD -> A -> B -> C -> NULL
```

We cannot simply ask for an array index.

Instead:

```text
Check A -> not C

Check B -> not C

Check C -> found it
```

In the worst case, we may have to examine every Node.

Therefore searching through the list can be:

```text
O(n)
```

---

# Linked List Cheat Sheet

```text
Node       = one element in the list

value      = data stored inside a Node

next       = reference to the next Node

head       = reference to the first Node

null       = end of the list

traversal  = following next from Node to Node

O(1)       = constant complexity

O(n)       = linear complexity
```

### Visual Summary

```text
              LINKED LIST
                   |
                   v
                 HEAD
                   |
                   v
             +-----------+
             | value: A  |
             | next -----|----+
             +-----------+    |
                              v
                         +-----------+
                         | value: B  |
                         | next -----|----+
                         +-----------+    |
                                          v
                                     +-----------+
                                     | value: C  |
                                     | next:null |
                                     +-----------+
```

---

# Connection to the Code Challenge

The Linked List implementation challenge asks for three important methods.

### insert(value)

Add a new Node at the head.

```text
Before:

HEAD -> B -> C -> NULL

After insert(A):

HEAD -> A -> B -> C -> NULL
```

This can be O(1).

### includes(value)

Traverse the list looking for a particular value.

```text
HEAD -> A -> B -> C -> NULL
        |    |    |
      check check check
```

Return:

```text
true
```

if the value is found, otherwise:

```text
false
```

This can be O(n).

### toString()

Traverse the entire list and represent its values as a string.

Example:

```text
{ A } -> { B } -> { C } -> NULL
```

This is also O(n) because every Node must be visited.

---

# Final Takeaway

The biggest idea I learned is that a linked list is based on **connections
instead of indexes**.

An array tells me where something is by position.

A linked list tells me where to go next.

Once I understand:

```text
HEAD -> NODE -> NEXT -> NODE -> NEXT -> NULL
```

the operations on a linked list become easier to understand because most of
them involve either changing a reference or following those references through
the list.

