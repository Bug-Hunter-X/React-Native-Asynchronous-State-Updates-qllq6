# React Native Asynchronous State Updates Bug

This repository demonstrates a common bug in React Native applications related to asynchronous state updates.  When updating state using `useState` or `useReducer`, the update doesn't happen immediately.  Attempting to access the updated state immediately after the update will result in accessing the previous state's value.

## Bug Description
The `bug.js` file contains a simple counter component.  The `incrementCount` function updates the count state, but then immediately logs the count.  Because the state update is asynchronous, the logged value will be the *old* count, not the updated one.

## Solution
The solution is to access the updated state value only *after* the state update has completed. This can typically be done by using the updated state value within the functional component's rendering process. React will re-render after the state update, ensuring you work with the correct value.

The `bugSolution.js` file demonstrates the corrected code.

## How to Reproduce
Clone this repository and run `npx react-native run-android` (or the iOS equivalent).  Observe that the console log shows the old count value, not the new one. Modify the code to reflect the correction shown in the solution.

## Technologies Used
* React Native
* JavaScript