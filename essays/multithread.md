---
layout: essay
type: essay
title: "Multithreading in Computer Science"
# All dates must be YYYY-MM-DD format!
date: 2024-03-14
published: true
labels:
  - Programming
  - Threads
---

<img width="200px" class="rounded float-start pe-4" src="../img/multithread/multithreadessayhead.jpg">

## Introduction

**Multithreading** is a widespread programming and execution model that allows multiple threads to exist within the context of a single process, sharing the process's resources but able to execute independently. The threaded programming model provides developers with a useful abstraction of concurrent execution. Multithreading can also be seen as a facet of parallelism in computation, where the execution of processes is carried out simultaneously.

## Understanding Threads

A **thread** is the smallest unit of processing that can be performed in an operating system. In most modern operating systems, a thread exists within a process - that is, a single process may contain multiple threads.

## Benefits of Multithreading

- **Responsiveness**: Multithreading can allow an application to remain responsive to input. In a one-thread program, if the main execution thread blocks on a long-running task, the entire application can appear to freeze. By moving such long-running tasks to a worker thread that runs concurrently with the main execution thread, it is possible for the application to remain responsive to user input while executing tasks in the background.

### Example of Responsiveness

Consider a word processing software. While you are typing or editing a document, the software is also performing other tasks like auto-saving the document, checking for spelling and grammar errors, and updating the display. These tasks are often handled by separate threads. If all these tasks were performed sequentially in a single thread, you might experience lag while typing, especially when the auto-save or spell-check function is running. By using multiple threads, the software remains responsive to your inputs.

---

- **Resource Sharing**: Threads share the memory and the resources of the process to which they belong. The benefit of sharing code and data is that it allows an application to have several different threads of activity within the same address space.

### Example of Resource Sharing

In a web server handling multiple requests, each request can be handled by a separate thread. All threads can share the same network and I/O resources, making the server more efficient than spawning a new process for each request.

---

- **Economy**: Because threads share the same address space, the system does not need to allocate memory for a new process. Also, context-switching between threads within the same process is typically more efficient than switching between processes.

### Example of Economy

Creating a new process requires the operating system to allocate memory and other resources. In a database system where thousands of users are querying the database simultaneously, using a thread for each user is more economical and efficient than creating a separate process for each user.

---

- **Utilization of Multiprocessor Architectures**: The benefits of multithreading can be greatly increased in systems having multiple processors. A single thread can only run on one CPU, so even on a multiprocessor machine, a single-threaded application can only run on one of those CPUs. By dividing a process into multiple threads that can run concurrently, the application can be made to run faster on a machine with multiple CPUs.

### Example of Utilization of Multiprocessor Architectures

In a video encoding application, different threads can be used to encode different parts of the video simultaneously. This can significantly reduce the encoding time on a multi-core or multi-processor system.

---

## Challenges with Multithreading

Despite the advantages, multithreading is not always the best solution. There are numerous challenges to be considered:

- **Synchronization**: Since threads share the same memory, inconsistencies can occur in situations where they try to read and write to the same data concurrently.

### Example of Synchronization

Consider a banking system where two threads are trying to update the same account. If one thread is reading the account balance while another thread is updating it, the first thread might read the wrong balance unless the operation is properly synchronized.

---

- **Deadlock**: Deadlocks can occur when two or more threads each holding a lock can cause a circular chain of threads waiting for resources.

### Example of Deadlock

In an operating system, one thread might hold a lock on the printer while waiting for the scanner, which is locked by another thread that's waiting for the printer. This circular wait can lead to a deadlock situation where neither thread can proceed.

---

- **Starvation**: Starvation describes a situation where a thread is unable to gain regular access to shared resources and is unable to make progress.

### Example of Starvation

In a ticket booking system, if high-priority threads keep coming, a low-priority thread might wait indefinitely, leading to starvation. This happens if the system always chooses the highest-priority thread.

---

- **Thread Interference**: Interference happens when two threads working on the same data interfere with each other.

### Example of Thread Interference

Consider a simple counter shared by two threads. If both threads read the counter and increment it simultaneously, they might both read the same value, increment it, and write it back, effectively only incrementing the counter once instead of twice. This is a classic example of thread interference.

---

### Example of Non-Multithreading

An example of a non-multithreaded process could be a simple command-line utility, such as a program that compresses a file. In this case, the program might only have one thread of execution, performing one operation at a time. It would start at the beginning of the file, compress it until it reaches the end, and then close. The user must wait for the entire operation to complete before regaining control of the command-line interface.

### Example of Multithreading

A common example of multithreading is a web browser. It might have one thread running the user interface (buttons and scrollbars), another downloading a file in the background, and another playing audio or video. This allows the user to navigate web pages while files are being downloaded or videos are playing, improving the overall user experience.

## Multithreading in C++

C++11 introduced a new thread library that allows for the creation of multithreaded programs. Here's a simple example of how to create threads in C++:

```cpp
#include <iostream>
#include <thread>

// This function will be called from a thread
void call_from_thread() {
    std::cout << "Hello, World" << std::endl;
}

int main() {
    // Launch a thread
    std::thread t1(call_from_thread);

    // Join the thread with the main thread
    t1.join();

    return 0;
}
```

In this example, `std::thread` is the thread class that's part of the C++ Standard Library. The `call_from_thread` function is called from `t1`, a newly created thread. The `join` function is used to make the main thread wait for the new thread to finish execution before it continues.

This is a very basic example. In real-world applications, you would typically use more advanced features of the C++ threading library, such as mutexes and condition variables, to handle synchronization between threads.

## Conclusion

Multithreading is a powerful tool for improving the performance of applications, but it must be used carefully due to the potential problems of synchronization and data consistency. However, with careful design and robust error handling, multithreading can provide significant benefits and enable the development of powerful, efficient, and responsive applications.
