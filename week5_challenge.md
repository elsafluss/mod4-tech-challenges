# Problem - Roman Numerals
![Roman Numerals](https://media.giphy.com/media/xT5LMNd1ieywmnI3Qc/giphy.gif)

Write a recursive function that converts an integer into a string such that the number is represented in Roman Numerals in the most efficient way.

For example, the number `4` could be written as `IIII` but it's more efficient to use `IV`since that's a shorter string.

Assume no number is greater than 4,000.

Here are the Roman Numeral equivalents you'll need to know:
- M=1000
- CM=900 
- D=500 
- CD=400
- C=100 
- XC=90 
- L=50 
- XL=40
- X=10 
- IX=9 
- V=5 
- IV=4 
- I=1

## JS Starter Code
```js
function toRoman(num) {
  // your code goes here
}

console.log(toRoman(128));  // should return "CXXVIII"
console.log(toRoman(2000)); // should return "MM"
console.log(toRoman(2017)); // should return "MMXVII"
console.log(toRoman(1999)); // should return "MCMXCIX"
```

# Instructions

1. Copy this markdown and paste in your own, privte gist
2. In your private gist, fill out the questions below
4. Submit by the due time as instructed in Zoom

Do not publish your code on a public repl.it or repo or other public means.

## Rewrite the question in your own words:
Given a number, return its roman numeral equivalent as the shortest string possible.


## What assumptions will you make about this problem if you cannot ask any more clarifying questions? What are your reasons for making those assumptions?
- the shortest string is the most efficient to write
- I should output in the correct roman numeral order


## What are your initial thoughts about this problem? (high level design, 2-3 sentences)
- break the number down by levels of roman numerals, starting at the highest
-   i.e. if the given number is between 400 and 100, output a C and see if there's another 100 to remove. if not, can I remove an XC? and so on
- add letters to the end of the string as we go ... maybe put them in an array and change it to a string at the end?

## How would you identify the elements of this problem?

- [ ] Searching of Data
- [ ] Sorting of Data
- [x] Pattern Recognition
- [ ] Build/Navigate a Grid
- [x] Math
- [ ] Language API knowledge
- [ ] Optimization


## Which data structure(s) do you think you'll use? What pros/cons do you see with that choice?
- Maybe I could put the roman numeral letters and amounts into an array of objects?
- Given a number, I want to check where it falls within the roman numerals so that feels like an if/else or switch statement
-   When I find where the number falls, remove the roman numeral amount from it and return that letter until I can't anymore.
-   Move to the next one (where an array of objects might come in handy)
-   That feels like nested for loops ... eeesh

## Write out a few lines of initial pseudocode: (mid-level design, NOT REAL CODE)
- given 384, find where it falls (between 400 and 100)
- remove 100 from it, return a C
- number is now 284, can I remove another 100? yes. return a C
- number is now 184, can I remove another 100? yes. return a C
- number is now 84, can I remove another 100? no. go to next numeral
- number is still 84, can I remove 90? no. go to next numeral
- number is still 84, can I remove 50? yes. return an L
  - no need to check that again, because if I could remove another 50, then I would have removed a 100 a few steps earlier (but I think I'll let the function check it again anyway)
- number is 34, can I remove 40? no. go to next numeral
- number is still 34, can I remove 10? yes. return an X
- number is 24, can I remove 10? yes. return an X
- number is 14, can I remove 10? yes. return an X
- number is 4, can I remove 10? no. go to next numeral
- number is still 4, can I remove 5? no. go to next numeral
- number is still 4, can I remove 4? yes. return an IV
- number is 0, can I remove 4? no. go to next numeral
- number is still 0, can I remove 1? no. end

- answer given would be CCCLXXXIV (I googled this, it's correct)

## Write out any implementation code OR link to repl
https://replit.com/@ElsaFluss/SmoggyFloweryDatabases#index.js


## What is the Big O complexity of your solution?
The Big O complexity seems like it's n+1. It's a recursive function, it's not necessarily getting easier by half each time, and it doesn't go over the data more than once.
