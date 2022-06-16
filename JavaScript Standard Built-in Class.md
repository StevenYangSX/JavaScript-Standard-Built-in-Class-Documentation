# JavaScript Standard Built-in Class

## Class String

### 1. [Character access](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#character_access)

```javascript
return 'cat'.charAt(1) // returns "a"
return 'cat'[1] // returns "a"
```

### 2. [Comparing strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#comparing_strings)

### 3. [String primitives and String objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#string_primitives_and_string_objects)

		1. JavaScript distinguishes between `String` objects and [primitive string](https://developer.mozilla.org/en-US/docs/Glossary/Primitive) values.
		1. String literals (denoted by double or single quotes) and strings returned from `String` calls in a non-constructor context (that is, called without using the [`new`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/new) keyword) are primitive strings. 
		1. JavaScript automatically converts primitives to `String` objects, so that it's possible to use `String` object methods for primitive strings.
		1. String primitives and `String` objects also give different results when using [`eval()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval). Primitives passed to `eval` are treated as source code; `String` objects are treated as all other objects are, by returning the object. 
		1. A `String` object can always be converted to its primitive counterpart with the [`valueOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/valueOf) method.

```javascript
// 1. 2. 3
let s_prim = 'foo'
let s_obj = new String(s_prim)
console.log(typeof s_prim) // Logs "string"
console.log(typeof s_obj)  // Logs "object"

// 4
let s1 = '2 + 2'              // creates a string primitive
let s2 = new String('2 + 2')  // creates a String object
console.log(eval(s1))         // returns the number 4
console.log(eval(s2))         // returns the string "2 + 2"

//5
console.log(eval(s2.valueOf()))  // returns the number 4
```

### 4. [Constructor](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#constructor)         String()

### 5. [Instance properties](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#instance_properties)     String.prototype.length

### 6. [Instance methods](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#instance_methods)

​	1. [`String.prototype.at(index)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/at) : The **`at()`** method takes an **integer value** and **returns** a new [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) consisting of the single UTF-16 code unit located at the specified offset. This method allows for positive and negative integers. **Negative integers count back** from the last string character.

```javascript
const sentence = 'The quick brown fox jumps over the lazy dog.';

let index = 5;

console.log(`Using an index of ${index} the character returned is ${sentence.at(index)}`);
// expected output: "Using an index of 5 the character returned is u"

index = -4;

console.log(`Using an index of ${index} the character returned is ${sentence.at(index)}`);
// expected output: "Using an index of -4 the character returned is d"


let returnedValue = sentence.at(5);
console.log("returnedValue is ->",returnedValue);
console.log("returnedValue is type of ->",typeof returnedValue);
```

2. [`String.prototype.charAt(index)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt) : The [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) object's **`charAt()`** method **returns a new string** consisting of the single UTF-16 code unit located at the specified offset into the string.
   1. parameters: An integer between `0` and `str.length - 1`. If the `index` cannot be converted to the integer or no `index` is provided or a **negative number**, the default is `0`, so the first character of `str` is returned.
   2. return value: A **string** representing the character (exactly one UTF-16 code unit) at the specified `index`. If `index` is **out of range**, `charAt()` returns an **empty string**. 

```javascript
const sentence = 'The quick brown fox jumps over the lazy dog.';

const index = 4;

console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// expected output: "The character at index 4 is q"

console.log("idnex out of range ->", sentence.charAt(99)); 
console.log("idnex out of range ->", sentence.charAt(-3));
// expected output: ""           empty string since index is out of range or nagetive
```

 	3. [`String.prototype.charCodeAt(index)`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt) : The **`charCodeAt()`** method returns an integer between `0` and `65535` representing the **UTF-16 code unit at the given index**.
 	4. [`String.prototype.concat(str [, ...strN \])`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat)  ： The **`concat()`** method concatenates the string arguments to the calling string and **returns a new string**.
     	1. parameters: One or more strings to concatenate to `str`.
     	2. return value:  **A new string** containing the combined text of the strings provided. The original strings **will NOT** be changed in place.

```javascript
let hello = 'Hello, '
console.log(hello.concat('Kevin', '. Have a nice day.'))
// Hello, Kevin. Have a nice day.

let greetList = ['Hello', ' ', 'Venkat', '!']
"".concat(...greetList)  // "Hello Venkat!"

"".concat({})    // [object Object]
"".concat([])    // ""
"".concat(null)  // "null"
"".concat(true)  // "true"
"".concat(4, 5)  // "45"
```

