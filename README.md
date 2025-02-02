# React UseEffect setInterval Memory Leak
This example demonstrates a common mistake in React: using `setInterval` within the `useEffect` hook without proper cleanup.  This leads to memory leaks and unexpected behavior, particularly when the component unmounts.

The `bug.js` file contains the flawed component. The `bugSolution.js` file provides a corrected version.

**How to reproduce:** Run the `bug.js` component. You'll notice that the counter continues to increment even after the component is unmounted (if you try to unmount it by setting the component to only render conditionally). 

**Solution:** Use the `clearInterval` method to clear the interval in the cleanup function of useEffect.