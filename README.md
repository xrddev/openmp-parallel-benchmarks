# OpenMP Parallel Benchmarks

This repository contains a small collection of benchmark programs written in C using OpenMP, focusing on basic parallelization techniques and simple performance evaluation on shared-memory systems.

The project studies how different OpenMP constructs and scheduling policies affect execution time and scalability on a few representative problems.

The implemented benchmarks are based on three main case studies:

- **Prime number computation** using OpenMP `parallel for` with reduction, including comparison of different scheduling policies (static, dynamic, guided).
- **Gaussian blur image processing**, implemented both with loop parallelism and with OpenMP tasks.
- **Task dependency example** using a producer–consumer style pipeline with OpenMP task dependencies to enforce correct execution order.

Each program includes simple timing measurements in order to compare serial and parallel execution and observe speedup behavior.

---

## What is demonstrated

This project demonstrates:

- Basic use of OpenMP directives: `parallel`, `for`, `reduction`, `schedule`, `task`, and `depend`.
- Loop parallelism and runtime scheduling selection.
- Task-based parallelism and explicit task dependency graphs.
- Simple performance measurements and comparison between serial and parallel execution.
- Practical handling of shared data and synchronization in OpenMP programs.

---

## Contents

- `primes.c`  
  Parallel computation of prime numbers using `parallel for` and reduction, with comparison of different scheduling policies.

- `gaussian.c`  
  Gaussian blur image processing using:
  - loop-based parallelization
  - task-based parallelization

- `task_dependencies.c`  
  Example of a pipeline using OpenMP tasks with dependencies (producer–consumer pattern).

- Test images and small input data used by the benchmarks.

---

## primes.c  (Prime numbers parallelization)

How to run:

Step 1 -> 

	gcc primes.c -fopenmp

Step 2 -> 
	
 	./a.out

## gaussian.c (Applying gaussian blur to a given image)

How to run:

Step 1 ->  
            
	gcc gaussian.c -fopenmp -lm

Step 2 ->       

	./a.out <blur-radius> <filename>, 

e.g. ./a.out  2  500.bmp


### Run with different numbers of threads
- export OMP_NUM_THREADS=1
- export OMP_NUM_THREADS=4

### For the benchmarks that support runtime scheduling selection, you can use:
- export OMP_SCHEDULE=static
- export OMP_SCHEDULE=dynamic
- export OMP_SCHEDULE=guided


---

## task_dependencies.c (Task dependencies and synchronization problems)

How to run:

Step 1 -> openMP_execution_model.txt needs to be in the same scope as the task_dependencies.c file

Step 2 -> 

 	gcc task_dependencies.c

Step 3 ->

 	./a.out

  
## 👤 Author

> GitHub: [xrddev](https://github.com/xrddev)


## 📝 License

Released under the [MIT License](LICENSE). Originally built as part of a university project.

