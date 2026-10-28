# Tideman Ranked-Pairs Voting

A C implementation of a ranked-pairs election algorithm. Voters rank candidates, and the program builds a directed graph of pairwise victories while preventing cycles.

## Algorithm

1. Record each voter's ranked preferences in a pairwise matrix.
2. Identify winning candidate pairs, excluding ties.
3. Sort pairs by decreasing victory margin.
4. Lock each pair only if it would not create a directed cycle.
5. Print the first candidate with no incoming locked edges.

The implementation supports up to nine candidates and uses recursive graph traversal for cycle detection.

## Build and run

Requires a C compiler and the CS50 library (`cs50.h` and `libcs50`) installed in the compiler's include/library paths.

```bash
cc tideman.c -lcs50 -o tideman
./tideman Alice Bob Charlie
```

Enter the number of voters, then each voter's candidate rankings when prompted. Candidate names must match the command-line names.

If your CS50 installation uses custom paths, supply the appropriate `-I` and `-L` flags when compiling.

## Project structure

| File | Purpose |
| --- | --- |
| `tideman.c` | Input handling, preference matrix, pair sorting, cycle detection, and winner selection |

## Technical focus

- Arrays and structs in C.
- Pairwise comparisons and sorting.
- Directed graphs and recursive cycle detection.
- Translating voting rules into an algorithm.

## Limitations

The program does not reject repeated candidate names within a ballot. Equal-strength pairs retain the order produced by the sorting implementation, and the program prints the first source candidate if more than one exists.

## Context

This project follows the CS50 Tideman exercise structure and depends on the CS50 library.
