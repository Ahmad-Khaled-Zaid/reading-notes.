## **What is functional programming?**
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data — Wikipedia
## **Pure functions**
## **Reading Files**
If our function reads external files, it’s not a pure function — the file’s contents can change.
```html
const charactersCounter = (text) => `Character count: ${text.length}`;

function analyzeFile(filename) {
  let fileContent = open(filename);
  return charactersCounter(fileContent);
}
```
## **Random number generation**
```html
function yearEndEvaluation() {
  if (Math.random() > 0.5) {
    return "You get a raise!";
  } else {
    return "Better luck next year!";
  }
}
```
Pure functions benefits
The code’s definitely easier to test. We don’t need to mock anything. So we can unit test pure functions with different contexts:
- Given a parameter A → expect the function to return value B
- Given a parameter C → expect the function to return value D

A simple example would be a function to receive a collection of numbers and expect it to increment each element of this collection.
```html
let list = [1, 2, 3, 4, 5];

const incrementNumbers = (list) => list.map(number => number + 1);
```