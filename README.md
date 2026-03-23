# Questions every comp-sci major should know

1. [What is an algorithm?](#1-what-is-an-algorithm?)
2. [Array vs. Linked List](#2-array-vs-linked-list)
3. [What is the role of an Operating System (OS)?](#3-what-is-the-role-of-an-operating-system-(OS))
4. [What is Big O notation?](#4-what-is-big-o-notation)
5. [Compiler vs. Interpreter](#5-compiler-vs-interpreter)


## 1. What is an algorithm?
An algorithm is a finite, well-defined sequence of steps or rules designed to perform a specific task or solve a particular problem. It takes an input, processes it through a series of deterministic instructions, and produces an output. Beyond just being a set of instructions, an algorithm must be correct (producing the right output for all inputs), finite (terminating after a finite number of steps), and efficient in its use of resources like time and memory. From a simple recipe for baking a cake to complex routing protocols on the internet, algorithms are the fundamental building blocks of all software.

## 2. Array vs. Linked List
An array stores elements in contiguous memory locations and allows fast random access using an index in O(1) time, but inserting or deleting elements is slow because elements need to be shifted. A linked list stores elements as nodes connected by pointers in non-contiguous memory, so access is slower (O(n)), but insertion and deletion are faster because only pointers need to be updated.

## 3. What is the role of an Operating System (OS)?
The operating system acts as a privileged intermediary between the user applications and the computer hardware. Its primary role is abstraction and resource management. It abstracts away the complexity of raw hardware—such as CPUs, RAM, and storage—providing a clean, consistent interface (like files, processes, and sockets) for application developers. Concurrently, it manages the finite physical resources of the system, arbitrating which processes get CPU time (scheduling), how much memory they can use (memory management), and how they access I/O devices, ensuring system stability, security, and fair performance across multiple running applications.

## 4. What is Big O notation?
Big O notation is a mathematical concept used in computer science to describe the upper bound or worst-case scenario of an algorithm's growth rate as the input size ($n$) approaches infinity. It classifies algorithms by how their runtime (time complexity) or memory usage (space complexity) scales with input size, ignoring constants and lower-order terms. For example, $O(1)$ denotes constant time (e.g., array access), $O(n)$ denotes linear time (e.g., a simple loop), and $O(n^2)$ denotes quadratic time (e.g., a nested loop). It provides a high-level, hardware-independent language to compare the efficiency and scalability of different algorithms, helping developers predict performance bottlenecks as data volumes grow.

## 5. Compiler vs. Interpreter
Both compilers and interpreters are programs that translate high-level source code into a form that a computer can execute, but they operate in fundamentally different ways. A compiler translates the entire source code into a standalone, low-level machine code file (e.g., an executable) in one go, before any execution occurs. This process is generally slower upfront but results in fast execution afterward. An interpreter, on the other hand, translates and executes the source code line-by-line or statement-by-statement at runtime, without generating a separate machine code file. This allows for greater flexibility and easier debugging (as execution can pause mid-run), but typically results in slower overall execution speed compared to compiled code. Languages like C and Rust are typically compiled, while Python and JavaScript are commonly interpreted (or use Just-In-Time compilation for optimization).


