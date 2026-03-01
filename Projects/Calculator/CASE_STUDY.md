# Calculator Project Case Study

## Project: Calculator

### Description
A simple calculator built with **HTML, CSS, and JavaScript**.  
The app performs basic arithmetic operations and provides visual feedback for positive, negative, and zero values.

---

## Problem-Solving Process
- Define the project goal: Build a calculator that can add, subtract, multiply, divide, and reset values.
- Plan the UI: Use a card layout with a display and grid-based buttons.
- Implement logic in JavaScript:
  - Store `currentInput`, `previousInput`, and `operator`.
  - Handle numbers, decimal points, operators, clear, and equals.
- Enhance UX:
  - Display numbers aligned right
  - Color code positive (green), negative (red), zero (neutral)
  - Smooth display animation on value change
- Test edge cases:
  - Prevent multiple decimals
  - Prevent calculations without operands
  - Round results to 6 decimal places

---

## UI/UX Decisions
- Color-coded display: Immediate visual feedback for users
- Hover and click effects: Buttons slightly scale for interactivity
- Grid layout: Uniform button size and spacing
- Card design: Clean, centered interface

---

## JavaScript Struggles & Solutions

| Problem | Solution |
|---------|---------|
| Multiple decimal points allowed | Added a check `if (value === '.' && currentInput.includes('.')) return;` |
| Display not updating smoothly | Added `opacity` transition for smoother visual update |
| Operator logic confusion | Separated `currentInput`, `previousInput`, and `operator` variables to manage state |
| Floating-point precision | Rounded results using `parseFloat(result.toFixed(6))` |

---

## Before & After Example

**Before (Simple addition logic)**

```js
let result = previousInput + currentInput; // didn’t convert to number
```

**After (working properly with decimals)**

```js
const prev = parseFloat(previousInput);
const curr = parseFloat(currentInput);
result = prev + curr;
result = parseFloat(result.toFixed(6));
```

