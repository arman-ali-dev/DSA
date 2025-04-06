## 📌 What is a Vector?

- A **vector** is a dynamic array from C++ STL.
- It can **increase or decrease its size** automatically at runtime.
- Unlike arrays, you don’t need to define the size while declaring it.

---

## 🔧 Syntax
```cpp
#include <vector>

vector<int> v; // Creates an empty vector of integers
```

---

## 🧠 Internal Working of Vectors

- Vectors are internally implemented using **dynamic arrays**.
- When you do `v.push_back(x)` and the current capacity is full:
  - A **new array** with **double capacity** is created.
  - Old elements are **copied** into the new array.
  - Old array is **deleted**.
- This is why `push_back()` is **amortized O(1)**, not always O(1).

### 📌 Example:
- Initial capacity = 1 → insert 1 element → capacity = 1  
- Now insert another → capacity doubles → new capacity = 2  
- Insert again → capacity doubles → capacity = 4  
- And so on...

---

## 🔹 Initialization Examples
```cpp
vector<int> a;              // Empty vector
vector<int> b(5);           // Vector of size 5 with default values 0
vector<int> c(5, 10);       // [10, 10, 10, 10, 10]
vector<int> d = {1, 2, 3};  // Initialized with values
```

---

## 🔄 Traversing a Vector
```cpp
// Normal for loop
for(int i = 0; i < v.size(); i++) {
    cout << v[i] << " ";
}

// Range-based loop
for(int x : v) {
    cout << x << " ";
}

// Iterator
for(auto it = v.begin(); it != v.end(); it++) {
    cout << *it << " ";
}
```

---

## 🔍 Important Functions

| Function        | Description                          |
|----------------|--------------------------------------|
| `v.push_back(x)` | Adds element x at the end            |
| `v.pop_back()`   | Removes last element                 |
| `v.size()`       | Returns number of elements           |
| `v.capacity()`   | Returns current allocated capacity   |
| `v.clear()`      | Clears all elements (vector becomes empty) |
| `v.empty()`      | Returns true if vector is empty      |
| `v.at(i)`        | Returns element at index i (with bounds check) |
| `v.front()`      | First element                        |
| `v.back()`       | Last element                         |

---

## ⏱️ Time Complexity

| Operation       | Time Complexity   |
|----------------|-------------------|
| `push_back()`   | O(1) Amortized    |
| `pop_back()`    | O(1)              |
| `insert()`      | O(n)              |
| `erase()`       | O(n)              |
| `access ([])`   | O(1)              |

---

