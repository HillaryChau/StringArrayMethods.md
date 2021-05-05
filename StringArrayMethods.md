# Array and String prototype methods

- array iteration methods are all O(N) - linear

## Array methods

- [Array.prototype.map](#Array.prototype.map)
- [Array.prototype.reduce](#Array.prototype.reduce)
- [Array.prototype.filter](#Array.prototype.filter)
- [Array.prototype.sort](#Array.prototype.sort)
- [Array.prototype.slice](#Array.prototype.slice)
- [Array.prototype.splice](#Array.prototype.splice)
- [Array.prototype.pop](#Array.prototype.pop)
- [Array.prototype.shift](#Array.prototype.shift)
- [Array.prototype.unshift](#Array.prototype.unshift)
- [Array.prototype.push](#Array.prototype.push)
- [Array.prototype.indexOf](#Array.prototype.indexOf)
- [Array.prototype.every](#Array.prototype.every)
- [Array.prototype.concat](#Array.prototype.concat)
- [Array.prototype.includes](#Array.prototype.includes)

## String methods

- [String.prototype.charAt](#String.prototype.charAt)
- [String.prototype.charCodeAt](#String.prototype.charCodeAt)
- [String.prototype.charAt](#String.prototype.charAt)
- [String.prototype.match](#String.prototype.match)
- [String.prototype.repeat](#String.prototype.repeat)
- [String.prototype.replace](#String.prototype.replace)
- [String.prototype.search](#String.prototype.search)
- [String.prototype.split](#String.prototype.split)
- [String.prototype.toLowerCase](#String.prototype.toLowerCase)
- [String.prototype.toUpperCase](#String.prototype.toUpperCase)
- [String.prototype.trim](#String.prototype.trim)

### Array.prototype.map

- loops thru an array
- takes transforms each element according to the callback
- returns a new array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// Double everything in the array and return a new arr with a named function

let arr = [1,2,3]
arr.map(doubler) // [2,4,6]

function doubler(arg){
    return arg \* 2
}
```

```javascript
// Example 2:
// Double everything in the array and return a new arr with an anonymous arrow function

let arr = [1, 2, 3];
arr.map((a) => a * 2); // [2,4,6]
```

```javascript
// Example 3:
// Add 10 to everything in the array and return a new arr

let arr = [1, 2, 3];
arr.map((a) => a + 10); // [12,14,16]
```

### Array.prototype.reduce

- loops through array
- takes a callback which usually uses two arguments, the accumulator and currentItem
- returns accumulator
- time complexity: O(N) - linear time

```javascript
// Example 1:
// Add sum everything in arr
let arr = [1, 2, 3];
arr.reduce((a, b) => a + b); // 6
```

```javascript
// Example 2:
// Add all strings together
let arr = ['hello', 'hi', 'bye'];
arr.reduce((a, b) => a + b); // 'hellohibye'
```

```javascript
// Example 3:
// Add all numbers together with a starting value of 10
let arr = [1, 2, 3];
arr.reduce((a, b) => a + b, 10); // 16
```

### Array.prototype.filter

- loops through array
- takes a callback
- if callback returns true, the item for that callback is retained
- if callback returns false, the item for that callback is filtered out
- returns new array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// filter out words that are shorter than length of 6

const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = words.filter((word) => word.length > 6);

console.log(result); // ["exuberant", "destruction", "present"]
```

```javascript
// Example 2:
// filter out words that are greater than length of 3

const words = ['hi', 'bye', 'spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = words.filter((word) => word.length > 3);

console.log(result); // ['hi', 'bye']
```

```javascript
// Example 3:
// filter out odd numbers

const numbers = [1, 2, 3, 4, 5];
const result = numbers.filter((number) => number % 2 === 0);

console.log(result); // [2,4]
```

### Array.prototype.sort

- loops through array
- takes a callback
- callback is responsible for sort order
- returns new array
- time complexity: O(n log n)

```javascript
// Example 1:
// sort numbers ascending
let arr = [2, 3, 1, 5, 10];

arr.sort((a, b) => a - b); // sort ascending [1,2,3,5,10]
arr.sort((a, b) => b - a); // sort descending [10,5,3,2,1]
```

```javascript
// Example 2:
// sort numbers descending
let arr = [2, 3, 1, 5, 10];

arr.sort((a, b) => b - a); // sort descending [10,5,3,2,1]
```

```javascript
// Example 3:
// sort words alphabetically
let arr = ['b', 'd', 'a', 'c'];

arr.sort(); // sort alphabetically ['a','b','c','d']
```

### Array.prototype.slice

- loops through array
- two arguments
  - first argument is index to start cutting
  - second argument is index to stop cutting
- callback is responsible for sort order
- returns new array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// slice from index 1 to 3
let arr = ['a', 'b', 'c', 'd', 'e'];

arr.slice(1, 3); // ["b","c"]
```

```javascript
// Example 2:
// slice from index 1 to end
let arr = ['a', 'b', 'c', 'd', 'e'];

arr.slice(1); // ["b","c","d","e"]
```

```javascript
// Example 3:
// slice from index 2 to end
let arr = ['a', 'b', 'c', 'd', 'e'];

arr.slice(1); // ["c","d","e"]
```

### Array.prototype.splice

- loops through array
- more than 2 arguments
  - first argument is index to start
  - second argument is number of items to delete
  - optional rest arguments are items to insert
- callback is responsible for sort order
- mutates original array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// splice out item at index 1 and replace with 'durian'
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.splice(1, 1, 'durian');
console.log(fruitBasket); // ['strawberry', 'durian', 'orange']
```

```javascript
// Example 2:
// splice out item at index 1
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.splice(1, 1);
console.log(fruitBasket); // ['strawberry', 'orange']
```

```javascript
// Example 3:
// splice out everything starting at index 1 to end
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.splice(1);
console.log(fruitBasket); // ['strawberry']
```

### Array.prototype.pop

- removes last item in an array
- takes no arguments
- mutates original array
- time complexity: O(1) - constant time

```javascript
// Example 1:
// pop on array and remove its last item
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.pop();
console.log(fruitBasket); // ['strawberry', 'apple']
```

```javascript
// Example 2:
// pop on array and remove its last item
let fruitBasket = [1, 2, 3];
fruitBasket.pop();
console.log(fruitBasket); // [1,2]
```

```javascript
// Example 3:
// pop twice on array and remove its last item
let fruitBasket = [1, 2, 3, 4];
fruitBasket.pop();
fruitBasket.pop();
console.log(fruitBasket); // [1,2]
```

### Array.prototype.shift

- removes first item in an array
- takes an argument which is the new item to add to the beginning of the array
- mutates original array
- time complexity: O(1) - constant time

```javascript
// Example 1:
// shift on array and remove its last item
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.shift();
console.log(fruitBasket); // ['apple', 'orange'];
```

```javascript
// Example 2:
// shift on array and remove its last item
let fruitBasket = [1, 2, 3];
fruitBasket.shift();
console.log(fruitBasket); // [2,3]
```

```javascript
// Example 3:
// shift twice on array and remove its last item
let fruitBasket = [1, 2, 3, 4];
fruitBasket.shift();
fruitBasket.shift();
console.log(fruitBasket); // [3,4]
```

### Array.prototype.unshift

- adds item to beginning array
- takes an argument which is the new item to add to the beginning of the array
- mutates original array
- time complexity: O(1) - constant time

```javascript
// Example 1:
// unshift an item to an array
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.unshift('peach');
console.log(fruitBasket); // ['peach', 'strawberry', 'apple', 'orange'];
```

```javascript
// Example 2:
// unshift an item to an array
let fruitBasket = [1, 2, 3];
fruitBasket.unshift(4);
console.log(fruitBasket); // [4,1,2,3]
```

```javascript
// Example 3:
// unshift twice an item to an array
let fruitBasket = [1, 2, 3, 4];
fruitBasket.unshift(0);
fruitBasket.unshift(1);
console.log(fruitBasket); // [0,1,1,2,3,4]
```

### Array.prototype.push

- adds item to end of array
- takes an argument which is the new item to add to the end of the array
- mutates original array
- time complexity: O(1) - constant time

```javascript
// Example 1:
// push peach on array
let fruitBasket = ['strawberry', 'apple', 'orange'];
fruitBasket.push('peach');
console.log(fruitBasket); // ['strawberry', 'apple', 'orange', 'push']
```

```javascript
// Example 2:
// push 4 on array
let fruitBasket = [1, 2, 3];
fruitBasket.push(4);
console.log(fruitBasket); // [1,2,3,4]
```

```javascript
// Example 3:
// push 5 and 6 on array
let fruitBasket = [1, 2, 3, 4];
fruitBasket.push(5);
fruitBasket.push(6);
console.log(fruitBasket); // [1,2,3,4,5,6]
```

### Array.prototype.indexOf

- finds first index of an item in array that matches the indexOf argument
- returns index of item or -1 if item to look for is not found in array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// look for number 4 in array
let arr = [1, 2, 3, 4];
arr.indexOf(4); // 3
```

```javascript
// Example 2:
// look for number 5 in array
let arr = [1, 2, 3, 4];
arr.indexOf(5); // -1
```

```javascript
// Example 3:
// look for number 4 in array where it appears multiple times
let arr = [4, 1, 2, 3, 4];
arr.indexOf(4); // 0
```

### Array.prototype.every

- loops through array
- takes a callback
- returns true if callback returns true for every item in loop
- mutates original array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// check if every item in arr is a number
let arr = [1, 2, 3, 4];
arr.every((num) => typeof num === 'number'); // true
```

```javascript
// Example 2:
// check if every item in arr is greater than 0
let arr = [1, 2, 3, 4];
arr.every((num) => num > 0); // true
```

```javascript
// Example 3:
// check if every item in arr is greater than 2
let arr = [1, 2, 3, 4];
arr.every((num) => num > 2); // false
```

### Array.prototype.concat

- argument is an array to combine with first array
- returns new array

```javascript
// Example 1:
// combine two arrays
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
array1.concat(array2); // ['a', 'b', 'c', 'd', 'e', 'f']
```

```javascript
// Example 2:
// combine two arrays
const array1 = [1];
const array2 = [2];
array1.concat(array2); // [1,2]
```

```javascript
// Example 3:
// combine two arrays
const array1 = ['a', 'b', 'c'];
const array2 = [1];
array1.concat(array2); // ['a', 'b', 'c', 1]
```

### Array.prototype.includes()

- loops through array
- takes a argument which is the item to look for
- returns true if item to look for is in the array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// look for 'a' in array
const array1 = ['a', 'b', 'c'];
array1.includes('a'); // true
```

```javascript
// Example 2:
// look for 'd' in array
const array1 = ['a', 'b', 'c'];
array1.includes('d'); // false
```

```javascript
// Example 3:
// look for 'd' in array
const array1 = [1, 2, 3];
array1.includes(1); // true
```

### String.prototype.charAt

- loops through string
- takes an index
- returns character at that index
- time complexity: O(N) - linear time

```javascript
// Example 1:
// check character at index 0
let str = '1234';
str.charAt(0); // 1
```

```javascript
// Example 2:
// check character at index 1
let str = '1234';
str.charAt(1); // 2
```

```javascript
// Example 3:
// check character at index 3
let str = '1234';
str.charAt(3); // 4
```

### String.prototype.charCodeAt

- loops through string
- takes an index
- returns character code at that index
- time complexity: O(N) - linear time

```javascript
// Example 1:
// check character code at index 0
let str = '1234';
str.charAt(0); // 49
```

```javascript
// Example 2:
// check character code at index 1
let str = '1234';
str.charAt(1); // 50
```

```javascript
// Example 3:
// check character code at index 3
let str = '1234';
str.charAt(3); // 51
```

### String.prototype.match

- loops through string
- takes a argument which is the pattern to look for
- returns array of matching strings
- time complexity: O(N) - linear time

```javascript
// Example 1:
// look for captial letters in string
const paragraph = 'The quick brown fox jumps over the lazy dog. It barked.';
const regex = /[A-Z]/g;
const found = paragraph.match(regex); // ['T', 'Z']
```

```javascript
// Example 2:
// look for lowercase letters in string
const paragraph = 'aaaBB';
const regex = /[a-z]/g;
const found = paragraph.match(regex); // ['a', 'a', 'a']
```

```javascript
// Example 3:
// look for letters 'a' in string
const paragraph = 'aze#@#@@mBB';
const regex = /[a]/g;
const found = paragraph.match(regex); // ['a']
```

### String.prototype.repeat

- loops through string
- takes a argument which number of times to repeat
- returns a new string with repeats
- time complexity: O(N) - linear time

```javascript
// Example 1:
// repeat string 3 times
const str = 'hi';
str.repeat(3); // 'hihihi'
```

```javascript
// Example 2:
// repeat string 0 times
const str = 'hi';
str.repeat(0); // ''
```

```javascript
// Example 3:
// repeat string 3 times
const str = '2';
str.repeat(2); // 'hihi'
```

### String.prototype.replace

- loops through string
- takes two arguments
  - first argument which is the pattern to look for
  - second argument string to replace with
- returns new string
- time complexity: O(N) - linear time

```javascript
// Example 1:
// replace word in string
const paragraph = 'The quick brown';
const regex = /(brown)/g;
paragraph.replace(regex, 'black'); // 'The quick black'
```

```javascript
// Example 2:
// replace word in string
const paragraph = 'The quick brown brown';
const regex = /(brown)/gi;
paragraph.replace(regex, 'black'); // 'The quick black black'
```

```javascript
// Example 3:
// replace word in string
const paragraph = 'The quick brown brown';
paragraph.replace('quick', 'black'); // 'The black brown brown'
```

### String.prototype.search

- loops through string
- takes an arguments
  - first argument which is the pattern to look for
- returns index of the first match between the regular expression and the given string, or -1 if no match was found.
- time complexity: O(N) - linear time

```javascript
// Example 1:
// find starting pattern in string
const paragraph = 'The quick brown';
const regex = /(brown)/g;
paragraph.search(regex); // 10
```

```javascript
// Example 2:
// find starting pattern in string
const paragraph = 'The quick brown brown';
const regex = /[h]/g;
paragraph.search(regex); // 1
```

```javascript
// Example 3:
// find starting pattern in string
const paragraph = 'the Quick brown brown';
const regex = /[A-Z]/g;
paragraph.search(regex); // 4
```

### String.prototype.split

- loops through string
- breaks up string according to argument which is the delimiter
  - first argument which is the pattern to look for
  - second argument string to replace with
- returns an array
- time complexity: O(N) - linear time

```javascript
// Example 1:
// splits string by spaces
const paragraph = 'The quick brown';
paragraph.split(' '); // ["The", "quick", "brown"]
```

```javascript
// Example 2:
// splits string by each character
const paragraph = 'The quick';
paragraph.split(''); // ["T", "h", "e", " ", "q", "u", "i", "c", "k"]
```

```javascript
// Example 3:
// splits string by the word 'the'
const paragraph = 'the quick the brown brown';
paragraph.split('the'); // ["", " quick ", " brown brown"]
```

### String.prototype.toLowerCase

- turns the whole string into all lower case

```javascript
// Example 1:
// turns to lower case
const paragraph = 'The quick brown';
paragraph.toLowerCase(); // 'the quick brown'
```

```javascript
// Example 2:
// turns to lower case
const paragraph = 'THe quick brown';
paragraph.toLowerCase(); // 'the quick brown'
```

```javascript
// Example 3:
// turns to lower case
const paragraph = 'The QUICK brown';
paragraph.toLowerCase(); // 'the quick brown'
```

### String.prototype.toUpperCase

- turns the whole string into all upper case

```javascript
// Example 1:
// turns to lower case
const paragraph = 'The quick brown';
paragraph.toUpperCase(); // "THE QUICK BROWN"
```

```javascript
// Example 2:
// turns to lower case
const paragraph = 'THe quick brown';
paragraph.toUpperCase(); // "THE QUICK BROWN"
```

```javascript
// Example 3:
// turns to lower case
const paragraph = 'The QUICK brown';
paragraph.toUpperCase(); // "THE QUICK BROWN"
```

### String.prototype.trim

- removes forward and back empty whitespace

```javascript
// Example 1:
// turns to lower case
const paragraph = '     The quick brown';
paragraph.trim(); // "The quick brown"
```

```javascript
// Example 2:
// turns to lower case
const paragraph = 'The quick brown    ';
paragraph.trim(); // "The quick brown"
```

```javascript
// Example 3:
// turns to lower case
const paragraph = '    The quick brown   ';
paragraph.trim(); // "The quick brown"
```
