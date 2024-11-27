# regEx


### Summary of Regular Expressions (RegEx) in JavaScript

Regular Expressions (RegEx) are patterns used to match character combinations in strings. In JavaScript, RegEx is implemented using the `RegExp` object or through regular expression literals. Here's a summary of all key aspects involved in RegEx in JavaScript.

---

### **1. Basic Syntax**

- **Literals**: Represent the exact string or pattern to match.
  ```javascript
  /hello/
  ```
- **Metacharacters**: Special characters with specific meanings.
  - `.`: Matches any single character (except newline).
  - `^`: Matches the start of a string.
  - `$`: Matches the end of a string.

---

### **2. Character Classes**

- **Predefined Character Classes**:
  - `\d`: Any digit (0-9)
  - `\D`: Any non-digit character
  - `\w`: Any word character (letters, digits, and underscores)
  - `\W`: Any non-word character
  - `\s`: Any whitespace character (spaces, tabs, newlines)
  - `\S`: Any non-whitespace character
  
  Example:
  ```javascript
  /\d+/  // Matches one or more digits
  ```

- **Custom Character Classes**:
  - `[abc]`: Matches either 'a', 'b', or 'c'.
  - `[^abc]`: Matches any character except 'a', 'b', or 'c'.

---

### **3. Quantifiers**

Quantifiers define how many times a character or group should appear.

- `*`: Matches 0 or more occurrences.
- `+`: Matches 1 or more occurrences.
- `?`: Matches 0 or 1 occurrence.
- `{n}`: Matches exactly `n` occurrences.
- `{n,}`: Matches `n` or more occurrences.
- `{n,m}`: Matches between `n` and `m` occurrences.

Example:
```javascript
/\d{2,4}/  // Matches 2 to 4 digits
```

---

### **4. Anchors**

Anchors define the position of the match within the string.

- `^`: Matches the start of the string.
- `$`: Matches the end of the string.

Example:
```javascript
/^abc/   // Matches 'abc' at the start of the string
/abc$/   // Matches 'abc' at the end of the string
```

---

### **5. Groups and Alternatives**

- **Groups**: Parentheses `()` are used to group expressions.
  Example:
  ```javascript
  /(abc|def)/  // Matches 'abc' or 'def'
  ```

- **Non-Capturing Groups**: `(?: ...)` groups but does not capture the match.
  Example:
  ```javascript
  /(?:abc|def)/
  ```

---

### **6. Flags**

Flags modify the behavior of a regular expression.

- `g`: Global match (matches all occurrences).
- `i`: Case-insensitive match.
- `m`: Multiline match.
- `s`: Allows `.` to match newlines.
- `u`: Unicode match.
- `y`: Sticky match (matches only at the current position in the string).

Example:
```javascript
/abc/g  // Global search for 'abc'
/abc/i  // Case-insensitive search for 'abc'
```

---

### **7. Methods**

- `test()`: Tests if a pattern exists in the string, returns `true` or `false`.
  ```javascript
  /\d/.test('123')  // true
  ```

- `exec()`: Executes the regular expression on a string and returns an array of matches (or `null` if no match).
  ```javascript
  /\d+/.exec('123')  // ['123']
  ```

- `match()`: Used on strings, returns an array of matches (with `g` flag) or a single match.
  ```javascript
  '123abc'.match(/\d+/)  // ['123']
  ```

- `replace()`: Replaces matched substrings with a specified replacement.
  ```javascript
  'hello world'.replace(/world/, 'universe')  // 'hello universe'
  ```

- `split()`: Splits a string into an array based on a regular expression.
  ```javascript
  'a,b,c'.split(/,/)  // ['a', 'b', 'c']
  ```

---

### **8. Special Sequences**

- `\b`: Word boundary.
- `\B`: Non-word boundary.
- `\n`: Newline.
- `\t`: Tab.
- `\r`: Carriage return.
  
Example:
```javascript
/\bhello\b/  // Matches 'hello' as a whole word
```

---

### **9. Lookahead and Lookbehind**

- **Lookahead**: `(?=...)` asserts that what follows the current position matches a pattern.
  - Positive Lookahead: `(?=...)`
  - Negative Lookahead: `(?!...)`

- **Lookbehind**: `(?<=...)` asserts that what precedes the current position matches a pattern.
  - Positive Lookbehind: `(?<=...)`
  - Negative Lookbehind: `(?<!...)`

Example:
```javascript
/\d(?=\w)/  // Matches a digit only if it’s followed by a word character
```

---

### **10. Example - Matching a Phone Number**

```javascript
let phonePattern = /\d{3}-\d{3}-\d{4}/;
let phone = '123-456-7890';
console.log(phone.match(phonePattern));  // ['123-456-7890']
```

---

### Conclusion

RegEx in JavaScript is a powerful tool for string manipulation, allowing you to search, match, and modify text with great flexibility. Understanding the syntax, modifiers, and methods involved will enable you to leverage RegEx for a wide range of text processing tasks.
