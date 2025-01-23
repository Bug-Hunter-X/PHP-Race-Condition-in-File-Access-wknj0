# PHP Race Condition in File Access

This repository demonstrates a race condition in PHP that occurs when multiple processes try to update the same file concurrently. The `bug.php` file shows the problematic code.  The `bugSolution.php` provides a solution using file locking to prevent this issue.

## The Problem
The issue arises from the lack of synchronization when two (or more) threads attempt to read, modify, and write back to a file.  The classic counter example highlights how one or more increments could be lost.

## The Solution
The solution involves using `flock()` to acquire an exclusive lock on the file before accessing it. This ensures that only one process can modify the file at a time, preventing the race condition.