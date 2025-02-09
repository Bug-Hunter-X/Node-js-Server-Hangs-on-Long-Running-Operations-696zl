# Node.js Server Hang

This repository demonstrates a common issue in Node.js where a server can hang due to long-running synchronous operations that block the event loop.  The `bug.js` file showcases this problem, while `bugSolution.js` provides a solution using asynchronous programming.

## Problem

Node.js is single-threaded.  If a long-running operation blocks the event loop (like a 5-second `while` loop in the example), incoming requests will not be processed, leading to a unresponsive server.  This can significantly impact performance and user experience.

## Solution

The solution involves using asynchronous programming techniques (like `setTimeout` or promises) to avoid blocking the event loop. This allows Node.js to continue processing other requests while the long-running task executes in the background.