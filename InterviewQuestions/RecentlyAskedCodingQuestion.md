<details>
  <summary>
    What will be the output? 🤔

import { useState, useRef } from "react";

export default function App() {
  const [count, setCount] = useState(0);
  const ref = useRef(0);

  const handleClick = () => {
    setCount(count + 1);
    ref.current += 1;

    console.log("State:", count);
    console.log("Ref:", ref.current);
  };

  return (
    <button onClick​={handleClick}>
      {count} | {ref.current}
    </button>
  );
}

Looks simple... but there’s a twist 👀

👉 What will be:

1. Console output after first click?
2. UI value after click?
   </summary>
   console.log("State:", count) prints 0, not 1 — because setCount is asynchronous. When you call setCount(count + 1), React schedules the update. It doesn't change the count variable immediately. The count inside this function closure is still 0. The new value 1 is only available in the next render.
console.log("Ref:", ref.current) prints 1 — because useRef is synchronous. ref.current += 1 mutates the value instantly. No waiting, no re-render needed. It's just a plain JavaScript object.
UI shows 1 | 1 — because after the click handler finishes, React re-renders the component. In the new render, count is now 1 and ref.current is also 1. So both show updated values on screen.

The key takeaway interviewers check here:
useState → batched, async, value available next render. Triggers re-render.
useRef → instant mutation, value available immediately. Does NOT trigger re-render.
</details>

1. Reverse a String 
2. Check if a String is a Palindrome 
3. Remove Duplicates from a String 
4. Find the First Non-Repeating Character 
5. Count the Occurrences of Each Character 
6. Reverse Words in a Sentence 
7. Check if Two Strings are Anagrams 
8. Find the Longest Substring Without Repeating Characters 
9. Convert a String to an Integer (atoi Implementation) 
10. Compress a String (Run-Length Encoding) 
11. Find the Most Frequent Character 
12. Find All Substrings of a Given String 
13. Check if a String is a Rotation of Another String 
14. Remove All White Spaces from a String 
15. Check if a String is a Valid Shuffle of Two Strings 
16. Convert a String to Title Case 
17. Find the Longest Common Prefix 
18. Convert a String to a Character Array 
19. Replace Spaces with %20 (URL Encoding) 
20. Convert a Sentence into an Acronym 
21. Check if a String Contains Only Digits 
22. Find the Number of Words in a String 
23. Remove a Given Character from a String 
24. Find the Shortest Word in a String 
25. Find the Longest Palindromic Substring
