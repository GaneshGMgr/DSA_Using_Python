# 🧠 DSA Using Python

This repository contains clean, beginner-friendly implementations of core **Data Structures and Algorithms (DSA)** concepts using Python. Each concept is explored through interactive **Jupyter Notebooks**, making it ideal for both learning and revision.

---

## 📂 Contents

| Notebook                      | Description                                                                                     |
|------------------------------|-------------------------------------------------------------------------------------------------|
| `dynamic_arrays.ipynb`        | Implementation and explanation of dynamic arrays (like Python lists), their resizing logic, and performance trade-offs. |
| `Linked_List.ipynb`           | Singly linked list with insertion, deletion, search, and traversal methods.                     |
| `stacks_using_arrays.ipynb`  | Stack implementation using arrays (lists) with push/pop operations.                             |
| `stacks_using_linkedlists.ipynb` | Stack implementation using linked lists.                                                     |
| `queue_LL_implementation.ipynb`  | Queue implementation using linked lists (enqueue, dequeue).                                 |
| `searching_sorting.ipynb`     | Classical searching (linear, binary) and sorting (bubble, selection, insertion, merge, quick sort) algorithms. |
| `hashing_linear_probing.ipynb` | Hash table implementation using linear probing for collision handling.                        |
| `hashing_via_chaining.ipynb`  | Hash table implementation using chaining (linked lists) to handle collisions.                  |

---

# 🔗 Linked List in Python (Jupyter Notebook)

This notebook provides a full implementation of a **Singly Linked List** from scratch in Python, without relying on built-in data structures for internal logic. It’s designed to be educational, beginner-friendly, and hands-on.

---

## 🧱 Node Structure

Each node contains:
- `data`: The actual value
- `next`: A pointer to the next node in the list

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

---

## 🧩 LinkedList Class with Core Operations

### 🔧 Basic Setup

| Method         | Description                          |
|----------------|------------------------------------|
| `__init__()`   | Initializes an empty list           |
| `__len__()`    | Returns the number of nodes         |
| `__str__()`    | Returns the linked list as a string |

---

### ➕ Insertion Methods

| Method                         | Description                     |
|--------------------------------|---------------------------------|
| `insert_head(value)`           | Insert at the beginning          |
| `append(value)`                | Insert at the end                |
| `insert_after(after_value, value)` | Insert after a specified node |

---

### ➖ Deletion Methods

| Method                 | Description                   |
|------------------------|-------------------------------|
| `delete_head()`        | Remove from the beginning     |
| `pop()`                | Remove from the end           |
| `remove(value)`        | Remove a node by value        |
| `delete_by_index(index)` | Remove a node at a position  |

---

### 🔍 Searching Methods

| Method                | Description                     |
|-----------------------|---------------------------------|
| `search(value)`       | Returns index of the value      |
| `__getitem__(index)`  | Access by index (like `LL[2]`)  |

---

### 🧰 Utility Methods

| Method      | Description           |
|-------------|-----------------------|
| `traverse()`| Prints all elements    |
| `clear()`   | Empties the entire list|

---

## 📌 Example Usage

L = LinkedList()

# Insert from head
L.insert_head(1)
L.insert_head(2)

# Insert from tail
L.append(3)

# Insert in the middle
L.insert_after(2, 5)  # 2 -> 5 -> 1 -> 3

# Delete operations
L.delete_head()
L.pop()
L.remove(5)

# Accessing
print(L)            # View the linked list
print(L[1])         # Indexing
print(L.search(3))  # Find index of value

# Utility
len(L)
L.clear()

---

## 🧠 Ideal For

- Beginners learning data structures  
- Practicing linked list logic without built-in types  
- Jupyter notebook-based visual exploration

---

## ✅ Dependencies

No external libraries needed — works in plain Python 3.

---

## 📁 File

- `Linked_List.ipynb` → Complete implementation with explanations and usage examples

---

# 📊 Dynamic Array Implementation in Python

This notebook implements a **Dynamic Array** from scratch in Python using low-level C-type arrays via the `ctypes` library. It mimics Python's built-in list but demonstrates how dynamic resizing and array operations work internally.

---

## 📝 Features and Operations

The class `MeraList` supports:

### 1. Creating the Dynamic Array
- Uses a low-level C-style array to store elements.
- Starts with initial capacity of 1.

### 2. Length (`len`)
- Returns the current number of elements in the array.

### 3. Append
- Adds an element at the end.
- Automatically resizes (doubles capacity) when full.

### 4. Pop
- Removes and returns the last element.
- Handles empty array gracefully.

### 5. Clear
- Empties the array, resets capacity to 1.

### 6. Find
- Searches for an element and returns its index.
- Returns error message if not found.

### 7. Insert
- Inserts an element at a specified index.
- Shifts subsequent elements right.
- Resizes if needed.

### 8. Remove
- Removes the first occurrence of an element by value.
- Uses the find method to get index, then deletes.

### 9. Delete by Index
- Deletes element at given position.
- Shifts subsequent elements left.

### 10. Indexing
- Supports element access via indexing (`obj[index]`).
- Handles out-of-bounds with error message.

### 11. String Representation
- Prints array elements like a Python list (e.g. `[1, hello, True]`).

---

## ⚙️ Implementation Details

- Uses `ctypes.py_object` to create fixed-size C-style arrays.
- Automatically doubles array size when capacity is reached.
- Manual element shifting for insertions and deletions.
- Negative indexing, slicing, sorting, and advanced features can be added later.

---

## 📌 Example Usage

L = MeraList()

# Append items
L.append(1)
L.append('hello')
L.append(False)
print(L)  # [1,hello,False]

# Length
print(len(L))  # 3

# Indexing
print(L[1])  # hello

# Pop last element
L.pop()  # prints: False
print(L)  # [1,hello]

# Find element index
print(L.find('hello'))  # 1
print(L.find('world'))  # ValueError - not in list

# Insert at position
L.insert(1, "new")
print(L)  # [1,new,hello]

# Delete by index
del L[2]
print(L)  # [1,new]

# Remove by value
L.remove("new")
print(L)  # [1]

# Clear array
L.clear()
print(L)  # []

---

# Hashing with Linear Probing in Python

This repository contains a beginner-friendly implementation of a **Hash Table** using **Linear Probing** collision resolution technique in Python. It demonstrates insertion, retrieval, and collision handling through open addressing.

---

## 📂 Contents

- `hashing_linear_probing.ipynb` – Implementation of a dictionary (hash table) with linear probing.

---

## Dictionary Class Overview

The `Dictionary` class maintains two arrays internally:
- `slots`: stores keys
- `data`: stores corresponding values

It supports:
- Insertion (`put`)
- Retrieval (`get`)
- Collision handling via linear probing (`rehash`)

---

## Code Implementation

```python
class Dictionary:
    def __init__(self, size):
        self.size = size
        self.slots = [None] * self.size  # Array to hold keys
        self.data = [None] * self.size   # Array to hold values

    def put(self, key, value):
        hash_value = self.hash_function(key)
        if self.slots[hash_value] is None:
            self.slots[hash_value] = key
            self.data[hash_value] = value
        else:
            if self.slots[hash_value] == key:
                self.data[hash_value] = value  # Update existing key
            else:
                new_hash = self.rehash(hash_value)
                while self.slots[new_hash] is not None and self.slots[new_hash] != key:
                    new_hash = self.rehash(new_hash)
                if self.slots[new_hash] is None:
                    self.slots[new_hash] = key
                    self.data[new_hash] = value
                else:
                    self.data[new_hash] = value  # Update existing key

    def get(self, key):
        start_slot = self.hash_function(key)
        position = start_slot
        while self.slots[position] is not None:
            if self.slots[position] == key:
                return self.data[position]
            position = self.rehash(position)
            if position == start_slot:
                return "Not Found"
        return "Not Found"

    def __getitem__(self, key):
        return self.get(key)

    def __setitem__(self, key, value):
        self.put(key, value)

    def rehash(self, old_hash):
        return (old_hash + 1) % self.size

    def hash_function(self, key):
        return abs(hash(key)) % self.size

    def __str__(self):
        result = []
        for i in range(self.size):
            if self.slots[i] is not None:
                result.append(f"{self.slots[i]} : {self.data[i]}")
        return " ".join(result)

```

# Hashing with Chaining in Python

This project implements a **hash table using chaining** to handle collisions. The chaining method uses linked lists to store multiple key-value pairs that hash to the same index.

---

## Overview

- The hash table uses an array (`buckets`) where each element is a linked list (`LL`) of nodes.
- Each node contains a `key` and a `value`.
- Supports insertion (`put`), retrieval (`get`), deletion (`del`), traversal, and resizing (rehashing).
- When the load factor (size/capacity) exceeds 2, the table doubles in size and all elements are rehashed.

---

## Code Implementation

```python
class Node:
    """
    Node class to store key-value pairs for the linked list.
    
    Example:
    # Name : python # 'Name' is key and 'python' is value
    # age : 42      # 'age' is key and 42 is value
    """
    def __init__(self, key, value):
        self.key = key
        self.value = value
        self.next = None

class LL:
    """
    Linked List implementation to handle collisions in hash table buckets.
    """

    def __init__(self):
        self.head = None

    def add(self, key, value):
        new_node = Node(key, value)
        if self.head is None:
            self.head = new_node
        else:
            temp = self.head
            while temp.next is not None:
                temp = temp.next
            temp.next = new_node

    def delete_head(self):
        if self.head is None:
            return "Empty"
        else:
            self.head = self.head.next

    def remove(self, key):
        if self.head is None:
            return "Empty"
        if self.head.key == key:
            self.delete_head()
            return
        temp = self.head
        while temp.next is not None:
            if temp.next.key == key:
                break
            temp = temp.next
        if temp.next is None:
            return "Not Found"
        else:
            temp.next = temp.next.next

    def traverse(self):
        temp = self.head
        while temp is not None:
            print(f"{temp.key} : {temp.value}  ", end="")
            temp = temp.next

    def size(self):
        temp = self.head
        counter = 0
        while temp is not None:
            counter += 1
            temp = temp.next
        return counter

    def search(self, key):
        temp = self.head
        pos = 0
        while temp is not None:
            if temp.key == key:
                return pos
            temp = temp.next
            pos += 1
        return -1

    def get_node_at_index(self, index):
        temp = self.head
        counter = 0
        while temp is not None:
            if counter == index:
                return temp
            temp = temp.next
            counter += 1

class Dictionary:
    """
    Hash table implementation using chaining via linked lists.
    """

    def __init__(self, capacity):
        self.capacity = capacity  # Number of buckets
        self.size = 0             # Number of key-value pairs stored
        self.buckets = self.make_array(self.capacity)  # Array of linked lists

    def make_array(self, capacity):
        L = []
        for _ in range(capacity):
            L.append(LL())
        return L

    def __setitem__(self, key, value):
        self.put(key, value)

    def __getitem__(self, key):
        return self.get(key)

    def __delitem__(self, key):
        bucket_index = self.hash_function(key)
        self.buckets[bucket_index].remove(key)
        self.size -= 1

    def __str__(self):
        for bucket in self.buckets:
            bucket.traverse()
        return ""

    def __len__(self):
        return self.size

    def get(self, key):
        bucket_index = self.hash_function(key)
        res = self.buckets[bucket_index].search(key)
        if res == -1:
            return "Not Present"
        else:
            node = self.buckets[bucket_index].get_node_at_index(res)
            return node.value

    def put(self, key, value):
        bucket_index = self.hash_function(key)
        node_index = self.get_node_index(bucket_index, key)
        if node_index == -1:
            # Insert new node
            self.buckets[bucket_index].add(key, value)
            self.size += 1
            load_factor = self.size / self.capacity
            print(load_factor)
            if load_factor >= 2:
                self.rehash()
        else:
            # Update existing node value
            node = self.buckets[bucket_index].get_node_at_index(node_index)
            node.value = value

    def rehash(self):
        self.capacity *= 2
        old_buckets = self.buckets
        self.size = 0
        self.buckets = self.make_array(self.capacity)
        for bucket in old_buckets:
            for i in range(bucket.size()):
                node = bucket.get_node_at_index(i)
                self.put(node.key, node.value)

    def get_node_index(self, bucket_index, key):
        return self.buckets[bucket_index].search(key)

    def hash_function(self, key):
        return abs(hash(key)) % self.capacity

# Example to demonstrate linked list creation and behavior
L = []
for i in range(3):
    L.append(LL())
L

L = [LL()] * 3
L

L = LL()
L.add(2, 3)
L.add(4, 5)
L.add(6, 7)
L.traverse()  # Output: 2 : 3   4 : 5   6 : 7

L.get_node_at_index(0).key  # Output: 2

# Example usage of Dictionary (hash table)

# 1. Insert operation
D1 = Dictionary(3)
D1.put("c", 20000)          # Load factor prints: 0.3333
D1.buckets[0].traverse()    # Output: c : 20000

D1.put("java", 30000)       # Load factor prints: 0.6666
D1.buckets[1].traverse()    # Output: java : 30000

D1.put("c++", 10000)        # Load factor prints: 1.0
D1.buckets[2].traverse()    # Output: c++ : 10000

D1.put("nodejs", 100)       # Load factor prints: 1.3333
D1.buckets[1].traverse()    # Output: c : 20000   nodejs : 100

D1.put("javascript", 40000) # Load factor prints: 1.6666
D1.buckets[0].traverse()    # Output: java : 30000   c++ : 10000

D1.put("react", 70000)      # Load factor prints: 2.0, triggers rehashing
# After rehashing, load factors during reinsertion:
# 0.1666, 0.3333, 0.5, 0.6666, 0.8333, 1.0

D1.put("flutter", 90000)    # Load factor prints: 1.1666
D1.put("laravel", 110000)   # Load factor prints: 1.3333
D1.put("django", 12000)     # Load factor prints: 1.5
D1.put("html", 14000)       # Load factor prints: 1.6666
D1.put("css", 13000)        # Load factor prints: 1.8333

# 2. Update operation
D1.put("java", 5000)
D1.buckets[0].traverse()    # Output: java : 5000

# 3. Fetch operation
print(D1["java"])           # Output: 5000
print(D1["css"])            # Output: 13000
print(D1["c"])              # Output: 20000
print(D1["c++"])            # Output: 10000
print(D1["javascript"])     # Output: 40000
print(D1["nodejs"])         # Output: 100
print(D1["hgre"])           # Output: 'Not Present'

# 4. Traverse all items
print(D1)                   # Prints all key-value pairs

# 5. Delete operation
del D1["java"]
print(D1["java"])           # Output: 'Not Present'
print(D1)                   # Prints all except 'java'

# 6. Length of Dictionary
print(len(D1))              # Output: 10

```

## 🎉 That's it!

Thanks for checking out this repository! Feel free to explore, modify, and experiment with the notebooks. Happy coding and data structuring!
