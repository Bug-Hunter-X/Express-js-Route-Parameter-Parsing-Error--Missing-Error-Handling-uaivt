# Express.js Route Parameter Parsing Error: Missing Error Handling

This repository demonstrates a common error in Express.js route handling where a missing error check for invalid route parameters can cause unexpected behavior or application crashes.  The `bug.js` file shows the erroneous code, while `bugSolution.js` provides a corrected version.

## Bug Description

The bug lies in the `/users/:id` route.  The code attempts to parse the `id` parameter as an integer and then uses it to find a user. If `id` is not a valid integer (e.g., it's a string or contains non-numeric characters), `parseInt(userId)` will return `NaN`, leading to the `users.find()` function failing to find the user even if such a user exists.  This may result in a 500 Internal Server Error, or unexpected behavior if the code doesn't adequately handle this case.

## Solution

The solution involves adding input validation to explicitly handle cases where the route parameter is not a valid integer.  This ensures that the application gracefully handles invalid input, preventing crashes and providing informative error messages to the client.