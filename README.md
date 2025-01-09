# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling.  The `bug.js` file shows a route that's vulnerable to errors if an invalid user ID is provided. The `bugSolution.js` file provides a corrected version with comprehensive error handling. 

## Problem

The `/users/:id` route in `bug.js` does not check if the `userId` is valid or if a user with that ID exists.  If an invalid ID is passed, the application might crash or return an unhelpful error message.

## Solution

The `bugSolution.js` file addresses this by incorporating error handling.  It checks if the `userId` is a valid number and then fetches the user from the database (simulated here). If the user is not found, it sends a 404 Not Found response.  Any other errors are caught and a 500 Internal Server Error is returned with an appropriate message.