# Node.js Server Unresponsiveness Due to Blocking Operation

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  In this example, a simple `for` loop simulates a CPU-intensive task that blocks the event loop, preventing the server from handling subsequent requests.

## Problem

Node.js is single-threaded.  Long-running synchronous operations in the main thread block the event loop, leading to unresponsiveness. The provided `bug.js` demonstrates this scenario.  Attempts to access the server while the long operation runs will fail or time out.

## Solution

The solution involves using asynchronous operations or offloading the long-running task to a worker thread or a separate process to prevent blocking the main thread. The `bugSolution.js` demonstrates using asynchronous operations via `setTimeout` for illustrative purposes.  For more complex scenarios, consider using worker threads or a task queue.