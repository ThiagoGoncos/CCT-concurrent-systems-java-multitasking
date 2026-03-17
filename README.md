# Concurrent Systems – Java Concurrency Project

## Project Overview

This project was developed as part of the **Concurrent Systems module** at **CCT College Dublin**.

The objective of the assignment was to demonstrate the use of **concurrent programming techniques in Java** to perform computational tasks more efficiently.

The program processes a dataset of **200 numeric values stored in a CSV file** and performs three main tasks:

1. Calculate the **standard deviation** of the dataset
2. Multiply two **10x10 matrices** using concurrent techniques
3. Sort all numbers using a **parallel merge sort algorithm**

Each task uses a different concurrency approach available in Java, allowing the program to demonstrate several parallel programming techniques.

---

## Project Objectives

The main goals of this assignment were:

- Demonstrate understanding of **Java concurrency concepts**
- Implement parallel algorithms using different concurrency models
- Apply concurrent processing to numerical computations
- Compare different concurrency mechanisms in Java

The project focuses on using:

- **Threads**
- **ExecutorService**
- **Fork/Join Framework**

These techniques allow tasks to run in parallel, improving performance and demonstrating practical concurrent programming patterns.

---

## Dataset

The program reads **200 numerical values** from a CSV file.

The dataset is used for three purposes:

- Calculating statistical metrics
- Building matrices for multiplication
- Performing sorting operations

The data is loaded from the CSV file using a custom class responsible for reading and converting the values into a numerical array.

---

## Program Workflow

The program performs the following sequence of operations:

1. Read numerical values from the CSV file
2. Calculate the mean of the dataset
3. Calculate the **standard deviation using Fork/Join**
4. Split the dataset into two **10x10 matrices**
5. Multiply the matrices using **two concurrency approaches**
6. Sort all numbers using **parallel merge sort**
7. Display results in the console

This workflow demonstrates how different concurrent algorithms can operate on the same dataset.

---

## Standard Deviation Calculation

The first computational task calculates the **standard deviation** of the dataset.

The program uses the **Fork/Join Framework**, which is designed for tasks that can be divided into smaller subtasks.

The algorithm works as follows:

1. The dataset is divided into smaller sections.
2. Each section calculates the **sum of squared differences from the mean**.
3. The results from each section are combined.
4. The final standard deviation is calculated.

Fork/Join improves performance by allowing different parts of the dataset to be processed simultaneously.

---

## Matrix Multiplication

The program converts the dataset into two **10x10 matrices**.

The first 100 numbers fill matrix **A**, and the next 100 numbers fill matrix **B**.

Two different concurrency techniques are used to multiply the matrices.

### Matrix Multiplication Using Threads

The first approach uses **manual thread creation**.

- One thread is created for each matrix row
- Each thread calculates all values in that row
- Threads run simultaneously
- The program waits for all threads to finish using `join()`

This demonstrates the use of **basic Java threading**.

---

### Matrix Multiplication Using ExecutorService

The second approach uses **ExecutorService**, which manages a pool of worker threads.

Instead of manually creating threads:

- A thread pool is created
- Each row calculation is submitted as a task
- The executor manages task scheduling

This approach is considered more scalable and safer for larger systems.

---

## Parallel Merge Sort

The final task sorts all numbers using **Merge Sort implemented with the Fork/Join framework**.

Merge Sort works by:

1. Splitting the dataset into smaller sections
2. Sorting each section independently
3. Merging the sorted sections together

Using Fork/Join allows multiple sorting tasks to run concurrently.

The final result is a list of numbers sorted in **descending order**.

---

## Technologies Used

The project was implemented using the following technologies.

### Java

The program was developed in **Java**, using its built-in concurrency features.

### Java Concurrency APIs

Several concurrency mechanisms were used:

- **Threads** – basic concurrency model
- **ExecutorService** – thread pool management
- **ForkJoinPool** – parallel task processing

### Java Utilities

Additional Java features used include:

- Arrays
- Streams
- BufferedReader for file input
- Recursive tasks for parallel algorithms

---

## Key Classes in the Project

The program is organised into multiple classes, each responsible for a specific task.

### ConcurrentRunner

Main class that controls the full execution of the program.

It:

- Loads the dataset
- Runs the standard deviation calculation
- Executes matrix multiplication
- Performs parallel sorting

---

### DataReader

Utility class responsible for reading the CSV file and converting its values into a numerical array.

---

### StandardDeviation

Implements a **Fork/Join recursive task** used to compute the sum of squared differences from the mean.

This is a key step in calculating the standard deviation.

---

### MatrixCalculation

Implements matrix multiplication using **manual threads**.

Each thread calculates one row of the result matrix.

---

### MatrixCalcExecutor

Implements matrix multiplication using **ExecutorService** and a thread pool.

Each row is processed as a task submitted to the executor.

---

### DataSorter

Implements a **parallel merge sort algorithm** using the Fork/Join framework.

The dataset is recursively split into smaller tasks which run concurrently.

---

## Learning Outcomes

This project demonstrates several important concepts in concurrent programming:

- Parallel computation
- Thread creation and management
- Task parallelism
- Fork/Join framework
- Concurrent sorting algorithms
- Efficient handling of computational workloads

These concepts are essential for building **high-performance software systems** that can process large datasets efficiently.

---

## Author 

This project was developed by **Thiago Goncalves da Costa** as part of the **Bachelor of Science in Computing and Information Technology** at **CCT College Dublin**.

During my studies, I used the institutional GitHub account associated with my student email:

2022161@student.cct.ie

Since institutional accounts and student emails may be deactivated after graduation, this repository was migrated to my personal GitHub account:

https://github.com/ThiagoGoncos

This ensures long-term preservation of the project, commit history, and academic work completed during the degree program.