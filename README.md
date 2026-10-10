# Thread Counting Using Static and Non-Static Variables

## 1. Overview

This project compares static and non-static counter variables in Java multithreading. It demonstrates how multiple threads access a shared static variable, how each thread maintains its own non-static counter, and how race conditions affect unsynchronized counting.

## 2. Objectives

- Understand static and non-static variables in Java.
- Observe race conditions in multithreaded programs.
- Compare thread-safe and unsafe counter implementations.
- Calculate absolute and percentage differences.
- Analyze the effect of increasing the number of threads.

## 3. Technologies Used

- Java
- Java Multithreading
- `AtomicLong`
- GitHub

## 4. Project Structure

```text
SEPM-Assignment---001-/
└── Lab_Thread_Counter/
    ├── Raiyyan_Thread.java
    ├── README.md
    ├── handwritten/
    │   ├── README.md
    │   └── handwritten_code.jpg
    ├── results/
    │   ├── README.md
    │   ├── test_1.png
    │   ├── test_2.png
    │   └── ...
    └── report/
        ├── README.md
        └── Thread_Counter_Report.pdf
```

*Note: Replace example filenames with your actual filenames.*

## 5. How to Compile and Run

Compile the Java program:

```bash
javac Raiyyan_Thread.java
```

Run the unsafe experiment:

```bash
java Raiyyan_Thread 5 10000 false
```

Run the thread-safe experiment:

```bash
java Raiyyan_Thread 5 10000 true
```

The program accepts three arguments:

- Number of threads
- Number of increments per thread
- Counter mode (`true` or `false`)

`true` uses `AtomicLong` for thread-safe counting, while `false` uses an ordinary unsynchronized static counter.

## 6. Test Cases

| Threads | Increments per Thread | Expected Count |
|---:|---:|---:|
| 1 | 1,000 | 1,000 |
| 2 | 10,000 | 20,000 |
| 5 | 10,000 | 50,000 |
| 10 | 50,000 | 500,000 |
| 20 | 50,000 | 1,000,000 |
| 50 | 50,000 | 2,500,000 |
| 100 | 50,000 | 5,000,000 |

The unsynchronized experiment is repeated at least five times for each thread count, as required by the assignment instructions.

## 7. Result Recording

Actual program outputs and screenshots are stored in the `results/` directory.

The following values are recorded for each test:

- Expected count
- Static count (unsafe)
- Non-static total
- Absolute difference
- Percentage difference

### Formulas

**Absolute Difference**

`|Static Count − Non-static Total|`

**Percentage Difference**

`(Absolute Difference / Non-static Total) × 100`

All result values should be calculated from actual program executions.

## 8. Observations

- A static variable is shared by all instances of its class.
- Each `Counter` object has its own non-static counter.
- An unsynchronized static counter may lose increments when multiple threads update it concurrently.
- `AtomicLong` provides atomic increment operations for the shared counter.
- The amount of lost updates can vary between unsafe runs.
- Increasing the number of threads does not guarantee a steadily increasing percentage difference.

## 9. Conclusion

This experiment demonstrates the differences between shared static variables and individual non-static variables in Java multithreading. It also illustrates how race conditions can produce incorrect results when multiple threads update a shared counter without synchronization. Using `AtomicLong` helps ensure correct shared-counter updates.

## 10. Submission Contents

The `Lab_Thread_Counter` directory contains the Java source code, handwritten code images, experiment output screenshots, and report PDF. The final report includes the test cases, actual outputs, result recording sheet, analysis, and conclusion.
