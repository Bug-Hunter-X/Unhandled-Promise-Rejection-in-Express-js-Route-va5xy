# Unhandled Promise Rejection in Express.js Route

This repository demonstrates a common error in Express.js applications: unhandled promise rejections within asynchronous route handlers.  The `bug.js` file shows an example where an asynchronous operation might fail, but the error is not properly caught and handled, leading to a silent failure. The `bugSolution.js` file provides the corrected code.

## Problem

The issue is the missing `.catch()` block in the asynchronous operation within the Express route handler.  If `someAsyncOperation()` rejects (due to the simulated error), the rejection is not handled, potentially leading to unexpected behavior or application crashes.  In production, this can be very difficult to debug.

## Solution

Proper error handling is crucial. The `bugSolution.js` file shows how to add a `.catch()` block to handle potential errors gracefully.  This approach allows for logging the error or sending an appropriate error response to the client, preventing silent failures.