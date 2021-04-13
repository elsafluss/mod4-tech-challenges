# Bracket Matcher

Ever wonder how your linter knows if you have matching brackets? Well it's time to think of a solution to that!

Given a set of brackets, `[, {, (`, create a function that determines if the brackets are well-formed (match) or not - even with bracket nesting. For example:

```javascript
bracket('{}');

// => true
```

```javascript
bracket('{(');

// => false
```

```javascript
bracket('{()}');

// => true
```

```javascript
bracket('{[)][]}');

// => false
```

```javascript
bracket(']');

// => false
```

```javascript
bracket('({[]}{[]})');

// => true
```

## Instructions

1. Copy this markdown and paste in your own, private gist
2. In your private gist, fill out the questions below
3. Submit by the due time as instructed in Zoom


## Rewrite the question in your own words:
Given a set of items, determine if each item has an opposite.

## What assumptions will you make about this problem if you cannot ask any more clarifying questions? What are your reasons for making those assumptions?
Brackets are directional. i.e. `[` is different from `]`.
Only brackets/parens are given.
Brackets are presented in an array as strings.

## What are your initial thoughts about this problem? (high level design, 2-3 sentences)
Iterate through the array, putting brackets into a temp array.
If current item is { and } is in the temp array, remove }
  Same for all pairs, in both directions
If temp array is empty when it's returned out of the iteration, true
  Otherwise false

## How would you identify the elements of this problem?

- [x] Searching of Data
- [ ] Sorting of Data
- [ ] Pattern Recognition
- [ ] Build/Navigate a Grid
- [ ] Math
- [ ] Language API knowledge
- [ ] Optimization


## Which data structure(s) do you think you'll use? What pros/cons do you see with that choice?
Arrays and an iterator
Easy to pop elements in/out of arrays and check its length

## Write out a few lines of initial pseudocode: (mid-level design, NOT REAL CODE)



## Write out any implementation code OR link to repl

```
const array = ['[', ']', '(', ')', '{', '}', '}']

let leftSquareCount = 0
let rightSquareCount = 0
let leftCurlyCount = 0
let rightCurlyCount = 0
let leftParenCount = 0
let rightParenCount = 0

const isEven = array.length % 2 === 0
console.log(isEven)

let oppositeArray = array.map(item => {
  if(item === '[') {
    leftSquareCount++
    return ']'
  } else if (item === ']') {                            
    rightSquareCount++
    return '['
  } else if (item === '{') {
    leftCurlyCount++
    return '}'
  } else if (item === '}') {
    rightCurlyCount++
    return '{'
  } else if (item === '(') {
    leftParenCount++
    return ')'
  } else if (item === ')') {
    rightParenCount++
    return '('
  }
})

const squaresEven = (leftSquareCount === rightSquareCount)
const curliesEven = (leftCurlyCount === rightCurlyCount)
const parensEven = (leftParenCount === rightParenCount)

console.log(squaresEven)
console.log(curliesEven)
console.log(parensEven)
```

## What is the Big O complexity of your solution?
