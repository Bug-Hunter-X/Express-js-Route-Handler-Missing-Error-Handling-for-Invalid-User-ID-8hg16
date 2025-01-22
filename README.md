# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The provided `bug.js` file shows a route that is vulnerable to crashing if the user ID is not a valid integer.

The `bugSolution.js` file provides a corrected version with proper error handling.

## Bug

The original code attempts to parse a user ID as an integer without checking its validity.  If the ID is not a number (e.g., a string, or null), `parseInt` will return `NaN`, leading to a failure in the `find` method and potential crashes.

## Solution

The solution involves adding input validation to the route handler.  Before attempting to parse the ID as an integer, it checks if the ID is a valid number using `isNaN`. If it's not a number, it returns a 400 Bad Request response.  This prevents unexpected crashes and provides a clear error message to the client.