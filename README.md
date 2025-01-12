# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common React bug involving the improper use of `setInterval` within the `useEffect` hook.  The uncorrected code leads to a memory leak because the interval continues to run even after the component is unmounted. This example showcases the problem and provides a corrected version.

## Bug Description
The `setInterval` function is used to update a counter every second. However, because there's no mechanism to clear the interval when the component unmounts, the interval continues to run, creating a memory leak.

## Solution
The solution involves using the return value of `useEffect` to clear the interval before the component is unmounted using `clearInterval`.