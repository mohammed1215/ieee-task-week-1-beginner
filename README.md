# ieee-task-week-1-beginner

## Task

### Theoritical
* Explain the difference between `==` and `===` in JavaScript.
  ### Answer
  * `==` compares the value not the dataType but `===` compares the value and the dataType
* Hamed is simply trying to sort an array of numbers but unfortunately this sort method isn't working as expected. Can you tell Hamed the reason for this behavior and how to implement it in a right way?
    ```js
    const arr = [10, 5, 11];
    arr.sort();
    ```
 ### Answer
 - because `sort()` method sorts the array depending on the ascii code or UTF-16 code 

### Practical
* Write a JavaScript program that converts temperature from Celsius to Fahrenheit.
  ### Answer
  ```js
  
  function convertCFTemperature(degreeInCelsius){
    let F_Temperature = ( (9/5) * degreeInCelsius) + 32;
  return F_Temperature;
  }
   convertCFTemperature(20);
  ```
* Write a JavaScript program that takes an array and updates it in place. Each Element in the array is a string or a number. If it's a number, you should multiply it by 3. If it's a string, you should make the first letter uppercase and the rest lowercase.
    
    **Example:**

    Input:
    ```js
    let arr = [19, "dreams", "PlayGround", 2, "xD", "i"];
    ```
    Output:
    ```js
    [57, "Dreams", "Playground", 6, "Xd", "I"]
    ```

    **Answer**
    ```js

      function updates(arr) {
  for (let i = 0; i < arr.length; i++) {
    if (typeof arr[i] === "number") {
      arr[i] *= 3
    } else if (typeof arr[i] === "string") {
      arr[i] = arr[i].toLowerCase()
      arr[i][0].toUpperCase()
      arr[i] = `${arr[i][0].toUpperCase()}${arr[i].slice(1)}`
    }
  }
  return arr
  }

  let arr = [19, "dreams", "PlayGround", 2, "xD", "i"]

  console.log(updates(arr))
    ```
    
* Adel wrote a secret message that he didn't want anyone to read easily. To make it difficult to understand, he reversed it. He then thought that it wasn't enough, so he wanted to perform another minor change that would make it unrecognizable. Write a JavaScript program that takes a string $s$ and prints it again after reversing it and making all vowel letters uppercase.
    
    **Example:**

    Input:
    ```js
    let s = "Hey There, I'm glad to have you";
    ```
    Output:
    ```
    UOy EvAh Ot dAlg m'I ,ErEhT yEH
    ```
  **Answer**
    ```js
    function encrypt(s) {
  let arr = Array.from(s).reverse()

  // s.
  for (let i = 0; i < s.length; i++) {
    if (
      arr[i] === "a" ||
      arr[i] === "e" ||
      arr[i] === "i" ||
      arr[i] === "o" ||
      arr[i] === "u"
    ) {
      arr[i] = arr[i].toUpperCase()
    }
  }
  return arr.join("")
  }

  let s = "Hey There, I'm glad to have you"

  console.log(encrypt(s))

    ```

* Write a JavaScript program that takes a string and an array of forbidden letters. Your program should print the string after removing the forbidden letters from it and make all letters separated by hiphens `-`.

    **Example:**

    Input:
    ```js
    let text = "Please";
    let forbiddenLetters = ['r', 'x', 'p', 'a'];
    ```
    Output:
    ```
    l-e-s-e
    ```

    **Answer**
```js
let text = "Please"
let forbiddenLetters = ["r", "x", "p", "a"]

function removeForbiddenLetters(text, forbiddenLetters) {
  for (let i = 0; i < text.length; i++) {
    text = text.toLowerCase()
  }

  for (let i = 0; i < forbiddenLetters.length; i++) {
    forbiddenLetters[i] = forbiddenLetters[i].toLowerCase()
  }

  let arr = [...text]

  for (let i = 0; i < arr.length; i++) {
    for (let j = 0; j < forbiddenLetters.length; j++) {
      if (arr[i] === forbiddenLetters[j]) {
        arr.splice(i, 1)
      }
    }
  }

  return arr.join("-")
}

console.log(removeForbiddenLetters(text, forbiddenLetters))
      
```
