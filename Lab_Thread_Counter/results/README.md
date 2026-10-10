# Test Results

This directory contains the actual program output screenshots for the thread-counting experiment.

## Included Results
- Static counter in unsafe mode (`false`)
- Static counter in thread-safe mode (`true`)
- Different thread counts and increments per thread
- Repeated unsafe-mode runs

## Test Cases

| Threads | Increments per Thread | Expected Count |
|---:|---:|---:|
| 1 | 1,000 | 1,000 |
| 2 | 10,000 | 20,000 |
| 5 | 10,000 | 50,000 |
| 10 | 50,000 | 500,000 |
| 20 | 50,000 | 1,000,000 |
| 50 | 50,000 | 2,500,000 |
| 100 | 50,000 | 5,000,000 |

The screenshots show the actual output produced during execution. Unsafe counter values may vary between runs.
