# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. Specifically, the `/users/:id` route does not handle cases where the `id` parameter is not a valid integer.

## Bug Description

The `/users/:id` route attempts to parse the `id` parameter as an integer using `parseInt()`. However, it does not check if the parsed value is actually a valid integer. If the `id` parameter is not a number (e.g., a string or a non-numeric value), `parseInt()` will return `NaN`. This will result in an error during the search for the user, causing the application to crash or behave unexpectedly.

## Solution

The solution involves adding proper error handling to check if `parseInt(userId)` returns a valid integer.  We use `isNaN()` to ensure that the parsed ID is a valid number.