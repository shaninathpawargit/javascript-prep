## Q1: Can you write a function in JavaScript to reverse the order of words in a given string?

**Solution 1: Using `split(),reverse(),join()`**

```javascript
function reverseWords(str) {
  // Split the string into an array of words using space as a delimiter
  const words = str.trim().split(' ');

  // Reverse the array of words
  const reversedWords = words.reverse();

  // Join the reversed array back into a string with spaces
  return reversedWords.join(' ');
}

// Example usage
const input = "Hello World from JavaScript";
const output = reverseWords(input);
console.log(output); // Output: "JavaScript from World Hello"
```

### Explanation:
1. **`str.trim()`**:
   - Removes any leading or trailing whitespace from the input string.
2. **`str.split(' ')`**:
   - Splits the string into an array of words using a space as the delimiter.
3. **`words.reverse()`**:
   - Reverses the order of the words in the array.
4. **`reversedWords.join(' ')`**:
   - Joins the reversed array of words back into a single string with spaces in between.


**Solution 2: Without using `reverse()`**

Here's an implementation of reversing the order of words **without using `reverse()`**:

```javascript
function reverseWords(str) {
  // Split the string into an array of words using space as a delimiter
  const words = str.trim().split(' ');
  
  // Initialize an empty string for the result
  let reversed = '';
  
  // Iterate through the words array from the end to the beginning
  for (let i = words.length - 1; i >= 0; i--) {
    if (words[i]) { // Check for empty strings (caused by extra spaces)
      reversed += words[i] + ' ';
    }
  }
  
  // Remove trailing space and return the result
  return reversed.trim();
}

// Example usage
const input = "Hello World from JavaScript";
const output = reverseWords(input);
console.log(output); // Output: "JavaScript from World Hello"
```

### How it works:
1. **`str.trim().split(' ')`**:
   - The string is trimmed to remove extra spaces at the beginning and end.
   - It's then split into an array of words.
2. **Iterate in reverse**:
   - Use a `for` loop starting from the last index of the `words` array to the first.
   - Append each word to the `reversed` string, adding a space after each word.
3. **Trim the final result**:
   - Use `trim()` to remove any trailing space left at the end.
