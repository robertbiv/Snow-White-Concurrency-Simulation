Snow White Concurrency Simulation

Description:
This project implements a concurrent simulation of the Snow White story using the BACI (Ben-Ari Concurrent Interpreter) system. It demonstrates process synchronization, semaphore usage, and atomic output handling across multiple concurrent actors.

The simulation coordinates five distinct processes (Queen, Old Peddler, Huntsman, Snow White, and Dwarves) to tell the story in a specific chronological order while allowing for concurrent execution and random interleaving of non-critical events.

System Requirements:
- BACI (Ben-Ari Concurrent Interpreter) environment installed.
- A Linux environment (or compatible system) to run the BACI compiler and interpreter.

Files:
- *.cm: The main C-- source code file containing the concurrent process logic.

How to Compile and Run:
1. Open a terminal in the directory containing the source code.
2. Compile the source file using the BACI compiler:
   bacc sourcefile.cm
   (Replace 'sourcefile.cm' with the actual filename)
3. Run the compiled executable using the BACI interpreter:
   bainterp sourcefile
   (Or './sourcefile' depending on your specific BACI installation setup)

Technical Details:
- Concurrency: The program uses `cobegin`/`coend` to launch multiple processes simultaneously.
- Synchronization: Binary semaphores are used to enforce the strict narrative dependency graph (e.g., The Huntsman cannot spare Snow White before the Queen orders the hunt).
- Atomicity: A dedicated semaphore protects standard output to ensure print statements from different processes do not interleave in the middle of a line.
- Randomness: `DelayRandom()` introduces variable timing to simulate realistic concurrent behavior.

Output:
The program produces a text-based story output. Due to the concurrent nature, the exact timing of independent events may vary between runs, but the causal logic of the story remains consistent.
