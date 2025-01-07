# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug: an infinite loop caused by improper use of the `useEffect` hook.  The `useEffect` hook, while powerful, can lead to unexpected behavior if the dependencies aren't managed correctly.

## The Bug

The `bug.js` file contains a component that attempts to increment a counter within a `useEffect` hook. The problem is that the dependency array is empty (`[]`), meaning the effect runs only once after the initial render. However, the effect itself modifies the `count` state, which triggers a re-render, leading to the effect running again and again, resulting in an infinite loop and potential crashes.

## The Solution

The `bugSolution.js` file provides a corrected version.  By adding `count` to the dependency array (`[count]`), the effect now only runs when the `count` value changes. This prevents the infinite loop, ensuring the counter increments only as expected.