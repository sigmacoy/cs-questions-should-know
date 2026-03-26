# Questions every comp-sci major should know

1. [What is an algorithm?](#1-what-is-an-algorithm)
2. [Array vs. Linked List](#2-array-vs-linked-list)
3. [What is the role of an Operating System (OS)?](#3-what-is-the-role-of-an-operating-system-os)
4. [What is Big O notation?](#4-what-is-big-o-notation)
5. [Compiler vs. Interpreter](#5-compiler-vs-interpreter)
6. [Concurrency vs Parallelism](#6-concurrency-vs-parallelism)

## 1. What is an algorithm?
An algorithm is a finite, well-defined sequence of steps or rules designed to perform a specific task or solve a particular problem. It takes an input, processes it through a series of deterministic instructions, and produces an output. Beyond just being a set of instructions, an algorithm must be correct (producing the right output for all inputs), finite (terminating after a finite number of steps), and efficient in its use of resources like time and memory. From a simple recipe for baking a cake to complex routing protocols on the internet, algorithms are the fundamental building blocks of all software.

Step-by-step procedure to solve a problem or perform computation. (Finite sequence of unambiguous instructions that transforms input to output)

## 2. Array vs. Linked List
An array stores elements in contiguous memory locations and allows fast random access using an index in O(1) time, but inserting or deleting elements is slow because elements need to be shifted. A linked list stores elements as nodes connected by pointers in non-contiguous memory, so access is slower (O(n)), but insertion and deletion are faster because only pointers need to be updated.

## 3. What is the role of an Operating System (OS)?
The operating system acts as a privileged intermediary between the user applications and the computer hardware. Its primary role is abstraction and resource management. It abstracts away the complexity of raw hardware—such as CPUs, RAM, and storage—providing a clean, consistent interface (like files, processes, and sockets) for application developers. Concurrently, it manages the finite physical resources of the system, arbitrating which processes get CPU time (scheduling), how much memory they can use (memory management), and how they access I/O devices, ensuring system stability, security, and fair performance across multiple running applications.

## 4. What is Big O notation?
Big O notation is a mathematical concept used in computer science to describe the upper bound or worst-case scenario of an algorithm's growth rate as the input size ($n$) approaches infinity. It classifies algorithms by how their runtime (time complexity) or memory usage (space complexity) scales with input size, ignoring constants and lower-order terms. For example, $O(1)$ denotes constant time (e.g., array access), $O(n)$ denotes linear time (e.g., a simple loop), and $O(n^2)$ denotes quadratic time (e.g., a nested loop). It provides a high-level, hardware-independent language to compare the efficiency and scalability of different algorithms, helping developers predict performance bottlenecks as data volumes grow.

More

Time Complexity: How runtime grows with input size
Space Complexity: How memory usage grows with input size
**Examples**:
- O(1): Constant - direct array access
- O(log n): Logarithmic search or binary search
- O(n): Linear - iterating through array
- O(n²): Quadratic - nested loops
**For example: A Leetcode problem constraint is 10⁵**:  
Need O(n) or O(n log n) solution  
O(n²) = 10¹⁰ operations → too slow

## 5. Compiler vs. Interpreter
**Compiler** translates entire source code to machine code **before execution**:
- **C++**, **C**: Compiled to native machine code
- **Java**: Compiled to bytecode (then interpreted by JVM)
**Interpreter** translates and executes code **line by line during runtime**:
- **Python**: Interpreted line by line 
- **JavaScript**: Interpreted in browsers
**Key differences**:
- **Compiler**: Faster execution, but slower startup (needs compilation)
- **Interpreter**: Slower execution, but immediate execution (no separate compile step)
**Java is both**: Compiled to bytecode, then interpreted by JVM (with JIT compilation)
Python: (.py → bytecode → PVM execution)

## 6. Concurrency vs Parallelism 
Concurrency is about dealing with multiple tasks at once, focusing on structure and task interleaving where tasks make progress in overlapping time periods, but not necessarily simultaneously—it enables a single-core system to handle multiple operations by switching between them.
Parallelism, in contrast, is about doing multiple tasks at the exact same time, requiring multiple processing units to execute operations simultaneously. Concurrency is about managing complexity and dealing with many things at once, while parallelism is about throughput and executing many things at once. They are related but distinct: you can have concurrency without parallelism (single-core multitasking), but parallelism inherently enables concurrency.

## 7. What is OOP?
The four pillars of Object-Oriented Programming (OOP) are encapsulation, abstraction, inheritance, and polymorphism. Encapsulation bundles data and methods into objects while hiding internal details; abstraction simplifies complexity by exposing only essential features; inheritance allows new classes to reuse and extend existing code; polymorphism enables objects of different types to be treated uniformly through a common interface. OOP is important because it promotes modularity, reusability, and maintainability, making complex software easier to design, debug, and scale. It is widely applied in GUI applications, game development, enterprise systems (like Java Spring), simulations, and mobile app development, where modeling real-world entities as objects naturally aligns with problem domains.

## 8. What is deadlock?

## 9. Process vs Threads?
**Process**: Independent program with own memory space
- Isolated, crash doesn't affect others
- Heavyweight, more overhead
**Thread**: Lightweight unit within a process
- Shares memory with other threads
- Fast creation, but less isolated
**Example**: Browser = process, each tab = thread


## 10. What is race condition?
When multiple threads access shared data simultaneously, and the final result depends on the timing of their execution.
```java
int balance = 100;

void withdraw(int amount) {
    if (balance >= amount) {
        balance = balance - amount;  // RACE CONDITION HERE
    }
}
```
**Thread 1**: `withdraw(80)` → checks balance (100), thinks it's OK  
**Thread 2**: `withdraw(80)` → also checks balance (100), thinks it's OK  
**Both subtract 80**: Balance becomes -60 (wrong!)
**Final result depends on timing** - if threads ran sequentially, only one would succeed.
Soln: Use `synchronized` keyword
```java
synchronized void withdraw(int amount) {
    if (balance >= amount) {
        balance -= amount;
    }
}
```
This makes threads take turns, preventing the race condition.

## 11. What is Dynamic Programming?
Dynamic Programming = Solving complex problems by breaking into overlapping subproblems and storing results to avoid recomputation. Either memoization (top-down) or Tabulation (bottom-up). Algorithm technique to optimization problems.

## 12. What is mutex?
The method used by the OS (along with other alternatives) to protect a common memory section from 2 or more threads accessing it at the same time., specially useful if both threads are interconnected and can cause deadlocks.

## 13. Given problem
``` cpp
Object obj = new Object();
Object *obj = new Object();
```
### Why do we even use *obj ?
- Object needs to outlive the scope → survives after function returns
- Large objects → stack has limited size (typically 1-8 MB), heap is much larger
- Polymorphism → dynamic binding with virtual functions works properly
- Unknown size at compile time → arrays, containers, etc.
- Manual control → you decide exactly when it's created and destroyed

## 14. RAM vs ROM
RAM (Random Access Memory) - temporary and volatile, losing its data when the device loses power. 
ROM is generally considered permanent or non-volatile memory, meaning it retains its data even when the power is turned off.
Most ROM are permanent, newer types can be rewritten under special circumstances, although they still function as a permanent storage for essential system like the BIOS and firmware. 

## 15. Supervised vs Unsupervised
Supervised - given input and needed correct output
	- uses labeled data (input-output pairs)
Unsupervised - the model learns by itself
	- finds patterns in unlabeled data without predefined outputs.

## 16. What is CPU?
- Central Processing Unit
It's the brain that runs all programs and processes.
Algorithm of the CPU is:
1. **Fetch** - get instruction from memory
2. **Decode** - understand what to do
3. **Execute** - perform the operation
Repeats billions of times per second.

## 17. Stack vs Heap
**Stack**: Automatic memory for function calls and local variables - size known at compile time, automatically cleaned when function exits.
Heap: Dynamic memory you manually allocate (with `new`, `malloc`) - size unknown at compile time, lives until you `free` it.

### Why even store in the heap? even tho heap is slower:
**Stack size is limited** (typically 1-8MB), while **heap can use all available RAM**.
Large data structures, dynamic allocations, or long-lived objects must go on heap.
