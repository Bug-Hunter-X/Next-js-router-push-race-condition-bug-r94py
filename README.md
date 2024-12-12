# Next.js router.push Race Condition Bug

This repository demonstrates a race condition that can occur when using `router.push()` in Next.js. The bug occurs when additional actions are performed after `router.push()` is called. These actions might interfere if not handled gracefully, leading to unexpected behaviour.

## Bug Description

The `router.push()` function is asynchronous. If the following code attempts to interact with the DOM after `router.push()` but before the route change is completed, unexpected behaviour may arise.  This issue becomes more apparent when dealing with complex state management or third-party libraries.

## Solution

The solution involves using the `router.events` to monitor route changes and perform actions after successful navigation.  This ensures all actions are performed in the proper order, avoiding race conditions.   Alternative solutions may involve promises or async/await functions to properly sequence the operations.
