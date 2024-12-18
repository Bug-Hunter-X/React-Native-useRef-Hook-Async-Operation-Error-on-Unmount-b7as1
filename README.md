# React Native useRef Hook Async Operation Error on Unmount

This repository demonstrates a common error in React Native when using the `useRef` hook with asynchronous operations.  The issue arises when a component unmounts before the asynchronous operation (e.g., a `setTimeout`, `fetch` call) completes. This can lead to unexpected behavior, including logs appearing after the component is gone and potential memory leaks.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run the app.
4. Navigate to the screen that contains the component. 
5. Quickly navigate away from that screen before the timer completes. Note the console log even after the screen is gone.

## Solution

The provided solution demonstrates how to properly handle asynchronous operations within the `useRef` hook to prevent these issues.  The key is to use the cleanup function in `useEffect` to cancel any ongoing operations when the component unmounts.