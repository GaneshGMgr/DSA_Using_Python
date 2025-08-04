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

## 🎉 That's it!

Thanks for checking out this repository! Feel free to explore, modify, and experiment with the notebooks. Happy coding and data structuring!
