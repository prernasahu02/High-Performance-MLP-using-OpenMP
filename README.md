# High-Performance Multilayer Perceptron (MLP) with OpenMP
## Introduction
This repository contains an optimized implementation of a Multilayer Perceptron (MLP) neural network in C, originally sourced from a public GitHub repository. The base implementation was analyzed through performance profiling and then optimized using OpenMP to leverage multi-core parallelism. This significantly enhances execution speed, making it suitable for high-performance computing (HPC) environments.

## Dataset: Banknote Authentication
The dataset used for this experiment is the Banknote Authentication Dataset from the UCI Machine Learning Repository. The dataset consists of features extracted from banknote images. Based on these extracted features, the goal is to classify whether a given banknote is authentic or fake. 
Example dataset used for training and testing: [Banknote authentication dataset from ULI ML Repository](https://archive.ics.uci.edu/ml/datasets/banknote+authentication)

## What is OpenMP?
**OpenMP** (Open Multi-Processing) is a widely used API for shared-memory parallel programming in C, C++, and Fortran. It provides simple compiler directives and library routines to distribute tasks across multiple CPU cores efficiently. OpenMP enables programmers to optimize computational workloads without manually handling low-level threading complexities.

## Need for High-Performance Computing (HPC)
As complex machine learning models grow, efficient computation becomes crucial for real-world applications. Traditional sequential execution often leads to excessive processing times, especially for large datasets and deep networks. High-performance computing helps by:

* Reducing execution time through multi-threading and parallelization.
* Utilizing multi-core CPU architectures to enhance efficiency.
* Optimizing resource utilization for large-scale computations.
* Improving scalability for training larger models in reasonable time frames.

## Profiling and Its Importance
Before optimizing the MLP algorithm, performance profiling was conducted to identify bottlenecks. Profiling helps analyze the execution time of different functions, loops, and memory operations to guide optimization efforts.

## Types of Profiling Used
* **Functional Profiling –** Analyzes execution time of different functions to identify slow functions.
* **Line Profiling –** Measures execution time of specific lines of code to pinpoint inefficiencies.
* **Hardware Profiling –** Uses tools like LIKWID to analyze CPU utilization, cache misses, and FLOPs.

## Optimizations Implemented
* **Parallelization with OpenMP –** Used multi-threading to distribute computations across CPU cores.
* **Optimized Forward & Backward Propagation –** Matrix multiplications parallelized for better performance.
* **Efficient Weight Updates –** Implemented optimized loop structures with minimal synchronization overhead.
* **Memory Access Optimizations –** Reduced cache misses and improved data locality.
* **Dynamic Thread Scaling –** Optimized OpenMP scheduling for balanced workload distribution.

## Performance Analysis
A detailed performance evaluation was conducted by running the parellelized perceptron implementation with varying numbers of threads. The execution times, speedup, and parallel fractions are recorded in the table below.
*     Serial Parallel Execution Time: 6.548s
![image](https://github.com/user-attachments/assets/92f00a29-7bb1-4016-a09c-7d9eaf1bf968)

![image](https://github.com/user-attachments/assets/681e16b7-7dd3-46e4-a810-1dba6a23e511)

![image](https://github.com/user-attachments/assets/bb6212e4-1456-4756-8321-bb1b27d6fedd)

*     Parallelization with thread count 32 shows the best performance.

## Source and Attribution
This project is based on the Multilayer Perceptron (MLP) implementation from manoharmukku/multilayer-perceptron-in-c, which is licensed under the **MIT License**.

## Enhancements in This Project:
* **Profiling:** Performed functional, line, and hardware profiling to analyze bottlenecks and improve performance.
* **Parallelization:** Implemented OpenMP for multi-threaded execution, significantly reducing computation time.
* **High-Performance Computing (HPC):** Optimized the MLP algorithm through OpenMP to efficiently utilize modern CPU architectures.
The original **MIT License** is included in this repository as required.


## Future Enhancements
* GPU Acceleration – Implement CUDA-based MLP for further speed improvements.

