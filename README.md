# Uncontrolled Form Fundamentals

## Problem Statement

Create a React component with an **uncontrolled form**. The form should have:

- A text input field managed using a **ref**.
- A "Submit" button that alerts the entered text upon clicking.
- Ensure that the input is **cleared** after the submission.

---

## Solution

```jsx
import React, { useRef } from 'react';

function UncontrolledForm() {
  const inputRef = useRef(null);

  const handleSubmit = (e) => {
    e.preventDefault();
    const enteredText = inputRef.current.value;
    alert(enteredText);
    inputRef.current.value = '';
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" ref={inputRef} placeholder="Enter text" />
      <button type="submit">Submit</button>
    </form>
  );
}

export default UncontrolledForm;
